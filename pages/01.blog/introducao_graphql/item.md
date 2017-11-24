---
title: 'Introdução ao GraphQL'
date: '00:00 11/24/2017'
taxonomy:
    category:
        - blog
    tag:
        - API
        - Grafos
---

 Web APIs são interfaces importantes na interoperabilidade de serviços na internet pois permitem a comunicação homogênica entre diversos componentes, trocando funcionalidades e informações. Mesmo com a ascenção do padrão REST sobre outras tecnologias de comunicação obsoletas, algumas necessidades atuais de operação clamam, por soluções mais escaláveis e flexíveis. O modelo GraphQL surge com tal objetivo, em contraponto ao padrão *de facto* que utilizamos hoje. Neste artigo proponho uma introdução à esta nova tecnologia, discutindo os principais conceitos e comparando como algumas funcionalidades são alcançadas entre o REST e o seu mais novo promissor concorrente.

===

## Introdução

Interoperabilidade e composição de serviços são palavras-chave no universo das aplicações modernas. Organizações solitárias não conseguem mais suprir as necessidades dos usuários por sistemas cada vez mais complexos, e por isso aliam-se à recursos externos (outras empresas, pessoas e ferramentas) para alcançar a manutenção e a expansão de seus mercados. As APIs são o principal canal por onde estas integrações são feitas. É através delas que organizações compartilham dados e funcionalidades, criando nichos onde todos os envolvidos tem a ganhar: Cada um fica especialista no que faz de melhor, e o utilizador da plataforma ganha tendo um serviço ou produto oriundo de componentes especializados e com funcionalidades que antes não seriam possíveis.

Depois de padrões obsoletos, como [RPC](https://pt.wikipedia.org/wiki/Chamada_de_procedimento_remoto) e o [SOAP](https://pt.wikipedia.org/wiki/SOAP), o REST ganhou espaço no final da década passada. O modelo utiliza padrões HTTP e Web definidos décadas antes (verbos, status codes, URIs) mas que ficaram esquecidas por um bom tempo. Entre as principais vantagens deste modelo estavam a descoberta automática de serviços, o caching e a interoperabilidade automática.

A grande vantagem de uma API está em compor serviços estritamente dado sua interface externa, sem nenhum tipo de preocupação sobre implementação, padrões e conhecimento. Ou seja, o comprometimento é sobre o comportamento externo e observável do componente, e nunca sobre qual linguagem foi utilizada ou como o processamento é feito. Esta característica permite, dada a necessidade de uma funcionalidade, escolher entre diversos fornecedores que a disponibilizam, sem se preocupar com nada além do que é retornado.

## E o GraphQL?

O [GraphQL](http://graphql.org/) é uma **especificação** de API baseada em grafos. É importante ressaltar que não é uma implementação em linguagem específica, mas sim um modo padronizado de disponibilizar seus serviços. Foi criado pelo Facebook e disponibilizado como um padrão aberto em [2015](http://facebook.github.io/graphql/October2016/), sendo adotado por, além de seu criador, projetos como o [Github](https://developer.github.com/v4/guides/intro-to-graphql/). Existem diversas [implementações do GraphQL](http://graphql.org/code/) disponíveis, em diversas linguagens.


Desde a abertura da especificação, a *hype* sobre o projeto tem sido bem grande:

![https://trends.google.com.br/trends/explore?date=today%205-y&q=graphql](/images/trend_graphql.png)

Principalmente na comunidade JavaScript e Node.js, além de outros projetos do Facebook, como o React:

![https://trends.google.com.br/trends/explore?date=today%205-y&q=graphql](/images/related_queries_graphql.png)

Logicamente, é importante colocar este comportamento em perspectiva. Por exemplo, as coisas parecem menos significativas quando comparamos com outras palavras-chave:

<script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/1225_RC02/embed_loader.js"></script>
<script type="text/javascript">
  trends.embed.renderExploreWidget("TIMESERIES", {"comparisonItem":[{"keyword":"graphql","geo":"","time":"2004-01-01 2017-11-24"},{"keyword":"rest","geo":"","time":"2004-01-01 2017-11-24"},{"keyword":"rpc","geo":"","time":"2004-01-01 2017-11-24"},{"keyword":"SOAP","geo":"","time":"2004-01-01 2017-11-24"}],"category":0,"property":""}, {"exploreQuery":"date=2004-01-01 2017-11-24,2004-01-01 2017-11-24,2004-01-01 2017-11-24,2004-01-01 2017-11-24&q=graphql,rest,rpc,SOAP","guestPath":"https://trends.google.com.br:443/trends/embed/"});
</script>


Por isso, apesar de haver um tendência no crescimento do REST e do GraphQL nos últimos anos em detrimento de tecnologias obsoletas, ainda estamos vivendo o início da ascenção do segundo. Ou seja, precisamos de observar mais a adesão da comunidade sobre a tecnologia antes de tecer previsões.

Do ponto de vista da comunidade, os números também são promissores. Por exemplo, no projeto [GraphQL.js](https://github.com/graphql/graphql-js), implementação-refência do modelo em JavaScript, já são mais de 100 contribuidores, 8.5k estrelas e 700 forks. 

## Primeiros passos: Grafos

O primeiro passo para decidir de o GraphQL é para você ou não é entender se o seu domínio pode ser melhor modelado através de um [Grafo](https://pt.wikipedia.org/wiki/Teoria_dos_grafos). Ou seja, tente imaginar seus clientes utilizando seus dados em função de nós (ou agentes) se comunicando através de inúmeras relações, onde o recurso em si é tão importante quanto a relação entre eles. Porque este é o modelo no qual as coisas serão retornadas para as aplicações que consumirão seus serviços.

## Consultas GraphQL?

O básico de toda API é fornecer meios de recuperar informações. No REST, estamos acostumados a acessar diversos endpoints para formar a massa de dados que necessitamos, agregando os recursos do lado do cliente. Esse já é um conceito bem diferente no GraphQL: Você tem um único endpoint e a sua query descreve exatamente quais informações você precisa. Ou seja, você pede todo o modelo de dados que deseja de uma vez só, com os relacionamentos representados na forma de um grafo. Um exemplo básico de query:

```
{
  hero {
    name
    friends {
      name
    }
  }
}
```
Estamos explicitamente dizendo o que queremos receber (*hero*) e quais atributos dele precisamos. Inclusive um desses atributos é uma lista de outros recursos (*friends*), que são disponibilizados sem necessidade de outra chamada. Uma possível resposta seria:
```
{
  "data": {
    "hero": {
      "name": "R2-D2",
      "friends": [
        {
          "name": "Luke Skywalker"
        },
        {
          "name": "Han Solo"
        },
        {
          "name": "Leia Organa"
        }
      ]
    }
  }
}
```

Existem várias [funcionalidades mais completas de consulta](http://graphql.org/learn/queries/), que se assemelham mais com problemas da vida real. Você pode [testá-las na API do Github](https://developer.github.com/v4/explorer/) bem facilmente, e eu não entrarei nestes detalhes aqui porque saem do escopo introdutório do trabalho.

## OK...e cadê o meu POST/PUT/DELETE?

Todas estas operações que alteram dados devem ser feitas através de [*mutations*](http://graphql.org/learn/queries/#mutations). Esta estrutura não é tão bem definida como estamos acostumados em APIs RESTful, mas o básico é bem tranquilo de entender. Passando as [variáveis](http://graphql.org/learn/queries/#variables) com os dados que você deseja criar, sua requisição poderia ficar assim:

```
mutation CreateReviewForEpisode($ep: Episode!, $review: ReviewInput!) {
  createReview(episode: $ep, review: $review) {
    stars
    commentary
  }
}

-- variáveis --
{
  "ep": "JEDI",
  "review": {
    "stars": 5,
    "commentary": "This is a great movie!"
  }
}
```

Por padrão, a API deve te responder com o modelo persistido após sua operação:

```
{
  "data": {
    "createReview": {
      "stars": 5,
      "commentary": "This is a great movie!"
    }
  }
}
```

## Tratando APIs legadas

Já está querendo migrar para o modelo GraphQL? Então é bom começar explicando para o seu chefe o que você vai fazer com aquela API RESTful novinha que vocês passaram meses desenvolvendo, dizendo para ele que estavam substituindo uma tecnologia obsoleta...

O projeto [Apollo](https://www.apollographql.com/) está aqui para te ajudar. Na verdade este é um conjunto de projetos, sob a bandeira de fornecer a interface GraphQL consumindo os dados de uma aplicação legada. Ou seja, é como se fosse um mapeamento entre uma ou várias APIs legadas e sua aplicação. Existem [vários conectores](https://github.com/apollographql) em tecnologias diferentes para fazer esta ponte.

## Preciso abandonar o HTTP?

Apesar de não ser obrigatório pela especificação, é difícil imaginar alguém não utilizar HTTP no contexto web. Então você ainda deve conviver com os elementos básicos do protocolo, como os status codes e os verbos. Como estas estruturas se inserem no GraphQL?

Primeiro, sobre os verbos: [Uma prática comum](https://developer.github.com/v4/guides/intro-to-graphql/#discovering-the-graphql-api) é sempre utilizar o POST para queries e mutations, e deixar o GET para consultas de [introspecção](http://graphql.org/learn/introspection/).

Sobre os códigos de erro, eles basicamente são ignorados quando o assunto é GraphQL. Ou seja, se a resposta contiver um erro ou não, o padrão é retornar sempre o código `200`. A identificação do problema deve ser feita dentro do *body* da resposta: Se houver o atributo `errors` na raiz do JSON de retorno, você já sabe que ocorreu algum problema.

Esta parte me deixou particularmente preocupado, principalmente do ponto de vista da compatibilidade legada com aplicações REST. Primeiro, você não pode contar com os diferentes verbos para garantir se a requisição é [idempotente ou segura](http://restcookbook.com/HTTP%20Methods/idempotency/); Para isso é necessário entendimento sobre a API. Além disso, você precisa analisar o body da resposta para saber se ocorreu algum problema. E pior: qual foi o problema? Novamente, você precisa de entender como está estruturada a interface. Com o REST, olhar para um código 404 é significativo em todas as APIs, deixando o entendimento mais fácil e o comportamento minimamente previsível.

## Autenticação/Autorização

Um conceito interessante proposto é a [separação clara da camada de regra de negócios](http://graphql.org/learn/thinking-in-graphs/#business-logic-layer) e as interfaces de comunicação com os clientes. Ou seja, eles já propõem um padrão que permite a coexistência de APIs, cada uma em um modelo:  


![](http://graphql.org/img/diagrams/business_layer.png)

Assim, a preocupação de autenticação/autorização não é contemplada pela especificação da tecnologia. Podem ser utilizados tokens, OAuth2 e outros protocolos da [mesma maneira que em outras APIs](https://developer.github.com/v4/guides/forming-calls/#authenticating-with-graphql).

## Paginação

Outra funcionalidade tradicional das APIs RESTful, a paginação permite vantagens nas duas pontas: Diminui a utilização temerária dos serviços (overhead desnecessário do servidor) e deixa o cliente escolher quais e quantos registros são necessários no momento.

O primeiro para diferenciar valores únicos de listas de objetos é através do plural. Ao ler `address` você já sabe que aquele campo retorna um único valor, diferente do campo `friends`. Para escolher quais são os limites superiores e inferiores, você pode passar parâmetros específicos nas queries. Por exemplo, para trazer os 10 primeiros amigos:

```
{
  hero {
    name
    friends(first:10) {
      name
    }
  }
}
```

Se adicionar o parâmetro `offset:10` na query acima, você  estará pegando a segunda página de amigos. Mais detalhes sobre a utilização destes parâmetros e da paginação em si podem ser encontrados [aqui](http://graphql.org/learn/pagination/).

## Caching

Uma revolução pouco explorada do HTTP é o sistema de caching nativo e fácil de entender. O [REST sabe aproveitar esse modelo como ninguém](http://restcookbook.com/Basics/caching/), através do emprego correto dos códigos de status e principalmente dos headers `If-modified-since`.

Já no GraphQL, não há solução tão direta assim. Alguns sistemas podem ser feitos internamente, através de estruturas auxiliares e banco de dados em memória, mas estas possibilidades não são pervasivas para o consumidor. Para esta abordagem, entre as [propostas mais aceitas](http://graphql.org/learn/caching/), está a utilização de IDs únicos para identificar os recursos. Assim os clientes podem fazer seu próprio esquema de caching, sabendo quando recursos surgem, são modificados ou somem.


## Descoberta de funcionalidades

O principal meio de descoberta de funcionalidades em uma API REST é o [HATEOAS](http://restcookbook.com/Basics/hateoas/). Através desse padrão, o recurso vem acompanhado de uma série de links de dados e funçoẽs relacionadasm, permitindo que o cliente automaticamente forneça ao usuário possíveis próximos passos. Por exemplo, depois de criar uma nova conta no banco, a API pode retornar, junto com os dados da nova conta, links para as operações de empréstimo e de depósito. Mais do que isso, a opção de saque não deve aparecer pois a conta acabou de ser criada e está vazia.

O GraphQL oferece um conjunto de operações de [instrospecção](http://graphql.org/learn/introspection/) para ajuadar na definição e explicação do [schema](http://graphql.org/learn/schema/) disponível. É justamente neste mecanismo que ferramentas como o [GraphiQL](https://github.com/graphql/graphiql) se baseiam. [É possível desenvolver](http://graphql.org/swapi-graphql/) um autocomplete que dá dicas sobre  quais tipos e campos podem ser utilizados em cada situação.

## Versionamento

Um problema secular no REST é o versionamento. Qualquer mudança na estrutura do retorno é de responsabilidade do servidor, e o cliente não tem como se adaptar a isso; Ou seja, é quebra de compatibilidade na certa. Por isso se convencionou a manter diversas versões da API, geralmente delimitadas por `api.example.com/v1` e `api.example.com/v2`. A governança desse meio é complicada, principalmente quando o assunto é documentação. Da mesma forma, a complexidade do desenvolvimento aumenta muito, elevando o risco de código duplicado e de baixa qualidade.

Com o GraphQL, isso não é necessário. A estrutura é definida pelo cliente e novos campos são opcionais, o que anula praticamente qualquer chance de quebra de compatibilidade. Nos casos de mudança no formato ou nos nomes dos campos, é fácil manter a forma mais nova como opcional por muito tempo, enquanto o meio antigo continua sendo o padrão e não gera problemas para aplicações mais antigas.



## Conclusão

Em meio à necessidade cade vez maior de interoperabilidade entre as aplicações, as APIs tomam papel central na discussão. Os divrsos modelos existentes tem pontos fortes e fracos, que são mais ou menos evidentes dependendo do contexto. Talvez o futuro seja ter camadas de APIs bem separadas tanto da camada de negócios quanto dos clientes. O consumidor então decide qual API é mais interessante para determinada funcionalidade.

Este é um desafio do ponto de vista técnico, pois um design fraco do lado do servidor fatalmente irá levar à duplicação de código e [inconsistência entre as diferentes APIs](http://graphql.org/learn/thinking-in-graphs/#business-logic-layer).

Falando especificamente do GraphQL, a tecnologia ataca aspectos até então descobertos pelo REST, como por exemplo a unificação dos recursos e a flexibilidade do modelo de resposta. Estas não são restrições de implementação, mas sim da própria arquitetura, proposta há mais de 15 anos e que não levava em consideração os requisitos de interoperabilidade que vemos hoje.

Por isso, vale a pena conhecer e acompanhar a evolução do GraphQL. Pelos patrocinadores de peso e crescente adesão pela comunidade, o projeto é um potencial candidato para engenhar o futuro das aplicações web.



## Referências

1. http://graphql.org/learn/
1. http://graphql.org/code/
1. http://graphql.org/learn/queries/
1. http://graphql.org/learn/schema/
1. http://graphql.org/learn/best-practices/
1. http://graphql.org/learn/thinking-in-graphs/
1. http://graphql.org/learn/serving-over-http/
1. http://graphql.org/learn/authorization/
1. http://graphql.org/learn/pagination/
1. http://graphql.org/learn/caching/
1. https://github.com/graphql/graphiql
1. https://developer.github.com/v4/guides/intro-to-graphql/
1. https://www.apollographql.com/
