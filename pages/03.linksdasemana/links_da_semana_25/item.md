---
title: 'Links da Semana #25'
date: '00:00 05/18/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. A replicação do PostgreSQL nativo é baseada em um modelo bem elegante sincronização de WAL, o "log" que descreve quais as mudanças o banco de dados recebeu. [Existem formas diferentes de fazer essa transmissão entre as diversas réplicas](https://blog.timescale.com/scalable-postgresql-high-availability-read-scalability-streaming-replication-fb95023e2af), dependendo da sua disposição em abrir mão da consistência em detrimento do desempenho. Essa configuração pode ser feita ainda de maneira global ou por `TRANSACTION`, permitindo controle de qual caso pede qual abordagem. De qualquer maneira, a principal vantagem é dispor de réplicas capazes de distribuir o processamento de queries de leitura, aumentando a disponibilidade e desempenho do sistema.

1. Uma descoberta que mudou minha vida foi a[ cláusula `FILTER` do PostgreSQL](https://medium.com/little-programming-joys/the-filter-clause-in-postgres-9-4-3dd327d3c852), que pode ser utilizada como uma condicional dentro do próprio `SELECT`.

1. A condicional `OR` nas consultas SQL pode trazer alguns problemas de desempenho. Não é sempre que dá para evitar,[ [existem casos que a substituição por outras expressões](https://www.cybertec-postgresql.com/en/avoid-or-for-better-performance/) pode ajudar bastante.

1. [O que são tablespaces](https://pgdash.io/blog/tablespaces-postgres.html?h)?

1. Dicas rápidas para [escrever boas issues](https://sebastiandedeyne.com/a-good-issue).

1. Uma das features mais legais do Python é poder [sobrescrever funções padrão da linguagem](https://realpython.com/operator-function-overloading/) (como `+, [], len()`) nos seus objetos, deixando a operação deles mais elegante e prática.

1. Assim [como no PHP](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration), o Python (ambos em versões mais novas) também permite a [anotação de tipagem em parâmetros e retornos de métodos](https://medium.com/@shamir.stav_83310/the-other-great-benefit-of-python-type-annotations-896c7d077c6b).

1. AIs podem ser rápidas, mas [ainda não são mais eficazes que humanos](https://www.theverge.com/2018/5/7/17316010/fast-ai-speed-test-stanford-dawnbench-google-intel) em alguns contextos.

1. Modelo de [previsão de valor de guitarras baseado](https://www.linkedin.com/pulse/how-much-should-you-pay-1960s-fender-stratocaster-owen-carey/) em características curiosas.
