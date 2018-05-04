---
title: 'Links da Semana #23'
date: '00:00 04/05/2018'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Para facilitar a vida na hora de executar os testes automatizados, o [pyppetter](https://miyakogi.github.io/pyppeteer/) provê a interface entre o código e o navegador, no mesmo estilo que projetos como selenium e mais avançado (e lento) que os headless browsers como o [PhantomJS](http://phantomjs.org/). Vale a pena conferir mais sobre ele com um [caso de uso de web scrapping](https://medium.com/commite/pyppeteer-the-snake-charmer-f3d1843ddb19) que mostra o poder da ferramenta.

1. O projeto [Rebound](https://github.com/shobrook/rebound) observa os erros de execução do seu código em Python e busca automaticamente as melhores respostas no Stack Overflow.

1. O [tinfoleak](https://github.com/vaguileradiaz/tinfoleak) é uma ferramenta OpenSource que reúne as principais funcionalidades de acesso a API do twitter para facilitar a vida de quem precisa extrair dados desta rede social.

1. Explicação das principais [formas de backup no PostgreSQL](https://severalnines.com/blog/top-backup-tools-postgresql) com suas vantagens, desvantagens e principais cenários de uso.

1. Novidade anunciada para o PostgreSQL 11: [utilizando a cláusula INCLUDE na criação dos indexes](http://paquier.xyz/postgresql-2/postgres-11-covering-indexes/) para aumentar a chance de scans index-only.

1. [Macetes e dicas para manter instâncias PostgreSQL em produção](https://severalnines.com/blog/ten-tips-going-production-postgresql) com pouca (menos) do de cabeça.

1. [Funcionamento de datas, timezones e intervalos no PostgreSQL](https://tapoueh.org/blog/2018/04/postgresql-data-types-date-and-time-processing/).

1. BrendDt apresenta uma [discussão sobre tipagem forte/fraca](https://www.stitcher.io/blog/what-php-can-be) e a aplicação disso no PHP.

1. [Métodos de encriptação de password no PHP](https://engagedphp.com/2018/03/storing-passwords-the-right-way/) (e porque isso é importante).

1. [Casos concretos (ou quase) das vantagens de desempenho do PostgreSQL 10](https://speakerdeck.com/genslein/postgres-10-performance-and-you). Ênfase no particionamento de tabelas nativo e indexes HASH e GIN para colunas compostas (JSONB).

1. Aleluia, depois de anos com aquela interface estilo BOL 2000, o [site oficial do PostgreSQL está de cara nova](https://www.postgresql.org/)

1. Apresentação simples de [para que servem os indexes e como utilizá-los](https://www.xaprb.com/slides/index-postgresql-database-postgresconf-2018/) no PostgreSQL.

1. As [Traits](http://php.net/manual/pt_BR/language.oop5.traits.php) são um excelente método para reutilização de código horizontal, ou seja, sem depender da hierarquia das classes (herança). Elas são muito utilizadas para composição de comportamentos, evitando uma série de problemas estruturais que são apontados [neste artigo](https://engagedphp.com/2018/04/implementing-abstract-classes-and-interfaces-with-traits/).

1. A [GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) é a regulamentação europeia sobre privacidade e uso de informações de usuários por sistemas de informação. É considerada bem restritiva para os padrões atuais e começa a ser obrigatoriamente adotada em 25/05/2018 para todos os sistemas comerciais que detenham dados de cidadões europeus. Mesmo que não seja o seu caso, espera-se que essa regulamentação se torne padrão para outras de outros países. Por isso, é importante começar a ver exemplos de aderência à norma europeia [como o proposto por Christoph Rumpel aqui](https://christoph-rumpel.com/2018/04/make-your-chatbots-gdpr-compliant).

1. Observações sobre [código legado e generalização de métodos](https://matthiasnoback.nl/2018/04/combing-legacy-code-string-by-string/): Aumentar a lista de parâmetros ou criar métodos alternativos que chamam o método básico?

1. [Novidades previstas para o PHP 7.3](https://ayesh.me/Upgrade-PHP-7.3).

1. [Comparações do modus operandis do cérebro humano com os computadores](http://nautil.us/issue/59/connections/why-is-the-human-brain-so-efficient).

1. [Um apelo pela importância da pesquisa quantitativa](https://medium.com/indeed-data-science/qualitative-before-quantitative-how-qualitative-methods-support-better-data-science-d2b01d0c4e64), especialmente dentro das ciências exatas.

1. [P-values não são o que parecem](https://lucklab.ucdavis.edu/blog/2018/4/19/why-i-lost-faith-in-p-values).

1. Refatoração voltada para [reuso e diminuição de acoplamento de módulos](http://engineering.khanacademy.org/posts/python-refactor-3.htm) em Python.
