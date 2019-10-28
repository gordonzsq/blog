---
title: next theme config
date: 2019-10-28 09:53:09
tags: hexo-config
categories: hexo
---

##next主题基本配置
https://hexo.io/themes/ 可以查看其他主题。 这里我主要说下NexT主题的相关配置。<!--more-->

####安装主题
直接将github上next主题文件clone到本地hexo blog的theme目录下即可，原next主题已经停止维护，所以目前选择如下地址的repo

```git clone https://github.com/theme-next/hexo-theme-next themes/next```

####启用主题

修改站点配置文件_config.yml

theme: next

####主题配置

```
cd themes/next
vi _config.yml
-------1 需要修改的配置1
# Schemes
#scheme: Muse
scheme: Mist#选择你喜欢的主题风格
#scheme: Pisces
#scheme: Gemini
-------2需要修改的配置2
 menu:#选择你要显示在页面中的一些选项，格式为：路径 || 图片
  home: / || home
  #about: /about/ || user
  tags: /tags/ || tags
  categories: /categories/ || th
  archives: /archives/ || archive
  #schedule: /schedule/ || calendar
  #sitemap: /sitemap.xml || sitemap
  #commonweal: /404/ || heartbeat
  
------- 3需要修改的配置3
# Enable / Disable menu icons / item badges.
menu_settings:
   icons: true
   
-------4需要修改的配置4
avatar:#显示头像的图片，图片放在主题source目录下的自定义路径
  url: /uploads/hd.png
  
 -------5需要修改的配置5
 social:
  GitHub: https://github.com/name || github
  E-Mail: mailto:mail@email.com || envelope
  Weibo: https://weibo.com/ididid/ || weibo

-------etc需要修改的配置etc...
#其它可选配置很多，如sidebar显示位置、方式....文件中大多有说明

```

#### 额外的一些操作
从github clone下来的主题需要删除原来的仓库，才能提交到hexo博客源码仓库，

```
git rm -rf --cached themes/next
git add themes/next
```