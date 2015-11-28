title: change protocal
date: 2014-11-17 00:42:26
tags: Github
---
或许你已经厌倦了每次`git push`的时候每次都要输入用户名密码，使用下面的方法可以让你使用ssh协议通过密钥验证的方式让你得到解脱。


* 准备好自己的密钥
`ssh-keygen -t rsa -C "your_name"`

* 登录`https://github.com/settings/ssh`，添加当前计算机的`~/.ssh/id_rsa.pub`公钥内容到github。

* 验证是否添加成功`ssh git@github.com`，如果返回以下内容，即代表添加成功！
`
Hi phpgao! You've successfully authenticated, but GitHub does not provide shell access.
`
* *保存项目最后一次修改并提交 --> 删除项目 --> clone项目,
采用ssh的方式克隆项目*`
git clone git@github.com:phpgao/BaiduSubmit.git`
* *修改https为ssh*`git remote set-url origin git@github.com:someaccount/someproject.git`

* 指定应该推送方式:
 > 
 >全部推送`git config --global push.default matching`
 >
 >部分推送`git config --global push.default simple`
 >
* `$ npm install hexo-deployer-git --save`
---
*顺便提一下git push总是报warning: push.default is unset错误，原来是版本兼容性的原因，低版本的git push如果不指定分支名，就会全部推送，而新版只会推送当前分支。*