---
title: Hexo的版本控制与持续集成
date: 2018-7-12 12:23:57
tags: hexo
categories: 转载

---
AppVeyor是目前唯一支持.NET开源项目的持续集成功能，运行环境是Windows，身为.NET开发者和软粉的我，怎么不支持一下这个有情怀的服务商呢？

太晚了，挖坑，明天继续写。

#### 第一步，创建CI项目
访问AppVeyor网站，注册或使用Github帐号授权登录，在PROJECTS页面点击【NEW PROJECT】，然后在右侧选择你的Hexo博客所在的仓库。
![11-1](http://ohl8u210m.bkt.clouddn.com/11-1.jpg)


#### 第二步，配置项目和环境变量
点击项目里的[SETTING]选项卡，配置以下几项：

Default branch -> [你存放原文件的分支名]
Branches to build -> 选择Only branches specified below,并填入[你存放原文件的分支名]
如下图，然后点击一下下方的Save按钮。
![11-2](http://ohl8u210m.bkt.clouddn.com/11-2.jpg)

点击右侧的Environment标签，添加环境变量:



|左对齐标题|	右对齐标题|
|--------|--------|
|STATIC_SITE_REPO|	你的仓库地址|
|TARGET_BRANCH	|编译后文件存放的分支|
|GIT_USER_EMAIL	|Github的用户邮箱|
|GIT_USER_NAME	|Github用户名|

如下图，然后点击一下下方的Save按钮。
![11-3](http://ohl8u210m.bkt.clouddn.com/11-3.jpg)


#### 第三步，获取Access Token
访问个人设置页面：
![11-4](http://ohl8u210m.bkt.clouddn.com/11-4.jpg)


点击边栏下方的【Personal access tokens】选项卡，并点击右上方的【Generate new token】按钮。Token description任意填写，下方的选项中全选repo即可。

最后，点击下方绿色的【Generate token】按钮。此时就能得到你的Access Token。

也可以参考官方文档

#### 第四步，加密Access Token
由于这个AccessToken是可以直接操作你的仓库的，而且配置文件是公开的，所以这时就要求对AccessToken进行加密。可到[AppVeyor Token加密页面](https://ci.appveyor.com/tools/encrypt)进行加密。把加密后的字符串填入下一步中的配置文件里。

#### 第五步，配置文件
在Hexo的根目录下新建一个appveyor.yml文件，写下以下内容
```
clone_depth: 5
# 这里是限制了只编译有源文件的分支，这样在创建了其它分支时就不会再次编译了
branches:
  only:
  - files#此处填写源码所在分支名
environment:
  access_token:
    secure: #加密后的access_token
install:
  - ps: Install-Product node 6.0 #原始环境的node 是4.x的版本，最好升级到最新的版本，防止Hexo的插件无法安装
  - node --version
  - npm --version
  - npm install
  - npm install hexo-cli -g
build_script:
  - hexo generate
artifacts:
  - path: public
on_success:
  - git config --global credential.helper store
  - ps: Add-Content "$env:USERPROFILE\.git-credentials" "https://$($env:access_token):x-oauth-basic@github.com`n"
  - git config --global user.email "%GIT_USER_EMAIL%"
  - git config --global user.name "%GIT_USER_NAME%"
  - git clone --depth 5 -q --branch=%TARGET_BRANCH% %STATIC_SITE_REPO% %TEMP%\static-site
  - cd %TEMP%\static-site
  - del * /f /q
  - for /d %%p IN (*) do rmdir "%%p" /s /q
  - SETLOCAL EnableDelayedExpansion & robocopy "%APPVEYOR_BUILD_FOLDER%\public" "%TEMP%\static-site" /e & IF !ERRORLEVEL! EQU 1 (exit 0) ELSE (IF !ERRORLEVEL! EQU 3 (exit 0) ELSE (exit 1))
  - git add -A
  - git commit -m "Update Static Site"
  - git push origin %TARGET_BRANCH%
  - appveyor AddMessage "Static Site Updated"
```
大致的意思是从github仓库的当前分支拉取下来，编译成静态文件后，在push到目标分支。由于AppVeyor环境中是通过Access Token访问我们的仓库的，而Hexo自带的部署则在访问的过程中需要我们输入帐号密码，所以Hexo g -d的命令就不适合在这里使用。需要先编译成静态文件，再把public文件夹的静态文件push到目标分支。

最后，把这个文件提交到Github上就可以测试了！在AppVeyor的首页可以看到部署的过程和结果~
![11-5](http://ohl8u210m.bkt.clouddn.com/11-5.jpg)


别说我没告诉你，还可以添加一枚徽章装装逼哦！Build status

可以看看我的配置文件，以及底部的两篇参考文章~

参考文章：

[Hexo利用AppVeyor持续集成](https://formulahendry.github.io/2016/12/04/hexo-ci/)

原文链接：https://yangshunjie.com/Use-Appveyor-to-continuously-integrate-your-Hexo-blog.html