---
title: Hexo博客多台电脑设备同步管理
date: 2019-02-22 21:39:07
tags: hexo
categories: IT
---


## 环境配置

相关环境
* 安装Node.js
* 安装git
* 安装hexo
	
## 创建分支
	 hexo生成的静态博客文件都是上传到GitHub上的, 且默认放在master分支上, 而一些相关的配置文件都在本地

* hexo的源文件（部署环境文件）可以都放在hexo分支上（可以新创建一个hexo分支），换新电脑时，直接git clone hexo分支

<!--more-->

- 对username.github.io仓库新建hexo分支

在Github的username.github.io仓库上新建一个hexo(分支名字可自定义)分支, 在下图箭头位置输入分支名字,回车即可创建成功

- 设置默认分支切换到该hexo分支，

并在该仓库->Settings->Branches->Default branch中将默认分支设为hexo，save保存

- 配置文件上传导Github该步骤需要在搭建博客的电脑上操作(博客配置文件和主题配置文件所在的电脑上操作)

- 克隆hexo分支(创建博客是的电脑平台)
	* 将上述新建的hexo分支克隆到本地, 在终端中cd进入该username.github.io文件目录
	* 在当前目录使用Git Bash执行git branch命令查看当前所在分支，应为新建的分支hexo
	~~~
	 git branch
	 *hexo
	~~~
	* 如果用Sourcetree软件管理代码的话, 克隆到本地的项目可能没有username.github.io层级, 所有文件都在根目录下, 操作上都不影响, 只需要记住操作要在文件的根目录下即可
- 上传部署文件
	* 先将本地博客的部署文件（Hexo目录下的全部文件）全部拷贝进username.github.io文件目录中去
	* 然后安装要用到的一些插件, 有的可能不需要, 但都安装了貌似没有任何影响

> npm install hexo-generator-index --save
> npm install hexo-generator-archive --save
> npm install hexo-generator-category --save
> npm install hexo-generator-tag --save
> npm install hexo-server --save
> npm install hexo-deployer-git --save
> npm install hexo-deployer-heroku --save
> npm install hexo-deployer-rsync --save
> npm install hexo-deployer-openshift --save
> npm install hexo-renderer-marked@0.2 --save
> npm install hexo-renderer-stylus@0.2 --save
> npm install hexo-generator-feed@1 --save
> npm install hexo-generator-sitemap@1 --save
> npm install hexo-generator-search --save
> npm install hexo-generator-searchdb --save复制代码

* 最后就是讲所有的文件都提交到hexo分支

* 提交时考虑以下注意事项

	* 将themes目录以内中的主题的.git目录删除（如果有），因为一个git仓库中不能包含另一个git仓库，否则提交主题文件夹会失败
	* 后期需要更新主题时在另一个地方git clone下来该主题的最新版本，然后将内容拷到当前主题目录即可
	* 最后用终端或者管理工具将所有文件提交到hexo分支		master分支和hexo分支各自保存着一个版本，master分支用于保存博客静态资源，提供博客页面供人访问；hexo分支用于备份博客部署文件，供自己维护更新，两者在一个GitHub仓库内也不会有任何冲突

## 同步到其他电脑
	
	* 将新电脑的生成的ssh key添加到GitHub账户上
	* 克隆username.github.io库的hexo分支到本地，此时本地git仓库处于hexo分支
	* 切换到username.github.io目录，执行npm install(由于仓库有一个.gitignore文件，里面默认是忽略掉node_modules文件夹的，也就是说仓库的hexo分支并没有存储该目录，所以需要install下)

> 如果node_modules文件没有丢失, 可不执行该操作
	
	* 到这里了就可以开始在自己的电脑上写博客了！
	* 需要注意的是每次更新博客之后, 都要把相关修改上传到hexo分支
	* 每次换电脑更新博客的时候, 在修改之前最好也要git pull拉取一下最新的更新


