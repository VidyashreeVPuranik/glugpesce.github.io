---
layout: post
title: Hosting a Profile in Gitlab
categories: event
date: 2020-04-30
author: Nidhi KS
---

# HOSTING A PROFILE WEBSITE IN GITLAB  
    
   Hosting a website which you  have designed is everyone's dream. If its yours too then  read along the blog and have in fact  hosted too.



#### Prerequisites:
- A GNU Linux machine.
- Basic Knowledge on HTML and CSS.
- An enthusiasm to learn.

#### Creating an Gitlab account

Click on https://gitlab.com/ -> Select the  register  button and create an account .

#### Installing Git & Configuaration

    sudo apt install git
    or
    
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt update
    sudo apt install git
    
b.Configuaration
     
    git config --global user.name  "Username"
    git config --global  user.email “UserName@gmail.com”
    git config --list
 
 
Production of SSH key.

   The public key is generated and it is given to Gitlab . The public key is like the handshake between your local machine and the gitlab server.
 
    ssh-keygen -t rsa -b 4096 -C “@nidhiks.excellence@gmail.com”
    eval $(ssh-agent -s)
    ssh-add ~/.ssh/id_rsa

Xclip is a tool used to copy the public key generated

    sudo apt-get install xclip
    xclip -sel clip < ~/.ssh/id_rsa.pub
    
Now the public key is copied to your clipboard.

-> Log in to your gitlab account at https://gitlab.com/

-> Go to settings which is in right top corner.


-> and select SSH key from the dropdown menu and you will be redirected to a page where you have to paste the ssh key  and put add a title i.e., the laptop you are using. (ex:Lenovo,HP,Dell)

Hurray!!!!        The configuaration is complete.

#### Creating a new repository 

-> Click the Gitlab icon present in top left corner.It redirects to the home profile page.

-> Click on Newproject button and give appropriate name.

#### Basic Git commands

->Click on https://gitlab.com/Happysunshine/gitsession . You will get  a repository with 4 files.

->Now click on Fork  #A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project. 

->Click on clone and copy the http path  or ssh path which you get. 

Get into Your terminal(CTRL+ALT+T)

Get into the directory where you want your repository to reside. Here I am considering home directory

          git init    #intialises a git repository ang gives the creates a .git file
          
Copy the path which you copied in https or ssh
          
          git clone "https://gitlab.com/Happysunshine/gitsession.git"  #Creates a folder called gitsession in your local machine.

-> To verify get into your file manager and check for the folder named gitsession . In this case the folder will be in the home directory.



->Change the back ground image and profile photo as required.

-> change to your gitsession folder using cd command

      cd gitsession
      
->To add all the files to your local machine execute

       git add -A     #To add all the files 
       git add file name  #To add a particular file.
       
->To commit the changes made to local repository execute

      git commit -m "Message"    #change the message appropriately.
      
->To push the changes to git repository 

      git push
      
To verify get into your account in gitlab and click on gitsession repo and you will find the files that you pushed.

Hurray!!!!  We have our repo ready. Time to host!!!


#### Hosting 


->Get into your gitsession folder.

       cd gitsession
       
->To host your website we should add CI/CD configuaration file


To create a file :
       
         touch .gitlab-ci.yml
         
To write in the file :
     
         nano gitlab-ci.yml

You will directed to nano text editor. Add the following
          
      pages:
        script:
        - mkdir .public
        - cp -r * .public
        - mv .public public
        artifacts:
          paths:
          - public
        only:
        - master
  


->Press CTRL+S for save and CTRL+X to exit.

->Now lets push the changes to gitlab .

     cd gitsession
     git add -A
     git commit -m"Added CI/CD executable file"
     git push
     
     
->Go to your gitlab account. Verify if you have a executable file in gitsession repo.

->Go to setting in the right most corner and click on CI/CD from the dropbox and click on pipelines.

->You will get a tick mark and passed . If you click job it will be running ,once job is succeded your website is hosted.

->Select settings and  click on pages from the dropdown list.

->You will find a URL in which your website is hosted. (ex:https://happysunshine.gitlab.io/gitsession/)

CONGRATS !!!! YOU HAVE YOUR WEBSITE HOSTED !!!!

Here you have your dream come true !!!Party hard for your success !!! 


Feel free to contact me for any of your queries or share your happiness!!!

  
  Telegram handle :  @Happysunshine_5





      
      
