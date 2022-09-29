# hexo简介

Hexo是一款基于Nodejs的，快速、简洁且高效的博客框架。具有丰富的插件和主题，具有超快的速度。支持Makedown语法，可以方便快捷的编写博客文档。同时支持node命令，可以一键部署到GitHub Pages, Heroku 或其他平台。

总之，是个写博客的利器。

# 事前准备

使用hexo前，首先要保证自己的电脑已经安装了Git 和 Node。且Node版本不低于10.13。

**安装Node**

Node.js 为大多数平台提供了官方的 [安装程序](https://link.zhihu.com/?target=https%3A//nodejs.org/en/download/)。

:cry::cry::cry: 千万别点 安装额外工具，千万别点。

# 快速入门

1. 安装hexo-cli

   使用npm或者yarn安装hexo的脚手架工具，这里以npm为例

   ```shell
   npm install -g hexo-cli
   ```

2. 初始化项目

   安装 hexo-cli 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。我们以新建一个hexo-demo项目为例进行说明。（先 cd 到你指定的文件夹比较方便）

   ```shell
   hexo init hexo-demo
   ```

   进入hexo-demo文件夹，安装依赖

   ```shell
   cd hexo-demo
   npm install
   ```

3. 运行项目

   安装完依赖以后，执行以下命令，启动hexo服务器，运行结果如图。

   ```sh
   hexo server
   # 简写
   hexo s
   ```

# 项目结构

进入hexo-demo文件夹，我们可以看到hexo的目录结构，如下所示。

```
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

## _config.yml

_config.yml是整个博客网站的配置文件，里面包含了网站的配置、网址配置、目录配置、主题配置等等内容。

你可以根据自己的需要进行修改，我修改了网站配置、网址配置和主题配置，其他的使用默认。

### 网站配置

默认的网站配置如下:

```
title: Hexo
subtitle: ''
description: ''
keywords:
author: John Doe
language: en
timezone: ''
```

修改后的实际配置：

```
title: Jacob-xyb
subtitle: '这是一个demo页'
description: 'hexoDemo用于介绍如何使用hexo'
keywords: 'hexo,node,博客'
author: Jacob-xyb
language: zh-CN
timezone: ''
```

一个比较重要的是语言(language)，这里记得要填中文zh-CN,这样安装不同的主题的时候，就可以显示中文了。

 ### 网址配置

url是博客上线后的网址，会在分享等地方用到，一定要记得修改

### 主题配置

修改 **_config.yaml** 中的 **theme**

## scaffolds

```
├── draft.md
├── FASTPANEL
├── post.md
```

模板文件夹，里面存放了3个模板文件，依次是草稿模板，页面模板和文章模板。

当我们使用hexo命令生成草稿、页面或者文章的时候，就是复制这些模板。

我们以文章模板为例进行说明。默认post.md内容为空，头部信息如下：

```
---
title: {{ title }}
date: {{ date }}
tags:
---
```

如果我们想所有新生成的文章都带上分类字段。我们可以修改post.md的头部。我们给头部添加了categories字段。

```
---
title: {{ title }}
date: {{ date }}
tags:
categories: 
---
```

这样我们使用`hexo new a` 生成a.md文章的时候，a.md文章顶部都会带上categories字段。

```
---
title: a
date: 2022-04-01 16:57:55
tags:
categories:
---
```

https://zhuanlan.zhihu.com/p/492115006

# 部署

1. 在hexo项目目录安装工具

```sh
npm install --save hexo-deployer-git
```

2. 设置 **_config.yaml** 文件

```
deploy:
  type: git
  repo: github仓库地址
  branch: master
```

3. 部署: `hexo d`

# 跳过渲染

跳过渲染有下述两种方法：

1. 在html文件中添加跳过渲染指令

> 用编辑器打开放入\Hexo\source\创建的文件夹中的 index.html 文件，在开头添加如下代码即可

```html
---
layout: false
---
```

添加该指令后，执行 hexo g命令时便会跳过该 index.html文件，使得index.html不受当前 hexo 主题影响，完全是一个独立的网页，如果网页引用了 css 或 js，css 和 js 需使用外链或者将css js 文件放入index.html同目录下引用。

引用图片亦是如此

2. 在_config.yml文件中设置skip_render

使用编辑器打开 Hexo 目录下的_config.yml文件，找到skip_render

skip_render一般有以下四种常用参数：

```html
跳过source目录下的 test.html: skip_render: test.html

跳过source目录下 test 文件夹内所有文件：skip_render: test/*

跳过source目录下 test 文件夹内所有文件包括子文件夹以及子文件夹内的文件：skip_render: test/**
```

跳过多个路径：

```html
skip_render:
 - test.html
 - test/*
```
