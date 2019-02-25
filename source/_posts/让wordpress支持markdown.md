---
title: 让wordpress支持markdown
date: 2019-02-23 01:39:07
tags: 
	- wordpress
	- markdown
categories: IT
---

# 缘由
几天前，我朋友看了我的博客说道，你的代码在博客里面排版一点也不美观，也不能高亮，于是向我推荐了markdown，我搜了相关与markdown和代码高亮的资料，并不断尝试找到了以下方法。

# 方法
#### 使用插件(可直接在插件里面搜到)
- **Disable Gutenberg**
插件wordpress5.0（5.0一下版本未测试过）需要禁用原版编辑器，**否则**会在代码框中出现 **乱码** 的问题（比如在C++文件中会把 << 转换掉 )
- **WP Editor.md**
markdown编辑器插件，我使用这几天感觉还不错！

<!--more-->

# 使用体验
- **可实时在编辑框右侧看到文章的排版布局;**
![](https://res.cloudinary.com/dn6fdfasw/image/upload/v1544521834/2018-12-11_17-48-28_%E7%9A%84%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE.png)
- **效率极高**
这得益于markdown的语法，不过让人头疼的是要背一些语法，不过很简单！
[语法学习一个网站](http://xianbai.me/learn-md/article/about/readme.html)
[语法学习一个博客](https://www.jianshu.com/p/45faddb1526d)
- **注重文章本身的书写**
不用去按鼠标即可操作。可以随时随地完成文章的书写和排版，排版只要在文章中插入语法即可。比如我在记事本里面写好这个，复制粘帖到编辑器里面，然后检查是否有排版写错了的地方，即可发表;
- **功能强大**
按语法可以在文章中甘特图，流程图，表格等等:
```
graph TD
A[NO.1]-->B(No.2)
B --> C{think}
C -->|是| C1[No.3]
C -->|否| C2[No.4]
C -->|随机|D[No.4]
```
| 序号 | Value | Qty |
|: - :| : - : | : - : |
|1|PDF阅读器|正版|
|2|有道云笔记|正版|
|3|百度网盘|正版|
|4|MS office|盗版|

- **可全屏编辑文章**

- **支持代码高亮**
[我的文章示例](https://emperinter.tk/2018/10/17/%e7%94%a8-c-%e5%92%8c%e6%a0%88%e5%ae%9e%e7%8e%b0%e6%95%b0%e5%88%b6%e8%bd%ac%e6%8d%a2%e5%92%8c%e8%bf%9b%e5%88%b6%e8%bd%ac%e6%8d%a2/)
*应该还可以加入什么代码高亮插件支持copy，之前有过，后来不小心删了就搞忘了*
![](https://res.cloudinary.com/dn6fdfasw/image/upload/v1544522348/2018-12-11_17-58-41_%E7%9A%84%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE.png)
- **可使用tab键**
程序员常用

- **添加图片方便**
插入图片只要网址即可，比如google一个图片,按格式 **![图片地址]** 即可;

建议注册一个 [cloudinary](cloudinary) 来存放自己的图片后，获取地址来添加的blog（可优化主机内存，加快访问速度）;
示例如下：
![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Tor-logo-2011-flat.svg/1200px-Tor-logo-2011-flat.svg.png)

#### 更多功能和体验欢迎大家继续去探索和发现，如有什么值得高兴的欢迎和我交流！

