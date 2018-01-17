---
title: 使用 Hexo + GitHub 轻松做出一个好看的博客  
date: 2018-01-17 11:32:46  
tags: Hexo  博客  
---
## 什么是 Hexo？

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## GitHub上的操作

在 GitHub 上新建一个空仓库，仓库的名称是「用户名.github.io」

## 安装前提

安装 Hexo 相当简单。然而在安装前，必须检查电脑中是否已安装下列应用程序：

* [Node.js](https://nodejs.org/en/)  
* [Git](https://git-scm.com/)  

如果您的电脑中已经安装上述必备程序，接下来只需要使用 npm 即可完成 Hexo 的安装。  

```
npm install -g hexo-cli

```

## 建站

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。 
 
```
hexo init myBlog

cd myBlog

npm i
```

新建完成后，指定文件夹的目录如下：

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

## 配置网站信息

1. 打开 _config.yml  

2. 把第 6 行的 title 改成你想要的名字

3. 把第 9 行的 author 改成你的名字

4. 把最后一行的 type 改成 type: git（git前面有一个空格）

5. 在最后一行后面新增一行，左边与 type 平齐，加上一行 repo: 仓库地址 


## 安装 git 部署插件

```
npm install hexo-deployer-git --save
```

执行`hexo deploy`

进入「你的用户名.github.io」对应的仓库，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接

你现在应该看到了你的博客！

## 写博客

1. `hexo new 博客标题`
2. 编辑文章
3. `hexo generate` 生成静态文件
4. `hexo deploy` 文件生成后立即部署网站
5. 去看你的博客，应该能看到第二篇博客了

## 更换主题

1. https://github.com/hexojs/hexo/wiki/Themes 上面有主题合集
2. 找一个你喜欢的主题，进入主题的 GitHub 首页，比如我找的是 https://github.com/foreachsam/hexo-theme-aiki
复制它的 SSH 地址或 HTTPS 地址
3. cd theme git@github.com:foreachsam/hexo-theme-aiki.git
4. cd ..
5. 将 _config.yml 的第 75 行改为 theme: hexo-theme-aiki，保存
6. hexo generate
7. hexo deploy
8. 稍后刷新博客页面，会看到一个新的外观。

## 上传源代码

「用户名.github.io」上保存的只是博客，并没有保存「生成博客的程序代码」，需要再创建一个名为 blog-generator 的空仓库，用来保存 myBlog 里面的「生成博客的程序代码」。  
在 GitHub 创建 blog-generator 空仓库  
这样一来，你的博客发布在了「用户名.github.io」而你的「生成博客的程序代码」发布在了 blog-generator。所有数据万无一失，你就不会因为误删 myBlog 目录而痛哭了。  

以后每次 hexo deploy 完之后，博客就会更新；然后你还要要 add / commit /push 一下「生成博客的程序代码」，以防万一。  

这个 blog-generator 就是用来生成博客的程序，而「你的用户名.github.io」仓库就是你的博客页面。  
 
 
参考资料：  

* [Hexo教程](https://hexo.io/zh-cn/docs/index.html)   
* [方方老师教程](https://xiedaimala.com)