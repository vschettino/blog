---
title: 'Links da Semana #75'
date: '00:00 02/14/2020'
taxonomy:
    category:
        - blog
    tag:
        - 'Links da Semana'
twitterenable: true
twittercardoptions: summary
twittershareimg: /linksdasemana/links_da_semana_1/links_semana.jpg
articleenabled: true
article:
    datePublished: '14-02-2020 15:45'
    dateModified: '14-02-2020 15:45'
    image_url: /linksdasemana/links_da_semana_1/links_semana.jpg
    author: 'Vinicius Schettino'
    publisher_logo_url: /blog/profile.jpg
    publisher_name: 'Vinicius Schettino'
musiceventenabled: false
orgaenabled: false
orga:
    ratingValue: 2.5
orgaratingenabled: false
eventenabled: false
personenabled: false
musicalbumenabled: false
productenabled: false
product:
    ratingValue: 2.5
restaurantenabled: false
restaurant:
    acceptsReservations: 'yes'
    priceRange: $
facebookenable: true
---

1. Muitas vezes precisamos esperar que o projeto/modificação esteja nas mãos dos usuários para perceber problemas de desempenho, memory leak e etc. Isso acontece pois algumas estruturas se comportam com um tempo de execução que depende do tamanho da entrada de dados. Quando testamos com poucos dados, não percebemos a diferença do desempenho e quem sofre com isso é o público lá na frente. Por isso é importante [analisar as funções e buscar tempo constante de execução](https://klaviyo.tech/magic-constant-time-tricks-that-klaviyo-uses-to-operate-at-huge-scale-879dfacdbee4) sempre que possível.

1. [MyPy](http://mypy-lang.org/) é um verificador de [type hint para Python](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html), permitindo que você aproveite o máximo dessa funcionalidade introduzida na versão 3.6 da linguagem. Como ele é bem flexível e permissivo, [algumas dicas podem ajudar a otimizar](http://calpaterson.com/mypy-hints.html) as análises e os resultados das execuções da ferramenta.

1. Dicas de [desempenho e organização do código](https://www.youtube.com/watch?v=fMRzuwlqfzs) para evitar problemas difíceis de detectar em Python.  

1. Resumo das dicas do dia: [utilize as f-strings em python para formatação](https://realpython.com/python-string-formatting/).

1. [Porque o `DROP` de colunas no PostgreSQL não libera espaço em disco imediatamente](https://realpython.com/python-string-formatting/)?

1. Visualização de dados em Python com o [Bokeh](https://docs.bokeh.org/en/latest/index.html)

1. Uma [boa regra geral](https://softwareengineering.stackexchange.com/questions/405038/result-object-vs-throwing-exceptions) para tratamento de erros em qualquer linguagem OO é utilizar exceções para erros inesperados e retornos (booleanos ou de objetos) para indicar que um cenário negativo, mas previsto da regra de negócio, se concretizou   

1.
