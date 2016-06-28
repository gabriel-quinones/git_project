git will use as the default terminal MinTTY 

to start minTTY go to the start menu and
search for git bash

Downloading git
https://git-scm.com/download

Gabriel@Gabriel-PC MINGW64 /
$ which git
/mingw64/bin/git

Gabriel@Gabriel-PC MINGW64 /
$ git --version
git version 2.9.0.windows.1

Basic Configuartion
#System level configurations
C:\Program Files\Git\mingw64\etc
git config --system

#User level configurations
$HOME\.gitconfig
git config --global

#Project level configurations
my_project/.git/config
git config

#Setting global variables
git config --global user.name "Gabriel Quinones"
git config --global user.email "someone@nowhere.com"
git config --global core.editor "notepad.exe"
git config --global color.ui true

#viewing variables
git config --list
user.name=Gabriel Quinones
user.email=someone@nowhere.com

#viewing configuration file in ~
$ cat .gitconfig
[user]
        name = Gabriel Quinones
        email = someone@nowhere.com
[core]
        editor = notepad.exe
[color]
        ui = true

#Getting git to start tracking your project
1. first cd into the project directory you want to track
2. run the following command:
  git init
3. this will create a .git directory
  ls -al
  total 4
  0 Jun 26 18:46 ./
  0 Jun 26 18:45 ../
  0 Jun 26 18:46 .git/

#Remove git by deleting .git directory

#Adding git changes to staging index
git add .

#Commit to git repository
git commit -m "Gabriel: Initial commit"

#viewing git log
$ git log
commit 5e393f00a6e0d5fb357ad9ce918e59494057f270
Author: Gabriel Quinones <someone@nowhere.com>
Date:   Sun Jun 26 18:54:49 2016 -0500

    Gabriel: Initial commit

#view logs options
git log -n 5
git log --since=2016-06-15
git log --until=2016-06-15
git log --author="Gabriel"
git log --grep="Init"

#HEAD points to tip of current branch
#Points to the last commit

#Checking status to synchronize
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.txt

no changes added to commit (use "git add" and/or "git commit -a")

#Viewing the modifications
git diff

#Removing file
git rm <file_to_delete>
git reset HEAD or git commit <file> -m "comment"

#renaming files will be tracked 
#as deleted then untracked file
#until its staged
git mv <file> <rename-file>

#move to another folder
git mv <file> <dir>/<file>

#committing all changes
git commit -am "message"

#Undoing Changes to working directory
#if you want to stay on the same branch
git checkout -- <file/directory>

#undo changes to staging area
git reset HEAD <file-to-reset>

#undoing commits
git revert <sha-substring>

#WARNING: move HEAD pointer
git reset --soft (keeps working directory changes)
git reset --mixed (changes staging index)
git reset --hard (changes working and index)

#git location
project/.gitignore

#gitignore syntax
* ? [aeiou] [0-9]
*.php
!index.php
assets/videos/

#ignore url
https://github.com/github/gitignore

#stop tracking a file and rm from repository
git rm --cached <file>

#refurring to commit tree
git HEAD^^ or git HEAD~2

#view git tree
git ls-tree HEAD

#view current branches
git branch

#creating a new branch
git branch <branch-name>

#view branch you are on
cat .git/HEAD or git branch (*)

#switch to new branch
git checkout <new-branch-name>