---
title: Git
date: 2019-02-23 01:29:06
tags: Git
categories: IT
---

## 我学习参考了一下网站：

[Git教程 | 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
[Git教材 | 菜鸟教程](http://www.runoob.com/git/git-tutorial.html)
[Key配置 | CSDN](https://blog.csdn.net/gdutxiaoxu/article/details/53573399)
[YOUTUBE | 学习视频教程](https://youtu.be/9zfQ0gVp6I4)

## 下载安装(ubuntu下）
我使用的环境是Ubuntu 18.04，其他系统上问题和流程应该类似 可以参照  Git安装配置|菜鸟教程

<!--more-->

> apt-get install libcurl4-gnutls-dev libexpat1-dev gettext \libz-dev libssl-dev

> apt-get install git

> git --version
git version 1.8.1.2

## 设置Git的user name和email：(如果是第一次的话)

> git config --global user.name "你的Github用户名"

> git config --global user.email "你的Github注册邮箱"

## 查看个人信息设置
> git config --list
- Git Key配置（我几天都卡在这里了)

参照:[GIt KEY 配置](https://blog.csdn.net/gdutxiaoxu/article/details/53573399)

* 检查是否已经有SSH Key.*

> cd~/.ssh
接着输入ls，

> ls
列出该文件下的文件，看是否存在 id_isa 和 id_isa.pub 文件（也可以是别的文件名，只要 yourName 和 yourName.pub 承兑存在），如果存在的话，证明已经存在 ssh key了，可以直接跳过生成密钥这一步骤，

- 生成密钥

> ssh-keygen -t rsa -C "你的Github邮箱"

连续3个回车。如果不需要密码的话。 最后得到了两个文件：id_rsa和id_rsa.pub。
添加密钥到ssh-agent
确保 ssh-agent 是可用的。ssh-agent是一种控制用来保存公钥身份验证所使用的私钥的程序，其实ssh-agent就是一个密钥管理器，运行ssh-agent以后，使用ssh-add将私钥交给ssh-agent保管，其他程序需要身份验证的时候可以将验证申请交给ssh-agent来完成整个认证过程。

~~~bash
#start the ssh-agent in the background
eval "$(ssh-agent -s)"
~~~
	 
添加生成的 SSH key 到 ssh-agent。

> ssh-add ~/.ssh/id_rsa

登陆Github, 添加 ssh
打开个人主页 点击个人头像 点击Settings 点击SSH and GPG keys 点击new SSH keys 把id_rsa.pub文件里的内容复制到key里面去（Title 随便填）

 
测试：

> ssh -T git@github.com
	 
你将会看到：

> Hi 你的Github用户名! You’ve successfully authenticated,but GitHub does not provide shell access.

Git 管理远程仓库上传本地仓库
    * 
创建文件夹（必须和Github远程仓库同名）
	* 
打开文件夹
	* 
- 初始化(会生成一个.git文件夹)

> git init

- 创建/修改好自己的文件
- 添加到暂存区
> git add 文件名

- 添加到本地仓库

> git commit -m '描述'
 
- 添加远程仓库链接

> git remote add origin 远程仓库链接
 
- 推送至Github

> git push -u origin master

- 克隆远端仓库

> git clone 远程仓库链接