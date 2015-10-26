# git-class
This is a repository to learn how to use Git.

## Main commands:

### Creating your first repository (3 stages):

1. Create repository folder
$ mkdir name_repository

2. Enter the folder
$ cd name_repository

3. Initializes a repository
$ git init
> After execute this command inside the repository folder where you want versioning, a hidden .git directory will be created, containing the repository structure. If this directory is deleted, the versioning of the folder no longer exists.

### Create a file
$ touch file.txt

### Edit the file
$ vim file.txt

### Check status of the repository
$ git status

### Stages
* 1st Stage - Untracked files
* 2nd Stage - Ready to be commited
* 3rd Stage - Commited

#### To include in what will be committed
$ git add arquivo.txt

#### To include all files
$ git add .

#### To commit the files
$ git commit -m “My first commit”

### Log
$ git log
//--- Se um arquivo alterado ele retorna para o segundo estágio (staged) necessitando ser comitado para ser novamente versionado ---//

Comita vários arquivos
$ git commit
//--- Descrever resumidamente o que foi feito em cada arquivo ---//

Adiciona todos arquivos modificados para serem comitados
$ git add .

Comita todos arquivos modificados (pulando o segundo estágio)
$ git commt -a -m “Comitando vários arquivos”

Comita todos arquivos modificados (pulando o segundo estágio)
$ git commt -a -m “Comitando vários arquivos”

Vendo o log

Mostra cada arquivo e o que foi modificado
$ git log -p

Mostra apenas os 2 últimos arquivos que foram modificados
$ git log -p -2

Mostra as estatísticas de todos os commits
$ git log --stat

Mostra os commits resumida em uma linha
$ git log --pretty=online

Mostra os commits resumida em formato diferente
$ git log --pretty=format:”%h - %an, %ar : %s”

Mostra os commits dos últimos 2 dias
$ git log --since=2.days

Mostra os commits dos últimas 2 semanas
$ git log --since=2.weeks

Ignorar arquivo ou pasta (não versionar)
Cria arquivo .gitignore, informando nele quais arquivos ou diretórios deverão ser ignorados
$ touch .gitignore

Fluxo de Commits
Volta arquivo para estágio inicial 
$ git reset HEAD teste2.txt

Voltando versões
$ git checkout 066a5b2cb04c61281
//--- onde “066a5b2cb04c61281” é o hach do arquivo, que pode ser obtido com o git log ---//

Remove comits e os arquivos ficam prontos para serem comitados
$ git reset HEAD~1 --soft 

Remove commits e arranca os arquivos associados
$ git reset HEAD~1 --hard

Faz o conteúdo do arquivo voltar ao estado original
$ git checkout -- exemplo.php

Branches (arvores)
Informa em qual branch você está
$ git branch

Cria um branch
$ git checkout -b funcionalidade1

Troca para branch (master)
$ git checkout master

Gruda branch a outro
$ git merge funcionalidade1

Remove commit que fez ultimo merge
$ git reset HEAD~1 --hard

Reorganiza commits e aplica (commit) no branch master
$ git rebase funcionalidade1

Para remover um branch utilize o comando:
$ git branch -D nome-do-branch


GITHUB (Repositório remoto do GIT)
https://github.com


Cria/gera chave no PC
$ ssh-keygen
//--- gera duas chaves: id_rsa e id_rsa.pub, sendo .pub pública ---//

Adicione a chave pública no GITHUB. 
Pegue o conteúdo da chave pública gerada e adicione no GitHub em Accounts → SSHKeys:

$ cat id_rsa.pub


Criando um novo repositório
Para criar um novo repositório é necessário:
clicar em Repositories
clicar em New
definir o nome do repositório
informar uma descrição (opicional)
escolher a opção Public pois a Private somente em contas pagas
não marcar a opção Initialize this repository with a README (criar apenas o repositório)

Fazendo primeiro push

Remove origin, caso precise
$ git remote remove origin

Adiciona repositorio remoto via HTTP
$ git remote add origin https://github.com/ijorgito/urldoGIT

Adiciona repositorio remoto via SSH
$ git remote add origin git@github.com/ijorgito/git-code-education.git

Envia branch master para o repositorio
$ git push origin master

Envia branch funcionalidade1 para o repositorio
$ git push origin funcionalidade1



Clonando um repositório
$ git clone git@github.com:ijorgito/git-codeEducation.git
//---pode ser passado um ultimo parâmetro, sugerindo um nome de diretório, se não for informado será criado o mesmo nome do repositório, nesse caso, “git-codeEducation” ---//

Lista branch locais e remotos
$ git branch -a

Clonando outro branch
$ git checkout -b funcionalidade1 origin/funcionalidade1

Verifica se todos os arquivos estão sincronizados
$ git pull

Traz modificações que estão no branch master remoto para local
$ git pull origin master

Cria tag local 
$ git tag 0.1.0

Envia tag local e gera release remoto
$ git push origin master --tags

Remove as tags criadas, utilize os comandos abaixo:
$ git tag -d 0.1.0  (removendo tag localmente)
$ git push origin :refs/tags/0.1.0 (removendo tag no repositório remoto)


Versionamento semântico
http://semver.org/



Referências:
Markdow
https://help.github.com/articles/markdown-basics/











