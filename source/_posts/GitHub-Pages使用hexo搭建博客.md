---
title: GitHub Pages使用hexo搭建博客
date: 2016-08-30 22:01:08
tags:
---

GitHub Pages + Hexo + MarkDown搭建简单静态个人播客
<!-- more -->

### 创建GitHub Pages仓库

1. create a new repository
repository name必须严格按照 username.github.io 的格式。其中username表示当前github帐号的用户名
<div class="tip">
plus：这里只关心github pages作为User Pages，暂不讨论Project Pages的情况
</div>

2. clone github pages到本地~/Github目录下（这里指定目录方便说明）
``` bash
~ $ pwd
~ $ /Users/***/Github
~ $ git clone https://github.com/username/username.github.io
```
也可以使用SourceTree，GitHub Desktop等客户端，方便之后的操作
至此，完成创建github pages

### 安装hexo

安装hexo的过程可以参考hexo官网的教程：[Hexo官网教程](https://hexo.io/zh-cn/docs/index.html) 

### Hexo建站

参考Hexo官方教程：[官方建站教程](https://hexo.io/zh-cn/docs/setup.html) 

### 设置参数

参考Hexo官方教程：[官方参数说明](https://hexo.io/zh-cn/docs/configuration.html)

### 提交到GitHub Pages

修改根目录下_config.yml文件的以下部分：

``` bash
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/liangie/liangie.github.io.git
  branch: master
```

为了能成功提交到github，需要安装hexo-deployer-git插件：

``` bash
$ npm install hexo-deployer-git --save
```

安装完成后执行命令完成部署：

``` bash
$ hexo generate
$ hexo deploy
```

之后即可通过设置的github pages地址开始访问了
