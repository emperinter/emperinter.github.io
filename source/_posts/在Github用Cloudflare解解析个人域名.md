---
title: 在Github用Cloudflare解解析个人域名
date: 2019-02-25 21:00:22
tags: 网站建设
categories: IT
---

### 我是GitHub创建了两个分支（master/hexo）

- Steps:
1.在有.git的文件夹里面新建一个**CNAME**文件（_**无后缀**_），并写入个人申请的个人域名（像我的则为：emperinter.tk）;
2.push更新到Github;
3.在Github里面的xxx.github.io里面的设置里面找到GitHub Pages（_**两个分支都要修改，如只有一个master则只修改master即可，分支是否必须修改未尝试过。**_），并在Custom domain里面填入你的域名（格式同上）；
4.登陆Cloudflare，添加DNS为如下格式(注意修改为自己的域名)：

| Type | Name | Domain name |
|:-:|:-:|:-:|
|CNAME | @ | emperinter.tk 


# 最新发现
> 也要在source文件里面建一个CNAME文件，不然每次更新后都会导致在Github里面的设置失效。
