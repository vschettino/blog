---
title: 'Porque Grav? (e não WordPress)'
date: '00:00 10/28/2017'
taxonomy:
    category:
        - blog
    tag:
        - WordPress
        - Ecossistemas
        - Grav
---

Para quase todo site que envolva publicação de conteúdo, o [WordPress](http://wordpress.org/) é a primeira opção. Desenvolvedores o tem em alta estima por diversos motivos, como a quantidade de temas e plugins disponíveis, fácil instalação e familiaridade tanto com o ecossistema quanto dos usuários com a interface. Contudo, já apresentei [desafios ainda não resolvidos na comunidade WordPress](http://vschettino.com.br/blog/analise_ecossistema_wordpress) que devem ser levados em consideração na hora da escolha. Alternativas como o [Grav](https://getgrav.org/) exploram um nicho específico de gerenciamento de conteúdo, com uma aposta bem clara: simplicidade. Neste artigo vou descrever algumas das principais caraterísiticas do Grav, suas diferenças em relação ao WordPress e, a título de exemplificação, como este blog foi projetado.  

===

## Pontos fortes do Grav
O principal apelo do Grav é desempenho, tanto para instalar quanto para rodar. Isso porque ele não utiliza banco de dados relacional. Todos os conteúdos são arquivos texto (por default utilizando a sintaxe [Markdown](https://pt.wikipedia.org/wiki/Markdown)), interpretados e transformados para HTML. relacionamento de páginas, tags também é feito de maneira dinâmica, mas com auxílio de um poderoso sistema de cache. Ou seja, a única dependência de infraestrutura é o PHP e um webservice de sua preferência.

É possível inclusive instalar e manter o site sem área administrativa, apenas por linha de comando e transferência de arquivos (seja SSH ou FTP). Mesmo assim são diversas [funcionalidades básicas](https://getgrav.org/features) (diria até mais que o WordPress) que não precisam de instalação adicional.

A comunidade é ativa, tanto no [fórum](https://discourse.getgrav.org/) quanto no [GitHub](https://github.com/getgrav/grav). A plataforma ainda é nova, mas já tem quase a mesma quantidade de estrelas e mais contribuidores que o próprio WordPress.

Do ponto de vista técnico, a arquitetura e as decisões de projeto estão anos-luz a frente do WordPress, como se pode imaginar pela idade da plataforma. O gerenciamento de dependências (via [composer](composer.org)) e a modularização dos temas é mais clara e moderna, facilitando a evolução da plataforma. o Grav Package Manager, ou `gpm`, deixa a instalação de novas funcionalidades bem prática:

```
$ bin/gpm install <plugin/theme>
```

## Pontos Fracos do Grav
A principal desvantagem do grav é na quantidade de temas e plugins disponíveis, se comparado com o WordPress. O ecossistema ainda não está evoluído a ponto de contar com diversos produtores de plugins, sejam comerciais ou free, o que torna mais limitado o raio de atuação da ferramenta.

A instalação e manutenção pode requerer conhecimento técnico e limitações de interface, o que afasta um pouco usuários que estejam interessados em publicar conteúdo apenas. Ou seja, na minha visão o nicho do Grav se limita a desenvolvedores, cientistas e entusiastas da computação, que querem sujar um pouco a mão em troca de muito mais simplicidade e desempenho.

## Minha utilização do Grav

O que mais me interessou no Grav foi o [plugin que sincroniza minhas páginas](https://github.com/trilbymedia/grav-plugin-git-sync) com um [repositório no GitHub](https://github.com/vschettino/blog). Ou seja, escrevo os posts na minha máquina utilizando o [Atom](https://atom.io/) e faço o "deploy" deles para o repositório, através do `push`. Pronto! automaticamente (através de um webhook) o site já fica atualizado. Essa sincroniza é bi direcional, ou seja: atualizações feitas diretamente no site (via interface administrativa, opcional) são enviados para o repositório também.

O tema utilizado é um dos mais famosos, o [Antimatter Open Publising](https://github.com/hibbitts-design/grav-theme-antimatter-open-publishing). a instalação do [skeleton](https://getgrav.org/downloads/skeletons) já trouxe alguns plugins práticos, mas este também é opcional.

## Conclusão
O Grav é uma ferramenta que atende necessidades básicas de um blog, principalmente se você utiliza ferramentas de desenvolvimento (linha de comando, Git) com facilidade. Com a simplicidade vem mais desempenho e menos dor de cabeça, o que me atraiu. A plataforma não é um concorrente direto à filosofia do WordPress (qualquer um pode publicar), mas sim uma alternativa que pode ser levada em consideração.
