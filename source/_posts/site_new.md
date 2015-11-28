title: Deploy New Website
date: 2014-09-21 00:31:07
tags: Github
---
<font size ='3' color="red">
```js
$ npm install hexo -g

//setup
$ hexo init nacker
$ cd nacker
$ npm install

//start server
$ hexo s

//create new post
$ hexo new "new page"

//generate static files
$ hexo g

```
```c
$ cd nacker
$ git init
$ git checkout --orphan dev
$ git add .
$ git commit -m"deploy nacker"

//make a repository named nacker
$ git remote add origin https://github.com/adanac/nacker.git

$ git push origin dev.
$ hexo generate

//edit _config.yml file
deploy: type: git
repo: git@github.com:adanac/nacker.git
$ npm install hexo-deployer-git --save
$ hexo deploy
```
