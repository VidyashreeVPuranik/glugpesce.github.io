---
layout: post
title: Getting started with Pelican
categories: event
date: 2020-05-09
author: zphoenix
---

**TL;DR** : [**Pelican**](https://blog.getpelican.com/) is a static site generator written mainly in Python and why we call it static is because it doesnt require any database and its very simple.<br>
Pelican takes the content in mostly as text or markdown format, push it to a template and outputs as a HTML and CSS page, sometime even JS if added in the template. Pelican is simple and lightweight unlike other websites build in HTML or CSS or PHP which have a complex structure. 


### Prerequisites
---

- [Python](https://www.python.org/)
- [Pip](https://pypi.org/project/pip/)
- [Git](https://git-scm.com/)
- [Gitlab Account](https://gitlab.com/users/sign_in#register-pane)

## Contents
---
1. Installations
2. Configuration
3. Create a repo/project in gitlab
4. Initial setup to get Pelican
5. Write the first blog
6. The OUTPUT
7. Thinking to host Pelican? 
8. Futuristic
9. Conclusion

### 1. Installations
---
- #### Install Python

 `sudo apt-get install python3.6`<br>
 
  or<br>
 
 `sudo add-apt-repository ppa:deadsnakes/ppa`<br>
 `sudo apt-get update`<br>
 `sudo apt-get install python3.6`

- #### Install PIP

  `sudo apt install python3-pip`<br>
  `sudo apt install build-essential python3-dev`

- #### Install Git

  `sudo apt install git`<br>
  
   #if any error persists try <br>
  `sudo add-apt-repository ppa:git-core/ppa`<br>
  `sudo apt update`<br>
  `sudo apt install git`
      
- #### Install Virtualenv

  `sudo apt install virtualenv`<br>
  `virtualenv pelican`
<br>

### 2. Configuration
---
- #### Configure Virtualenv
It creates an environment and its suggested to overcome conflits when multiple projects in a machine and libraries issues.

 `virtualenv pelican`<br>
 `cd pelican`<br>
 `source bin/activate`<br>
  Output<br>
  `(pelican) z@zphoenix:~/pelican$`
<br>
  
### 3. Create a repo/project in gitlab
---
- #### a. Sign Up

  Register here : https://gitlab.com/users/sign_up
  
  So we have two options
  
  * Either get the pelican site running on `your_username.gitlab.io `
  
      or 
      
  * create a group and riunning on `your_groupname.gitlab.io`
  
  Here lets follow group method.<br>
  - #### Create a new group
  Firstly lets create a group & click the link to create a new group :  https://gitlab.com/groups/new
  
   ![img1](/assets/img/blog/pelican1.png)<br><br>
        
    _Note : _In the place of `zphoenix` have your `username`.
    
   ![img1](/assets/img/blog/pelican2.png)<br><br>
    
    So we create a new project under same name `blog-username.gitlab.io`<br>
    
- #### b. Clone the project
  
  Lets clone the project and start working on it. 
  
  - Click on `Clone` & Copy the ssh key
  - Open Terminal `ctrl+shift+t`     
  - Clone the repo     
   
     `git clone git@gitlab.com:blog-username.gitlab.io/blog-username.gitlab.io.git`<br>
        
     Output<br>
     `(pelican) z@zphoenix-pc:~/pelican$ git clone git@gitlab.com:blog-zphoenix.gitlab.io/blog-zphoenix.gitlab.io.git`<br>
     `Cloning into 'blog-zphoenix.gitlab.io'...`<br>
     `remote: Enumerating objects: 3, done.`<br>
      `remote: Counting objects: 100% (3/3), done.`<br>
      `remote: Compressing objects: 100% (2/2), done.`<br>
      `remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0`<br>
      `Receiving objects: 100% (3/3), done.`<br>


### 4. Initial setup to get Pelican
---

- #### Installation

  `pip install pelican`<br>
  `pip install markdown`<br>
  
- #### Get a basic site

  `pelican-quickstart`<br><br>
  Output<br>
  ![img1](/assets/img/blog/pelican4.png)<br><br>
  _Note_ : This command generates all required files basically basic pelican structure, there will be questions poped up, makesure you give URL Prefix as __'blog-username.gitlab.io'__ and leave rest as default values [ (Y/n) have default value as Yes and (y/N) is vice-versa ]

### 5. Write the first blog
---

- #### Create a blog post

  `cd content`<br>
  `touch firstPost.md` #To create the file<br>
  `nano firstPost.md` #To open the file<br>
 
  Add these below contents 

  ```
  Title: My First Post<br>
  Date: 2020-05-08 18:59<br>
  Modified: 2020-05-09 19:30<br>
  Category: Python<br>
  Tags: pelican, publishing<br>
  Slug: my-first-post<br>
  Authors: zphoenix, GLUG PESCE<br>
  Summary: Short version for index and feeds<br><br>
 
   This is the content of my super blog post.
  ```

 _Note_ : Reference - https://docs.getpelican.com/en/3.6.3/content.html and Slug is nothing but filename without space, makesure to give `-` instaed of ` ` #space
 
 Once you are done press `ctrl + s` to save and `ctrl + x` to exit from nano editor.<br>
 
- #### Convert post into html

  `pelican content`<br>
  `make html`<br>
  
  Try to check if public folder is created, if that has generated proceEd, else cross check and try again!!!<br>
 

###  6. The OUTPUT
---
Inorder to preview the firstPost.md - The blog post<br>
 `make serve`<br>
 Now open http://localhost:8000 in your web browser, your very first pelican based blog site is hosted locally :)
 
 Output
 ![img1](/assets/img/blog/pelican5.png)<br><br>
 
 **Hurray !!!! Congratulations here goes your Pelican BLog Post**
<br>
 _Note :_ To preview in our localhost you can even `cd` into `public` folder and type 
 
 - `python -m SimpleHTTPServer` #if using Python2 
 - `python -m http.server` #if using Python3<br>
 
### 7. Thinking to host Pelican?
---
Lets get three important files<br>

- #### requirement.txt
  But before getting into it lets try do get a requirements.txt file. Why is requirements.txt is important?<br>
  We all may run different python environments and with different versions and we primarily generate and share requirements.txt file to make it easier for other developers to install the correct versions of the required Python libraries/Packages to run the Python code that we have written.<br>
  
   `touch requirements.txt`<br>
   `nano requirements.txt`<br><br>
 Paste the below contents in `requirements.txt`<br>
 
```
 markdown
 pelican
```

- #### .gitlab-ci.yml<hr>
  It is a configuration file that will build and deploy or host our website in Gitlab Pages.<br>
   `touch .gitlab-ci.yml`<br>
   `nano .gitlab-ci.yml`<br><br>
   Paste these content in `.gitlab-ci.yml`<br>

  ```
   image: python:3.6-alpine

   pages:
     script:
     - pip install -r requirements.txt
     - pelican -s publishconf.py
     artifacts:
       paths:
       - public/
     only:
       - master
   ```
 
- #### .gitignore<hr>
  Lets create a .gitignore.<br>
  
   `touch .gitignore`<br>
   `nano .gitignore`<br><br>
   Paste these content in `.gitignore`<br>

  ```
   /public
   *.pyc
  ```
  <br>
- #### Lets PUSH !!!<br>
   Now lets push the pelican source code.
   
  ```
    git add .
    git commit -m "First Commit to add Pelican Blog Site"
    git push
  ```
  <br>
- #### CI/CD Configuration<hr>
   So go to CI/CD - > pipeline -> jobs<br>
   If the status of your job is `passed` then your Pelican based Blog Site you will find it at `blog-username.gitlab.io`<br><br>
   ![img1](/assets/img/blog/pelican6.png)<br><br>
   So your dream come true your very own Blog site LIVE !!! - Check out it here - blog-zphoenix.gitlab.io
<br>

### 8. Futuristic
---
- Add more post
  Start writing blogs buddies 
- Get a new theme for your site
  We are working on a basic default one try to experiment with themes :)
- Add few javascript tricks and let me know, im still learning JS !
<br>

### 9. Conclusion
---
Having said this blog is just a kickstart and its only your try will fetch you a great work out of you. Pelican is python based and its so easy to work and deploy too. And ifou are looking for a [ready repo](https://gitlab.com/blog-zphoenix/blog-zphoenix.gitlab.io).

In the virtue of getting writing this blog here is the OUTPUT : https://blog-zphoenix.gitlab.io/<br>

If any errors do ping me  or if you had a better pelican hosted share it with me, there will be something that i can learn from yours.

- Telegram : @blackzphoenix
- Email ID : zphoenix@disroot.org
- Mastodon : zphoenix@fsmi.social


**Reference**

- [Git and Git Configuration](https://glugpesce.github.io/event/2019/10/31/introduction-to-git.html)
- [Pelican Documentation](https://docs.getpelican.com/en/stable/)
- Pelican examples on Gitlab : 

   - [Gitlab on Pelican](https://gitlab.com/pages/pelican)
   - [VoidSpaceXYZ's example hosted](https://voidspacexyz.gitlab.io/pages/)

