---
title: Hexo搭建博客记录
tags:
  - hexo
  - github
categories: Hexo
description: hexo+GitHub搭建博客记录
date: 2020-09-15 11:19:35
---


博客是用来记录学习过程的好工具，可以对整个的学习做系统的梳理，方便以后回顾学习知识更加高效。Hexo+GitHub搭建博客是免费的，不需要服务器，正所谓便宜大碗好用，薅羊毛怎么能少得了我。果断学习搭建教程。

## 搭建过程需使用的工具

1、git

2、GitHub

3、node

4、hexo

### git

这是git下载链接[git下载](https://git-scm.com/downloads)

### GitHub

注册GitHub账号，[GitHub官网](https://github.com/)

下载并安装好git之后，在GitHub注册账号，然后打开git bash，全局配置用户名和邮箱

```
git config --global user.name "你的用户名"
```

```
git config --global user.email "你的邮箱"
```

生成ssh key

```
ssh-keygen -t rsa -C "你的邮箱"
```

在git bash执行这个命令之后就会在你的系统盘生成密钥对，一个公钥一个私钥。然后再到你的GitHub上点击个人头像点击settings找到SSH and GPG keys，添加公钥，把系统盘的公钥添加进去。这样你的git就连接到了你的GitHub，当你想要连接GitHub的远程仓库，把你电脑上的本地仓库的东西推送到远程仓库就可以轻松实现，在这里公私钥对就是对你的个人身份进行验证，因为你的GitHub有你的公钥，当你在本地电脑用git推送信息到GitHub远程仓库时，会对信息用私钥签名加密，然后GitHub就从你的SSH中找到你的公钥对信息进行解密，如果可以解出来那就说明身份无误。

接着，在GitHub新建一个repository，命名一定要严格按照

```
你的GitHub账户名.github.io
```

这种格式来，GitHub对这种格式的仓库可以直接用域名访问，浏览器输入

```
http://你的GitHub账户名.github.io
```

你就可以看到你的博客页面

### node

node安装[地址](https://nodejs.org/en/)

我目前对于node的理解还处在于包管理工具的阶段，没有深入的接触，只是觉得使用npm下载各种数据包之类的超级方便一个命令行就轻松搞定了。这里我也是采用node来安装hexo。

### hexo

hexo他有官方的文档写的超级详细，[附链接](https://hexo.io/zh-cn/docs/)

全局安装hexo

```
npm install -g hexo-cli
```

使用hexo初始化一个文件

```
hexo init 文件名
```

到文件目录中

```
cd 文件名
```

使用npm安装依赖

```
npm install
```

使用hexo-deployer-git一键部署，这个在官方文档有专门的栏目讲到了。

```
npm install hexo-deployer-git --save
```

修改_config.yml文件，该文件是配置文件，很多东西都可以在这里修改，如主题，根目录之类的

![deploy地址](https://github.com/Twlig/picture/blob/master/deploy%E5%9C%B0%E5%9D%80.png?raw=true)

把repo的值改成自己对应的仓库地址。

```
hexo -g
hexo -d
```

就可以生产静态文件，并部署网站，部署之后你就可以在以下网址中访问你的服务器啦。

```
http://你的GitHub账户名.github.io
```

我要吃饭去了，不写了，等我晚点再补一下hexo写作和markdown的文章。