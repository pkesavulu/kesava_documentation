# Git basic commands:
---

## set the git username

> git config --global user.name "kesava"

## set the git user email id

> git config --global user.email "pkesavulu.91@gmail.com"

## git intialization use to create .git directory

> git init

## list out the configuration properties

> git config --list

## status of the git files 

> git status

## add file into staging place

> git add file_name(to add single file) or git add -A(to add all the files) or git add -all(to add all the files)

## use commit command to place the files into staging to repository

> git commit -m "this is my first file to add git repository"

## To check git log or show the commited files

> git log

## recently entered git logs or commited files

> git log -n 1 

> git log -n 10

## This command use to connect the remote machine github machine

> git remote add origin https://github.com/pkesavulu/sample2.git

## this command use to push the data in repository

> git push -u origin master

## remove file from git staging place before going to git repository

> git reset sample2

## update the data into repository

> git push -u origin master
		(or)
> git push -f origin master

## how to pull the data

> git pull origin

        (or)

> git fetch origin	

## remove file from git repository

> git rm file1.txt

> git commit -m "remove file1.txt"

## But if you want to remove the file only from the Git repository and not remove it from the filesystem, use this command

> git rm --cached file1.txt

> git commit -m "remove file1.txt"

And to push changes to remote repo

> git push origin branch_name  

## creating branches

> git branch sample_branch

## how to switch to other git branch

> git checkout sample_brach

## git branch 

- It show all the existed branch
- By defualt master branch
- Use of branch is to change code again and agin it's not effected again and again master barnch(main branch).
- we are doing always changes right so we created branches finaly we merge those things in to a single branch.


## use of .gitignore file

- If you want to avoid (or) ignore some file to place (or) checkin into repository at the time to create simply ".gitignore file"
and to place what are all the file avoid in that.

- Then it show only .gitignore file only.

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
        sample.txt

```

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
````

- If you need more information see this [video](https://www.youtube.com/watch?v=ErJyWO8TGoM)
 
## How to delete branch in git

```
To remove a local branch from your machine:

 > git branch -d {the_local_branch} (use -D instead to force deleting the branch without checking merged status)

To remove a remote branch from the server:

 > git push origin --delete {the_remote_branch}

```

## Git stash

 > It is used to store the data in temp location

```
> git stash 
> git stash list 
> git stash show 
> git stash clear

```

## Get deleted files back with git pull

> You can reset local branch to what's at remote

```
> git reset --hard origin/master

```
## How to deleted directory in git 

> try the below command to deleted directory

```
synax:- 

git rm -r <folder_name>
git rm -r --cached <folder_name>


```
```
example:-
---
> git rm -r TUI  (or)   git rm -r --cached TUI
> git commit -m "Remove directory"   
> git push -u origin master

```
## How to go last commit

> use this command to switch into previous index in git 

```
syntax:-

git log (it display the last commits with id)
git checkout <id>

```
```
example:-
---

> git log 

commit 4c1f23c8a655295a6f88953d8d8b3613d1783e90 (HEAD -> kesava) --> it means local machine
Merge: b0a1b8c a4aaf82
Author: pkesavulu <pkesavulu.91@gmail.com>
Date:   Wed Nov 28 13:16:04 2018 +0530

    changed conflict files

commit a4aaf8219edf7602273acb787e2438eeb6c6c97f (origin/kesava) --> it means remote machine
Author: pkesavulu <pkesavulu.91@gmail.com>
Date:   Mon Nov 12 12:30:16 2018 +0530

    Removed ThalesJhipsterUI

commit b0a1b8c7b02d24b7d3e318587cf67a923860055d
Author: pkesavulu <pkesavulu.91@gmail.com>
Date:   Mon Nov 12 12:27:03 2018 +0530

    ThalesJhipsterUI

commit 4e7a6c29a7c883c3646754bc6e2b2caffcf74a71
Author: pkesavulu <pkesavulu.91@gmail.com>
Date:   Mon Nov 12 12:20:20 2018 +0530


> git checkout a4aaf8219edf7602273acb787e2438eeb6c6c97f --> The repositry change into the last commit id like it's go to the perticular  commit id changes what we mentioned.

now it's change as like current changes

```


## Automatic merge failed; fix conflicts and then commit the result problem

> try to check your code first what are all the class has conflict.
```
If you have questions, please
<<<<<<< HEAD
your local machine code
=======
remote code
>>>>>>> a4aaf8219edf7602273acb787e2438eeb6c6c97f

```
> try to check changes like if you like you logic try to place as same and remove remote logic, other wise remove your local logic and use git add -A or git add .

> Next try to commit this code in local machine use this command :git commit -m "chaged confict code"

> All conflicts are fixed and local changes also automatically fixed.

## git basic commands 

> if you want git basic commands try to click this link https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html
