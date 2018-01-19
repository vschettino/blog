---
title: 'Links da Semana #13'
date: '00:00 01/19/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. A [capacidade de realizar operações paralelas do PostgreSQL](https://www.postgresql.org/docs/10/static/parallel-query.html) é importante para o desempenho em ambientes distribuídos e de alta disponibilidade e concorrência. O hash paralelo, que é uma das principais operações por trás dos `JOINS`, e [possivelmente será incluído na versão 10 do PostgreSQL](https://write-skew.blogspot.com.br/2018/01/parallel-hash-for-postgresql.html).

1. Entre os motivos de se trabalhar na arquitetura de réplicas *read only* do PostgreSQL estão a alta disponibilidade, tolerância a falhas e a distribuição de queries somente leitura. Para garantir que estes requisitos estão satisfeitos, é necessário [monitorar o desempenho das operações de replicação](http://sysadvent.blogspot.com.br/2017/12/day-12-monitoring-postgres-replication.html), ajustando a topologia de acordo com as necessidades do domínio.

1. Agora o [PostgreSQL tem um twitter oficial](https://twitter.com/postgresql)! Por enquanto, parece que vai ser bem atualizado e está com notícias bem legais. Vamos acompanhar.

1. O `pg_pool` é uma ferramenta voltada para [connection pooling e balanceamento de carga de instâncias PostgreSQL](http://pgpool.net/mediawiki/index.php/Main_Page). A proposta é diminuir o número de conexões necessárias (e seu overhead significativo no caso deste SGBD) através do reaproveitamento e fazer a distribuição de queries entre diversas réplicadas, baseando-se na carga atual de cada nó.  

1. Descobrir se um paciente está em estado terminal é importante para o chamado "cuidado paliativo", que envolve suporte psicológico e emocional para a família e para o doente na eminência do óbito. Este [artigo do New York Times](https://www.nytimes.com/2018/01/03/magazine/the-dying-algorithm.html) mostra como até um gato se mostrou mais eficiente que médicos na detecção de casos terminais, e como andam o desenvolvimento de algoritmos para detecção deste estágio.

1. Cientistas da Google apresentaram algumas [imagens psicodélicas que enganam algoritmos de reconhecimento de padrões](http://www.bbc.com/news/technology-42554735), fazendo com que eles indiquem objetos que definitivamente não estão lá.  

1. Andrew Burt expressa sua [preocupação com as recentes iniciativas para regulamentar genericamente a "Inteligência Artificial"](https://www.nytimes.com/2018/01/04/opinion/leave-artificial-intelligence.html). Ele argumenta como o termo é amplo e controverso, como a regulamentação ampla é perigosa e cita algumas propostas mais pontuais que já corroboram com a privacidade e transparência em domínios concretos.

1. O [CoffeeMiner é um projeto acadêmico que mostra como explorar redes WiFi desprotegidas](http://arnaucode.com/blog/coffeeminer-hacking-wifi-cryptocurrency-miner.html) para, através de um ataque do tipo [MITM (Man In The Middle)](https://pt.wikipedia.org/wiki/Ataque_man-in-the-middle) fazer com que os navegadores dos usuários minerem cripto moedas sem seu consentimento.

1. Simon Riggs [discute resultados preliminares do impacto](https://blog.2ndquadrant.com/postgresql-meltdown/) das vulnerabilidades [Meltdown e Spectre](https://meltdownattack.com/) no desempenho do PostgreSQL.

1. O [GraphQL](http://vschettino.com.br/blog/introducao_graphql) vem ganhando popularidade nos últimos tempos. Agora, o projeto [Graphile](https://www.graphile.org/) permite a criação de uma API com este padrão diretamente de tabelas no PostgreSQL.
