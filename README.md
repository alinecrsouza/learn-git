# git-class
This is a repository to learn how to use Git.

## Main commands:

### Creating your first repository (3 stages):

#### Create repository folder
$ mkdir name_repository

#### Enter the folder
$ cd name_repository

#### Initializes a repository
$ git init
> After execute this command inside the repository folder, a hidden .git directory will be created, containing the repository structure. If this directory is deleted, the versioning service of the folder no longer exists.

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
$ git add file.txt

#### To include all files
$ git add .

#### To commit the files
$ git commit -m “My first commit”

#### To commit all files
$ git commit
> Briefly describe what was done on each file.

#### Commit all modified files (skipping the second stage)
$ git commit -a -m “Commit message”

#### Back the file to the first stage
$ git reset HEAD teste2.txt

### Log
$ git log
> If a file is changed, it returns to the second stage (Ready to be commited). 

#### Shows each file and what was modified
$ git log -p

#### Show only the last 2 files that were modified
$ git log -p -2

#### Shows statistics of all the commits
$ git log --stat

#### Shows a summary of commits in a row
$ git log --pretty=online

#### Shows a summary of commits in a custom format
$ git log --pretty=format:”%h - %an, %ar : %s”

#### Shows commits of the last two days
$ git log --since=2.days

#### Shows commits of the last two weeks
$ git log --since=2.weeks

### Ignore file or folder (no versioning)
$ touch .gitignore
> Create .gitignore file and insert in it the files or directories that should be ignored.

### Versions
#### Going back versions
$ git checkout 066a5b2cb04c61281
> Where "066a5b2cb04c61281" is the commit hash that can be obtained from the git log.

#### Remove a certain number of commits
$ git reset HEAD~x
> Where x is the number of commits that you want to remove.

#### Remove the last commit, but keep the related files
$ git reset HEAD~1 --soft 

#### Remove the last commit AND the related files
$ git reset HEAD~1 --hard

#### Makes the file content back to the original state
$ git checkout -- exemplo.php

### Branchs
#### Informs on which branch you are
$ git branch

#### Create a branch
$ git checkout -b functionality1

#### Return to master branch 
$ git checkout master

#### Merge functionality1 branch to master branch
$ git merge functionality1

#### Reorganizes commits and applies (commit) on master branch
$ git rebase functionality1

#### Remove a branch
$ git branch -D name-of-branch

### SSH with authentication key
#### Create the key
$ ssh-keygen
> generate two keys: id_rsa and id_rsa.pub, and .pub is the public one.

#### Add the public key on GitHub
$ cat id_rsa.pub
> Take the public key generated content and add on GitHub in Accounts → SSHKeys:




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











