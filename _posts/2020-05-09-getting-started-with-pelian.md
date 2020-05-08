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
- #### Install Python<hr>
 `sudo add-apt-repository ppa:jonathonf/python-3.6`
 `sudo apt-get update && sudo apt-get install python3.6`

- #### Install PIP<hr>
 `sudo apt install python3-pip`<br>
 `sudo apt install build-essential python3-dev`

- #### Install Git<hr>
 `sudo apt install git`<br>
 
 if any erro persists try <br>
 `sudo add-apt-repository ppa:git-core/ppa`<br>
 `sudo apt update`<br>
 `sudo apt install git`
      
- #### Install Virtualenv<hr>
 `sudo apt install virtualenv`<br>
 `virtualenv pelican`
 
### 2. Configuration
---
- #### Configure Virtualenv<hr>
It creates an environment and its suggested to overcome conflits when multiple projects in a machine and libraries issues.

 `virtualenv pelican`<br>
 `cd pelican`<br>
 `source bin/activate`<br><br>  
  Output<br>
  `(pelican) z@zphoenix:~/pelican$`
  
- #### 
  
### 3. Create a repo/project in gitlab
---
- #### a. Sign Up<hr>

  Register here : https://gitlab.com/users/sign_up
  
  So we have two options
  
  * Either get the pelican site running on `your_usernamegitlab.io `
  
      or 
      
  * create a group and riunning on `your_groupname.gitlab.io`
  
  Here lets follow group method.<br>
  - #### Create a new group
  Firstly lets create a group & click the link to create a new group :  https://gitlab.com/groups/new
  
   <media-tag src="https://files.cryptpad.fr/blob/2d/2dbb9406bb61f31c790ed7d040056d2b9b9fcad01d7d2227" data-crypto-key="cryptpad:lnwV75oY16Z01nV+NYL7U5i/7e2SaVEVBNcV8Sc9oIY="></media-tag><br><br>
        
    _Note : _In the place of `zphoenix` have your `username`.
    
   <media-tag src="https://files.cryptpad.fr/blob/a7/a71f985d1ab336b8db8823444cdb0ea8fc070e25dad1d764" data-crypto-key="cryptpad:JTflyUSMaoa4FvX9Ei7AH8ewIwu8d1u3VLtTiCn62zk="></media-tag><br><br>
    
    So we create a new project under same name `blog-username.gitlab.io`<br>
    
- #### b. Clone the project<hr>
  
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

- #### Installation<hr>
  `pip install pelican`<br>
  `pip install markdown`<br>
- #### Get a basic site<hr>
  `pelican-quickstart`<br><br>
  Output<br>
  <media-tag src="https://files.cryptpad.fr/blob/f5/f5558820c5e603dd05d62e26129f70ed1f439b770a3a1d25" data-crypto-key="cryptpad:lMouPoaUPkn9WGOLcFGkNkc2Nz5Uvu0TTT0u9ZOC8mc="></media-tag><br><br>
  _Note_ : This command generates all required files basically basic pelican structure, there will be questions poped up, makesure you give URL Prefix as __'blog-username.gitlab.io'__ and leave rest as default values [ (Y/n) have default value as Yes and (y/N) is vice-versa ]

### 5. Write the first blog
---

- #### Create a blog post <hr>
 `cd content`<br>
 `touch firstPost.md` #To create the file<br>
 `nano firstPost.md` #To open the file<br>
 
 Add these below contents 

 >Title: My First Post<br>
Date: 2020-05-08 18:59<br>
Modified: 2020-05-09 19:30<br>
Category: Python<br>
Tags: pelican, publishing<br>
Slug: my-super-post<br>
Authors: zphoenix, GLUG PESCE<br>
Summary: Short version for index and feeds<br><br>
 >This is the content of my super blog post.

 _Note_ : Reference - https://docs.getpelican.com/en/3.6.3/content.html
 
 Once you are donepress `ctrl + s` to save and `ctrl + x` to exit from nano editor.<br>
- #### Convert post into html<br>
 `pelican content`<br>
 or<br>
 `make html`<br>
 Try to check if public folder is created, if that has generated procedd, else cross check and try again!!!<br>
 

###  6. The OUTPUT
---
Inorder to preview the firstPost.md - The blog post<br>
 `make serve`<br>
 Now open http://localhost:8000 in your web browser, your very first pelican based blog site is hosted locally :)
 
 Output
 <media-tag src="https://files.cryptpad.fr/blob/b1/b15a865b98d43e59296c394a3d1115d2637b27bde7e39e98" data-crypto-key="cryptpad:WJJCX4BeW1VKTswDDTbFSscEvt0ECUCZt9MhQDQWhpc="></media-tag><br><br>
 
 **Hurray !!!! Congratulations here goes your Pelican BLog Post**
<br>

### 7. Thinking to host Pelican?
---
Lets get two important files<br>
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
  <script src='https://gitlab.com/snippets/1974975.js'></script>
  
```
image: python:3.6-alpine

pages:
  script:
  - pip install -r requirements.txt
  - pelican -s publishconf.py
  artifacts:
    paths:
    - public/
```

- #### Lets PUSH !!!<br>
   Now lets push the pelican source code.
   
```
   git add .
   git commit -m "First Commit to add Pelican Blog Site"
   git push
```
- #### CI/CD Configuration<hr>
So go to CI/CD - > pipeline -> jobs<br>
If the status of your job is `passed` then your Pelican based Blog Site you will find it at `blog-username.gitlab.io`<br><br>
So your dream come true your very own Blog site LIVE !!!

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

If any errors do ping me  or if you had a better pelican hosted share it with me, there will be something that i can learn from yours.

- Telegram : @blackzphoenix
- Email ID : zphoenix@disroot.org
- Mastodon : zphoenix@fsmi.social


**Reference**<hr>

- Git and Git Configuration : https://glugpesce.github.io/event/2019/10/31/introduction-to-git.html
- Pelican Documentation : https://docs.getpelican.com/en/stable/
- Pelican examples on Gitlab : 

 - Gitlab on Pelican : https://gitlab.com/pages/pelican
 - VoidSpaceXYZ's example hosted : https://voidspacexyz.gitlab.io/pages/

