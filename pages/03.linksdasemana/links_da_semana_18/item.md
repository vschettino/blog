---
title: 'Links da Semana #18'
date: '00:00 03/02/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. O Facebook lançou o [osquery](https://github.com/facebook/osquery), um framework que promete facilitar o acesso a informações do nível do sistema operacional. Disponível para diversas plataformas (Windows, Linux e macOS), o projeto promete prover acesso aos dados de sensores, processos, módulos do kernel através de uma [interface relacional](https://osquery.io/schema/2.11.2) via SQL.

1. Mesmo em SGBDs que suportam acesso concorrente às informações, existem momentos que algumas operações precisam entrar na fila para evitar a quebra do padrão ACID. É importante [conhecer quando isso pode acontecer e como evitar](https://www.citusdata.com/blog/2018/02/15/when-postgresql-blocks/), uma vez que o desempenho da aplicação pode ser severamente afetado.

1. O PostgreSQL fornece uma política de segurança baseada não só em relações, schemas e databases, mas também a nível de linhas de uma determinada tabela. Esta pode ser uma camada extra de proteção em sistemas críticos onde a mesma estrutura comporta dados de clientes/usuários distintos e a separação entre eles é questão prioritária do produto. É o [estudo de caso apresentado pela Crunchy Data](http://info.crunchydata.com/blog/a-postgresql-row-level-security-primer-creating-large-policies), que mostra como este mecanismo funciona e alguns exemplos de aplicações.

1. Simon Riggs, um dos principais contribuidores do PostgreSQL, [discorre sobre os limites de tamanho das tabelas do SGBD](https://blog.2ndquadrant.com/postgresql-maximum-table-size/), dando explicações de como ele é calculado e contando a história de como ele evoluiu drasticamente depois da resolução de um pequeno bug que estava adormecido há mais de 20 anos.

1. O modelo [ternário do SQL](https://en.wikipedia.org/wiki/Three-valued_logic) pode causar situações bem contra intuitivas, que geralmente pegam de surpresa. Isso porque além do `TRUE` e do `FALSE`, também temos o `UNKOWN`. [Este artigo rápido](http://tanin.nanakorn.com/blogs/389) mostra uma destas situações.  

1. [Desvendando o Log do PostgreSQL](https://severalnines.com/blog/decoding-postgresql-error-logs).

1. Comparação de floats é um [problema](https://stackoverflow.com/questions/5595425/what-is-the-best-way-to-compare-floats-for-almost-equality-in-python) na [maioria](https://stackoverflow.com/questions/3148937/compare-floats-in-php) das [linguagens](https://stackoverflow.com/questions/1088216/whats-wrong-with-using-to-compare-floats-in-java), onde os programadores mais novos acabam tomando um susto quando `(10.25 == 10.50 - 0.25)` retorna `FALSE`. Quando tratar desse tipo de dados é imprescindível, este [*custom type* para tratar números racionais no PostgreSQL](https://github.com/begriffs/pg_rational) pode ajudar bastante.

1. O `WITH` e as `WINDOW FUNCTIONS` são estruturas importantes dos SGBDs modernos, que fazem parte das [Common Table Expressions (CTE)](https://pt.wikipedia.org/wiki/Common_table_expression) que o padrão SQL prevê. Além de ajudarem a escrever queries mais legíveis, algumas funcionalidades recursivas e de acesso interativo a resultados parciais das queries aumentam o poder de fogo da linguagem. Este artigo traz alguns [exemplos de funcionamento destas estruturas](http://mjk.space/advanced-sql-cte/).

1. Contas no Twitter como a de [Vicki Boykis](https://twitter.com/vboykis) têm se dedicado a promover pinturas clássicas com legendas bem humoradas que relatam a vida dos profissionais de tecnologia: o movimento foi batizado de [#devart](https://twitter.com/hashtag/devart?src=hash).

1. [Gerenciamento de dependências no Python](https://code.kiwi.com/our-comprehensive-guide-to-python-dependencies-8a5a4366a563), tanto para pacotes livres quanto privados.

1. Caso de uso da [migração de grandes projetos de software](https://medium.com/@boxed/moving-a-large-and-old-codebase-to-python3-33a5a13f8c99) do Python 2.x para o 3.x, com auxílio do projeto [Six](https://medium.com/@boxed/moving-a-large-and-old-codebase-to-python3-33a5a13f8c99).

1. [Dicas de acessibilidade](https://www.sitepoint.com/making-bootstrap-accessible/) utilizando o [Bootstrap](https://getbootstrap.com/)

1. Exemplo da extensão do [Design Pattern Factory](https://www.tutorialspoint.com/design_pattern/factory_pattern.htm), aproveitando a ideia original e promovendo um código mais encapsulado e limpo: o [Simple Factory](https://www.startutorial.com/articles/view/understanding-design-patterns-simple-factory).
