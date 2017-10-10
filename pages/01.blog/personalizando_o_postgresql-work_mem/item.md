---
title: 'Personalizando o PostgreSQL - work_mem'
date: '00:00 10/03/2017'
taxonomy:
    category:
        - blog
    tag:
        - PostgreSQL
        - SGBD
        - Tunning
---


O PostgreSQL oferece uma série de parâmetros configuráveis, voltados para atender aos diversos contextos aos quais ele é aplicado. Neste artigo iremos discutir o parâmetro `work_mem`, sua utilidade e aprender como é possível detectar sua possível má configuração.


===

## Personalização do PostgreSQL


Os parâmetros de configuração do PostgreSQL existem para que o especialista responsável ajuste o comportamento do sistema de gerenciamento de banco de dados em detrimento do contexto no qual ele será aplicada. Notoriamente, duas forças devem ser observadas na etapa de projeto:

1. Aspectos arquiteturais de hardware, como memória, armazenamento, distribuição, etc.

1. Aspectos não funcionais como disponibilidade, eficiência de leitura/escrita, segurança, confiabilidade, etc.

Estas forças não podem ser analisadas separadamente, e ainda por cima interagem diretamente com as funcionalidades que compõem o produto, criando um ecossistema único de características que devem ser observadas. O PostgreSQL suporta essas necessidades distintas principalmente através de parâmetros configuráveis, que aproveitam melhor os recursos e dão, sempre em troca de outro requisito, retorno em aspectos que qualidade importantes para a aplicação.

Neste artigo falaremos do parâmetro `work_mem`, um dos mais fáceis de entender, detectar mau uso e personalizar.  

## Encontrando espaço para trabalhar

Talvez o aspecto mais importante da configuração de `work_mem` seja a escalabilidade deste parâmetro em relação ao crescimento natural de uma aplicação, e por consequência seu banco de dados. Os anos passam, o número de usuários funcionalidades aumenta. Isso significa que apenas o volume de operações com dados vai crescer? Não. Junto com o aumento da demanda pelos dados, a *complexidade das operações também cresce*. Ou seja, são necessários mais filtros, _joins_, agregações e restrições de integridade. Buscar otimização destas consultas através da indexação, evolução do projeto conceitual e até mesmo estruturas auxiliares de dados (por exemplo, um BD não relacional) são as primeiras soluções que pensamos, mas elas não são eficientes se o PostgreSQL não encontrar na memória principal um espaço de trabalho adequado.

Pense no `work_mem` como o limitador do espaço (ou _buffer_) que cada conexão tem para realizar as operações de busca, especialmente operações de [Hash](https://pt.wikipedia.org/wiki/Tabela_de_dispers%C3%A3o). Assim, as operações que não cabem nesta memória dedicada são realizadas com auxílio de _file buffers_ que se apoiam na memória secundária (Disco), muito mais lenta.


## Como Descobrir se a `work_mem` está transbordando?

Como geralmente acontece, podemos investigar as estratégias de operação através da declaração `EXPLAIN ANALYZE`. Ao executar uma consulta com esta instrução, você verá uma linha parecida com essa:

```
Buckets: 4096  Batches: 2  Memory Usage: 2948kB
```

Aqui, sem entrar em detalhes técnicos do funcionamento da _Hash Table_, o PostgreSQL tinha disponível apenas 4096 buckets para trabalhar (que é o padrão, 4MB), e por isso foi necessário criar dois Batches diferentes, apenas um deles na memória (que alocou 2948 dos buckets). O resto foi parar no (lento) _file buffer_.

Se você alterar o parâmetro `work_mem` no arquivo `postgresql.conf`, digamos para 8MB, o resultado do `EXPLAIN ANALYZE` poderia ser diferente

```
Buckets: 8192  Batches: 1  Memory Usage: 5860kB
```

Aqui vemos que foi possível alocar mais memória para apoiar a operação, o que fez desnecessária a utilização do _file buffer_.

## Limitações desta técnica

Como nem tudo são flores, este parâmetro não é mágico; Este valor é dedicado não só para cada conexão, mas possivelmente cada _join_ da consulta, quando estes demandam _merge sorts_ em sua operação. Por isso, precisamos ser razoáveis com seu acréscimo. gastar muita memória com com estas operações e deixar outras funções do PostgreSQL (ou até de outro serviço, dependendo da sua arquitetura) sem espaço para trabalhar pode degradar ainda mais a performance da aplicação.


Como sempre, teste diferentes valores e faça medições concisas. Discuta com sua equipe sobre os resultados encontrados e monitore continuamente a performance do banco de dados.

### Referências

1. https://dzone.com/articles/is-your-postgres-query-starved-for-memory (referência principal e bom ponto de partida para compreensão do papel das Hash Tables no PostgreSQL)

1. https://www.postgresql.org/docs/9.6/static/runtime-config-resource.html

1.  https://wiki.postgresql.org/wiki/Tuning_Your_PostgreSQL_Server
