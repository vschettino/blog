---
title: 'Links da Semana #16'
date: '00:00 02/16/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Utilizar toda hora as funções `LOWER` do PostgreSQL e suas análogas nas linguagens de programação deixa o código mais difícil de ler e o esquecimento pode acarretar um comportamento inconsistente nas buscas de uma aplicação. Por isso existe o tipo [citex](https://www.postgresql.org/docs/current/static/citext.html), que ajuda na hora de [comparar textos "case insensitive"](https://nandovieira.com/using-insensitive-case-columns-in-postgresql-with-citext)

1. [Compilado de funções do PostgreSQL pouco conhecidas](https://nandovieira.com/using-insensitive-case-columns-in-postgresql-with-citext), incluindo dicas de estrutura, utilização e performance.

1. Diferença dos principais tipos de `SCAN` do PostgreSQL [explicados com exemplos práticos](https://www.cybertec-postgresql.com/en/postgresql-indexing-index-scan-vs-bitmap-scan-vs-sequential-scan-basics/)

1. [Este tutorial](https://tapoueh.org/blog/2018/01/exporting-a-hierarchy-in-json-with-recursive-queries/) ensina dois aspectos poderosos do PostgreSQL: As queries com `WITH RECURSIVE` e a transformação de resultados em JSONs diretamente através do banco de dados, facilitando a integração com outras plataformas e facilitando bem o trabalho da aplicação.

1. Dois caszzos de uso do Docker que vão além de CI/CD: [Utilização de dados de produção para testes](https://medium.com/fintech-studios-engineering/creating-fast-lightweight-testing-databases-in-docker-2a8164d2f519) e garantindo a [confiabilidade dos testes em ambientes complexos](https://blog.frankdejonge.nl/regaining-trust-in-your-tests-with-docker/), como quando se depende de serviços externos.

1. A Função `EXTRACT` do PostgreSQL é extremamente poderosa e razoavelmente eficiente para extrair porções específicas de datas em diversos formatos, podendo deixar as queries bem mais legíveis. Este tutorial fornece uma [série de exemplos de uso dessa funcionalidade](https://karolgalanciak.com/blog/2018/01/30/postgresql-quick-tips-working-with-dates-using-extract-function/).

1. A Wired publicou um artigo levantando [pontos fracos e limitações das tecnologias de Machine Learning](https://www.wired.com/story/greedy-brittle-opaque-and-shallow-the-downsides-to-deep-learning/). Além das velhas discussões sobre a opacidade e baixa auditabilidade destas tecnologias, os autores lançam questões sobre a desaceleração da inovação no campo e soluções como o aprendizado assistido que vêm ganhando espaço ultimamente.

1. Aplicação de [reconhecimento de faces com óculos especiais](https://www.technologyreview.com/the-download/610214/chinese-cops-are-using-facial-recognition-specs/) utilizados por policiais chineses.

1. O projeto [Cookiecutter](https://github.com/pydanny/cookiecutter-django) reune um boilerplate/blueprint para projetos Django estruturando um ecossistema bem completo para sua aplicação.

1.  Um design de aplicações chamado "Unary Call Sites" me chamou a atenção. Ao invés de declarar métodos chamados em diversos lugares, cada método deve ser chamado uma única vez. O reaproveitamento fica por conta da funções bases que são acessíveis através de adapters que basicamente estão lá justamente para isso. Isso em tese evitaria dependências instáveis e modificações em funções com centenas de consumidores que verão o comportamento esperado se alterar (ou a dolorida adição de um parâmetro extra "opcional").  Mais detalhes e discussões [nesse artigo](https://matthiasnoback.nl/2018/01/unary-call-sites-intention-and-revealing-interfaces/).
