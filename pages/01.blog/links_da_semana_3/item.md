---
title: 'Links da Semana #3'
date: '00:00 10/31/2017'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Verificação de integridade de variáveis em busca de valores não nulos geralmente gera um código muito extenso (cheio de condicionais) ou um código propenso a falhas. A verdade é que [quanto menos você lida com nulls, mais fácil de entender fica seu código](https://github.com/google/guava/wiki/UsingAndAvoidingNullExplained). Para tratar destes casos, Larry dá umas dicas legais sobre [iteração em arrays em PHP](https://www.garfieldtech.com/blog/short-array-iteration), prezando principalmente pela legibilidade e estabilidade.  

1. Já [tornei público](http://vschettino.com.br/blog/grav_wordpress) que o conteúdo deste blog é mantido no [Github](https://github.com/vschettino/blog) e automaticamente sincronizado aqui quando faço um push da master. O pessoal da [Bitfalls.com](https://bitfalls.com/) deu um jeito (apesar de bem mais complicado) de [fazer o mesmo utilizando wordpress](https://www.sitepoint.com/git-and-wordpress-how-to-auto-update-posts-with-pull-requests/).

1. O [ngrok](https://ngrok.com/) é uma ferramenta prática para fazer um túnel entre uma porta na sua máquina e a internet. É útil para fazer testes com APIs externas, liberar prévias para stakeholders externos e executar testes automatizados, tudo isso sem grandes investimentos ou preocupações de segurança.

1. Os [dois primeiros posts](https://dev.to/gonedark/writing-clean-code) da série "Writing Clean Code" de [Jason McCreary](https://twitter.com/gonedark) já sairam. Lá ele levanta questões importantes para legibilidade do código, enquanto colegas fazem comentários pertinentes e proporcionam uma boa discussão sobre o tema.

1. Poucos vícios de progamação são tão nocivos à manutenibilidade do código quanto a [obsessão por primitivos](https://refactoring.guru/smells/primitive-obsession). Algumas noções aprendidas nas matérias básicas de algoritmos não são escaláveis para sistemas complexos, e a economia na hora de criar variáveis primitivas em detrimento da legibilidade é uma delas.

1. Quanto mais sistemas utilizam inteligência artificial para tomada de decisões importantes, mais alternativo torna-se explorar possíveis vulnerabilidades nestes métodos computacionais. O objetivo dos invasores é divergir o resultado do algoritmo manipulando a entrada, buscando saídas específicas ou simplesmente diferentes dos objetivos da ferramenta.  Este artigo discorre sobre as [principais categorias de ataques](https://blog.xix.ai/how-adversarial-attacks-work-87495b81da2d) e as principais defesas que podem ser consideradas.

1. O trabalho de  [Joe "begriffs" Nelson](https://begriffs.com/) ajuda a compreender melhor o [funcionamento dos domínios no Postgres e no SQL em geral](https://begriffs.com/posts/2017-10-21-sql-domain-integrity.html). Exemplos práticos mostram o poder desta estrutura para garantir a integridade do banco, principalmente quando não há pleno controle da qualidade dos inputs via aplicação/código.

1. Este artigo [compara o desempenho entre o particionamento lógico do PostgreSQL 10 e do TimeScaleDB](https://blog.timescale.com/time-series-data-postgresql-10-vs-timescaledb-816ee808bac5), que é uma extensão do primeiro, quando o assunto é banco de dados temporal. Mesmo um pouco enviesado, é uma boa oportunidade para entender o poder e as limitações do [particionamento declarativo](https://www.postgresql.org/docs/10/static/ddl-partitioning.html) introduzido na nova versão.

1. O [POWA](http://dalibo.github.io/powa/) é uma ferramenta opensource de análise do desempenho para PostgreSQL. Além do monitoramento em tempo real e dos gráficos, ele sugere a [otimização de consultas através de índices](https://blog.dbi-services.com/postgresql-index-suggestion-with-powa), com auxílio do [HypoPG](https://github.com/dalibo/hypopg). Ainda não testei a ferramenta, mas pretendo fazê-lo e dedicar uma postagem exclusiva ao tópico.

1. [Resumão das principais funcionalidades de PostgreSQL 10](http://www.cybertec.at/best-of-postgresql-10-for-the-developer/) do ponto de vista dos desenvolvedores, algumas há muito esperadas e que estão fazendo sucesso.
