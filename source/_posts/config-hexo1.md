---
title: 图片处理 
date: 2017-02-14 11:22:33
tags: hexo-config
categories: hexo
---

## hexo的图片处理

关于图片的处理问题。

<!--more-->

next主题  [文档地址](http://theme-next.iissnan.com/theme-settings.html) （安装、使用等非常详细）

部署在github上图片显示会非常慢，另外，在上传多个大文件的照片时，也会产生难以忍受的长时间等待，所以找了一个第三方的图床替代之。

## 笔记

#### 注册图床网站帐号

国内免费图床也有好多家，在此选择了一个极简图床（感觉它是专为个人博客弄的，直接可复制markdown文本过来），
同时申请一个七牛云帐号，在极简图床网站上设置好七牛云帐号的信息，因为设置后，极简图床才能用较多的空间和不
再有上传时间间隔的限制，设置很简单，此处不再赘述。

#### 选取图片

选取一些图片到临时目录，然后改变图片的大小（极简图床限制单张图片大小1M）

```
categories: /categories  #增加分类标签
scheme: Mist             #修改next主题样式（3个，参见文档和配置文件）
social:                  #增加图像下的个人链接
  GitHub: ×××
  Weibo: ×××
avatar: /images/avatar.png #个人头像图片
duoshuo_shortname: xxx     #第三方插件（评论）
```
