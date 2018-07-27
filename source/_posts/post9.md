---
title: hexo部署到GitHub懵逼版
date: 2018-04-26 13:28:56
tags: hexo
categories: 原创
copyright: true

---

#### 1.建立GitHub repositores

GitHub上创建自己博客同名的repositories登录到自己的github上，选择 new repositories ->创建 lushunde321 如图：我的github用户是lushunde321，所以我只能创建 lushunde321.github.io ，这里是github默认同名的才会被github page 创建blog。直接点击cheated repoisitory ,弹出如下页面，表示已经创建成功。
![](http://ohl8u210m.bkt.clouddn.com/9-1.png)

#### 2.下载安装git与node.js
①
方式一(官网下载)：https://git-scm.com/download/win (到此页面后，稍微等一下会有下载弹框)

方式二(csdn下载)：http://download.csdn.net/download/ainuser/9952103

安装git(按照图上选择即可)
![](http://ohl8u210m.bkt.clouddn.com/9-2.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-3.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-4.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-5.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-6.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-7.jpg)
![](http://ohl8u210m.bkt.clouddn.com/9-8.jpg)

至此，安装git步骤结束。

②

下载node.js

下载方式一：http://nodejs.org/download/

下载方式二：https://nodejs.org/en/

下载方式三：http://download.csdn.net/download/ainuser/9952074

安装node.js
#### 3. 设置Git连接GitHub的基本设置

全局配置切换到淘宝源

npm config set registry https://registry.npm.taobao.org
```python
npm config set registry https://registry.npm.taobao.org
```
设置全局配置user.name 和user.email

git config –global user.name “lushunde321” 
git config –global user.email “lushunde321@163.com”

展示效果
```Python
Lu@DESKTOP-GBTEDDT MINGW64 ~/Desktop
$ git config --global user.name "lushunde321"

Lu@DESKTOP-GBTEDDT MINGW64 ~/Desktop
$ git config --global user.email "lushunde321@163.com"

Lu@DESKTOP-GBTEDDT MINGW64 ~/Desktop
$

```
生成SSH密钥设置到Github(需先设置user.name和user.email)
```python
cd ~/.ssh 
ssh-keygen -t rsa -C “lushunde321@163.com”
```
展示效果
```python
Lu@DESKTOP-GBTEDDT MINGW64 ~/.ssh
$ cd ~/.ssh
bash: cd: /c/Users/Lu/.ssh: No such file or directory
Lu@DESKTOP-GBTEDDT MINGW64 ~/.ssh
$ ssh-keygen -t rsa -C "lushunde321@163.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Lu/.ssh/id_rsa):
Created directory '/c/Users/Lu/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Lu/.ssh/id_rsa.
Your public key has been saved in /c/Users/Lu/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:Ih5glTLSLXZMdKCFOQ0xe6hk/czngRQbgjd2oA8zymk lushunde321@163.com
The key's randomart image is:
+---[RSA 2048]----+
| .=&B=.          |
|..%@Bo+          |
| XOB+o           |
|=o*o= .          |
|oE .o=.oS        |
|.  . oo..        |
|    .  .         |
|                 |
|                 |
+----[SHA256]-----+

Lu@DESKTOP-GBTEDDT MINGW64 ~/.ssh
```
设置ssh key到GitHub 
默认生成ssh key在C:\Users\username.ssh文件夹中，复制 id_rsa.pub文件到 github->settings->SSH and GPG key->new ssh key 如图 
![](http://ohl8u210m.bkt.clouddn.com/9-9.png)

![](http://ohl8u210m.bkt.clouddn.com/9-10.png)

ssh设置是否成功测试

ssh -T git@github.com
```python
Lu@DESKTOP-GBTEDDT MINGW64 /Hexo
$ ssh -T git@github.com        #测试ssh连接
The authenticity of host 'github.com (192.30.255.113)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes      #第一次测试，yes即可
Warning: Permanently added 'github.com,192.30.255.113' (RSA) to the list of known hosts.
Hi lushunde321! You've successfully authenticated, but GitHub does not provide shell access.

Lu@DESKTOP-GBTEDDT MINGW64 /Hexo
$ ssh -T git@github.com            #第二次ssh测试
Hi lushunde321! You've successfully authenticated, but GitHub does not provide shell access.
```
基本设置完成。
#### 4.安装hexo插件
③：

安装hexo

首先在本地磁盘中建立一个Hexo文件夹用于存储本地文件(做本地文件保存以及测试使用)



然后在文件夹中右击打开git命令框(我第一次直接在桌面右击，所以命令行无效果)



在git命令框中安装Hexo(npm
 install -g hexo)



初始化(hexo init)
```
hexo init
```
配置github项目连接
找到hexo根目录下的_config.yml文件找到如下结构进行修改
```python
修改为：
deploy:
 	type: git
    repo: ssh://git@github.com/itbingcheng/itbingcheng.github.io
    branch: master
```
启动服务(npm install -->hexo server -->hexo clean -->hexo generate -->hexo deploy)



浏览器输入http://localhost:4000,按理来说应该会出现本地访问页面，但是按照此步骤可能不会出现

注意：访问本地页面的时候hexo server 不可以按ctrl+c停止服务，否则会报404

解决：(npm install hexo-deployer-git --save)



如果上述方法不行的话，可以试试下面的(可以的话，请忽略。)

sudo
 npm install hexo-server

npm
 install hexo-server --save

如果试过还不可以的话，请根据报错，复制到百度自行查找解决方案或者留言评论

重新部署更新(下面这条命令会经常用到)

(hexo
 clean -->hexo generate -->hexo deploy)

本地测试:



如果你们的跟我的不一样，正常，因为我的是已经更换了模板之后的，你们只要根据网址可以访问到页面即可



很多设置信息等都在setting里面大家可以去这里面找想要的设置选项等等信息
#### 5.绑定域名
<p><span style="font-size:18px;">然后设置网站解析(让你输入的IP是这样得到的)</span></p>
<p><span style="font-size:18px;">键盘快捷键win+r输入cmd回车/或者win+x-&gt;a-&gt;是</span></p>
<p><span style="font-size:18px;">得到如下dos窗口后输入ping ainusers.github.io(ainusers是我的名字，就是上面注册github项目的名字即你的用户名)</span></p>
<p><span style="font-size:18px;">因为你刚才创建的项目已经被放到github服务器上面了，所以你这样相当于租用了github的服务器</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827115339257?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">将IP输入到解析网站的弹框中即可完成解析</span></p>
<p><span style="font-size:18px;">还有三个需要设置的地方:</span></p>
<p><span style="font-size:18px;">A：<img src="https://img-blog.csdn.net/20170827115652192?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""></span></p>
<p><span style="font-size:18px;">B：在D盘Hexo目录下的source中建一个CNAME命名的文件夹(切记没有后缀)</span></p>
<p><span style="font-size:18px;">创建方式，</span></p>
<p><span style="font-size:18px;">右键新建txt文本-&gt;输入你购买的域名www.ainusers.top-&gt;保存关闭</span></p>
<p><span style="font-size:18px;">然后快捷键F2或者右键该文本重命名-&gt;将.txt后缀去掉-&gt;会提示文件不可用继续确定即可</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827120127610?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""></span></p>
<p><span style="font-size:18px;">内容如下所示</span></p>
<p><img src="https://img-blog.csdn.net/20170827120144791?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt="" style="font-size:18px;"></p>
<p><span style="font-size:18px;">C：绑定域名</span><img src="https://img-blog.csdn.net/20170827120657763?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""></p>
<p><img src="https://img-blog.csdn.net/20170827120723514?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></p>
<p><img src="https://img-blog.csdn.net/20170827120739967?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></p>
<p><img src="https://img-blog.csdn.net/20170827120758281?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></p>
<p><span style="font-size:18px;">域名从.github.io后缀修改成你的域名后缀，才可以说明你以上步骤正确。</span></p>
<p><span style="font-size:18px;">我在网上找了一个例子，比如下图所示</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827121118409?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>