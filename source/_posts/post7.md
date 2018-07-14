---
title: linux系统学习
date: 2018-03-29 10:20:56
tags: linux
categories:	原创

---
##### 系统目录
![](http://ohl8u210m.bkt.clouddn.com/7-1.jpg)

除了home文件夹其他文件夹不要乱动
ect文件夹 所有文件和软件程序的配置文件
lib文件夹    库文件夹
home文件夹    其中有个家目录是你登陆后默认位置
bin    可执行程序


_ _ _


##### Ubuntu实用快捷键:
Alt+Shift+数字：分屏显示

_ _ _

##### 常用命令:
![](http://ohl8u210m.bkt.clouddn.com/7-2.png)
cd Desktop    切换目录
pwd  显示路径
touch 文件名    创建文件
clear 清屏
mkdir 文件夹    创建文件夹
cd .. 返回上层目录
cd ../.. 返回上两层
cd -返回上次路径
cd ～ 家目录

mkdir /a/b/c -p  创建多层目录
mv a  b     重命名
mv a  目录    移动
cp A B   拷贝A到B
cp  A  B -r拷贝A目录
保存退出vim：1. ：wq     2. :x     3. shift+ZZ

输入python    》》》 模式 交互模式

ipython3     既可以输入python语法 也能用linux 命令

通过终端打开新的sublime或者通过终端用sublime打开文件直接输入subl

*/etc/apt/sources.list     源地址 文件    更新 源地址文件后要使用 apt-get update 使其生效*

ls /    斜杠代表根目录
ls /bin    根目录下的bin文件列表
ls -选项   -a 隐藏显示 -l 列表显示 -h 显示大小

通配符
*     匹配任意个字符
？     匹配一个任意字符
[] [”和“]”将字符组括起来，表示可以匹配字符组中的任意一个。“-”用于表示字符范围。
Ubuntu软件操作的相关命令sudo apt-get update 更新源

sudo apt-get install package 安装包
=
sudo apt-get remove package 删除包

sudo apt-cache search package 搜索软件包

sudo apt-cache show package 获取包的相关信息，如说明、大小、版本等

sudo apt-get install package --reinstall 重新安装包

sudo apt-get -f install 修复安装

sudo apt-get remove package --purge 删除包，包括配置文件等

sudo apt-get build-dep package 安装相关的编译环境

sudo apt-get upgrade 更新已安装的包

sudo apt-get dist-upgrade 升级系统

sudo apt-cache depends package 了解使用该包依赖那些包

sudo apt-cache rdepends package 查看该包被哪些包依赖

sudo apt-get source package 下载该包的源代码

sudo apt-get clean && sudo apt-get autoclean 清理无用的包

sudo apt-get check 检查是否有损坏的依赖

##### sh脚本
1.将命令写入sh文件中。
2.给予文件执行权限.
3../文件名  即可执行sh脚本

