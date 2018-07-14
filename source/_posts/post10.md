---
title: hexo部署到GitHub
date: 2018-04-26 13:28:56
tags: hexo
categories: 原创

---

<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;"><span style="font-family:Arial;font-size:18px;line-height:26px;"><span style="color:rgb(51,51,51);">在github上面创建项目(借用github服务器)</span></span></span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;"><span style="font-family:Arial;font-size:18px;line-height:26px;"><span style="color:rgb(51,51,51);"><img src="https://img-blog.csdn.net/20170827113105472?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></span></span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;"><span style="font-family:Arial;font-size:18px;line-height:26px;"><span style="color:rgb(51,51,51);"><img src="https://img-blog.csdn.net/20170827113226349?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></span></span></p>
<p><span style="font-size:18px;">很多设置信息等都在setting里面大家可以去这里面找想要的设置选项等等信息</span></p>
<p><img src="https://img-blog.csdn.net/20170827113449269?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></p>
<p><strong><span style="font-size:18px;">搭建个人博客=域名(外网可访问的地址)+外网服务器(外网存储文件图片的地方)+解析(本地与服务器做映射)</span></strong></p>
<p><strong><span style="font-size:18px;">①：</span></strong></p>
<p><strong><span style="font-size:18px;">下载git</span></strong></p>
<p><span style="font-size:18px;">方式一(官网下载)：https://git-scm.com/download/win(到此页面后，稍微等一下会有下载弹框)</span></p>
<p><span style="font-size:18px;">方式二(csdn下载)：http://download.csdn.net/download/ainuser/9952103</span></p>
<p><strong><span style="font-size:18px;">安装git(按照图上选择即可)</span></strong></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827093914311?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827093929117?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827094005220?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827094024947?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827094051631?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827094104359?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827094117906?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827094130781?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">至此，安装git步骤结束。</span></p>
<p><span style="font-size:18px;">②</span></p>
<p><span style="font-size:18px;"><strong>下载node.js</strong></span></p>
<p><span style="font-size:18px;">下载方式一：<span style="font-family:Arial;line-height:26px;"><span style="font-family:'Microsoft YaHei';"><a href="http://nodejs.org/download/" style="color:rgb(202,0,0);text-decoration:none;" target="_blank">http://nodejs.org/download/</a></span></span></span></p>
<p><span style="font-size:18px;"><span style="font-family:Arial;line-height:26px;">下载方式二：https://nodejs.org/en/</span></span></p>
<p><span style="font-size:18px;"><span style="font-family:Arial;line-height:26px;">下载方式三：http://download.csdn.net/download/ainuser/9952074</span></span></p>
<p><span style="font-size:18px;"><strong>安装node.js</strong></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827101020621?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827101033115?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827101041106?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827101052270?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827101102499?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><img src="https://img-blog.csdn.net/20170827101111557?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">至此，node.js安装步骤完毕。</span></p>

#### 设置Git连接GitHub的基本设置

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
<p><span style="font-size:18px;">③：</span></p>
<p><span style="font-size:18px;"><strong>安装hexo</strong></span></p>
<p><span style="font-size:18px;">首先在本地磁盘中建立一个Hexo文件夹用于存储本地文件(做本地文件保存以及测试使用)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827102052285?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">然后在<span style="color:#cc0000;">文件夹中右击打开git命令框(我第一次直接在桌面右击，所以命令行无效果)</span></span></p>
<p><span style="font-size:18px;"><span style="color:#cc0000;"><img src="https://img-blog.csdn.net/20170827102357800?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></span></p>
<p><span style="font-size:18px;">在git命令框中安装Hexo(<span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">npm
 install -g hexo</span>)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827102933652?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">初始化(<span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">hexo</span><span class="hljs-keyword" style="margin:0px;padding:0px;border:0px;line-height:16.38px;font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;vertical-align:baseline;color:rgb(137,89,168);white-space:pre;background-color:rgb(232,242,251);">init</span>)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827103131590?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">启动服务(npm install --&gt;hexo server --&gt;hexo clean --&gt;hexo generate --&gt;hexo deploy)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827104107665?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><span style="color:rgb(51,51,51);font-family:'ff-tisa-web-pro-1', 'ff-tisa-web-pro-2', 'Lucida Grande', 'Hiragino Sans GB', 'Hiragino Sans GB W3', 'Microsoft YaHei', 'WenQuanYi Micro Hei', sans-serif;line-height:23.8px;">浏览器输入</span><a href="http://baixin.io/2015/08/HEXO%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/%E5%B0%B1%E5%8F%AF%E4%BB%A5%E7%9C%8B%E5%88%B0%E6%9C%80%E5%8E%9F%E5%A7%8B%E7%9A%84%E6%95%88%E6%9E%9C%E4%BA%86" style="margin:0px 4px;padding:0px;border:0px;line-height:23.8px;font-family:'ff-tisa-web-pro-1', 'ff-tisa-web-pro-2', 'Lucida Grande', 'Hiragino Sans GB', 'Hiragino Sans GB W3', 'Microsoft YaHei', 'WenQuanYi Micro Hei', sans-serif;vertical-align:baseline;color:rgb(0,104,139);" target="_blank">http://localhost:4000</a>,按理来说应该会出现本地访问页面，但是按照此步骤可能不会出现<br></span></p>
<p><span style="font-size:18px;"><span style="color:#ff0000;">注意：访问本地页面的时候hexo server 不可以按ctrl+c停止服务，否则会报404</span></span></p>
<p><span style="font-size:18px;">解决：(npm install hexo-deployer-git --save)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827105244408?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">如果上述方法不行的话，可以试试下面的(可以的话，请忽略。)</span></p>
<p><span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">sudo
 npm install hexo-server</span><br></span></p>
<p><span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">npm
 install hexo-server --save</span><span style="font-size:12.6px;"><br></span></span></span></p>
<p><span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">如果试过还不可以的话，请根据报错，复制到百度自行查找解决方案或者留言评论</span></span></span></p>
<p><span style="font-size:18px;">配置github项目连接使hexo d 命令可用
打开hexo主目录下_config.yml文件找到类似下面文字更改为相同：
<span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;font-size:12.6px;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"
>deploy:
> type: git
    repo: ssh://git@github.com/itbingcheng/itbingcheng.github.io</span><span class="hljs-comment" style="margin:0px;padding:0px;border:0px;font-size:12.6px;line-height:16.38px;font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;vertical-align:baseline;color:rgb(142,144,140);white-space:pre;background-color:rgb(232,242,251);"></span><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;font-size:12.6px;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">
    branch: master</span></span></p>

<p><span style="font-size:18px;"><span style="font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><span style="font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><strong><span style="color:#4d4d4c;">重新部署更新(</span><span style="color:#ff0000;">下面这条命令会经常用到</span><span style="color:#4d4d4c;">)</span></strong></span></span></span></p>
<p><span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><strong>(</strong></span></span></span><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">hexo
 clean --&gt;hexo generate --&gt;hexo deploy)</span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">本地测试:</span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;"><img src="https://img-blog.csdn.net/20170827110920903?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">如果你们的跟我的不一样，正常，因为我的是已经更换了模板之后的，你们只要根据网址可以访问到页面即可</span></p>

<p><span style="font-size:18px;"><strong>购买域名</strong></span></p>
<p><span style="font-size:18px;">我选的是阿里的，还有比如花生壳等等我就不列举了</span></p>
<p><span style="font-size:18px;">https://wanwang.aliyun.com/domain/<br></span></p>
<p><span style="font-size:18px;"><strong>购买流程(后缀不同，费用也不同，我买的是最便宜的.top后缀：3年三十多)</strong></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827113737818?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">下面的流程就跟淘宝购物一样了，别选多余的，就购买域名即可，其他的全家桶就不要购买了。</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827114247435?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">下面是我支付成功之后的截图</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827114335409?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">然后就是解析(通俗来讲也就是本地与服务器做映射)</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827114552581?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827114810622?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
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
<p><span style="font-size:18px;">修改_config.yml</span></p>
<p><span style="font-size:18px;"><img src="https://img-blog.csdn.net/20170827121348745?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvQWluVXNlcg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" alt=""><br></span></p>
<p><span style="font-size:18px;">查找repository方式</span></p>
<p><span style="font-size:18px;">我也忘记怎么找了，你直接把你的用户名和项目名替换即可</span></p>
<p><span style="font-size:18px;">例如:zhangsan.github.io</span></p>
<p><span style="font-size:18px;">替换之后http://github.com/zhangsan/zhangsan.github.io.git</span></p>
<p><span style="font-size:18px;">使git部署</span></p>
<p><span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);">npm
 install hexo-deployer-git --save</span></span></p>
<p><span style="font-size:18px;">基本的流程到这里快要结束了</span></p>
<p>最后执行:<span style="font-size:18px;"><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;background-color:rgb(232,242,251);"><span style="line-height:16.38px;"><strong></strong></span></span></span><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">hexo clean --&gt;hexo generate --&gt;hexo deploy</span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">你就可以看到你的博客了</span></p>
<p><span style="color:rgb(77,77,76);font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;line-height:16.38px;white-space:pre;font-size:18px;">记住，每次修改配置信息或者其他必须要执行上面的步骤，才可以使得配置信息生效。</span></p>
<p><span style="font-family:Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, serif;font-size:18px;color:#4d4d4c;"><span style="line-height:16.38px;white-space:pre;">还有就是上面的配置信息，主要流程就是:本地文件(配置github连接)-&gt;github(配置域名)-&gt;服务器域名</span></span></p>