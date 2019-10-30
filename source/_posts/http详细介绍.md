title: HTTP详细介绍
toc: true
thumbnail: https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1572427490730&di=f014e48a5ddb0ec64d76567fe91c051c&imgtype=0&src=http%3A%2F%2Fuser-gold-cdn.xitu.io%2F2018%2F10%2F22%2F1669b18d26d8a1a2%3Fw%3D640%26h%3D480%26f%3Djpeg%26s%3D46869
categories: 网络
tags: [HTTP, TCP/IP]

---

超文本传输协议(HTTP),是一种用于客户端和服务端之间的应用层通信协议.其特点是简单快速、灵活.HTTP是一种无状态协议.HTTP协议不对请求和响应之间的通信状态进行保存,不保留一切请求和响应的信息

<!--more-->

## HTTP报文
> 用于HTTP协议交互的信息是一种由多行数据构成的字符串文本, 称为HTTP报文.请求端的HTTP报文叫做请求报文,响应端的叫做响应报文.



### 1.请求和响应信息的报文结构

 ![](http://images0.cnblogs.com/blog/644616/201507/031831271286984.jpg)
 
 请求和响应的信息都是由 头部 + 空行 + 实体的
 