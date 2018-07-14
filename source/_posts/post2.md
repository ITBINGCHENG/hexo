---
title: VPS安装Aria2+WEBUI搭建离线下载神器
date: 2018-02-01 23:11:38
categories: 转载
tags: 
	- 离线下载
	- Aria2
---
<span style="font-size:16px;line-height:2;">在vps上面安装Aria2实现离线下载。</span><br>

<span style="font-size:16px;line-height:2;">本教程共三个部分</span><br>

#### <span style="font-size:16px;line-height:2;"><strong>一、安装aria2</strong></span><br>

<span style="font-size:16px;line-height:2;">1、安装aria2的方法很简单，一条命令就够了</span><br>

<span style="font-size:16px;line-height:2;">centos 7：</span> <br>

<span style="font-size:16px;line-height:2;"><span style="color:#337FE5;">yum install epel-release</span><span style="color:#337FE5;"></span><br>

</span> <span style="font-size:16px;line-height:2;color:#337FE5;">yum install aria2</span><br>

<br>

<span style="font-size:16px;line-height:2;">ubuntu：</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">apt-get install aria2</span><br>

<br>

<span style="font-size:16px;line-height:2;">如果出现【Unable to locate package aria2】或者【No package aria2 available.】的错误，表示你需要更新一下。</span><br>

<span style="font-size:16px;line-height:2;">centos：<span style="color:#337FE5;">yum update</span></span><br>

<span style="font-size:16px;line-height:2;">ubuntu：<span style="color:#337FE5;">apt-get update</span></span><br>

<br>

<span style="font-size:16px;line-height:2;">系统版本不同源自带的aria2版本也会不同，centos6的话是aria2 16.0X的版本，centos7能到18.x，至于ubuntu，一向包更新的比较快，应该都是最新（苏苏未测试）。如果你对版本不满意，也可以自己下载源码后编译，这个不做讨论。</span><br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<span style="font-size:16px;line-height:2;">2、下载安装好了以后，远程下载文件就很简单了</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">单个文件下载</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c http://example.org/mylinux.iso</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">从两个来源（更多也可以）</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c http://a/f.iso ftp://b/f.iso</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">BitTorrent</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c http://example.org/mylinux.torrent</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">BitTorrent Magnet URI</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c 'magnet:?xt=urn:btih:248D0A1CD08284299DE78D5C1ED359BB46717D8C'</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">Metalink</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c http://example.org/mylinux.metalink</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">文本文件uri.text中的链接(URI)</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c -i uri.txt</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">&nbsp;</span><span style="font-size:16px;line-height:2;color:#CC33E5;">显示种子中包含了哪些文件</span><br>

<span style="font-size:16px;line-height:2;color:#CC33E5;">aria2c -S bit.torrent</span><br>

<br>

<span style="font-size:16px;line-height:2;"><a target="_blank" href="http://ohl8u210m.bkt.clouddn.com/2-1.jpg" id="ematt:1435"><img src="http://ohl8u210m.bkt.clouddn.com/2-1.jpg" title="点击查看原图" alt="a1.jpg" border="0" width="479" height="173"></a></span><br>

<br>

<br>



#### <span style="font-size:16px;line-height:2;"><strong>二、配置aria2</strong></span><br>

<span style="font-size:16px;line-height:2;">1、开启RPC远程管理命令</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">aria2c --enable-rpc --rpc-listen-all=true --rpc-allow-origin-all -c -D</span><br>

<span style="font-size:16px;line-height:2;">说明: 这个命令在VPS上运行即可开启rpc服务,可以用多种方式进行远程管理,但貌似不会保存配置文件,重启后会丢失之前的下载记录</span><br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<span style="font-size:16px;line-height:2;">2、让配置文件不丢失</span><br>

<span style="font-size:16px;line-height:2;">用winscp新建以下文件【/root/aria2.conf】，文件内容如下：</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">## '#'开头为注释内容, 选项都有相应的注释说明, 根据需要修改 ##</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">## 被注释的选项填写的是默认值, 建议在需要修改时再取消注释 &nbsp;##</span><br>

<br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#允许rpc</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">enable-rpc=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#允许所有来源, web界面跨域权限需要</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">rpc-allow-origin-all=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#允许非外部访问</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">rpc-listen-all=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#RPC端口, 仅当默认端口被占用时修改</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#rpc-listen-port=6800</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#用户名</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">rpc-user=susu</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#密码</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">rpc-passwd=138vps</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">###速度相关&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#最大同时下载数(任务数), 路由建议值: 3</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-concurrent-downloads=5</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#断点续传</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">continue=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#同服务器连接数</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-connection-per-server=5</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#最小文件分片大小, 下载线程数上限取决于能分出多少片, 对于小文件重要</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">min-split-size=20M</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#单文件最大线程数, 路由建议值: 5</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">split=10</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#下载速度限制 0 不限制</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-overall-download-limit=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#单文件速度限制</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-download-limit=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#上传速度限制</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-overall-upload-limit=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#单文件速度限制</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">max-upload-limit=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#断开速度过慢的连接</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#lowest-speed-limit=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#验证用，需要1.16.1之后的release版本</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#referer=*</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">###进度保存相关&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">input-file=/root/aria2.session</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">save-session=/root/aria2.session</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#定时保存会话，需要1.16.1之后的release版</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#save-session-interval=60</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">###磁盘相关&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#文件保存路径, 默认为当前启动位置</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">dir=/var/www/html/</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#文件缓存, 使用内置的文件缓存, 如果你不相信Linux内核文件缓存和磁盘内置缓存时使用, 需要1.16及以上版本</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#disk-cache=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#另一种Linux文件缓存方式, 使用前确保您使用的内核支持此选项, 需要1.15及以上版本</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#enable-mmap=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#文件预分配, 能有效降低文件碎片, 提高磁盘性能. 缺点是预分配时间较长</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#所需时间 none &lt; falloc ? trunc &lt;&lt; prealloc, falloc和trunc需要文件系统和内核支持</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">file-allocation=prealloc</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">###BT相关&nbsp;</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#启用本地节点查找</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">bt-enable-lpd=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#添加额外的tracker</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#bt-tracker=&lt;URI&gt;,…</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#单种子最大连接数</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#bt-max-peers=55</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#强制加密, 防迅雷必备</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#bt-require-crypto=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#当下载的文件是一个种子(以.torrent结尾)时, 自动下载BT</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">follow-torrent=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#BT监听端口, 当端口屏蔽时使用</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#listen-port=6881-6999</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#aria2亦可以用于PT下载, 下载的关键在于伪装</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#不确定是否需要，为保险起见，need more test</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">enable-dht=false</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">bt-enable-lpd=false</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">enable-peer-exchange=false</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#修改特征</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">user-agent=uTorrent/2210(25130)</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">peer-id-prefix=-UT2210-</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#修改做种设置, 允许做种</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">seed-ratio=0</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#保存会话</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">force-save=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">bt-hash-check-seed=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">bt-seed-unverified=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">bt-save-metadata=true</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#定时保存会话，需要1.16.1之后的某个release版本</span><br>

<span style="font-size:16px;line-height:2;color:#9933E5;">#save-session-interval=60</span><br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<span style="font-size:16px;line-height:2;">3、然后运行该命令</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">aria2c --conf-path=/root/aria2.conf -D</span><br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<p>

	<span style="font-size:16px;line-height:2;">4、开机自动启动，</span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;">centos</span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;">到【/etc/rc.d/rc.local】文件下面加入下面这一行</span> 

</p>

<span style="font-size:16px;line-height:2;color:#337FE5;">aria2c --conf-path=/root/aria2.conf -D &amp;</span><br>

<p>

	<br>

</p>

<p>

	<span style="font-size:16px;line-height:32px;white-space:normal;">ubuntu</span> 

</p>

<p>

	<span style="font-size:16px;line-height:32px;white-space:normal;">到【/etc/rc.local</span><span style="font-size:16px;line-height:32px;white-space:normal;"></span><span style="font-size:16px;line-height:32px;white-space:normal;">】文件内</span><span style="font-size:16px;">，在【exit 0】前面加入下面一行</span> 

</p>

<p>

	<span style="color:#337FE5;font-size:16px;line-height:32px;white-space:normal;">aria2c --conf-path=/root/aria2.conf -D &amp;</span><span style="font-size:16px;"></span> 

</p>

<p>

	<br>

</p>

<p>

	<br>

</p>



#### <span style="font-size:16px;line-height:2;"><strong>三、安装WEBUI</strong></span><br>

<span style="font-size:16px;line-height:2;">1、首先要安装http服务，注意，如果有iptables，要先开放80端口，具体教程请本博客搜索 iptables</span><br>

<span style="font-size:16px;line-height:2;">centos：</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">yum &nbsp;-y &nbsp;install &nbsp;httpd</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">chkconfig --levels 235 httpd on</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">service httpd start</span><br>

<br>

<span style="font-size:16px;line-height:2;">ubuntu：</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">apt-get -y install apache2</span><br>

<br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<span style="font-size:16px;line-height:2;">2、到https://github.com/ziahamza/webui-aria2 下载最新的WebUI压缩包。或者：https://pan.lanzou.com/1131145，再或者：http://dl.138vps.com/linux/aria2_webui.tar.gz</span><br>

<span style="font-size:16px;line-height:2;">解压后上传到 【/var/www/html/】，并改名为【webui】。同时设置权限：</span><br>

<span style="font-size:16px;line-height:2;color:#337FE5;">chmod 755 /var/www/html/webui</span><br>

<br>

<br>

<span style="font-size:16px;line-height:2;">3、http://IP地址/webui 就可访问成功；如果报错，在“设置”--&gt; “服务器设置”中“主机：”后后面填写自己的IP地址就可；</span><br>

<p>

	<br>

</p>

<p>

	<br>

</p>

<span style="font-size:16px;line-height:2;">如果Aria2.conf配置文件中启用了RPC安全认证，需要在WEB客户端设置中填入RPC用户名和密码，否则客户端报错。</span><br>

<p>

	<br>

</p>

<p>

	<span style="font-size:14px;"><span style="color:#E56600;font-size:16px;">也可以使用苏苏更为喜欢的另一个web管理面板</span><span style="font-size:16px;">：</span></span><a href="http://dl.138vps.com/linux/ariang.tar.gz" rel="external nofollow" target="_blank"><span style="color:#4C33E5;font-size:16px;">http://dl.138vps.com/linux/ariang.tar.gz</span></a>

</p>

<p>

	<br>

</p>

<p>

	<span style="font-size:16px;line-height:2;">苏苏的教程中，难免有谬误的地方，具体的玩法，就自己琢磨吧。</span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><br>

</span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><span style="white-space:normal;font-size:16px;">配合h5ai，实现下载视频后在线播放：</span><span style="white-space:normal;color:#4C33E5;font-size:16px;"><span style="color:#4C33E5;font-family:微软雅黑, 'Arial Narrow', HELVETICA;font-size:16px;line-height:24px;text-indent:28px;white-space:normal;background-color:#FFFFFF;"><a href="http://www.138vps.com/vpsjc/946.html" target="_blank" style="white-space:normal;"><span style="color:#4C33E5;">http://www.138vps.com/vpsjc/946.html</span></a></span></span><br>

</span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><span style="white-space:normal;color:#4C33E5;font-size:16px;"><br>

</span></span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><span style="white-space:normal;color:#4C33E5;font-size:16px;"><span style="color:#000000;">据反馈，centos7安装好WebUI后，连接上去会出现“</span><span style="color:#000000;font-family:微软雅黑;font-size:16px;line-height:30px;white-space:normal;background-color:#FFFFFF;">上次连接请求未成功，正在尝试使用另一个配置 糟糕！ 无法连接到 Aria2 RPC 服务器，将在10秒后重试........</span><span style="color:#000000;"></span><span style="color:#000000;">”的错误，这个时候再运行一遍第二步的第1步代码就好了：</span></span></span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><span style="white-space:normal;color:#4C33E5;font-size:16px;"><span style="color:#337FE5;font-family:微软雅黑;font-size:14px;line-height:20px;white-space:normal;background-color:#FFFFFF;">aria2c --enable-rpc --rpc-listen-all=true --rpc-allow-origin-all -c -D</span><span style="color:#337FE5;"></span><br>

</span></span> 

</p>

<p>

	<span style="font-size:16px;line-height:2;"><span style="white-space:normal;color:#4C33E5;font-size:16px;"><br>

</span></span> 

</p>			

			<p></p>

			        