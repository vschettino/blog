---
title: 'Analisando o Ecossistema WordPress'
date: '00:00 10/14/2017'
taxonomy:
    category:
        - blog
    tag:
        - WordPress
        - Ecossistemas
---

Em 2017, o ecossistema WordPress completa 14 anos de existência. A plataforma open source de CMS (_Content Management System_) está presente em [28,8% dos sites](https://wordpress.org/about/stats/) e [26% dos e-commerces](http://www.thewhir.com/web-hosting-news/magento-woocommerce-lead-ecommerce-platform-market-share-report), o que a torna uma tecnologia essencial para o conceito de internet que conhecemos hoje. Tamanha influência e alcance potencializam desafios das esferas técnicas, organizacionais e sociais, que ameaçam a atratividade e a evolução da plataforma. Neste artigo irei apresentar os principais desafios técnicos com os quais o WordPress atualmente encara, e quais caminhos estão sendo trilhados para garantir que a presença deste gigante da internet não seja abalada.  

===

## Sobre o WordPress

A primeira versão estável do WordPress foi lançada em [27 de maio de 2003](https://wordpress.org/news/2003/05/wordpress-now-available/), por [Matt Mullenweg](https://ma.tt/). Desde então foram 34 novas versões, com contribuições do mundo todo. Tanto a hospedagem através do [WordPress.com](https://wordpress.com) quanto as principais decisões e plugins são desenvolvidos pela [Automattic](https://automattic.com/), encabeçada pelo precursor do WordPress.  

O diferencial da ferramenta é a liberdade para criar o conteúdo e publicá-lo da maneira que lhe parecer melhor, sem barreiras financeiras ou de negócio. O core é completamente Open Source, e existem milhares de plugins gratuitos para auxiliar nas tarefas mais básicas. O WordPress depende apenas do PHP e do MySQL, tecnologias amplamente encontradas em planos de hospedagem acessíveis, o que torna a disponibilização do site algo mais simples. Além disso, a proposta é que não seja necessário conhecimento técnico por parte do criador do conteúdo para manunteção da ferramenta; teoricamente, tudo é feito através da interface com poucos cliques, sem necessidade de atenção a questões técnicas como programação, versão dos componentes e segurança.

## Quem se preocupa com o site?

No modelo básico do WordPress, você cria seu conteúdo e disponibiliza na plataforma. Seu provedor de hospedagem fornece a instância com o PHP, MySQL e o servidor web (geralmente Apache ou Ngnix). Agora, quem cuida de questões técnicas relacionadas ao site? Por exemplo, atualizações de segurança, configuração do PHP, otimização do banco de dados? A verdade é que este modelo [cria um abismo que não está sob responsabilidade de ninguém](https://www.rarst.net/wordpress/technical-responsibility/).

Existem hospedagens exclusivas de WordPress, que se propõem a resolver estes problemas; contudo, elas acabam por entrar em [conflito](https://www.crazyegg.com/blog/reasons-to-use-wordpress/) [com os ideais](https://smartblogger.com/wordpress-hosting/) [básicos de liberdade e autonomia do WordPress](http://www.wpbeginner.com/beginners-guide/what-are-the-limitations-of-wordpress-com/), como por exemplo a instalação de qualquer plugin, estilização das páginas e questões de copyright.

Esta característica é a principal inovação do WordPress, mas também cria o cenário para potencialização dos desafios que serão descritos nas próximas seções.

## Versão do PHP e do Wordpress

A plataforma [não tem uma política de suporte com período definido](https://codex.wordpress.org/Supported_Versions) como é possível ver no [PostgreSQL](https://www.postgresql.org/support/versioning/), [MySQL](https://www.mysql.com/support/supportedplatforms/database.html), [PHP](http://php.net/supported-versions.php) e [Ubuntu](https://www.ubuntu.com/info/release-end-of-life), o que já dificulta a dizer se o fato de mais da metade dos sites WordPress (53,9%) não utilizarem a versão mais nova, que já está disponível desde junho, pode ser visto como um problema ou não. A informação (ainda que vaga) é de que:

> Previous major releases from 3.7 onwards may or may not get security updates as serious exploits are discovered.

Nesse caso, os números oficiais mostram que cerca de 5% utilizam uma versão não suportada da plataforma (menor que 3.7)

Ao meu ver, a alta adesão às atualizações do WordPress se devem principalmente:

1. A atualização default automática em patches de segurança.
1. A possibilidade de atualizações automáticas entre _major versions_
1. O alerta (através de uma _popup_) aos usuários com versões desatualizadas, explicando os benefícios da atualização e encorajando à execução imediata do ato.

O problema fica mais claro quando o assunto é PHP. A versão estável da linguagem é a 7.1. lançada no final de 2016. Contudo, apenas 4% dos sites wordpress utilizam a versão mais nova da linguagem. Utilizando a série estável do PHP7, o número sobe modestamente para 17,5%, provavelmente graças à hospedagem WordPress.com e a [recomendação do PHP7 para instalação do WordPress](https://wordpress.org/about/requirements/). A branch 5.6 do PHP, a mais alta versão da série 5, já não é ativamente desenvolvida desde o início do ano. Mesmo ganhando mais um ano de "security fixes only", esta versão só será suportada até o final de 2018. Mesmo assim, 82,5% dos sites WordPress estão utilizando uma versão da série 5 do PHP. Para piorar, **41,7% deles usa uma versão que não recebe nem atualizações de segurança**, pois estão abaixo da versão 5.6. Além dos ganhos em desempenho, web standards e funcionalidades que as versões mais novas do PHP trazem, existem uma [grande quantidade de vulnerabilidades](http://www.cvedetails.com/vulnerability-list.php?vendor_id=74&product_id=128&version_id=106044&page=1&hasexp=0&opdos=0&opec=0&opov=0&opcsrf=0&opgpriv=0&opsqli=0&opxss=0&opdirt=0&opmemc=0&ophttprs=0&opbyp=0&opfileinc=0&opginf=0&cvssscoremin=0&cvssscoremax=0&year=0&month=0&cweid=0&order=1&trc=40&sha=3de0c8236c2794b0d468d567e8879f77cfc28458) que não serão corrigidas.  

O motivo para tamanho descaso com a versão do PHP é que não há um responsável para tratar destas questões. A equipe do WordPress também [não pretende forçar tais atualizações](https://make.wordpress.org/core/2015/09/10/wordpress-and-php7) ou utilizar as mesmas técnicas supracitadas para [estimular a atualização do PHP ](https://wptavern.com/wordpress-to-bump-recommended-php-version-from-5-6-to-7-0-by-the-middle-of-2017).

## Segurança

A presença do WordPress na internet faz com que ele seja um natural alvo de ataques. Contudo, a falta de conhecimento técnico dos responsáveis, da abertura de vulnerabilidades em nome da praticidade e dos componentes desatualizados potencializam a as brechas de segurança. São [inúmeros casos](http://www.cvedetails.com/product/4096/Wordpress-Wordpress.html?vendor_id=2337) de alto impacto, a maioria utilizando algum destes fatores como principal vetor.

## Mercado de Plugins

Com mais de 52 mil plugins ativos apenas na loja oficial, grande parte das funcionalidades do WordPress é disponibilizada através de componentes de terceiros. É possível verificar a popularidade e a UX destes componentes, mas não a [qualidade do código](http://ieeexplore.ieee.org/abstract/document/6406333/) nem a versão do PHP compatível. Novamente, seria necessário um responsável técnico para avaliação deste caracterísitcas, que podem influenciar diretamente no desempenho e segurança do site. Um plugin que não é compatível com o PHP7 iria inviabilizar a atualização de todo o site.


## Qualidade do Código

Um dos principais problemas do WordPress é a arquitetura cliente-servidor clássica, onde o server-side renderiza todas as páginas e envia para o navegador. Não há separação backend/frontend clara, o que dificulta a evolução e manunteção da ferramenta. Existem avanços claros como o [Calypso](https://developer.wordpress.com/calypso/) e a [API RESTful](https://developer.wordpress.org/rest-api/), mas que ainda demorarão para serem padrões _de facto_ na indústria.

Além disso, é impossível não reparar no modelo estruturado e orientado a funções que o WordPress segue. Existem esforços de padronização e qualidade, mas a própria arquitetura da aplicação implementa tem mais de 10 anos, e não segue princípios de orientação a objetos, teste e reúso. Não faltam [razões](https://tommcfarlin.com/technical-qualities-of-wordpress/) para o estado que o core da plataforma esteja no estado atual, principalmente com a filosofia apresentada neste trabalho. Este cenário, seja por qual motivo tenha se construído, dificulta a evolução da plataforma através de contribuições da comunidade, já que não segue padrões da indústria atual.



## Conclusão
Logicamente, o papel do WordPress está sendo feito, uma vez

### Referências


1. https://wordpress.org/about/stats/
1. https://wptavern.com/wordpress-to-bump-recommended-php-version-from-5-6-to-7-0-by-the-middle-of-2017
1. http://php.net/supported-versions.php
1. https://make.wordpress.org/core/2015/09/10/wordpress-and-php7/#comment-27668
1. https://www.rarst.net/wordpress/technical-responsibility/
1. https://wordpress.org/about/
1. https://en.wikipedia.org/wiki/WordPress#History
1. https://wordpress.org/plugins/
1. https://managewp.com/14-surprising-statistics-about-wordpress-usage
1. http://www.cbronline.com/news/cybersecurity/breaches/wordpress-security-weak-spot-lets-hackers-infiltrate-and-vandalise/
1. https://stackoverflow.com/questions/26893790/about-wordpress-theme-architecture-one-index-php-vs-multiple-template-files
1. https://ma.tt/2017/09/on-react-and-wordpress/
1. https://codex.wordpress.org/WordPress_APIs
1. https://premium.wpmudev.org/blog/wordpress-security-exploits/
1. https://developer.wordpress.com/calypso/
1. https://wordpress.org/about/requirements/
1. http://www.cvedetails.com/vulnerability-list.php?vendor_id=74&product_id=128&version_id=106044&page=1&hasexp=0&opdos=0&opec=0&opov=0&opcsrf=0&opgpriv=0&opsqli=0&opxss=0&opdirt=0&opmemc=0&ophttprs=0&opbyp=0&opfileinc=0&opginf=0&cvssscoremin=0&cvssscoremax=0&year=0&month=0&cweid=0&order=1&trc=40&sha=3de0c8236c2794b0d468d567e8879f77cfc28458
1. https://w3techs.com/technologies/overview/content_management/all/
