---
title: Xmind破解
date: 2018-11-20 06:66:06
tages: 破解
categories: IT
---


## 缘由:

Xmind是一款好的思维导图软件,能进行很好的编辑,易于使用的界面,且平台较多(MAC,Windows,Linux,iphone,安卓),且能进行导出pdf等格式;但对于我们用户来说当然还是免费吸引较大了

### 经过:
- 1.刚开始使用是在windows平台,具体就不说了,看网站:[XMind破解](https://github.com/mounui/Xmind/tree/master/XMindCrack)
- 2.后来基本使用Ubuntu了,用wine可以使用一些windows软件;
- 3.最近学习要用就想到了windows版本,以前没有相关资料,但不知道怎么配置具体目录而失败!
- 4.最后呢!找到了教程:[教程来源](https://www.jianshu.com/p/9d93b1754549)

### 步骤:
- 1.去官网下载软件:[XMind下载](https://www.xmind.cn/download/xmind8/)(或我的网盘:[Xmind/百度网盘](https://pan.baidu.com/s/1PELdBG2dmDUAOEPZw95BbQ))
- 2.下载替换脚本[XMindCrack](https://pan.baidu.com/s/1uCaAObP2OFyVPymcyZxIIQ)
- 3.下载好最新XMind压缩包之后解压, 再解压XMind_amd64.tar.gz到XMind_amd64目录下.(我的是64bit的系统, 如果是32bit的系统解压到XMind_i386目录即可)
- 4.修改host:
shell下, 输入以修改host:
> sudo vi /etc/hosts
在文本末尾添加: 127.0.0.1 www.xmind.net
- 5.回到解压后的文件夹的根目录, 运行
> ./setup.sh
安装好依赖库之后, 再次进入XMind_amd64, 运行XMind.

- 6.在XMind主界面依次: Help -> License, 复制以下license key即可, 邮箱随便填:
~~~
XAka34A2rVRYJ4XBIU35UZMUEEF64CMMIYZCK2FZZUQNODEKUHGJLFMSLIQMQUCUBXRENLK6NZL37JXP4PZXQFILMQ2RG5R7G4QNDO3PSOEUBOCDRYSSXZGRARV6MGA33TN2AMUBHEL4FXMWYTTJDEINJXUAV4BAYKBDCZQWVF3LWYXSDCXY546U3NBGOI3ZPAP2SO3CSQFNB7VVIY123456789012345
~~~