---
layout: post
title: GIMP Workshop
categories: event
date: 2018-04-09
---

### Introduction to Git

![](https://cdn-images-1.medium.com/max/800/1*9VlqcleV4uhord3IzL0pGQ.jpeg)

#### **Contents **

1.  Git
1.  Why Git ?
1.  Installation and Configuration Settings
1.  Existing project to Git Repository
1.  Commit
1.  Clone and Push a repository
1.  Create a branch for Issues, Push, Merge, Delete a repository after commit

<br> 

<br> 

![](https://cdn-images-1.medium.com/max/800/1*Ju-X7VzkCnYT7UngdT26Qw.png)
<span class="figcaption_hack">Type caption for image (optional)</span>

    Git is a Open-Source distributed control system to manage changes to source code. It was developed by Linus Torvalds.
    Most widely used control system in the world. It keeps track of all the modification to the code. Mistakes or error in source code can be overcome by looking at the previous changes.
    And Git repository hosting service i.e., GitHub which is owned by Microsoft.
    a. Download link : www.git-scm.com/downloads
    b. select OS. and download will be made.
    Select GNU/Linux Users
       sudo apt-get install git
       or
       sudo add-apt-repository ppa:git-core/ppa
       sudo apt update
       sudo apt install git
    git config --global user.name "User Name"
    git config --global user.email "UserName@gmail.com"
    git config --list
    git config --help
    Production of SSH key.
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_rsa
    copy id_rsa.pub content by going to C drive -> User -> UserAccount -> .ssh
    xclip -sel clip <~/.ssh/id_rsa.pub
    navigate to project folder from terminal
    git init #.git file will be created if the command was executed correctly
    git status
    staging area : The directory we use to organize files that are tracked and committed before pushing it to the repo.
    git add -A #To add all files
    git add filename
    Remove files from staging area : 
    git reset filename
    git reset #To remove all files
    git commit -m "First Commit" #-m is message passed
    git log #Can view commits we made
    git clone <url> #To track an existing repo
    Eq. 
    mkdir first
    git clone <url>
    ls -la #Shows all files in directory
    git diff #shows any changes made
    git add -A
    git commit -m "Updated first commit"
    If several people are working on a single project
    git remote -v #locations where our repo will get external commit or push 
    git branch -a #list all git branches
    git pull origin master #pull changes from remote repo
    git push origin master #pushes changes to remote repo i.e., master branch
    Usually a developer will create his/her own branch then add things or report.
    git branch <branch name>
    git branch #shows all branches
    git checkout <branch name> #switches branch
    eg.  same example... make some changes in file.
    git add -A
    git commit -m "Update 2"
    git push -u origin <branch name> #origin is the name of and followed by branch name
    git branch -a
    git checkout master
    git pull origin master
    git branch --merged
    git merge <branch name>
    git push origin master
    git branch --merged
    git branch -d <branch name> #delete in directory
    git branch -a
    git push origin --delete <branch name>
    git branch -a

<br> 
