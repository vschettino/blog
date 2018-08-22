---
title: 'Trabalhando com estimativas que servem pra alguma coisa'
date: '00:00 08/22/2018'
published: true
taxonomy:
    category:
        - blog
    tag:
    - cultura
    - evolução de software
    - gerência de projetos
---

As estimativas de esforço em desenvolvimento de software  geralmente tendem a dois extremos: simplesmente não existem (quando ficar pronto vai estar pronto) ou são feitas por um gerente que simplesmente quer aquele prazo, que não necessariamente é viável. Nenhuma das duas abordagens é interessante para o resultado do projeto. Lógico que o desenvolvedor não gosta de tecer estimativas: ele se sente como se estivesse dando o chicote na mão do feitor. Da mesma forma, o gerente é avaliado de acordo com sua capacidade de cumprir expectativas. Ou seja, ele quer que o prazo (e o escopo) seja cumprido de qualquer forma.

===

## A importância das estimativas

Qual é a utilidade da estimativa? Considerando uma estimativa razoável, ela tem um poder grande sob o resultado do projeto, que é mais uma composição de timing e escopo do que simplesmente um amontoado de features:

- A viabilidade do projeto pode ser analisada de acordo com a estimativa do tamanho dele
- A lucratividade do projeto está relacionada não só ao custo dele, mas em qual momento ele será finalizado
- Não só a prioridade do projeto como um todo está ligada aos fatores a cima, mas também a prioridade de cada feature que será desenvolvida.

Por isso, é raro um stakeholder saber dizer a prioridade de uma funcionalidade sem saber quanto ela custa. Isso acaba gerando uma priorização fora da realidade e insatisfação com o resultado do projeto. Assim, o problema é que além do atraso, a lista de features entregues pode agregar pouco valor ao negócio.

## A ameaça da estimativa forçada

Outro problema sério das estimativas de software é quando o gestor praticamente obriga o desenvolvedor a dar um determinado prazo. Ou seja, ele quer escutar "x horas" e por isso fará de tudo para que o desenvedor diga algo perto disso. É mais comum ainda quando o gestor é (ou era) desenvolvedor e acha que sabe da parte operacional do projeto. Então ele utilizará do seu cargo/experiência para escutar algo próximo daquilo. Nem é preciso dizer que se fosse assim era mais fácil nem perguntar, gastando tempo a toa. Além disso o gestor perde uma excelente oportunidade de escutar uma estimativa sincera.

## Granularizar o escopo

O primeiro passo é **tecer estimativas em tarefas pequenas**. Ou seja, abordagem bottom up. Quando alguém planeja algo usando como unidade mínima semanas, as vezes até mesmo dias, é fácil saber que o planejamento ou é decorativo ou não será cumprido (mesmo efeito). Desenvolvedores precisam de unidades pequenas para tecer previsões a nível de horas. Ou seja:

- Quanto tempo levo para implementar esse método que salva os arquivos na Amazon s3?
- Quanto tempo levo para estudar como fazer a rotina de bakcups?
- Qual o máximo de tempo que levaria para refatorar essa classe?

Por isso planejamentos detalhados feitos de "cima para baixo" no início do projeto estão fadados a morrer. Primeiro porque é inviável saber que aquele método específico precisará ser desenvolvido daqui há 6 meses. Segundo que mesmo que você saiba que será necessário, não sabe a complexidade com tanta antecedência. Haverá testes unitários? Qual o tamanho do arquivo? Até mesmo como estarão as bibliotecas de acesso a amazon?

O maior problema deste passo é encontrar especificações boas o suficiente para permitir tamanho detalhamento. Isso também sigifica que o projeto será planejado em tempo de execução, o que pode assustar clientes e gestores mais conservadores. Por fim, a especificação de projetos menores com escopo mais definido e prioritário ajudam nesse tipo de coisa.

## Planejamento consciente

O segundo passo é utilizar **embasar estimativas em métodos científicos consolidados**. Sim, isso significa que um gráfico de Gantt, um MS Project ou uma planilha não são suficientes para tecer planejamentos realistas.

O experiente Joel Spolsky, fundador do StackOverflow, propõe o que ele chama de [Evidence Based Schedule (EBS)](https://www.joelonsoftware.com/2007/10/26/evidence-based-scheduling/): utilizar estimativas anteriores para dizer quem são os melhores previsores. Ou seja, utiliza as estimativas e os tempos reais que cada desenvolvedor desempenhou historicamente são utilizados para dizer o quanto ele vai acertar no futuro ou não.

Assim se concebe não uma data específica para entrega, mas sim um intervalo de datas com certas probabilidades da entrega realmente acontecer. Assim os gestores podem planejar as entregas com uma margem mais realista, por dois motivos: Dados históricos foram utilizados, aumentando a precisão da previsão; e agora estamos falando de probabilidades, não de uma data forçada.


## Conclusão

Estimativas são a base de um bom planejamento. Planejamentos são bons para gestores, que podem contar com o escopo correto no timing do mercado e para desenvolvedores, que podem contar com o tempo correto para desenvolver software de qualidade e dentro do devido processo. Contudo, os problemas que rodeiam esta tarefa são muitos e acabam levando a planejamentos decorativos, que todos sabem que não serão cumpridos. A abordagem de estimar o esforço de pequenas atividades e utilizar métodos mais elaborados no planejamento podem ajudar na satisfação dos stakeholders com o produto final.
