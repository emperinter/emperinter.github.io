---
title: V2ray使用教程
date: 2019-02-22 00:06:23
tags: V2ray
categories: IT

---

# 缘由：
更换服务器为CentOs7系统以后就开始琢磨以前想尝试的V2ray来翻墙了，结果卡在了配置文件这儿，搜了很多资料感觉很复杂，弄明白一点后就搞了个极简教程！

## V2ray 官网服务器端/客户端 安装

这个按[官网步骤](https://toutyrater.github.io/prep/install.html)就行了，没什么说的；极简步骤如下：

- 查看服务器时间
对于 V2Ray，它的验证方式包含时间，就算是配置没有任何问题，如果时间不正确，也无法连接 V2Ray 服务器的，服务器会认为你这是不合法的请求。所以系统时间一定要正确，只要保证时间误差在90秒之内就没问题。

<!--more-->

~~~bash
 date -R
 Sun, 22 Jan 2017 10:10:36 -0500
~~~

- 校准为东八区(你客户端使用当地时间)

~~~bash
sudo date --set="2017-01-22 16:16:23"
Sun 22 Jan 16:16:23 GMT 2017
~~~
- 下载安装文件

~~~bash
wget https://install.direct/go.sh
~~~

- 安装

~~~bash
sudo bash go.sh
~~~
- 启动

~~~bash
sudo systemctl start v2ray配置文件
~~~
### 服务器端

#### 生产一个ID
[在线UUID生成器/用于生成一个随机id](https://www.uuidgenerator.net/)

*编辑配置文件*

> vi /etc/v2ray/config.json


~~~json
{
	"inbounds": [{
		"port": 16823, // 服务器监听端口（类似于SS的端口）
		"protocol": "vmess", // 主传入协议
		"settings": {
			"clients": [{
				"id": "63d6668a-b898-4404-B07C-9d804af7f78a", // 用户 ID，客户端与服务器必须相同/填入上述网站生成的ID
				"alterId": 64 //客户端与服务器必须相同
			}
		]}
	}],
	
	"outbounds": [{
		"protocol": "freedom", // 主传出协议
		"settings": {}
	}]
}
~~~

*检查配置是否有问题*

> /usr/bin/v2ray/v2ray -test -config /etc/v2ray/config.json

重新启动

> sudo systemctl start v2ray

### 安卓手机端配置

软件:[v2rayNG](https://play.google.com/store/apps/details?id=com.v2ray.ang&hl=zh)


手机端填入信息步骤如下:

1.选Vmess协议

2.填入信息于服务器配置相同

### Windows配置

[软件下载地址](https://github.com/v2ray/v2ray-core/releases)
	
- 直接解压到桌面
	
- 用记事本打开config.json，并写成一下信息（注意 服务器端口/id/alterId与服务器端的配置相同，否则无法运行）


~~~json
{
	"inbounds": [{
		"port": 1080, // 监听端口
		"protoco": "socks", // 入口协议为 SOCKS 5
		"sniffing": {
			"enabled: true,
			"destOverride": ["http", "tls"]
		},
	
		"settings": {
			"auth": "noauth" //socks的认证设置，noauth 代表不认证，由于 socks 通常在客户端使用，所以这里不认证
		}
	}],
	
	"outbounds": [{
		"protocol": "vmess", // 出口协议
		"settings": {
			"vnext": [{
				"address": "serveraddr.com", // 服务器地址，请修改为你自己的服务器 IP 或域名
				"port": 16823, // 服务器端口
				"users": [{
					"id": "63d6668a-b898-4404-B07C-9d804af7f78a", // 用户 ID，必须与服务器端配置相同
					"alterId": 64 // 此处的值也应当与服务器相同
				}]
			}]
		}
	}]
}
~~~

- 运行v2ray.exe
	
- 浏览器代理（需代理才能使用/以Firefox为例）



