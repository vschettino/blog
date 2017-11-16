---
title: 'Refatoração: As prinpais categorias de Bad Smells'
date: '00:00 11/13/2017'
taxonomy:
    category:
        - blog
    tag:
        - refatoração
        - engenharia continua
        - evolução de software
---

A refatoração está entre umas das principais atividades de manunteção da qualidade internet de código fonte. Não há *codebase* imune à deterioração causada pelo tempo, pelas más práticas e pela falta de padronização dos responsáveis por sua manutenção. Complementando artigos passados, irei apresentar as principais categorias de Bad Smells (mau cheiros) e seus impactos na qualidade do código.

===

## Introdução

Para quem ainda não leu o artigo sobre os [conceitos básicos da refatoração](http://vschettino.com.br/blog/introducao_refatoracao) e a [palestra que dei sobre o tema](vschettino.com.br/blog/palestra_refatoracao) há umas semanas, recomendo fazê-lo antes de continuar a leitura.

Assim como as Design Patterns, os Code Smells são bem dividos em categorias distintas e com os remédios corretos. Ou seja, [para cada Bad Smell definido na literatura](http://refactoring.com), existe um conjunto de métodos para sanar o problema. Irei utilizar linguagem e categorias mais informais para facilitar o entendimento.

## Estufadores

Conhecidos em inglês como "Bloaters", são componentes que cresceram demais e concentram grande parte da responsabilidade e dos problemas do projeto. Geralmente sofrem modificações toda hora, [ferindo o princípio Aberto/Fechado](https://robsoncastilho.com.br/2013/02/23/principios-solid-principio-do-abertofechado-ocp/). Estes métodos, classes e arquivos geralmente viram intocáveis no projeto, simplesmente porque dão medo de chegar perto. Fica difícil rastrear todos os efeitos que uma mudança causa num componente muito grande, então este tipo de problema gera um risco grande para a manutenção.

Os principais métodos de tratamento envolvem extrair comportamentos e atributos em classes menores e mais [coesas](https://pt.stackoverflow.com/questions/81314/o-que-s%C3%A3o-os-conceitos-de-coes%C3%A3o-e-acoplamento). Geralmente estes componentes incham por uma decisão ruim de design e utilização dos conceitos de orientação a objetos.


## Mau uso da orientação a objetos

A Orientação a Objetos pode ser abusada e mau utilizada em diversos aspectos, que desvirtuam seu propósito original. Os casos mais comuns envolvem a confusão entre quando usar [herança e quando usar composição](https://pt.stackoverflow.com/questions/25619/composi%C3%A7%C3%A3o-e-agrega%C3%A7%C3%A3o-quais-as-diferen%C3%A7as-e-como-usar), criando uma árvore de herança para compartilhar comportamentos que não são necessários em todas as classes. Acontece também o contrário, onde um comportamento comum é implementado diversas vezes, ou quando um comportamento é rejeitado pela maior parte dos herdeiros. Como a [orientação a objetos te ajuda a evitar estruturas `switch`](https://stackoverflow.com/questions/31518236/object-oriented-programming-avoid-switch-case-and-if-else-java), a presença constante destes no código geralmente é sinal de falta de polimorfismo.  

Geralmente o melhor remédio para esta categoria de problemas é a reengenharia da estrutura do projeto, separando melhor as heranças e as interfaces.

## Inibidores de Modificação

Caem nesta categoria os Code Smells que atrapalham na hora de realizar mudanças no código. Todos os Code Smells, em maior ou menor grau, influenciam neste aspecto, já que dificultam a legibilidade e a compreensão do código. Contudo, nesta categoria estão os problemas que deixam uma modificação simples virar algo mais complexo e com ramificações difíceis de acompanhar. É o caso de estruturas que te obrigam a realizar a mesma alteração (por exemplo, mudar uma constante) em diversos lugares, muitas vezes difíceis de achar. Interfaces e Heranças mal feitas podem ter efeito semelhante, onde qualquer nova alteração obriga uma refatoração da estrutura e da relação entre os componentes.

## Dispensáveis

São porções de código que não precisavam estar lá, e só servem para deixar tudo mais difícil de entender e evoluir. Os mais comuns são código duplicado, [principal vilão da refatoração](https://solidsourceit.wordpress.com/2012/08/03/does-source-code-duplication-matter/) e comentários que tentam disfarçar um código mau feito. O "código morto", comentados ou em locais que não são acessados também são desafios para manunteção, principalmente para novos mantenedores.

## Acopladores

Código acoplado é, por definição, mais difícil de manter. A acoplação ocorre quando dois componentes se relacionam, seja por herança, utilização de métodos e atributos, ou passagem como parâmetro. Quando mais acoplados, mais complicado é trocar um componente por outro de comportamento semelhante, deixando o processo de evolução agarrado nas interfaces já existentes. É impossível promover acoplamento nulo em todo o sistema, mas deve-se evitar que, por exemplo, métodos façam muitas chamadas para classes diferentes ou que um mesmo componente chame diversas classes ao mesmo tempo.


## Conclusão

O objetivo deste artigo é introduzir brevemente os principais tipos de code smells, sem entrar em detalhes sobre cada um deles ou como efetivamente detectá-los na code base. Contudo, ao entender as principais características destas classes de mau cheiros e como elas estão relacionadas à qualidade do código, o desenvolvedor poderá ficar atento aos efeitos e aos sinais destas estruturas, facilitando o processo de refatoração. 


## Referências

1. https://refactoring.guru/refactoring/what-is-refactoring
1. https://bids.berkeley.edu/news/joy-code-refactoring
1. http://refactoring.com
1. https://refactoring.guru/refactoring/smells
