---
title: 初识travis CI (让hexo在github上持续集成)
date: 2019-10-25 11:18:28
tags: travis ci
categories: travis ci

---

[持续集成服务部署Travis CI 官方链接](https://travis-ci.com)

Travis CI 提供的是持续集成服务（Continuous Integration，简称 CI）。它绑定 Github 上面的项目，只要有新的代码，就会自动抓取。然后，提供一个运行环境，执行测试，完成构建，还能部署到服务器。

<!-- more -->	

持续集成指的是只要代码有变更，就自动运行构建和测试，反馈运行结果。确保符合预期以后，再将新代码"集成"到主干。

持续集成的好处在于，每次代码的小幅变更，就能看到运行结果，从而不断累积小的变更，而不是在开发周期结束时，一下子合并一大块代码。

### 官方文档

主页：[https://travis-ci.com](https://travis-ci.com)

文档：[https://docs.travis-ci.com](https://docs.travis-ci.com)

github：[https://github.com/travis-ci/](https://github.com/travis-ci/)

hexo 配置 travis：[https://hexo.io/zh-cn/docs/github-pages](https://hexo.io/zh-cn/docs/github-pages)

### hexo 增加 travis ci说明

    按如上官方文档配置时，其默认使用的是repository的gh_pages分支，github支持在gh_pages分支上部署项目主页，但是包含的主题有限，不包含博主使用的next主题，所以更改代码分支为dev分支，而页面分支github非支持的主题下仅能在master分支上构建。
    
附修改的travis配置文件 .travis.yml
 
```
language: node_js
node_js: stable

# S: Build Lifecycle
install:
  - npm install


#before_script:
 # - npm install -g gulp

script:
  - hexo g

after_script:
  - cd ./public
  - git init
  - git config user.name "gordonzsq"
  - git config user.email "gordonzsq@sina.com"
  - git add -A
  - git commit -m "Update docs"
  - git push --force --quiet "https://${GH_TOKEN}@${GH_REF}" master:master
# E: Build LifeCycle

branches:
  only:
    - dev
env:
 global:
   - GH_REF: github.com/gordonzsq/gordonzsq.github.io.git

```
 
### 一些中文说明

最好最全的学习资料永远在官方文档，但对于初学者来说整理好的中文资料更便于快速理解

www.ruanyifeng.com/blog/2017/12/travis_ci_tutorial.html

https://www.jianshu.com/p/951ce2fb255d











