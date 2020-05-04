---
layout: post
title: Introduction to Git
categories: event
date: 2019-10-31
---

### Introduction to Git

![](https://cdn-images-1.medium.com/max/400/1*9VlqcleV4uhord3IzL0pGQ.jpeg)


#### **Contents**

1.  Git
1.  Why Git ?
1.  Installation and Configuration Settings
1.  Existing project to Git Repository
1.  Commit
1.  Clone and Push a repository
1.  Create a branch for Issues, Push, Merge, Delete a repository after commit

![](https://cdn-images-1.medium.com/max/400/1*Ju-X7VzkCnYT7UngdT26Qw.png)

##### 1. Git<br> 
Git is a Open-Source distributed control system to manage changes
to source code. It was developed by Linus Torvalds.<br> <br> 
##### 2. Why Git?<br>
Most widely used control system in the world. It keeps track of all the
modification to the code. Mistakes or error in source code can be overcome by
looking at the previous changes.<br> And Git repository hosting service i.e., Gitlab, Mercury, GitHub few more.<br><br> 

##### 3a. Installation<br> 
* ###### GNU/Linux Users
       sudo apt-get install git
     or
       sudo add-apt-repository ppa:git-core/ppa
       sudo apt update
       sudo apt install git
 
* ###### Windows Users<br>
  Download from link : www.git-scm.com/downloads<br> Select OS and 32bit or 64bit based on your requirement.<br>

##### 3b. Configuration & Production of SSH key<br> 

###### Configuring

    git config --global user.name "UserName"
    git config --global user.email "UserName@gmail.com"
    git config --list
    
    git config --help #For manual page or help page
    
###### Production of SSH Key
   
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    eval $(ssh-agent -s)
    ssh-add ~/.ssh/id_rsa
    
   **GNU\Linux User :**
   
    xclip -sel clip <~/.ssh/id_rsa.pub
   
   **Windows User :**
   
   Copy id_rsa.pub content by going to C drive -> User -> UserAccount -> .ssh<br><br>
##### 4. Existing project to Git Repository<br> 
Navigate to project folder from terminal<br> 
`To Git file will be created if the command was executed correctly` 

    git init 
`staging area : The directory we use to organize files that are tracked and committed before pushing it to the repo.`   
    
    git status
`To add all files &  To add a single file`
   
    git add -A 
    git add filename 
    
`#To remove all files & To Remove files from staging area :` 

    git reset 
    git reset filename
<br> 
##### 5. Commit<br> 

`To commit`

    git commit -m "First Commit" #-m is message passed
`To can view our commits`

    git log 
   <br>
   
##### 6. Clone and Push a repository<br> 
To track an existing repo

    git clone <url> 
    
   Example : 
   
    mkdir first
    git clone <url>
    ls -la #Shows all files in directory
    git diff #shows any changes made
    git add -A
    git commit -m "Updated first commit"
    
If several people are working on a single project<br> 

`locations where our repo will get external commit or push`

    git remote -v 
`list all git branches`    
    
    git branch -a 
`pull changes from remote repo`

    git pull origin master 
`pushes changes to remote repo i.e., master branch`    
    
    git push origin master 
    
   <br>
   
##### 7. Create a branch for Issues, Push, Merge, Delete a repository after commit
**Branch :**
Usually a developer will create his/her own branch then add things or report.<br> 

    git branch <branch name> 
`shows all branches`    
    
    git branch 
`switches branch<br> <br> `    
    
    git checkout <branch name> 
    
Example : 
same example... make some changes in file and then<br> 

    git add -A
    git commit -m "Update 2"
    
**Push :**<br> 
`Origin is the name of and followed by branch name`

    git push -u origin <branch name> 
    git branch -a
    
**Merge :**<br> 

    git checkout master 
    git pull origin master
    git branch --merged
    git merge <branch name>
    git push origin master
    
**Delete :**<br> 

    git branch --merged
    
    #delete in directory
    git branch -d <branch name>
    
    git branch -a
    git push origin --delete <branch name>
    git branch -a

