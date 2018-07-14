---
title: 啦啦啦
date: 2018-01-29 23:14:38
tags:
---
SSSSR 多用户配置 - Leonn 的博客
目录


	1. 配置方法


	1. SS 单用户配置
	2. SSR 单用户配置
	3. SS 多用户配置
	4. SSR 多用户配置


	1. 注意事项


	1. 重启 SS
	2. 开启端口

搭建教程参考我以前写的

	* 这里只说如何修改配置，一定注意看最后写的注意事项！

配置方法

SS 单用户配置


	* 默认的就是单用户的，我解释下含义
	* 配置文件路径：/etc/shadowsocks.json
	* 注意使用的时候删除备注信息

{ "server":"0.0.0.0", "server_port":8989, /* 这个是你的SS端口*/"local_address":"127.0.0.1", "local_port":1080, "password":"yourpassword", /* 这个是你的SS密码*/"timeout":300, "method":"aes-256-cfb", /* 这个是你的SS加密协议，*/"fast_open": false}

SSR 单用户配置


	* 默认的就是单用户的，我解释下含义
	* 配置文件路径：/etc/shadowsocks.json
	* 注意使用的时候删除备注信息

{ "server":"0.0.0.0", "server_ipv6": "[::]", "server_port":8989, /* 这个是你的SSR端口*/"local_address":"127.0.0.1", "local_port":1080, "password":"yourpassword", /* 这个是你的SSR密码*/"timeout":300, "method":"aes-256-cfb", "protocol": "auth_sha1_compatible", /* 这个是你的SSR加密协议，*/"protocol_param": "", /* 这个是你的SSR加密参数，不用填，*/"obfs": "http_simple_compatible", /* 这个是你的SSR混淆协议，*/"obfs_param": "", /* 这个是你的SSR混淆参数，不用填，*/"redirect": "", "dns_ipv6": false, "fast_open": false, "workers": 1}

SS 多用户配置


	* 配置文件路径：/etc/shadowsocks.json
	* 注意使用的时候删除备注信息
	* 多用户多端口配置和单用户相比，需要将内容替换为以下的

{ "server":"0.0.0.0", "local_address":"127.0.0.1", "local_port":1080, "port_password":{ "8989":"password0", /* 这个是你的SS端口和密码*/"9001":"password1", /* 这个是你的SS端口和密码*/"9002":"password2", /* 这个是你的SS端口和密码*/"9003":"password3", /* 这个是你的SS端口和密码*/"9004":"password4"/* 这个是你的SS端口和密码,如果不够可以继续模仿增加*/ }, "timeout":300, "method":"aes-256-cfb", /* 这个是你的SS加密协议，*/"fast_open": false}
