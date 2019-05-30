---
title: 'Introdução à Refatoração de Código'
date: '00:00 11/01/2017'
taxonomy:
    category:
        - blog
    tag:
        - refatoração
        - engenharia continua
        - evolução de software
---

A refatoração está entre umas das principais atividades de manunteção da qualidade internet de código fonte. Não há *codebase* imune à deterioração causada pelo tempo, pelas más práticas e pela falta de padronização dos responsáveis por sua manutenção. Neste artigo irei explicar a importância da técnica e as principais práticas associadas na indústria.

===

## O que é refatorar?

O conceito de refatoração não é, por si só, complicado. Talvez o principal autor sobre o tema seja [Martin Fowler](http://martinfowler.com/), que escreveu livros e artigos sobre o tema. Para ele, [refatoração é](https://refactoring.com/):

> Uma técnica disciplinada para reestruturação de código fonte já existente, alterando a estrutura interna sem afetar o comportamento externo.

Ou seja, a refatoração é uma técnica para alterar como o software faz alguma coisa, e não o que ele faz. Em efeitos práticos, você buscar melhorar o funcionamento do código sem deixar que o observador externo perceba a mudança.

Normalmente, os desenvolvedores mais novos logo associam "melhorar o funcionamento código" com desempenho. Ou seja, consumir menos recursos computacionais. Este não é o primário objetivo de uma refatoração, até porque "mais rápido" é uma característica observável e por isso fere o princípio básico da técnica.

![http://www.bonkersworld.net/building-software/](https://bids.berkeley.edu/sites/default/files/kyle_blog_pic.png)

O conceito proposto por Martin Fowler abriga um conjunto de práticas simples e sistemáticas que objetivam melhora a manutenibilidade do código, principalmente a legibilidade. Escrevi sobre [algumas destas técnicas anteriormente no blog](http://vschettino.com.br/blog/palestra_refatoracao), mas hoje eu gostaria de aproveitar apenas a definição previamente explicada e os objetivos básicos da estratégia, para entrar numa questão maior.

![](http://deus.co.uk/images/refactoring.png)

## Porque refatorar?

> Se não há relação direta entre desempenho, novas funcionalidades e refatoração, porque eu faria isso? Parece desperdício de tempo.

Novamente, esta pode ser a visão do desenvolvedor menos experiente, que muitas vezes não atribui à manutenibilidade a devida importância. Este atributo de software é [reconhecido pela ISO/IEC 9126](https://en.wikipedia.org/wiki/ISO/IEC_9126) e suas atualizações e mede o quão complicado é modificar e evoluir um software. É díficil citar aqui todos os trabalhos que apontam os benefícios de um alto índice de manutenibilidade, principalmente para diminuir defeitos, entregar funcionalidades mais rapidamente e trilhar o caminho para melhorar outros aspectos, como qualidade e segurança. Por isso o esforço sem valor de negócio agregado diretamente, rapidamente se justifica (e se paga) quando o software começa a crescer.

## Como refatorar

Este foi o foco de uma [palestra minha há algumas semanas](http://vschettino.com.br/blog/palestra_refatoracao), então não irei repetir muita coisa. O resumo é que:

1. A refatoração deve ser feita em pequenas doses, acompanhando o crescimento natural do sistema.
1. Nem tudo precisa ser refatorado, utilize o bom senso e procure pelos [code smells](https://sourcemaking.com/refactoring/smells)
1. Analise o código e se pergunte: Se eu tivesse um minuto para refatorar, onde eu o utilizaria?

## O que refatorar

Esta talvez seja a pergunta mais interessante. Creio que as técnicas de refatoração sejam triviais de se aprender, e (espero) que o leitor já esteja motivado sobre a importância e as metas da refatoração. Irei escrever um artigo específico sobre as principais categorias de code smells em breve, analisando porque eles são considerados más práticas e como eles impactam o dia a dia da evolução do código.

## Conclusão

Este foi um artigo introdutório que pode ser resumido com uma única frase: A refatoração é um processo contínuo para manter e recuperar a qualidade do código fonte, potencializando a evolução do software, tanto em requisitos funcionais quando não funcionais.

Ou seja, a refatoração deve ser parte constante do processo de desenvolvimento, pois permite à equipe continuar o trabalho de evolução com os subsídios necessários.





## Referências

1. https://refactoring.guru/refactoring/what-is-refactoring
1. https://bids.berkeley.edu/news/joy-code-refactoring
1. http://refactoring.com
