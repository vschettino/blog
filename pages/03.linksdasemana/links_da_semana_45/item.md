---
title: 'Links da Semana #45'
date: '00:00 01/11/2019'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Relato da [migração do backend do The Guardian de MongoDB para PostgreSQL](https://www.theguardian.com/info/2018/nov/30/bye-bye-mongo-hello-postgres).

1. Seja em pesquisa ou em provisionamento de ambientes de teste/staging, garantir que dados sensíveis de usuários não estejam expostos, e que eles não sejam identificados através deles. O [PostgreSQL oferece vários mecanismos para ajudar neste processo](http://blog.taadeem.net///english/2019/01/03/8_anonymization_strategies_with_postgres), além de auxiliar também no processo de amostragem, também muito importante, com o [pg_sample](https://github.com/mla/pg_sample).

1. Você sabia que existem [14 métodos diferentes de autenticação no PostgreSQL](https://momjian.us/main/blogs/pgblog/2019.html#January_2_2019)?

1. Pensamentos de um desenvolvedor que passou um [ano vivendo no vale do silício](https://evertpot.com/a-look-back-at-sf/).

1. Discussões sobre um [padrão de nomenclatura melhor](https://blog.nikolaposa.in.rs/2019/01/06/better-naming-convention/).

1. Dicas para [aumentar a eficiência do processo de code review](https://sergeyzhuk.me/2018/12/29/code_review/).

1. O padrão de compressão Brotli para HTTP que promete [eficiência e descompressão muito mais rápidas que o tradicional GZIP](https://www.opencpu.org/posts/brotli-benchmarks/), ao custo de uma compressão mais cara.  

1. [HTTP Status Code 406 - Not Acceptable](https://evertpot.com/http/406-not-acceptable).

1. [Visualizações de dados do final do século 19](https://richardbrath.wordpress.com/2018/12/31/album-de-statistique-graphique/).

1. Qual o [entendimento](https://blog.revolutionanalytics.com/2017/08/probably-more-probably-than-probable.html), em porcentagem de probabilidade, de expressões comuns como "provavelmente" e "improvável"?  

## Projetos Legais

1. Existem projetos para criar ou obscurecer estas bases de dados, como o faker para [PHP](https://github.com/fzaninotto/Faker) e [Python](https://pypi.org/project/Faker/).

1. Criando indícies hipotéticos com o [HypoPG](https://github.com/HypoPG/hypopg). Assim você pode descobrir se (e quanto) o PostgreSQL iria utilizar o índice antes de decidir dedicar os recursos para tal.

1. Com o projeto [Have I Been Pwned](https://haveibeenpwned.com/) é possível saber
se os dados informados pelos seus usuários, como [email](https://haveibeenpwned.com/)) e [senha](https://haveibeenpwned.com/)), já foram vazados e se encontram em bancos de hashing na internet, apontando a potencial vulnerabilidade. É uma alternativa ainda mais completa às verificações tradicionais de força de senha, por exemplo.
