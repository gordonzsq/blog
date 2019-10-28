---
title: 搭建hexo笔记
date: 2017-02-14 16:10:12
tags: hexo-config
categories: hexo
---
## 关于 Hexo？

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
<!-- more -->

## 优势

简洁、快速，可以方便的部署在如github pages等地方

## 安装hexo所需环境

[文档地址](https://hexo.io/zh-cn/docs/index.html)  （安装、使用等非常详细）
- [Node.js](http://nodejs.org/)
- [Git](http://git-scm.com/)

安装node 和 git：(以ubuntu下工具链为例)

``` bash
$ sudo apt-get install git-core`
```
``` bash
$ curl https://raw.github.com/creationix/nvm/master/install.sh | sh`
```

 更新node：
 ``` bash
 $ nvm install stable
 ```

## 安装hexo

``` bash
npm install -g hexo-cli
```
## 笔记

#### 创建博客

``` bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```
#### 配置 修改 _config.yml (至少下面这些吧^-^,含义很好理解)

``` 文本
theme: next 
title: name
...
language: zh-Hans
timezone: Asia/Shanghai
url:abc.com
root: /
...
deploy:
  type: git
  repo:***
  branchL master
```

#### 主题配置 修改

next主题  [文档地址](http://theme-next.iissnan.com/theme-settings.html) （安装、使用等非常详细）
```
categories: /categories  #增加分类标签
scheme: Mist             #修改next主题样式（3个，参见文档和配置文件）
social:                  #增加图像下的个人链接
  GitHub: ×××
  Weibo: ×××
avatar: /images/avatar.png #个人头像图片
duoshuo_shortname: xxx     #第三方插件（评论）
```

#### 写文章

``` bash
$ hexo new [layout] <title>
```

#### 查看和部署

``` bash
$ hexo g                   #生成静态页面
$ hexo d                   #部署
（如以上配置为部署到相应项目，修改该项目gitubpages属性，
则可以通过yourname.github.io访问，
配置说明：https://hexo.io/zh-cn/docs/github-pages#Private-repository
并可通过创建CNAME文件自定义域名访问）
$ hexo s -p port           # 开启本地server
```
