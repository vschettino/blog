---
title: 'Sobre as licenças OpenSource - O básico que você precisa saber'
date: '00:00 10/26/2017'
taxonomy:
    category:
        - blog
    tag:
        - OpenSource
---

O universo OpenSource se baseia na liberdade de uso, modificação e distribuição de código fonte entre contribuidores e utilizadores ao redor do mundo. Contudo, existem condições e limitações para essa liberdade, de acordo com o modelo de licença que foi utilizado pelo criador do trabalho. Muitos desenvolvedores não tem conhecimento sobre o comportamento das diversas licenças, não sabendo como licenciar seu código nem como escolher softwares de terceiros (biblitoecas, frameworks, etc) que ofereçam condições legais compatíveis com seus objetivos. Este artigo é uma iniciativa de explicar as condições, garantias e liberdades das principais licenças, sem complicação.

===

## Antes de mais nada: se não tiver uma licença?

Este cenário não só pode ocorrer, mas também é relativamente comum. Por padrão todos os direitos de exploração são reservados ao autor e não há liberdade explícita de uso, distribuição ou modificação, mesmo que o código esteja disponível (por exemplo no GitHub). Ou seja, **você não deve utilizar aquele código.**

Caso o autor tenha disponibilizado seu trabalho em um ambiente público, é possível que ele tenha esquecido da licença. Então vale a pena entrar em contato com ele para esclarecer melhor os termos de uso daquele código fonte.

## Licenças de software livre

As licenças de software livre possuem três objetivos comuns:

1. Permitir a universalização de projetos de software.
1. Manter as devidas referências de autoria e contribuição.
1. Evitar processos jurídicos contra os autores por qualquer problema que o software tenha causado ("culpabilidade").

Existem várias formas de fazer isso, com níveis de permissividade e condicionamento diferentes. Algumas pretendem deixar o processo de distribuição, uso e modificação o mais aberto e universal possível, outras servem para situações onde esta visão atrapalharia a incorporação de código aberto em produtos de software. As próximas seções trazem informações básicas das três principais licenças, iniciando pela que possui mais condições e indo até as mais permissivas.

## GPLv3: a mais restritiva
A [General Public License v3](https://www.gnu.org/licenses/gpl-3.0.txt) é uma licença copyleft, que tem como objetivo de permitir a plena utilização, difusão e modificação do código fonte mantendo claramente a referência e os créditos ao autor original. Adicionalmente, a GPLv3 obriga que todo o código produzido através da utilização do código original deve ser licenciado sob os mesmos termos, que incluem a distribuição universal do código fonte, documentação e as mesmas liberdades de uso.

Quando o objetivo é fazer um componente completamente reutilizável e livre, garantindo que qualquer melhoria nele vai continuar sendo livre, esta é uma boa licença para se escolher.

**Você só deve utilizar um componente GPLv3 em um projeto se quiser que ele também seja GPLv3**, pois o trecho sob esta licença "contamina" todo o código fonte. Como possível alternativa, existe a [Lesser General Public License (LGPLv3)](https://www.gnu.org/licenses/lgpl-3.0.txt), que limita a "contaminação" a modificações diretas do código original. Ou seja, se ele é utilizado na íntegra, acessado como uma "biblioteca" ou "serviço", através de uma interface provisionada pelo trabalho original, o resto do código pode ser licenciado sob outras regras.

## Open Source Seletivo: Mozilla Public License 2.0

Essa é [uma licença](https://www.mozilla.org/media/MPL/2.0/index.txt) copyleft, mas bem mais fraca que as anteriores. É necessário **manter a licença do trabalho original e disponíveis para o mundo apenas os arquivos originais e suas modificações**. Ou seja, ela pode ser utilizada em um projeto maior e fechado (ou sob outra licença), mas os arquivos do trabalho original e suas modificações devem ser tornados públicos.

## Apache 2.0 e o direito de patente

A [Licença Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0.html) é utilizada em quase todos os projetos da Apache Foundation, uma das maiores organizações de código aberto do mundo. Diferente da licença GPLv3, ela não obriga que todo trabalho derivado mantenha a mesma licença; ou seja, você **pode utilizar uma parte de código aberto dentro do seu código proprietário, cobrar por ele e não disponibilizar para ninguém**.

Uma característica que aproxima as três licenças acima é a concessão do direito de patente. Ou seja, estas licenças garantem que não **é possível processar os contribuidores nem os utilizadores por infração de patente.** Esta cláusula serve para inviabilizar que algum contribuidor espalhe sua biblioteca pelo mundo para então começar a cobrar royalties dos utilizadores.


## Licença MIT: direto ao ponto

Talvez seja a licença mais permissiva entre as populares, já que não fala nada sobre patentes e diz que tudo é permitido. É mais fácil dizer o que ela ela não deixa: Infração de copyright (roubar a autoria) e  culpabilidade dos contribuidores. Tanto é que esta licença tem três parágrafos apenas e as vezes vem acompanhada de um documento adicional para esclarecer outros detalhes de uso.


## E as outras licenças?

Existem outras licenças relevantes por aí, mas geralmente são comparáveis com uma das citadas acima. Por isso, minha orientação é:

Se você estiver fazendo um código e tem intenção de deixá-lo aberto, escolha uma das licenças acima baseando-se nas suas intenções de distribuição. Estas são as principais licenças e mais fáceis de entender, então você saberá com mais facilidade os impactos da sua decisão.

Se você encontrar algum projeto OpenSource que não utiliza uma dessas licenças, será fácil pesquisar na internet e achar alguma comparação com uma das licenças supracitadas, do tipo: "A licença X parece com a Y mas possui uma cláusula extra sobre Z".

## Conclusão
Encontrar uma licença para um projeto OpenSource, ou mesmo decidir sobre a incorporação de um código de terceiro no seu projeto não é uma tarefa trivial para nossos desenvolvedores. O objetivo deste artigo é ser um guia simples e acessível para atender a grande maioria das situações, tanto para os contribuidores quanto para os utilizadores de software livre.

## Aviso
Não tenho formação jurídica, necessária para avaliar com a devida profundidade decorrências legais da utilização ou da violação das licenças aqui citadas. Nestes casos, sugiro a consulta à um especialista.

## Referências

1. https://choosealicense.com/
1. https://pt.wikipedia.org/wiki/Copyleft
