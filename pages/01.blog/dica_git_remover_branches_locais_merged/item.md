---
title: 'Quick Tip Git: "Limpar" as branches locais sem referência remota e que já foram "merged"'
date: '00:00 01/19/2018'
taxonomy:
    category:
        - blog
    tag:
        - tips
        - git
---

A dica rápida da vez fica por conta do Git. Quando trabalhamos em um ambiente colaborativo, como o [GitHub](https://github.com), o uso de [branches](https://git-scm.com/book/pt-br/v1/Ramifica%C3%A7%C3%A3o-Branching-no-Git-O-que-%C3%A9-um-Branch) atômicas, de [vida curta](https://trunkbaseddevelopment.com/short-lived-feature-branches/) e descritivas é bem comum. Apesar das vantagens, isso gera um pequeno incômodo. Um número grande de branches que vão aos poucos atrapalhando a visibilidade de comandos como o `git branch -a` e as funções de autocomplete. Limpar as branches remotar é relativamente fácil, durante o processo de [Pull Request](https://help.github.com/articles/deleting-and-restoring-branches-in-a-pull-request/) e do [Merge Request](https://gitlab.com/gitlab-org/gitlab-ce/merge_requests/6449) do Github e Gitlab, respectivamente. Agora, isso por si só não remove as referências que a cópia local mantem da remota. Para removê-las, utilize o seguinte comando:

```
git remote prune origin
```

Assim, as referências a branches que já não existem mais na remote, somem da listagem do `git branch -a`. Agora, e no caso das branches que chegaram a sofrer o "fetch" e estão efetivamente na máquina? O comando `git branch -d` para cada branch faria o trabalho de limpeza, mas é bem manual. A dica é utilizar a saída de `git branch --merged` para facilitar o processo. Para ter uma camada de segurança (não apagar branches importantes como a master e a develop), o comando abaixo te dá a oportunidade de alterar quais branches serão removidas.

```
git branch --merged >/tmp/merged-branches && vi /tmp/merged-branches && xargs git branch -d </tmp/merged-branches
```
Pronto, sua cópia de trabalho está limpa!

## Referências

1. https://stackoverflow.com/questions/7726949/remove-local-branches-no-longer-on-remote
