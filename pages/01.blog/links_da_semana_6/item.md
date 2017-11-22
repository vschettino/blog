---
title: 'Links da Semana #6'
date: '00:00 11/22/2017'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
---

1. Para quem está buscando como migrar para o PostgreSQL 10 sem ter que parar a aplicação durante muito tempo, Rodrigo Rosas fornece o relato de como ele fez a [migração com downtime mínimo, usando o pglogical](https://rosenfeld.herokuapp.com/en/articles/infrastructure/2017-11-10-upgrading-postgresql-from-9-6-to-10-with-minimal-downtime-using-pglogical).  

1. O particionamento de tabelas é uma das principais novidades do PostgreSQL 10, sendo muito útil quando o assunto é escalabilidade. O pessoal do TimeScale explica como o [particionamento funciona, suas limitações e futuras melhorias](https://blog.timescale.com/scaling-partitioning-data-postgresql-10-explained-cd48a712a9a1) (sem muita propaganda desta vez).

1. Funções agregadas fazem muita coisa, mas são limitadas quando você precisa da agregação para filtrar ou ordenar os próprios registros da tabela. Você pode utilizar `JOINS ` e subqueries, ou partir para a [utilização de funções de janela](http://mjk.space/advanced-sql-window-functions/) (window).

1. `INSERTS` são operações razoavelmente lentas quando o assunto é inserção em massa. A utilização das `TRANSACTIONS` únicas e das verificações de integridade deixam o processo custoso, e podem ser substituídas por [outros métodos de inserção em lotes](https://www.citusdata.com/blog/2017/11/08/faster-bulk-loading-in-postgresql-with-copy/), como o `COPY`.

1. Stefan Koopmanschap discute um hábito interessante: [não utilizar o -m nos commits git](https://leftontheweb.com/blog/2017/11/10/One-year-without-m/), evitando mensagens muito curtas. Apesar de tirar um pouco da agilidade do processo de `commit`, a prática pode ter efeitos interessantes na qualidade do histórico, como o autor e outros discutem nos comentários.

1. A utilização de versões do PHP recentes é importante para a segurança e a evolução da internet como um todo, não só para a comunidade PHP. Isso porque a linguagem está em 80% dos sites, então influencia diretamente a saúde de todo o ecossistema. Por isso é importante [acompanhar a disseminação das novas versões e os requisitos mínimos das bibliotecas](https://seld.be/notes/php-versions-stats-2017-2-edition). *(nota: como o estudo é feito utilizando dados do packagist, ele não é representativo do ecossistema como um todo, já que existem milhares de sites que não o utilizam. O [W3Techs](https://w3techs.com/technologies/details/pl-php/all/all) apresenta números mais abrangentes)*   

1. Se você já sabe porque não deve rodar o Composer como root, ótimo! Snipe ensina como [desfazer o lambança e começar a utilizar um usuário não privilegiado](https://snipe.net/2017/11/15/so-you-ran-composer-as-root/) para os comandos de instalação/atualização.  

1. Andrej Karpathy levanta uma excelente discussão sobre o [futuro da integiência artificial](https://medium.com/@karpathy/software-2-0-a64152b37c35), principalmente em detrimento do desenvolvimento tradicional de software: Ele cunha o termo Software 2.0, que irá substituir diversas funcionalidades hoje sanadas com soluções tradicionais. Vantagens como tempo constante de execução e descoberta autônoma de padrões podem fazer que os programadores de hoje virem os professores de máquinas de amanhã, complementa seu colega [Pete Warden](https://petewarden.com/2017/11/13/deep-learning-is-eating-software/).  

1. Como o Twitter decidiu aumentar o número de caracteres de 140 para 280? Pode ter parecido arbitrário, mas na verdade eles [observaram a distribuição normal da quantidade de caracteres dos tweets](https://blog.twitter.com/engineering/en_us/topics/insights/2017/Our-Discovery-of-Cramming.html) e perceberam que existia um corte abrupto próximo dos 140 caracteres, enquanto a curva natural deveria se alongar até 274 caracteres. Nessa onda, Jake VanderPlas levanta discussão parecida [no número caracteres por linha de programas em Python](http://jakevdp.github.io/blog/2017/11/09/exploring-line-lengths-in-python-packages/).  
