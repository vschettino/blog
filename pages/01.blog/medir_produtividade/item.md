---
title: 'Como medir a produtividade do processo de desenvolvimento?'
date: '00:00 12/20/2017'
taxonomy:
    category:
        - blog
    tag:
        - produtividade
        - evolução de software
        - gerência de projetos
---

A produtividade do desenvolvedor é fator essencial para desempenho de empresas de base tecnológica. Com a ascensão de sistemas cada mais presentes no cotidiano da sociedade, entregar a tempo as funcionalidades certas virou prioridade e condição que diferencia organizações que terão ou não sucesso. É natural que os gerentes e diretores queiram contar com equipes cada vez mais produtivas. E, como bons gestores, eles sabem que antes de melhorar qualquer coisa é necessário medir. Neste artigo irei discorrer de métricas de produtividade, modelos de acompanhamento e mostrar se é possível chegar num modelo sólido e justo para medir a produtividade no processo de desenvolvimento. *Spoiler: não dá*.

---

## Introdução

Pelo menos uma vez por mês algum colega me pergunta quais métricas são boas para avaliar a produtividade de um desenvolvedor. Para começar, a maioria das organizações não sabe diferenciar o que seria a eficiência do desenvolvedor do restante da equipe, como por exemplo analistas e Q.A. Se o caso de uso não está bem descrito ou a equipe de Q.A. é ruim em detectar falhas, duas possíveis medidas de produtividade já podem ser descartadas. Neste artigo o foco está no desenvolvedor, então é preciso assumir que os artefatos pré e pós desenvolvimento possam ser considerados padronizados e análogos para todas as tarefas que chegam para os desenvolvedores.

Outro problema é muito bem descrito pela conhecida [Lei de Goodhart](https://en.wikipedia.org/wiki/Goodhart's_law). Qualquer conjunto definido de métricas utilizadas para avaliação será distorcido e enviesado, tornando a satisfação da métrica o objetivo. Então, se qualquer conjunto de métricas for utilizado como parâmetro avaliar os desenvolvedores, eles serão aos poucos impelidos a cumprir suas metas e aos poucos deixarão de pensar nos objetivo reais de desenvolver rápido e bem. Isso ocorre com maior intensidade quando a métrica é considerada injusta, ou quando incentivos financeiros estão atrelados à aderência às métricas. O [princípio da incerteza](https://en.wikipedia.org/wiki/Uncertainty_principle) está emocionalmente ligado a esse fato: Ao tentar medir o processo, ele certamente será influenciado pela nova atividade que foi agregada.

Antes de concluir que é impossível setar uma suíte de métricas e concluir a produtividade de um desenvolvedor a partir delas, vou apresentar as medidas mais comuns (só porque é impossível, não quer dizer que não tentem) e maneiras mais saudáveis de abordar essa questão, que é importantíssima para as organizações modernas.

## Linhas de código

Essa é provalmente a pior de todas. Se Alice desenvolveu 10k linhas de código, não quer dizer que ela produziu menos que o Bob com suas 100k novas linhas. Na verdade é mais fácil inferir que Bob utilizou um design muito pior e com pouco aproveitamento. Se na empresa deles essa fosse a medida para premiação de final de ano, o programador gambiarra iria ganhar, deixando o profissional mais qualificado com sentimento latente de injustiça.

Linhas de código servem para medir o tamanho de um software, e só. Um software de 10k é menor que um software de 100k, e se um software cresceu 200% em linhas de código em um ano, você pode imaginar que ele triplicou de tamanho. Essa medida é útil para normalizar comparações de defeitos, vulnerabilidades e falhas em componentes diferentes, em medidas como "0.4 defeitos para cada KLOC". Mas mesmo assim é necessário tomar cuidado com componentes de linguagens e padrões diferentes, que certamente serão mais ou menos prolixos.

## Pontos de função (ou similares)

Mesmo que você tenha uma forma perfeita de medir a "quantidade de funcionalidades" que um desenvolvedor entregou (o que você não tem), ainda é discutível o quão útil para o usuário final foram aquelas features. O mesmo ponto de função pode ser mais útil para plataforma que outro, além um bug difícil de rastrear e sem pontos de função associados pode ter sido resolvido em tempo recorde, e ele não influenciaria nesta métrica de produtividade.

## Número de casos resolvidos

Não precisa de ser desenvolvedor para perceber que, quando o número de casos (issues/tasks) é a métrica de produtividade, os desenvolvedores vão priorizar os mais fáceis para resolver.  Mesmo que haja uma normalização por dificuldade (representada em dias, tags etc), algúem precisa fazer esta atribuição. Se for o usuário, ele não vai querer saber apenas de prioridades, o que não reflete no desafio técnico. Se for o desenvolvedor, ele vai tender a sempre jogar valores mais altos, valorizando seu esforço. Quando sobrar para alguém um caso difícil, ele acabará por procurar a solução mais rápida, que tende a não ser a melhor. Perceba que ele não faz isso com uma maldade consciente, mas pelo próprio estímulo que a métrica lhe concedeu; é como se cumprir a meta, que antes era um marginal instrumento de medição, virasse o objetivo do seu trabalho. Além disso, os casos sofrem alterações monstruosas de tamanho, estrutura e objetivos, e não podem ser pensados como uma única tarefa.    

## Tempo médio de atendimento, colaboração e satisfação do usuário

O principal problema dessas métricas é, antes de mais nada, como extraí-las. Como saber se realmente o atendimento inicial foi feito em poucas horas? O responsável pode ter feito um simples comentário genérico para ganhar tempo. A colaboração envolve diversas ações, variam de acordo com o meio e os envolvidos. E a satisfação está diretamente relacionada à capacidade que o responsável teve em resolver o problema no tempo que o autor da queixa espera ser razoável. Nem precisa explicar que ele não tem o domínio técnico para dizer isso, então pode julgar como ruim um atendimento extremamente complexo e demandou muito tempo, mas que lhe parecia trivial.

## Formas saudáveis de avaliação

A primeira dica é avaliar um determinado time de desenvolvimento, não apenas o desenvolvedor. Em equipes multifuncionais com macro responsabilidades bem definidas (como pregam as metodologias ágeis), é  mais fácil definir quais são os outputs esperados. Afinal, qual é o produto de um desenvolvedor? O código? conhecimento? software? Na equipe, a resposta é mais simples: software funcionando. Então as métricas ficam mais amplas e não fixam olhares em particularidades do desenvolvimento. É mais fácil também acompanhar a qualidade do software produzido, e problemas detectados são apresentados e discutidos com a equipe como um todo, sem apontar o dedo para um pseudo responsável.

Dados históricos também são essenciais para este tipo de análise. Principalmente porque a evolução histórica de um time é  mais significativa que a comparação entre duas equipes diferentes, que possuem uma série de particularidades de função e composição distintas, como já explicado acima. Então o acompanhamento da produtividade de uma equipe pode ser muito mais explicativo, perguntando-se por exemplo "porque este mês tivemos uma queda neste quesito?".

O segredo está num conjunto grande de métricas e uma avaliação pessoal e íntima de cada pessoa ou equipe. Quando os mais diversos aspectos estão sendo analisados e a conclusão é feita levando em consideração as particularidades de cada um, o processo se torna, no mínimo, mais justo. Por exemplo, a Alice do exemplo anterior seria condecorada, porque resolveu mais casos e diminui o número de defeitos mesmo tendo produzido menos linhas de código. Agora Bob, apesar de não programar tão bem também pode merecer um tapinha nas costas por responder muito bem e de prontidão aos casos críticos que lhe são atribuídos.

## Conclusão

A medição e avaliação de qualquer processo é importante para que este possa melhorar continuamente. Apesar de ser impossível uma única medida de produtividade para o desenvolvedor, existem maneiras de avaliar e acompanhar o desempenho das equipes de desenvolvimento. A chave é utilizar as diversas métricas produzidas durante o processo de criação de software e chegar a conclusões personalizadas. Isso leva composição de um time não somente multidisciplinar, mas que agrega perfis diferentes, contribuindo para os objetivos reais da organização. Pior que não medir, é medir mal e utilizar os resultados dos números frios para tomar decisões importantes. O que nos resta é encontrar atalhos razoáveis.

## Referências

1. https://martinfowler.com/bliki/CannotMeasureProductivity.html
