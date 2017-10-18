---
title: 'Testes rápidos de saúde do PostgreSQL'
date: '00:00 09/10/2017'
taxonomy:
    category:
        - blog
    tag:
        - PostgreSQL
        - SGBD
        - monitoramento
---

Os principais gargalos que encontramos nas aplicações web geralmente estão diretamente relacionados aos bancos de dados. Muitos desenvolvedores utilizam as ferramentas, sejam SGBDs relacionais ou não, como uma caixa preta, sem conhecimento ou motivação para personalizar parâmetros de configuração essenciais para o desempenho adequado destes componentes. Neste artigo vou introduzir duas queries SQL que podem ajudar a identificar gargalos clássicos em sistemas de banco de dados, além de fornecer algumas dicas que podem te ajudar a resolvê-los.

===

## Gargalo em operações de consulta

Neste caso, a maior parte dos gargalos está na estruturação das consultas e no projeto do banco de dados, e não na configuração do ambiente. Existem [diversos](https://www.sqlshack.com/sql-query-performance-tuning-tips-non-production-environments/) [trabalhos](https://dzone.com/articles/6-simple-performance-tips-sql) que abordam esse tema, mas não é o nosso foco de hoje.

A eficiência de um banco de dados como o PostgreSQL em operações de leitura está diretamente relacionado a capacidade dele em fazer caching dos dados, oferecendo-os muito mais rapidamente às próximas requisições. Quando falo em mais rápido, realmente me refiro a ordens de magnitude mais rápido, uma vez que o acesso à memória secundária (disco) chega a ser [1 milhão de vezes mais lento que o acesso à memória principal](https://computing.llnl.gov/tutorials/parallel_comp/). Isso porque eu nem estou comparando com memórias mais caras e rápidas, como as encontradas dentro do processador. E como saber se o meu PostgreSQL está fazendo um caching eficiente? A seguinte query pode te ajudar a ter essa noção:


```
SELECT
  sum(heap_blks_read) as heap_read,
  sum(heap_blks_hit)  as heap_hit,
  sum(heap_blks_hit) / (sum(heap_blks_hit) + sum(heap_blks_read)) as ratio
FROM
  pg_statio_user_tables;
```

Nesse caso, estamos comparando a proporção entre o número de vezes que foi possível recuperar a informação via cache (memória principal) e o número de vezes que foi necessário recorrer ao disco (memória secundária). Uma boa referência para começar a analisar este parâmtro é ter uma eficiência de pelo menos 99%.

### Ops, detectei um problema!

Se você notar uma eficiência de cache muito baixa, é bom começar a estudar as causas deste problema. Uma dica é observar a quantidade de memória disponível para o PostgreSQL. É uma medida meio básica, mas a falta de memória pode ser a principal causa desta ineficiência, e precisa ser analisada. Outra possibilidade é observar através do `SELECT EXPLAIN` se os índices estão sendo corretamente utilizados, porque na maioria das vezes quando não há caminho indexado para construção da resposta, o PostgreSQL terá que acessar o disco para montar a árvore, o que pode ainda tirar do cache outras informações importantes que poderiam acelerar outras consultas.

## Gargalo em operações de inserção

Como tudo na vida, o que ajuda um aspecto de qualidade pode prejudicar outro. É caso dos Índices, que são um dos principais componentes de um banco de dados e permitem leituras muito mais eficientes, mas impactam no desempenho de escrita do banco. Isso acontece porque quando existem índices afetados por um `INSERT`, ele precisa percorrer a estrutura de indexação para inserir as informações em aderência a estrutura vigente. Não é possível simplesmente colocar a nova tupla no topo da pilha ou no fim da lista. Por isso, quanto mais índices existem, mais custoso tende a ser o processo de inserção. Isso vale também, em geral, para os `UPDATE` e `DELETE`.


Em aplicações tradicionais, esta característica representa um bom _tradeoff_, já que as operações de consulta e agregação possuem um alto nível de complexidade e filtragem, além de transmitir e iterar sobre mais dados. Nos casos mais específicos (pense em um servidor de log ou de rastreamento de usuários em sites), o índice pode ser construído a parte para evitar estes problemas, fazendo a primeira captação dos dados em uma estrutura auxiliar e desordenada.

Contudo, um número excessivo de índices não necessariamente ajuda nas operações de consulta, mas impactam negativamente no desempenho de inserção da mesma forma. Como detectar estes casos? O seguinte comando pode te ajudar:

```
SELECT
  schemaname || '.' || relname AS table,
  indexrelname AS index,
  pg_size_pretty(pg_relation_size(i.indexrelid)) AS index_size,
  idx_scan as index_scans
FROM pg_stat_user_indexes ui
JOIN pg_index i ON ui.indexrelid = i.indexrelid
WHERE NOT indisunique AND idx_scan < 50 AND pg_relation_size(relid) > 5 * 8192
ORDER BY pg_relation_size(i.indexrelid) / nullif(idx_scan, 0) DESC NULLS FIRST,
pg_relation_size(i.indexrelid) DESC;

```

Com ele, será possível listar os índices pouco utilizados nas últimas consultas, indicando que é possível remover estes índices sem grandes impactos no custo de leitura, mas possibilitando maior desempenho de inserção.

## Mais importante que otimizar é medir

É sempre importante medir o desempenho de consultas representativas da carga de produção do software, para acompanhar os impactos de quaisquer mudanças e discutir sua utilidade e relevância diante dos _tradeoffs_ encontrados. Não só nos casos apresentados acima, mas qualquer tipo de evolução precisa estar devidamente monitorada para possibilitar crescimento e melhoria saudável da aplicação.

### Referências

1. https://www.citusdata.com/blog/2017/09/29/what-performance-can-you-expect-from-postgres/?utm_source=postgresweekly&utm_medium=email
