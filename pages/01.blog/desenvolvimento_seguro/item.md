---
title: 'Diretrizes para desenvolvimento de software seguro'
date: '00:00 07/27/2019'
taxonomy:
    category:
        - blog
    tag:
        - segurança
        - monitoramento
---

O desenvolvimento de software moderno envolve o domínio de diferentes linguagens, frameworks, bibliotecas e abordagens. Com estas responsabilidades, outra preocupação inerente ganha ainda mais destaque: a segurança das aplicações, desde sua concepção até o comportamento em ambiente de produção. O objetivo deste artigo é trazer os principais aspectos dos desafios de segurança do ponto de vista dos desenvolvedores de software.

===

## De quem é a responsabilidade?

Neste aspecto não adianta muito discutir o que é deveria ser, mas sim destacar o que é: o desenvolvedor é o principal responsável pela segurança das aplicações.  Não é só pela falta de profissionais especializados (não só em segurança, mas por exemplo em banco de dados ou infra) na maior parte das equipes de sofrware, mas simplesmente porque o código desenvolvido é a principal portadora de vulnerabilidades.

Quando se utiliza projetos open source maduros e bem estabelecidos em banco de dados, sistema operacional, criptografia e etc, raramente a falha de segurança vem de dentro desses projetos. Normalmente o que acontece:

1. O desenvolvedor não utilizou corretamente a ferramenta.
1. O projeto teve uma vulnerabilidade divulgada, prontamente disponibilizou um patch...mas o processo de desenvolvimento/deploy não permitiu a rápida atualização.

Nos dois casos, o principal responsável técnico é a equipe de desenvolvimento. E no caso do emprego de projetos abandonados e cheios de vulnerabilidades? O desenvolvedor deveria ter tomado os devidos cuidados e realizado as análises necessárias para evitar a incorporação de uma dependência tão perigosa.

Para entender este ponto de vista, é só visitar o [Have I Benn Pwned?](https://haveibeenpwned.com/), site que reune os principais vazamentos de e-mail e senha. São comuns os casos onde por exemplo mais de 700 milhões de emails (muitos com nomes, telefones, IPs e gênero) foram vazados quando os desenvolvedores esquecerem uma instância do MongoDB pública e sem senha.  

## OWASP

A boa notícia é que os desenvolvedores não estão sozinhos nesta tarefa. O Open Web Aplication Security Project (OWASP) é uma organização independente sem fins lucrativos que direciona esforços em favor da segurança e padronização das aplicações voltadas para internet. O grupo organiza eventos, palestras, artigos e listas com recomendações para os desenvoldores da área. Entre as mais interessantes está o [Top Ten Security Risks](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project) qeu reune as ameaças mais comuns em sistemas para internet. Pelo menos 90% das falhas apontadas são responsabilidade direta dos desenvolvedores. O [documento](https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf) reune ainda exemplos, histórico, os impactos em diferentes ótica e principais prevenções para cada tipo de brecha. Além da lista análoga de [principais controles preventivos](https://www.owasp.org/images/b/bc/OWASP_Top_10_Proactive_Controls_V3.pdf) o grupo também organiza a [lista de vulnerabilidades mobile](https://www.owasp.org/index.php/OWASP_Mobile_Security_Project#Top_Ten_Mobile_Risks). São mantidos projetos de bibliotecas e ferramentas voltadas para testes de segurança/penetração e para aplicação das medidas de controles difundidas.

Ṕara mais detalhes sobre estas listas e exemplos práticos, disponibilizo aqui os slides de um curso que ministrei sobre o tema recentemente:
- https://docs.google.com/presentation/d/1Jv7Tq2xlvDJhY5XlJf6nVTYtmnY2OENVu1lYFc7Ils4/edit?usp=sharing


## Conclusão
Apesar do peso nas costas dos desenvolvedores, segurança é e sempre foi um requisito dos sistemas de informação, e suas políticas, recursos e funcionalidades devem estar alinhadas e serem suportadas pelos stakeholders. Ou seja, é necessário que as pessoas de negócio envolvidas ajudem a definir os níveis de segurança necessários de acordo com o contexto do produto, e saibam dos impactos que isso vai causar no tempo e no custo do projeto.

Práticas de desenvolvimento seguro são acessíveis pelos produtores do software. A chave é definir tais práticas como obrigatórias nos projetos e constantemente monitorar, revisar e testar se tais conceitos estão sendo observados.
