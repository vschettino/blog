---
title: 'Links da Semana #35'
date: '00:00 08/30/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. [Clusterização de Redes Complexas no Neo4j](https://medium.com/@vitorcautiero/community-detection-in-social-networks-with-neo4j-and-netscan-d2f90074dcbb).

1. Influência da [comunidade opensource na qualidade de código](https://www.tomasvotruba.cz/blog/2018/08/09/why-is-your-company-losing-money-by-not-open-sourcing-2-code-quality/).

1. Dicas de como lidar com [código legado quando se tem pouco tempo](https://chrismm.com/blog/strategies-for-dealing-with-poor-code-in-limited-time/).

1. Dicas de [refatoração em PHP](https://chrismm.com/blog/strategies-for-dealing-with-poor-code-in-limited-time/) com exemplos reais.

1. [Transformando texto em imagens utilizando redes neurais](http://t2i.cvalenzuelab.com/). Meio viajado, mas gera umas imagens interessantes.

1. Artigo extenso e detalhado sobre a [história de Ada Lovelace](https://twobithistory.org/2018/08/18/ada-lovelace-note-g.html), considerada a criadora do primeiro programa de computador digno do nome. O trabalho foca no problema resolvido com esse algoritmo e no perfil visionário da matemática, que observou que o poder da máquina de Babbage ia muito além do que os próprios criadores ousavam sonhar.

1. Criar novas colunas `not null` ou com `DEFAULT` no PostgreSQL quando a instância está em produção sempre foi um desafio gigantesco. Primeiro porque são operações lentas (que pedem scans ou reescritas completas das tabelas) e segundo porque a tabela fica completamente travada (lock) durante a operação. Até `SELECTs` são obrigados a aguardar, o que faz que virtualmente ninguém tenha coragem de criar campos com tais restrições em produção, deixando o modelo mais propenso a falhas de integridade. O problema deve ser [resolvido no PostgreSQL 11, com uma solução teoricamente simples mas de implementação sofisticada](https://brandur.org/postgres-default).

1. [Série de artigos](https://tapoueh.org/blog/2018/08/postgresql-concurrency-an-article-series/) sobre os desafios e soluções relacionados a tratamento de concorrência no PostgreSQL, com ênfase nas [dicas de modelagem que podem te ajudar a se livrar desse tipo de problema](https://tapoueh.org/blog/2018/07/modeling-for-concurrency/).

1. Raro estudo (ainda que pouco rigoroso) sobre [aplicações reais e o tenebroso `ssd wearout`](https://blog.okmeter.io/real-world-ssd-wearout-a3396a35c663), que é quando o disco SSD chega no limite de operações de escrita "seguras".

1. Implementando [busca textual no PostgreSQL](https://austingwalters.com/fast-full-text-search-in-postgresql/). Existem soluções dedicadas para o problema da busca textual, mais rebuscadas e com maior desempenho, como o famigerado [ElasticSearch](https://www.elastic.co/). Contudo a praticidade do PostgreSQL (seu sistema já pode estar utilizando-o) para funcionalidades não tão críticas justifica esse tipo de abordagem.

1. [Dicas para aproveitar mais o psql](https://pgdash.io/blog/postgres-psql-tips-tricks.html).

1. Lições para como utilizar e criar seus [decorators em python](https://realpython.com/primer-on-python-decorators/).
