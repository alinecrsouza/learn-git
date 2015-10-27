# git-class
This is a repository to learn how to use Git.

## Main commands

### Creating your first repository (3 stages)

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
$ git reset HEAD file.txt

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
> Generate two keys: id_rsa and id_rsa.pub, and .pub is the public one.

#### Add the public key on GitHub
$ cat id_rsa.pub
> Take the public key generated content and add on GitHub in Accounts → SSHKeys.

### Remote repository
#### Adds remote repository via HTTP
$ git remote add origin https://github.com/alinecrsouza/name_of_repository

#### Adds remote repository via SSH
$ git remote add origin git@github.com:alinecrsouza/name_of_repository.git

#### Send master branch to the repository
$ git push origin master

#### Send functionality1 branch to the repository
$ git push origin functionality1

#### Remove origin, just in case
$ git remote remove origin

#### Clone a repository
$ git clone git@github.com:alinecrsouza/name_of_repository.git
> One last parameter may be passed, suggesting a new repository name, if not informed it will be created with the same name.

#### List local and remote branch
$ git branch -a

#### Cloning another branch
$ git checkout -b functionality1 origin/functionality1

#### Checks if all files are synchronized
$ git pull

#### Brings changes that are in remote master branch to the local master branch
$ git pull origin master

### Create a remote repository on a local server
#### 1st step
$ git init --bare
> Execute this command inside the folder you want to serve as a remote repository.

#### 2nd Step 
git remote add *alias_repository* ssh://ip/path_of_repository

### Tags
#### Create a local tag
$ git tag 0.1.0

#### Sends the local tag and generates a remote release
$ git push origin master --tags

#### List the tags
$ git tag

#### To remove the tags created
$ git tag -d 0.1.0  
> remove the tag in the local repository

$ git push origin :refs/tags/0.1.0
> remove the tag in the remote repository
