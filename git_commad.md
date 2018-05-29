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

## creating branches

> git branches sample_branch

## how to switch to other git branch

> git checkout sample_brach

## git branch 

- It show all the existed branch
- By defualt master branch
- Use of branch is to change code again and agin it's not effected again and again master barnch(main branch).
- we are doing always changes right so we created branches finaly we merge those things in to a single branch.