---
title: 'Links da Semana #1'
date: '00:00 10/18/2017'
taxonomy:
    category:
        - blog
    tag:
        - Links da Semana
        - Ecossistemas
---

1. [Uma séria vulnerabilidade no protocolo WPA2](https://www.krackattacks.com/) foi descoberta esta semana, pelo pesquisador [Mathy Vanhoef](https://twitter.com/vanhoefm). Ela foi batizada de KRAK (Key Reinstallation Attacks). Explorando a troca de chaves que acontece no início da comunicação (_handshake_), o invasor poderia forjar chaves de criptografia e comprometer comunicações que não estivesse trafegando com outras medidas de segurança (por exemplo, HTTPS). O impacto se dá principalmente porque os Roteadores raramente são atualizados por usuários leigos, então principalmente em redes públicas é bom ter cuidado redobrado. Algumas [distribuições U/Linux já anunciaram patches](https://sempreupdate.com.br/amp/2017/10/ubuntu-debian-fedora-e-outras-distribuicoes-gnulinux-corrigem-bug-wpa2-krack.html) para resolver o problema.

1. Já ficou dias buscando sequencialmente qual commit introduziu um defeito na aplicação? O git pode te ajudar com o comando pouco conhecido [bisect](https://git-scm.com/docs/git-bisect). Resumidamente, ele te ajuda a buscar o commit problemático buscando dentro de um intervalo definido (que é configuração de qual versão está definitivamente certa e qual está definitivamente errada). A partir daí, é feita uma [busca binária](https://pt.wikipedia.org/wiki/Pesquisa_bin%C3%A1ria), que é mais eficiente do que  listar todos os commits e ir testando um por um.
1. A Alphabet, dona da Google, [anunciou nesta terça que irá lançar um "programa de proteção avançada" no Gmail](https://www.cnbc.com/2017/10/17/google-gmail-advanced-security-for-officials-and-journalists.html). Usuários neste programa receberiam funcionalidades de segurança avançada, como o fortalecimento do processo de recuperação de senha e atualizações de segurança mais rapidamente. Especula-se que tal medida venha como resposta aos ataques durante as eleições americanas, já que o programa é voltado para jornalistas e autoridades. Coincidência ou não, o anúncio veio no mesmo dia que o [Presidente Michel Temer admitiu usar um Gmail para assuntos oficiais desde a Vice Presidência da República](https://oglobo.globo.com/brasil/camara-torna-publico-celular-de-temer-estou-falando-com-presidente-esta-perfeitamente-21953572), sob a justificativa que o "sistema do planalto nem sempre funciona bem". Me pergunto porque tais funcionalidades avançadas não são disponíveis para todos?
1. O [Google Calendar enfim irá cara nova na web](https://googlediscovery.com/2017/10/17/google-calendar-ganha-nova-interface-com-material-design/amp/). Seguindo o padrão de outros produtos Google e a própria agenda nos dispositivos móveis, será lançada a interface com [Material Design](https://material.io/guidelines/). Ainda não há data precisa para implantação do novo _Look and Feel_, mas tudo indica que será um processo incremental.
1. As Máquinas Pensam? A pergunta é polêmica atualmente, imagine em 1950? Muita gente conheceu [Alan Turing](https://pt.wikipedia.org/wiki/Alan_Turing) pelo filme "Jogo da Imitação", de 2014. Para entender um pouco mais das ideias do precursor da computação como conhecemos hoje, recomendo a leitura de seu [artigo mais famoso, de 1950](http://www.loebner.net/Prizef/TuringArticle.html). Nele, Turing lança suas principais teorias sobre as máquinas e sua capacidade de "pensar", onde é possível ver paralelos com os desafios da inteligência computacional moderna.  
1. Depois de uma longa espera, o [PostgreSQL 10.0 foi lançado](https://www.postgresql.org/about/news/1786/). A versão conta com uma série de novidades robustas, voltadas para os desafios modernos em tratamento de dados. Replicação Lógica (nativa), melhorias no particionamento e no paralelismo e avanços significativos na replicação síncrona são apenas algumas das novidades.
1. O PostgreSQL 10.0 trouxe [diversas mudanças quando o assunto é monitoramento](https://pganalyze.com/blog/whats-new-in-postgres-10-monitoring-improvements.html). Permissões especiais de monitoramento, reestruturação dos nomes (xlog enfim vai se chamar wal) e extensão das informações na ``pg_stat_activity`` são algumas das novidades.
1. Os engenheiros do Gitlab explicaram como [trabalharam com a escalabilidade do PostgreSQL](https://about.gitlab.com/2017/10/02/scaling-the-gitlab-database/) embutido da ferramenta, tanto para a plicação em nuvem quanto a self-hosted.
1. Adam Culp é mais um tentando te [convencer a migrar para o PHP7](http://www.geekyboy.com/archives/1376). Acho que nem preciso acrescentar mais nada depois de tantos argumentos e pessoas dizendo que isso deve ser feito para ontem.
1. Herberto Graça fala sobre os benefícios da [arquitetura baseada em eventos](https://herbertograca.com/2017/10/05/event-driven-architecture/), principalmente do aspecto de separação de responsabilidades. É uma visão atual sobre a relação entre componentes e o ecossistema que eles estão inseridos. Vale a pena conferir.
1. Cientistas mostraram que é possível projetar uma AI muito eficiente com razoável baixo custo computacional, sendo executada dentro de um celular. Com a proposta de [Amanda Ramcha](http://amramcharan.com/) e seus coautores, é possível [identificar com quase 100% de acurácia se uma planta está doente](https://www.wired.com/story/plant-ai), a partir de uma amostra (bem preparada) de apenas 2756 imagens.
1. Paras Chopra faz uma [introdução de altíssimo nível aos principais conceitos de Machine Learning](https://growth.wingify.com/what-you-need-to-know-before-you-board-the-machine-learning-train-a81c513098fe), sem assustar ninguém e voltado para gerentes e líderes. O artigo faz contraponto à hype sobre a tecnologia, dando um passo para trás e fazendo uma análise sóbria do mercado.  