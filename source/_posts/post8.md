---
title: py网络编程
date: 2018-04-15 16:08:38
categories: 原创
tags: python3

---
### socket

- - -

##### 1.什么是socket
socket(简称 套接字) 是进程间通信的一种方式，它与其他进程间通信的一个主要不同是：

它能实现不同主机间的进程间通信，我们网络上各种各样的服务大多都是基于 Socket 来完成通信的

例如我们每天浏览网页、QQ 聊天、收发 email 等等
##### 2.创建socket
在 Python 中 使用socket 模块的函数 socket 就可以完成：

`socket.socket(AddressFamily, Type)`
说明：
函数 socket.socket 创建一个 socket，返回该 socket 的描述符，该函数带有两个参数：

Address Family：可以选择 AF_INET（用于 Internet 进程间通信） 或者 AF_UNIX（用于同一台机器进程间通信）,实际工作中常用AF_INET
Type：套接字类型，可以是 SOCK_STREAM（流式套接字，主要用于 TCP 协议）或者 SOCK_DGRAM（数据报套接字，主要用于 UDP 协议）
创建一个tcp socket（tcp套接字）
```python
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

print ('Socket Created')
创建一个udp socket（udp套接字）

import socket

s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

print ('Socket Created")
```
###udp
UDP --- 用户数据报协议，是一个无连接的简单的面向数据报的运输层协议。UDP不提供可靠性，它只是把应用程序传给IP层的数据报发送出去，但是并不能保证它们能到达目的地。由于UDP在传输数据报前不用在客户和服务器之间建立一个连接，且没有超时重发等机制，故而传输速度很快。

UDP是一种面向无连接的协议，每个数据报都是一个独立的信息，包括完整的源地址或目的地址，它在网络上以任何可能的路径传往目的地，因此能否到达目的地，到达目的地的时间以及内容的正确性都是不能被保证的。
UDP特点：
UDP是面向无连接的通讯协议，UDP数据包括目的端口号和源端口号信息，由于通讯不需要连接，所以可以实现广播发送。 UDP传输数据时有大小限制，每个被传输的数据报必须限定在64KB之内。 UDP是一个不可靠的协议，发送方所发送的数据报并不一定以相同的次序到达接收方。

##### udp网络程序-发送数据
创建一个udp客户端程序的流程是简单，具体步骤如下：

创建客户端套接字
发送/接收数据
关闭套接字


代码如下：

```python
#coding=utf-8

from socket import *

#1. 创建套接字
udpSocket = socket(AF_INET, SOCK_DGRAM)

#2. 准备接收方的地址
sendAddr = ('192.168.1.103', 8080)

#3. 从键盘获取数据
sendData = raw_input("请输入要发送的数据:")

#4. 发送数据到指定的电脑上
udpSocket.sendto(sendData, sendAddr)

#5. 关闭套接字
udpSocket.close()
```
##### 创建udp网络程序-接收数据
```python
#coding=utf-8

from socket import *

#1. 创建套接字
udpSocket = socket(AF_INET, SOCK_DGRAM)

#2. 绑定本地的相关信息，如果一个网络程序不绑定，则系统会随机分配
bindAddr = ('', 7788) # ip地址和端口号，ip一般不用写，表示本机的任何一个ip
udpSocket.bind(bindAddr)

#3. 等待接收对方发送的数据
recvData = udpSocket.recvfrom(1024) # 1024表示本次接收的最大字节数

#4. 显示接收到的数据
print recvData

#5. 关闭套接字
udpSocket.close()
```
##### echo	将收到的消息返回给发送方
```python
#coding=utf-8

from socket import *

#1. 创建套接字
udpSocket = socket(AF_INET, SOCK_DGRAM)

#2. 绑定本地的相关信息
bindAddr = ('', 7788) # ip地址和端口号，ip一般不用写，表示本机的任何一个ip
udpSocket.bind(bindAddr)

num = 1
while True:

    #3. 等待接收对方发送的数据
    recvData = udpSocket.recvfrom(1024) # 1024表示本次接收的最大字节数	#使用的是网络调试助手,收到的消息格式为数组	(数据,(地址,端口))

    #4. 将接收到的数据再发送给对方
    udpSocket.sendto(recvData[0], recvData[1])

    #5. 统计信息
    print('已经将接收到的第%d个数据返回给对方,内容为:%s'%(num,recvData[0]))
    num+=1


#5. 关闭套接字
udpSocket.close()
```

##### udp广播
```python
#coding=utf-8

import socket, sys

dest = ('<broadcast>', 7788)#此变量定义为广播地址第一个字段自动寻找本网段广播地址

# 创建udp套接字
s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
# 对这个需要发送广播数据的套接字进行修改设置，否则不能发送广播数据
s.setsockopt(socket.SOL_SOCKET, socket.SO_BROADCAST,1)#重点

# 以广播的形式发送数据到本网络的所有电脑中
s.sendto("Hi", dest)

print )"等待对方回复（按ctrl+c退出）")

while True:
    (buf, address) = s.recvfrom(2048)
    print ("Received from %s: %s" % (address, buf))
```

