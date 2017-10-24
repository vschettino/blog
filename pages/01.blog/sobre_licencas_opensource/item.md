---
title: 'Sobre as licenças OpenSource - O Básico que você precisa saber'
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

Este cenário não só pode ocorrer, mas também é relativamente comum. Por padrão todos os direitos de exploração são reservados ao autor e não há liberdade explícita de uso, distribuição ou modificação, mesmo que o código esteja disponível (por exemplo no GitHub).

Caso o autor tenha disponibilizado seu trabalho em um ambiente público, é possível que ele tenha esquecido da licença. Então vale a pena entrar em contato com ele para esclarecer melhor os termos de uso (ou não) daquele código fonte.

## GPLv3: a mais restritiva
A [General Public License v3](https://www.gnu.org/licenses/gpl-3.0.txt) é uma licença copyleft, que tem como objetivo de permitir a plena utilização, difusão e modificação do código fonte mantendo claramente a referência e os créditos ao autor original. Adicionalmente, a GPLv3 obriga que todo o código produzido através da utilização do código original deve ser licenciado sob os mesmos termos, que incluem a distribuição universal do código fonte, documentação e as mesmas liberdades de uso.

Quando o objetivo é fazer um componente completamente reutilizável e livre, garantindo que qualquer melhoria nele vai continuar sendo livre, esta é uma boa licença para se escolher.

**Você só deve utilizar um componente GPLv3 em um projeto se quiser que ele também seja GPLv3**, pois o trecho sob esta licença "contamina" todo o código fonte. Existe a [Lesser General Public License (LGPLv3)](https://www.gnu.org/licenses/lgpl-3.0.txt), que limita a "contaminação" a modificações diretas do código original. Ou seja, se ele é utilizado na íntegra, acessado como uma "biblioteca" ou "serviço", através de uma interface provisionada pelo trabalho original, o resto do código pode ser licenciado sob outras regras.



## Aviso
Não tenho formação jurídica, necessária para avaliar com a devida profundidade decorrências legais da utilização ou da violação das licenças aqui citadas. Nestes casos, sugiro a consulta a um especialista.

## Referências

1. https://choosealicense.com/
1. https://pt.wikipedia.org/wiki/Copyleft
