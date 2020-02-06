---
layout: post
title: Introduction to Git
categories: event
date: 2019-10-31
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

![](https://cdn-images-1.medium.com/max/800/1*Ju-X7VzkCnYT7UngdT26Qw.png)

**1. Git**<br> Git is a Open-Source distributed control system to manage changes
to source code. It was developed by Linus Torvalds.<br> <br> 
**2. Why Git?**<br>
Most widely used control system in the world. It keeps track of all the
modification to the code. Mistakes or error in source code can be overcome by
looking at the previous changes.<br> And Git repository hosting service i.e.,
GitHub which is owned by Microsoft.<br> 
**3a. Installtion**<br> a. Download link
: www.git-scm.com/downloads<br> b. select OS. and download will be made.<br>
Select GNU/Linux Users<br>    sudo apt-get install git<br>    or<br>    sudo
add-apt-repository ppa:git-core/ppa<br>    sudo apt update<br>    sudo apt
install git<br> 
**3b. Configuration**<br> git config --global user.name "User
Name"<br> git config --global user.email "UserName@gmail.com"<br> git config
--list<br> <br> git config --help<br> <br> Production of SSH key.<br> ssh-keygen
-t rsa -b 4096 -C "your_email@example.com"<br> eval "$(ssh-agent -s)"<br>
ssh-add ~/.ssh/id_rsa<br> copy id_rsa.pub content by going to C drive -> User ->
UserAccount -> .ssh<br> xclip -sel clip <~/.ssh/id_rsa.pub<br> <br> <br> 
**4.
Existing project to Git Repository**<br> navigate to project folder from
terminal<br> git init #.git file will be created if the command was executed
correctly<br> git status<br> <br> staging area : The directory we use to
organize files that are tracked and committed before pushing it to the repo.<br>
git add -A #To add all files<br> git add filename<br> <br> Remove files from
staging area : <br> git reset filename<br> git reset #To remove all files<br>
<br> 
**5. Commit**<br> git commit -m "First Commit" #-m is message passed<br>
git log #Can view commits we made<br> <br> 
**6. Clone and Push a
repository**<br> git clone <url> #To track an existing repo<br> Eq. <br> mkdir
first<br> git clone <url><br> ls -la #Shows all files in directory<br> <br> git
diff #shows any changes made<br> git add -A<br> git commit -m "Updated first
commit"<br> <br> If several people are working on a single project<br> git
remote -v #locations where our repo will get external commit or push <br> git
branch -a #list all git branches<br> <br> git pull origin master #pull changes
from remote repo<br> git push origin master #pushes changes to remote repo i.e.,
master branch<br> <br> 
**7. Create a branch for Issues, Push, Merge, Delete a repository after commit**<br> Usually a developer will create his/her own
branch then add things or report.<br> git branch <branch name><br> git branch
#shows all branches<br> git checkout <branch name> #switches branch<br> <br> eg.
same example... make some changes in file.<br> git add -A<br> git commit -m
"Update 2"<br> <br> **Push :**<br> git push -u origin <branch name> #origin is
the name of and followed by branch name<br> git branch -a<br> <br> **Merge
:**<br> git checkout master<br> git pull origin master<br> git branch
--merged<br> git merge <branch name><br> git push origin master<br> <br>
**Delete : **<br> git branch --merged<br> git branch -d <branch name> #delete in
directory<br> git branch -a<br> git push origin --delete <branch name><br> git
branch -a

<br> 
