---
title: Hexo搭建流程
date: 2022-01-18 10:03:15
tags: Hexo
cover: https://files.catbox.moe/phpclq.jpg
---

## 2021.01.18
#### 1. 在github创建新仓库
这里我使用GitHub Pages来展示个人博客，而GitHub Pages分为两种类型：
  1.  Project Pages：用来展示项目
  2.  User Pages：用来展示用户
所以这里选择了User Pages来展示博客。步骤如下：
* 在github上创建新的个人仓库，github上的仓库名应该为: username.github.io 这里username是自己github的用户名，该仓库的名称是固定写法，例如我的仓库名即为:<https://kaiyuanbear.github.io> 并且在后续安装了Hexo的发布插件之后，可将项目发布到github上，这时再访问:<https://kaiyuanbear.github.io> 即可看到最新的博客展示了。
* 创建两个分支: `master`和`hexo`，其中`master`用来存放Hexo生成静态资源后的文件，`hexo`则用来存放博客的相关配置和md等文件。
* 将`hexo`分支在setting中设置为默认分支。

## 2021.01.20
#### 2. 安装git
Git是一个开源的分布式版本控制系统。可以有效、高速地处理从很小到非常大的项目版本管理。详细学习课程可以参看廖雪峰老师的[git教程](https://www.liaoxuefeng.com/wiki/896043488029600)。Hexo的博客项目搭建好之后需要同步到GitHub上，而Git就是进行版本控制和推送的工具。
* Git的[下载地址](https://git-scm.com/downloads)，根据自己电脑的实际情况选择安装包下载并安装。
* 安装完成git之后需要在命令行工具中创建ssh key,并对git作相关配置，详细流程可以在百度上搜索，这里就不详述了

## 2021.01.21
#### 3. 安装Node.js
由于Hexo是基于Node.js的，所以需要事先安装Node.js,可以在[官方下载](https://nodejs.org/en/download/)处进行下载并安装，建议选择最近的一个稳定版本进行安装。安装包中包含了Node.js和npm，安装完成后可在命令行中使用`node -v`和`npm -v`验证是否安装完成

#### 4. 安装Hexo
终于到了本文主角Hexo了，Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
* 安装Hexo: 在命令行中输入`npm i -g hexo-cli`
* 安装完成后，将命令行的文件夹切换到想要存放博客相关文件的文件夹下，然后键入指令
  ```
  hexo init blog  // 初始化hexo，并创建名为blog的文件夹
  cd blog         // 进入创建的文件夹
  npm i           // 安装Hexo所需要的npm包
  ```
* 使用`hexo n`可以创建新的文章，`hexo s`可以启动服务并在本地预览，默认是在`localhost:4000`可以预览，`hexo g`则是根据当前文件生成相应的静态资源
* 如果需要对博客站进行配置，可查阅[官方文档](https://hexo.io/zh-cn/docs/configuration)

#### 5.部署网站