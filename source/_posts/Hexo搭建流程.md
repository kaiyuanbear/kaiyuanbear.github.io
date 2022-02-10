---
title: Hexo搭建流程
date: 2022-01-18 10:03:15
tags: Hexo
cover: https://files.catbox.moe/phpclq.jpg
---

## 2022.01.18
#### 在github创建新仓库
这里我使用GitHub Pages来展示个人博客，而GitHub Pages分为两种类型：
  1.  Project Pages：用来展示项目
  2.  User Pages：用来展示用户
所以这里选择了User Pages来展示博客。步骤如下：
* 在github上创建新的个人仓库，github上的仓库名应该为: username.github.io 这里username是自己github的用户名，该仓库的名称是固定写法，例如我的仓库名即为:<https://kaiyuanbear.github.io> 并且在后续安装了Hexo的发布插件之后，可将项目发布到github上，这时再访问:<https://kaiyuanbear.github.io> 即可看到最新的博客展示了。
* 创建两个分支: `master`和`hexo`，其中`master`用来存放Hexo生成静态资源后的文件，`hexo`则用来存放博客的相关配置和md等文件。
* 将`hexo`分支在setting中设置为默认分支。

## 2022.01.20
#### 安装git
Git是一个开源的分布式版本控制系统。可以有效、高速地处理从很小到非常大的项目版本管理。详细学习课程可以参看廖雪峰老师的[git教程](https://www.liaoxuefeng.com/wiki/896043488029600)。Hexo的博客项目搭建好之后需要同步到GitHub上，而Git就是进行版本控制和推送的工具。
* Git的[下载地址](https://git-scm.com/downloads)，根据自己电脑的实际情况选择安装包下载并安装。
* 安装完成git之后需要在命令行工具中创建ssh key,并对git作相关配置，详细流程可以在百度上搜索，这里就不详述了

## 2022.01.21
#### 安装Node.js
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

## 2022.02.10
#### 部署网站
我们将在该步骤中把本地的Hexo与本文第一部分提到的github关联起来，在我们更新了文章之后，需要更新并部署到github上。这需要在_config.yml配置文件中修改相应配置：
```
deploy:
  type: 'git'
  repo:  https://github.com/kaiyuanbear/kaiyuanbear.github.io.git // 个人自己申请的github仓库User Pages地址
  branch: master
```

#### 绑定域名
// TODO 待后续更新

#### 更换主题
Hexo上有形式多样、风格迥异的主题，这里完全可以根据自己需要在[官方主题](https://hexo.io/themes/)中安装自己所喜欢的主题。这里我仅以我所选择的[nexmoe](https://nexmoe.com/)主题为例：
* 该主题需要先安装`hexo-theme-nexmoe`(nexmoe主题安装包)和`hexo-wordcount`(用于字数统计及阅读时常)两个npm包
* 然后在`_config.yml`中将`theme`设置为`nexmoe`
* 接着在根目录下新建`_config.nexmoe.yml`，将[nexmoe主题仓库](https://github.com/theme-nexmoe/hexo-theme-nexmoe-example)中的_config.new.yml中的内容直接复制到`_config.nexmoe.yml`文件中
* 之后输入`hexo s`启动本地开发服务即可看到该主题的样式了
* 最后如果需要进行个性化配置可以参考[主题文档](https://docs.nexmoe.com/config/analysis/)进行配置
  
后面我将另外开一篇文章记录我自己进行的个性化修改配置

#### 发布文章
上文中提到过使用`hexo n 标题`可以创建标题为“标题”的新博客文章，这个时候可以看到在`/source/_posts/`中多了名为`标题.md`的文件，文件格式为md，这里md文件中使用的是Markdown的语法。Markdown是一种可使用普通文本编辑器编写的标记语言，通过简单的标记语言，可以使文本内容具有一定的样式。其语法简洁明了，容易掌握。详见[Markdown语法说明](https://www.appinn.com/markdown/)