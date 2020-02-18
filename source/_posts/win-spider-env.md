---
title: windows开发环境记录
date: 2020-02-17 08:53:06
tags:software
categories: windows
---
windows下搭建python开发环境用到的一些记录。

<!--more-->

在学习用python编写爬虫的时候，用到一些windows下的工具，于是在windows平台下搭建一个环境，用于学习python。

#### 安装python
在[python官网](https://www.python.org)直接下载windows版本安装包，安装即可。
python安装包集成了pip，但如果安装的时候，没有选择pip，可以在cmd下运行如下命令安装pip
```
python -m pip install -U pip
```

#### 安装python模块
1 官方源直接按装
```
pip install module_name
```

2 指定国内源安装（解决墙，无法访问国外网站的各种问题）
如用豆瓣的源：
```
pip install -i --trusted-host http://pypi.douban.com/simple/ module_name
```

3 下载whl文件，本地安装
下载地址[https://www.lfd.uci.edu/~gohlke/pythonlibs](https://www.lfd.uci.edu/~gohlke/pythonlibs)

cmd下安装moudle，安装失败时往往是下错了whl文件或者需要先安装其它依赖模块，根据文件名和系统环境很容易看出那个是需要安装的whl文件。
```
pip install modle_name.whl
```
#### pycharm调用模块配置

pycharm工程下调用系统存在的module，直接修改项目中的pyven.cfg：
```
include-system-site-packages = true
```

#### 安装notebook（推荐）
学习期间并不推荐使用pycharm作为工具，虽然它可以更简单的安装一些模块和开发环境，但python开发、运行的环境相对简单清晰，用pycharm节省不了太多时间，但是其工具隐藏了大部分清晰的配置和关联（并且收费），小而美的编辑器更适合学习，并在玩转python的过程中更得心应手。更推荐使用notebook这类工具。

使用时遇到在chrome中无法打开页面的情况，ie中没有问题，不影响使用。

安装：
```
pip install ipython
pip install notebook
pip install tornado
```
执行notebook（启动服务）：
```
jupyter-notebook
```
#### 安装Sublime Text
Sublime Text 是一款流行的代码编辑器软件，也是HTML和散文先进的文本编辑器，可运行在Linux，Windows和Mac OS X。也是许多程序员喜欢使用的一款文本编辑器软件。
[官方下载](www.sublimetext.com)安装即可。


#### 安装fiddler和switchyOmega插件
[fiddler下载地址](https://www.telerik.com/fiddler)
1 fiddler设置
在抓取网页数据时，在情景模式中设置的代理端口要和fiddler中tools-options-connections中的端口一致（因默认的8888容易被其它服务占用，所以建议修改个不常用的端口号作为代理服务端口）

2 switchyOmega浏览器设置
在chrome中安装switchyomega可能依然存在翻墙问题，此时可以直接去下载switchyomega， 解压后进入chrome浏览器->选择设置扩展程序->打开开发者模式->选择加载已解压的扩展程序……即可。

#### 安装mysql
[win下mysql安装地址](https://www.mysql.com/cn/why-mysql/windows/)


#### 安装navicat
[navicat 破解及安装地址](https://www.cnblogs.com/wei9593/p/11907307.html)


#### 安装npm&node

[官方地址](https://nodejs.org/en/download/)


#### 其它
windows下文件拷贝到linux下文件乱码问题：
将编码格式GB2312转换为UTF-8即可：
```
iconv -f GB2312 -t UTF-8 somefile.md -o somefile.md
```
windows下无法访问github问题（应该是仅DNS不解析，具体原因不清楚，墙的话，修改hosts是不会好用的哦
修改Windows/System32/drivers/etc/hosts， 增加
```
192.30.253.112 github.com
192.30.253.119 gist.github.com
151.101.100.133 assets-cdn.github.com
151.101.100.133 raw.githubusercontent.com
151.101.100.133 gist.githubusercontent.com
151.101.100.133 cloud.githubusercontent.com
151.101.100.133 camo.githubusercontent.com
151.101.100.133 avatars0.githubusercontent.com
151.101.100.133 avatars1.githubusercontent.com
151.101.100.133 avatars2.githubusercontent.com
151.101.100.133 avatars3.githubusercontent.com
151.101.100.133 avatars4.githubusercontent.com
151.101.100.133 avatars5.githubusercontent.com
151.101.100.133 avatars6.githubusercontent.com
151.101.100.133 avatars7.githubusercontent.com
151.101.100.133 avatars8.githubusercontent.com
```

还想用docker、ssh……工具，但是对windows下的各种破解软件，和超不习惯的命令行搞得有些烦了，又不喜欢把大量文件放虚拟机中，目前为了学习还好，做东西还是想回到熟悉的linux下，于是写个简单的爬虫后，不打算继续安装其它工具了，虽然linux下的fiddler很难用，可能要物色其它proxy，但是各有好处吧，等有空再回windows下学习时在继续搭建windows下的环境吧～～～～



