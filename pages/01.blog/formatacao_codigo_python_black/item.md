---
title: 'Formatação Automática de Código Python com Black'
date: '00:00 07/30/2019'
taxonomy:
    category:
        - blog
    tag:
        - python
        - refatoração
external_links:
    target: _blank
    mode: active
twitterenable: true
twittercardoptions: summary_large_image
twittershareimg: /blog/formatacao_codigo_python_black/pep8.jpg
articleenabled: true
article:
    datePublished: '29-01-2020 15:23'
    dateModified: '29-01-2020 15:23'
    image_url: /blog/formatacao_codigo_python_black/pep8.jpg
    author: 'Vinicius Schettino'
    publisher_logo_url: /blog/blog-header.jpg
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
rich_preview_description: 'Formatação Automática de Código Python com Black '
rich_preview_thumbnail: /user/pages/01.blog/formatacao_codigo_python_black/pep8.jpg
---

A legibilidade do código fonte de uma aplicação é uma das características mais importantes ao pensar em manutenibilidade e evolução. Isso porque [código deve ser feito para pessoas](https://medium.com/@ilyothehorrid/writing-code-for-humans-5b80a89f439c), e não simplesmente para execução por parte das máquinas. Como [80% do tempo de um desenvolvedor é gasto em leitura](https://www.quora.com/As-a-programmer-whats-the-percentage-that-you-spend-time-reading-code-and-writing-code), a facilidade de compreensão de uma *codebase* é extremamente importante para detecção de defeitos e evolução da plataforma. Neste artigo vou apresentar o um formatador automático de código Python chamado black, e o porquê dele se destacar neste meio onde já existem outras ferramentas.

===

## Sobre o *black*

O [black](https://black.readthedocs.io/en/stable/) é um projeto que se descreve como o formatador inflexível da linguagem Python. Isso porque seu "estilo" de formtação é um subconjunto da conhecida [PEP8](https://www.python.org/dev/peps/pep-0008/). Para quem não conhece, esta norma busca aumentar a legibilidade e promover a consistência dos repositórios Python, independente do contexto de aplicação. Ou seja, o código formatado pelo black está geralmente dentro da norma geral da linguagem e por isso atende a padrões mais abrangentes.


## Multiambiente
Uma das principais características do *black* é que ele foi projetado para integrar com as diversas IDEs e ambientes de desenvolvimento. É possível integrar com VSCode, Pycharm, Atom, Vim, Emacs ou simplesmente executar diretamente na linha de comando. Isso facilita o desenvolvimento distribuído e globalizado, sem necessidade forçar um padrão de ambiente aos desenvolvedores. Além disso a execução via CLI facilita a configuração automática em [hooks do git](https://git-scm.com/book/pt-br/v1/Customizando-o-Git-Hooks-do-Git) e no fluxo de integração contínua (CI/CD).

## Regras claras e concisas
O conjunto de regras do black é claro e pequeno, podendo ser [facilmente entendido em linguagem corrente na documentação do projeto](https://black.readthedocs.io/en/stable/the_black_code_style.html). Isso facilita na hora de explicar e discutir as regras. E não são necessárias configurações adicionais, arquivos ou sintaxe específica no código para dizer o que ele deve ou não deve fazer.

## Formatação automática
Existem outras boas ferramentas aderentes à PEP8, mas que fazem mais um papel de linting. Ou seja, atingem um espectro maior de funcionalidades, como verificar imports/variáveis não utilizadas e condicionais duvidosas. Por isso tais ferramentas não fazem as correções automaticamente, já que nestes casos as modifiações podem gerar um comportamento inesperado no código. o Black automaticamente formata o código e pode ser configurado através de atalhos específicos ou no ato de salvar um arquivo.

## Code Review
O code review é uma dos principais ferramentas para detecção precoce de defeitos e pode gerar discussões positivas que levam a melhoria da qualidade de software e disseminação de conhecimento entre os envolvidos e documentação para as próximas gerações. Um dos principais para uma boa revisão é justamente a [capacidade de leitura do código](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/). Assim, é muito mais fácil revisar e fazer comentários relevantes quando o código está mais fácil de ler. Além disso, é menos uma preocupação para o revisor, que pode focar em outros aspectos que os corretores automáticos não atuam.

## Próximos passos
Formatação de código é apenas um dos aspectos da legibilidade e manutenibilidade do código. Outros problemas podem ser detectados com análise estática do código, através dos aplicativos conhecidos como *linters*. Especialmente no processo de revisão de código, este tipo de ferramenta ajuda bastante. O mais famoso em python é o [pylint](https://www.pylint.org/), que integra bem com as principais IDEs. Adicionalmente, a maior parte dos ambientes gráficos possuem linters nativos. Contudo são necessárias configurações e verificações de compatibilidade entre os ambientes. Por isso considero esta uma etapa posterior à adoção de ferramentas que padronizam a formatação do código.

## Conclusão
A busca pela manutenibilidade do repositório é um processo contínuo, que pode ser melhorado gradativamente de acordo com a cultura e os objetivos organizacionais. O black é um formatador de código com características de design que fomentam sua adoção em processos produtivos já complexos, e é mais um passo em direção à padronização e melhoria do código.
