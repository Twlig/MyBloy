---
title: hexo使用心得以及markdown编辑器
date: 2020-09-15 14:04:21
categories: Hexo
tags: [hexo, markdown,typora]
description: hexo使用方法以及markdown编辑器
---

吃完饭回来的我又回来啦，继续编辑我的搭建博客记录，上一回咱们讲到hexo搭建，那搭建好了框架，肯定就要用呀。咋用呀？不会！看官方文档呀！啥？太多了，懒得看！行吧，我来给你划重点，看完我的文章包教会！

### hexo文件目录

hexo的目录就是下面这个亚子的。

![hexo文件目录](https://github.com/Twlig/picture/blob/master/QQ%E6%88%AA%E5%9B%BE20200915151606.png?raw=true)

node_modules应该是hexo的依赖库啥的。

picture忽略不计，这是我自己用来上传图片的git仓库。晚点再唠一下这个图片上传的问题。

public就是部署之后会自动上传到用户名命名的那个远程git仓库的静态网页。

.deploy_git应该是和github远程仓库连接的本地仓库，当执行部署命令时，就会自动把public文件的东西推送到远程仓库，就达到了更新的目的。

scaffolds就是一些markdown模板，你可以在新建文章的时候使用这里面的模板，更加快捷的写文章。

```
hexo new photo "王小花自传"
```

就像上面这个写，hexo就会去scaffolds中找到photo文件，然后以这个为模板生成你的新文章。

source就是你写的文章的存放地，你的post文章，page文章，还有草稿draft文章。

themes就是主题，你可以在_config.yml中修改你的主题。这里有很多主题可以[下载](https://hexo.io/themes/)。下载之后解压放到到hexo文件目录的themes文件夹中。找到theme字段，填写你想要的主题文件名。推荐[next主题](https://github.com/theme-next/hexo-theme-next)。

_config.yml文件就是配置文件，各种参数都可以在里面修改。想要具体了解可以看官网[参数](https://hexo.io/zh-cn/docs/configuration)。

### hexo常用的命令

#### init

```
hexo init
```

就是初始化王小花的文件夹，表示你王小花从今以后要在这个文件夹下面用hexo写自己的博客了

#### new

```
hexo new [layout] <title>
```

这个命令嘛，就是新建你自己的文章呀。至于layout是个啥，就是你新文章的布局，有三种：post、page、draft。生成的文件分别在source/_post，source和source/_draft下。其中呢，post就是你部署上服务器之后会显示在网页上的文章，如果你不写明layout默认也是这个类型的，而page呢，我的理解是用来做分类和标签页的东西，最后的draft就是你王小花不想被别人看到的草稿，你也可以选择优化好文章之后，使用：

```
hexo publish <title>
```

比如：

```
hexo publish “王小花为何那样”
```

这个“王小花为何那样”呢，就是title啦，title就是你文章的标题

#### server

```
hexo server  
```

启动服务器，就是在你的localhost:4000端口可以访问的那种，比如，王小花在写文档的时候，她觉得她写的好挫，布局太丑了，表达没有很清楚，但是她又想要看看到底丑成个啥样子，那她就可以开她的服务器，在本地自己好好瞅瞅哪不行！具体就是这样操作，hexo新建一个文章，打开文章的md文件，用markdown编辑器编辑的同时，开启hexo服务器，写了一小点，想看看自己的成果，那就crtl+s，然后浏览器访问本地localhost:4000，你就可以实时看到你的文章。

#### generate

```
hexo generate
hexo g //简写也可
```

这个命令是用来生成静态文件的，官网是这么说的，我猜是生成静态文件保存到public文件夹里面，至于为啥我没有hexo g我也可以在本地看到实时的结果，问就是不知道，我的小脑袋瓜子还没想明白。顺便小声逼逼一下，我想做大佬的小娇妻，哪位大佬可以l带带我，自学实在是太孤独了。

#### deploy

```
hexo deploy
hexo d //简写
```

这个命令就像它的长相一样，就是部署到服务器上去。

#### clean

```
hexo clean
```

除缓存文件 (`db.json`) 和已生成的静态文件 (`public`)。

在某些情况（尤其是更换主题后），如果发现对站点的更改无论如何也不生效，执行clean清楚缓存。

差不多也就这些命令了，你就可以把hexo用的七七八八了。

### markdown图片显示问题

前面在hexo文件目录的时候讲到了我的picture文件夹，这个是我新建的git仓库，主要是用来存放我的博客图片。因为你在markdown里面放置图片的时候，你直接从本地托图片过去，图片的路径是本地图片路径，你在本地看肯定没问题，可以显示出来。但是要放在服务器上就显示不了了，服务器又无法识别你的本地地址。因此，我们需要把图片专门新建一个仓库来管理，需要的图片就放进去。这个仓库要和远程github仓库连接，把本地的图片上传到远程，然后我们打开远程仓库的对应图片时，右键选择复制地址。把这个地址填在markdown图片地址里面就可以了。这时，服务器加载图片的时候就会去你的github图片仓库里面找了。

### markdown编辑器

我比较推荐的是typora这个是真的好用。这是下载[地址](https://www.typora.io/)。

至于markdown语法部分，这不是要用再学嘛，随便找一个[语法教程](https://www.jianshu.com/p/191d1e21f7ed/)。而且typora其实都可以在段落和编辑里面找到现成的，哪里需要点哪里。