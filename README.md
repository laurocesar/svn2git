# svn2git

Anotação rápida de script de migração de repositório SVN para GIT, incluindo branches e tags

Baseado em https://git-scm.com/book/en/v2/Git-and-Other-Systems-Migrating-to-Git

## Pre script

Crie o repositório em um servidor. Pode ser o Github, Bitbucket, ou qualquer outro.

## Executando o script

Atualize as informações do repositório no arquivo `svn2git.sh`
Acrescente permissão para executar o scritp, com `chmod +x svn2git.sh`

## Post script

### Remover branches inválidos

Depois de executar o script, pode ser que restem branches como `trunk@456`. Você pode usar `git branch` para ver se é esse o caso, e então, usar `git branch -d trunk@456` para remover o branch inválido antes de enviá-lo para o origin.

### push ao origin

Use:

```
git push origin --all 

git push origin --tags
````
