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

#Adding git changes
git add .

#Commit to git repository


