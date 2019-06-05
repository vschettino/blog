---
title: 'Microframeworks para uma web mais rápida, flexível e integrada'
date: '00:00 01/30/2018'
taxonomy:
    category:
        - blog
    tag:
        - produtividade
        - microframworks
        - php
        - python
---

Em uma web dominada por frameworks complexos e monolíticos, emerge um conceito de projeto que preza agilidade, integração e flexibilidade. No lugar de plataformas que oferecem centenas de funcionalidades, padrões bem definidos e comunidade cativa, os microframeworks apostam em ecossistemas mais amplos, foco em funcionalidades-chave e flexibilidade para integrar projetos de diversos fornecedores para embasar o necessário para o produto em questão -- e nada mais. Neste artigo, apresento as principais diretrizes que norteiam este tipo de framework, faço comparações com modelos tradicionais e dou exemplo de alguns expoentes do segmento.

---


## O que são microframeworks

Estes frameworks abordam a oferta de funcionalidades de maneira diferenciada. Por exemplo, eles oferecem:

* Arquitetura flexível e aberta à extensão
* Propósitos mais específicos e bem delineados
* Facilidade para integração de funcionalidades de outros fornecedores

Diversas linguagens tem representantes no gênero, mas as voltadas para web acabam se destacando, como o PHP e o Python. Por exemplo temos o Flask, o Falcon e o Silex. Eles se restringem à interface REST e a estrutura Request/Responde básica do HTTP, enquanto oferecem interfaces para integração com outros projetos, que adicionam camadas como ORM, OAuth, Segurança, etc.

## Arquitetura

Como estes frameworks permitem a integração com camadas mantidas por equipes diferentes, com abordagens e arquiteturas diferentes? Através de [Middlewares](https://softwareengineering.stackexchange.com/questions/203314/what-is-the-middleware-pattern). Ou seja, as bibliotecas são "empilhadas" em uma pipeline pela qual o `request` e, posteriormente, a `response` passam e podem ser processados e modificados antes e depois do acesso ao código da aplicação. Por exemplo, no [Falcon](http://falcon.readthedocs.io/en/stable/api/middleware.html):

```
class ExampleMiddleware(object):

    def process_request(self, req, resp):
      """ código para pré processar os inputs:
      Aqui podem ser implementadas regras de autorização,
      OAuth, Inicialização de Session (ORM). Modificações
      request e na response serão passadas para o código da aplicação    
      """
    def process_response(self, req, resp, resource, req_succeeded):
        """ código para fechar o processamento da aplicação
        Aqui podem ser implementadas funções de logging, fechamento de sessão, etc

# Insere o middleware na pilha de execução do Falcon
api = falcon.API(ExampleMiddleware())

```

Exemplos semelhantes são feitos com [Hooks](http://falcon.readthedocs.io/en/stable/api/hooks.html) através da estrutura de decorators, ou com os [providers do Silex](http://php-pb.net/2014/05/27/microframeworks/), por exemplo.

## Conclusão

Este é um artigo introdutório sobre o tema, apenas para salientar a diferença dos microframeworks em relação a abordagem tradicional. Através deles, é possível integrar serviços de fornecedores diferentes, escolhendo os que melhor se encaixam no projeto que você está desenvolvendo atualmente.


## Referências

* https://blog.appdynamics.com/engineering/php-microframework-vs-full-stack-framework/
* https://stackoverflow.com/questions/7560602/are-microframeworks-intended-for-large-code-bases
* https://www.slant.co/topics/532/~best-python-microframeworks
* http://php-pb.net/2014/05/27/microframeworks/
* https://www.noupe.com/development/javascript-jquery/11-minimal-javascript-frameworks-96416.html
