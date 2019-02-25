---
title: WordPress 迁移/重装
date: 2019-01-23 06:06:06
tags: WordPress
categories: IT
---

<h2>缘由：</h2>

<strong>1.个人php版本过低（5.5）且有听说Wordpress不再支持php7.2以下版本；2.个人安装的是Centos6版本，之前安装一些功能不支持（Eg：V2ray）；</strong>

<h2>工具：</h2>

<ul>
<li>git + GIthub</li>
<li>phpMyAdmin</li>
</ul>

<h2>步骤：</h2>

<strong>1.数据库备份下载（phpMyAdmin）</strong>
登陆个人服务器ip地址，进入phpMyadmin，登陆数据库。把整个数据库备份下来；

<strong>2.网站整个文件夹备份</strong>
登陆ssh进入vps，用<a href="https://emperinter.tk/?p=124">git命令行</a>把整个网站文件夹备份到GIthub里面。
现在Github私库不要钱了，如果不考虑隐私，倒是一个很好的“云盘”

<!--more-->

<strong>3.重新搭建wordpress需要的lnmp和php等等</strong>
这个没什么说的，老样子;

<strong>4.新数据库完全删除</strong>
进入phpMyAdmin,删除自动安装的数据库；

<strong>5.导入备份数据库（phpMyAdmin上传有50M以下限制)</strong>

<strong>6.网站文件夹下载</strong>
登陆服务器，覆盖新安装的；

注意权限的重新赋予

<pre><code>chmod -R 755 /home/wwwroot && chown -R www /home/wwwroot
</code></pre>

<strong>7.wp-config 数据库信息更改（若新数据库的用户名等等更改了，未改则跳过）</strong>

<pre><code>vi /home/wwwroot/emperinter.tk/wp-config.php
</code></pre>

( 注意替换成自己的安装目录)

<strong>8.DNS解析设置</strong>

<h1>坑</h1>

<h3>WordPress您当前正在编辑显示最新文章的页面</h3>

<img src="https://www.softwen.com/wp-content/uploads/image/20180921/1537541209565552.jpg" alt="" />

<h3>解决方法：</h3>

1.进入phpMyAdmin

2.找到wp_posts(文章储存的地方）

3.点击结构

4.找到Id

<img src="https://res.cloudinary.com/dn6fdfasw/image/upload/v1549035472/%E6%96%B0%E5%BB%BA%E4%BD%8D%E5%9B%BE%E5%9B%BE%E5%83%8F.bmp" alt="" />

5.点击“更多”

6.点击“主键”

7.若提示失败则点击“修改”，后勾选"A_I"，点击保存，后返回再次点击“主键”；

8.若再次提示失败则单独导出wp_posts;

9.删除数据库里面的wp_posts;

10.重新导入wp_posts & <strong>注意再次导入时取消勾选“不要给零值使用自增 (AUTO_INCREMENT)”</strong>
<img src="https://res.cloudinary.com/dn6fdfasw/image/upload/v1549036305/%E6%8D%95%E8%8E%B71.png" alt="" />

11.再次重复步骤1-7即可；