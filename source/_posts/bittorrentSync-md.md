---
title: 手机电脑同步
date: 2017-03-1 16:21:21
tags: 手机电脑同步bittorrentsync
categories: 同步工具
---

这两天想把手机上的照片备份到电脑上，于是发现了一个这样的linux和iphone间方便、快速的传输神器--bittorrentSync。
<!--more-->
[bittorrentSync](https://help.getsync.com/hc/en-us) 是一个个人设备（手机-电脑-平板-NAS等）间同步照片/数据的神器，出于需要，安装并尝试了一下，感觉非常好用^-^。

## 简要说明
bittorrentSync 在appstor和安卓应用商店中有应用的客户端，同时[官网](https://help.getsync.com/hc/en-us)上有在win或者linux下搭建服务端的说明，几条命令，非常简单。

传输文件或者照片时需要链接在同一个wifi上（家庭基本都是如此），然后设备间拷贝照片和文件将会非常快速和方便，另外，在iphone上的应用，仅能拷贝相册中的图片，功能比较少，但正是目前最想要的功能，也就无所谓啦。

## 笔记

#### 安装
iphone中，直接搜索bittorrentSync，安装即可。

ubuntu下个人快速安装如下：

``` bash
$ echo "deb http://linux-packages.resilio.com/resilio-sync/deb resilio-sync non-free" | sudo tee /etc/apt/sources.list.d/resilio-sync.list
$ wget -qO - https://linux-packages.resilio.com/resilio-sync/key.asc | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install resilio-sync
```

#### 启动服务

``` bash
$ rslsync
```

#### 使用

- 打开浏览器，访问127.0.0.1:8888
- 创建新的用户名密码->增加共享路径->手机扫QR code的2维碼（可以设置成永久，默认3天有效）

ok…… ，以后就可以方便的把手机上的照片放到电脑上，然后删掉，不怕手机空间不足啦～～
