---
title: 'Problemas com a Licença BSD + Patent Clause - React e outros projetos do Facebook'
date: '00:00 10/16/2017'
taxonomy:
    category:
        - blog
    tag:
        - Ecossistemas
        - React
        - OpenSource
hide_git_sync_repo_link: false
hide_from_post_list: false
---

Os últimos meses tem sido de expectativa para os aficcionados pelo React. Depois da [decisão da Apache  Foundation](https://issues.apache.org/jira/browse/LEGAL-303) de colocar a Licença BSD + Patents Clause, utilizada pelo Facebook no React e no React Native (e em outros produtos), na lista de [licenças proibidas de integrarem produtos Apache](https://www.apache.org/legal/resolved#category-x), muita gente temeu não poder utilizar mais tais tecnologias em seus produtos. Afinal, o que diz a licença e quais cuidados devem ser tomados?

## Porque a cláusula de patente?

Segundo o Facebook, esta cláusula ajuda a evitar disputas de patente. Se você utiliza software do Facebook - por exemplo, o React - e tenta processá-los por infrações relacionadas a patente, [você perde o direito de usar a patente](https://code.facebook.com/posts/112130496157735/explaining-react-s-license/) do React. Não entrando no mérito de julgar esta estratégia, [não seria a primeira organização](https://react-etc.net/entry/react-patents-facebook-license-faq-adoption-by-apple-and-microsoft) à utilizá-la.

## A Confusão

Já existiam críticas a licença, mas a decisão da Apache Foundation foi um baque importante. Isso porque a lista de projetos sob a organização Apache é gigante e base de outros projetos, então muitos encararam a decisão como um banimento ao React. O [WordPress anunciou que iria parar de utilizar o React](https://ma.tt/2017/09/on-react-and-wordpress/), tanto na reescrita do WordPress.com quanto na nova versão do editor de conteúdo. Não discutiram se a cláusula era um problema ou não, mas sim que não seria responsabilidade do WordPress tratar de convencer o mundo se a cláusula faz sentido.  


## Continuação da História

Até então o Facebook não tinha feito um bom trabalho explicando a licença, o que foi o [combustível da confusão](https://react-etc.net/entry/your-license-to-use-react-js-can-be-revoked-if-you-compete-with-facebook). Através de um [FAQ](https://code.facebook.com/pages/850928938376556) recente, eles tentaram explicar ocorrido, mas já era um pouco tarde. Apesar de primariamente irredutíveis, em  [25/09/2017](https://github.com/facebook/react/commit/8c3cececb765a0a0ad8b0faca764ef30be494a74) foi anunciada a **troca da licença para a MIT**, aparentemente terminando o imbróglio. Segundo o Diretor de Engenharia [Adam Wolff](https://thenextweb.com/dd/2017/09/25/facebook-re-licenses-react-mit-license-developer-backlash/):

> React is the foundation of a broad ecosystem of open source software for the web, and we don’t want to hold back forward progress for nontechnical reasons.

Segundo a mesma reportagem, o Facebook continua acreditando que a cláusula é inofensiva e importante, mas eles "falharam em convencer a comunidade de vez."

## Conclusão

Apesar de ser uma peleja resolvida, duas lições podem ser tiradas deste caso. Primeiro, fica clara a importância de entender a licença sob a qual bibliotecas e frameworks estão protegidos antes de adicioná-los aos seus projetos. Não é atoa que existem [diversas licenças](https://opensource.org/licenses), e [a escolha](https://choosealicense.com/) vai depender dos objetivos do projeto e da estratégia de distribuição.

O segundo ponto é a relação de um ecossistema OpenSource com empresas privadas. O Facebook é um dos maiores contribuidores de software livre atualmente, e sabe muito bem da importância de engajar contribuições e utilizações da comunidade para os seus produtos. Irredutíveis no primeiro momento, eles perceberam a importância de manter o alinhamento com outros componentes do ecossistema, sob pena de serem deixados de lado por outras tecnologias melhor compactuadas com o contexto livre. Percebe-se assim o poder da comunidade OpenSource nas estratégias das mais poderosas organizações.
