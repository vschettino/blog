---
title: 'Links da Semana #2'
date: '00:00 10/25/2017'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Para quem gosta (como eu) de utilizar o `psql` para [executar queries com o PostgreSQL](https://www.postgresql.org/docs/10/static/app-psql.html), pode não gostar da paginação/formatação dos resultados, principalmente em tabelas com muitas colunas. Isso porque o `psql` utiliza o `less` como padrão para preparar os resultados, e essa ferramenta não tem nenhum suporte específico para tabelas. Para quem precisa de uma interface mais completa e não quer dar um salto para pesadas IDEs, sugiro dar uma olhada no projeto [PSPG](https://github.com/okbob/pspg), que trás funcionalidades como cores, tabulação, congelamento de colunas durante a navegação horizontal e muitas outras funcionalidades interessantes.

1. Quem já conhece o [Twelve-Factor App](https://www.12factor.net/) deve saber a importância nunca utilizar código para armazenar senhas, chaves e outras configurações voláteis entre os ambientes de desenvolvimento, homologação e produção. Este artigo bota a mão na massa e [mostra como utilizar variáveis de ambiente no PHP](https://jolicode.com/blog/what-you-need-to-know-about-environment-variables-with-php), junto com dicas e ferramentas para aumentar a segurança e a praticidade desta abordagem.
1. Inspirado no `rails/rake stats`, o Laravel agora oferece um comando para [levantar métricas de tamanho de código no seu projeto](https://laravel-news.com/laravel-stats-package). É possível utilizar os dados sobre número de classes, métodos e linhas de código de diversos componentes para acompanhar o crescimento da codebase.
1. Para quem não tem medo da matemática, este artigo explica [porque o deep learning é capaz de generalizar bem os resultados](https://arxiv.org/pdf/1710.05468.pdf), e quais são as práticas necessárias para que isso seja verdade em diversos contextos.
1. [Luminoth é uma biblioteca para treinar e utilizar o reconhecimento de padrões em imagens](https://luminoth.ai/). A interface em linha de comando é assustadoramente simples e direta, e pode ser facilmente integrada em aplicações maiores. Já suporta integração com grandes bases de dados e com o Google Cloud Engine.
1. Suave como uma pata de elefante, [Simon Riggs](https://twitter.com/simon_riggs), fundador da [2ndQuadrant](https://www.2ndquadrant.com/en/) e um dos maiores contribuidores da comunidade PostgreSQL, escreveu um artigo dizendo [porque o PostgreSQL é melhor que o MySQL](https://blog.2ndquadrant.com/postgresql-better-mysql-1/). Sim, foi literalmente esse o título do artigo. O tema central do artigo é o formato distinto das comunidades, tendo como ilustração o famigerado [bug #144](https://bugs.mysql.com/bug.php?id=199) do MySQL que foi resolvido este mês...após 14 anos. Como era de se esperar, os comentários na página acabaram sendo ainda mais interessantes que o artigo.
1. Apesar da eficência do índice B-Tree no PostgreSQL, existem [alternativas mais eficientes em algumas situações](https://www.citusdata.com/blog/2017/10/17/tour-of-postgres-index-types/), como em campos multivalorados e com texto plano.
1. Muitos desenvolvedores utilizam números "aleatórios" sem entender que na verdade, aleatoriedade pode ser mais uma questão de desconhecimento do que de fatores naturais. Se essa informação foi surpresa para você, este [vídeo do VSauce](https://www.youtube.com/watch?v=9rIy0xY99a0) vai ser bem interessante.
1. [Views](http://www.devmedia.com.br/conceitos-e-criacao-de-views-no-sql-server/22390) são uma ferramenta clássica dos bancos de dados relacionais. Em alguns casos, a [view materializada pode ser ainda mais útil](https://www.postgresql.org/docs/current/static/rules-materializedviews.html), já que elas persistem os dados da consulta geradora e podem ser atualizadas através de `cronjobs` ou de `triggers`, sendo uma alternativa rápida de cache/datawarehouse sem muita dor de cabeça.  
