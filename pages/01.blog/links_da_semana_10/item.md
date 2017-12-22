---
title: 'Links da Semana #10'
date: '00:00 12/22/2017'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Bancos de dados com estruturas muito dinâmiacas tendem a confundir as rotinas de indexação e planejamento de queries, causando, entre outros problemas, utilização ineficiente e desncessária de disco. Com a extensão ``pg_repack``, é possível [medir e controlar este problema com custo computacional menor que outras alternativas](https://www.redpill-linpro.com/sysadvent/2017/12/08/pg_repack.html).

1. Matt Asay faz uma análise direta do modelo de comunidade do PostgreSQL, mostrando porque esse [SGBD ainda não consegue ultrapassar o alcance do Oracle](https://www.techrepublic.com/article/theres-one-big-reason-that-postgres-cant-kill-oracle-and-its-not-the-technology/). O modelo de mercado, contratos e marketing da Oracle acabam por controlar um grande *market share* que, se seus únicos desafios fossem de natureza técnica, muito provavelmente o PostgreSQL seria mais que suficiente.

1. Pouca gente se dá conta, mas o SQL tem uma [lógica ternária para tratar condições](http://modern-sql.com/concept/three-valued-logic). Além dos tradicionais `TRUE` e `FALSE`, também temos o `UNKOWN`. A explicação é simples: no SQL, strings vazias (`null`) podem ser qualquer coisa, e não necessariamente "nada". Por isso, não é possível dizer, ao comparar uma string com `null`, se elas são iguais ou diferentes. Resultado: `UNKNOWN`. [Este artigo](http://modern-sql.com/feature/is-distinct-from) mostra algumas particularidades que isso gera, algumas bem desconhecidas e que podem acarretar em comportamentos inesperados difíceis de detectar.  

1. E se o PostgreSQL utilizasse threads ao invés dos tradicionalíssimos processos? Konstantin Knizhnik [apresentou um protótipo com técnicas que podem tornar esta modificação viável](https://www.postgresql.org/message-id/9defcb14-a918-13fe-4b80-a0b02ff85527%40postgrespro.ru), com resultados preliminares interessantes.

1. Como escolhemos o que lembrar e o que esquecer? Com o universo de informações que nos deparamos diariamente, escolher sabiamente o que deve ser registrado com maior persistência é essencial. É o que Rahaf Aljundi e seus colegas estão estudando, [para criar máquinas que saibam o que é relevante ou não para ser aprendido](https://www.technologyreview.com/s/609710/neural-networks-are-learning-what-to-remember-and-what-to-forget/).

1. Engenheiros da Stitch Fix Algorithms tentam reproduzir para lojas virtuais uma caracterísitca até então ímpar das lojas físicas: o atendente que te olha e acerta de primeira uma jaqueta que cabe perfeitamente em você. Mesmo com feedbacks do tipo "coube perfeitamente" ou "ficou largo", ainda é difícil dizer se isso ocorreu porque você é grande demais ou a roupa é muito pequena. Utilizando métodos de análise de notas em testes de educação padronizados (nos EUA, os SATs), onde alunos diferentes recebem provas diferentes mas terão seus scores comparados entre si, eles explicam como [tentam acertar se determinada vestimenta é ideal para você](http://multithreaded.stitchfix.com/blog/2017/12/13/latentsize/).

1. As Fake News foram determinantes nas eleições dos EUA de 2017, e tem tudo para execer um papel semelhante nas eleições brasileiras de 2018. No plano ideal, pessoas aprenderiam a checar fontes e não acreditar em notícias esdrúxulas, como o [chip da besta de Dilma Roussef ou a proposta de alterar a bíblia de Jean Wyllys](https://www.fatosdesconhecidos.com.br/5-noticias-falsas-que-voce-pensou-que-fossem-reais/). Mas esse caminho não parece ter dado muito certo. Entram então as tecnologias de inteligência artificial voltadas para identificar e reduzir a circulação (e consequente renda) destas notícias. Este artigo [mostra o estado da arte das pequisas e o que as organizações estão fazendo para combater este mal](https://www.technologyreview.com/s/609717/can-ai-win-the-war-against-fake-news/).

1. [Exemplo de como quebrar uma máquina de CAPTCHA bem simples](https://medium.com/@ageitgey/how-to-break-a-captcha-system-in-15-minutes-with-machine-learning-dbebb035a710), mas utilizado por mais de 1 milhão de sites Wordpress.

1. Quais variáveis ajudam a predizer se um funcionário irá deixar a empresa em breve? Imad Dabbura [mostra o resultados de diversos algoritmos de predição](https://towardsdatascience.com/predicting-employee-turnover-7ab2b9ecf47e), sem conclusões muito surpreendentes.

1. Uma das formas de se pensar em software é através de uma pipeline, ou straming. Os dados entram no primeiro componente, que realiza a transformação que lhe é devida e passa para o próximo, até terminar o ciclo. Este design é interessante em situações de ETL, data mining ou até mesmo tratament oe requisições HTTP, pois facilita o reuso e composição de componentes distintos. Asmir Mustafic apresenta algumas [implementações e cuidados que a arquitetura em pipeline requer](https://www.goetas.com/blog/modular-application-architecture-pipelines/).

1. E se, ao invés de agregar componentes pelo o que eles fazem (como tradicionalmente separamos, models, controllers, helpers), eles fossem organizados pelas funcionalidades que eles participam? É uma[ visão interessante de Matthieu Napoli](http://mnapoli.fr/organizing-code-into-domain-modules/) e que pode ser estudada e aproveitada, que seja pelo menos em partes específicas da aplicação. 
