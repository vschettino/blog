---
title: 'Sobre condicionais e booleanos'
date: '00:00 11/10/2017'
taxonomy:
    category:
        - blog
    tag:
        - Evolução de Software
        - Refatoração
---

A legibilidade do código é um dos principais requisitos para a manutenibilidade. Ou seja, quanto mais legível é o código, mais fácil fica de entendê-lo e dar evoluí-lo da maneira correta. As condicionais são as principais estruturas que contribuem para complexidade da leitura do código; Por muitas vezes, elas expressam diretamente a regra de negócios envolvida e acabam representando um esforço cognitivo adicional durante a leitura do código.

## Valores booleanos em condicionais

Uma estrutura muito comum de se encontrar nas codebases é:

```
function isActive(){
    if(this->active == true)
      return true;
    else
      return false;
}
```

A leitura desta estrutura fica complexa, principalmente em exemplos mais realistas. Se o valor testado `this->active` já representa um valor verdadeiro ou falso, porque a comparação com o `true`? Uma maneira mais direta de escrever um código com a mesma saída seria:

```
function isActive(){
    if(this->active)
      return true;
    else
      return false;
}

```

Mais limpo e mais direto. Neste caso, podemos escrever um código ainda mais direto e fácil de entender:

```
function isActive(){
      return this->active;
}
```

A diferença é ainda mais gritante em casos complexos. Imaginemos que para descobrir se o objeto está ativo é necessário uma comparação mais complexa. A escrita mais direta deixa tudo mais claro:

```
function isActive(){
      return (this->expire_date > now());
}
```

## Nome de variáveis booleanas

Já sabemos que nomear coisas está entre as [atividades mais difíceis da computação](https://martinfowler.com/bliki/TwoHardThings.html). Contudo, nomes claros e, principalmente, padronizados, de componentes no código (Classes, Variáveis, Métodos) é uma caracterísitca fundamental para legibilidade. No caso do booleano, o nome pode ajudar ainda mais nas comparações diretas. Por exemplo, nomes de métodos e variáveis devem seguir um padrão que identifica se o valor que a estrutura retorna ou aponta é booleano. O prefixo "is" (`isActive()`, `isPriority`) é um bom identificador, pois deixa a condição ainda mais clara:

```
if(this->isActive())
  #código para permitir a alteração  
```

##  Referências

1. https://martinfowler.com/bliki/TwoHardThings.html
1. https://stackoverflow.com/questions/1227998/naming-conventions-what-to-name-a-boolean-variable
1. https://stackoverflow.com/questions/1370840/naming-conventions-what-to-name-a-method-that-returns-a-boolean
