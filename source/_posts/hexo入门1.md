---
title: hexo入门 1
---

# 安装
前置环境： 
- git
- node.js

 对 只需要一个node就行，git是为了能从github下载项目文件

`node.js v-18.7`
`hexo v-7.2`

其他：浏览器 和 md编辑器如 vscode

## 局部安装 hexo
`npm install hexo`

只和该项目有关的工具和依赖始终建议使用局部安装。

> node包全局安装和局部安装的区别:
> 
> 没啥区别,全局的包可以在任何地方使用,局部包只能在当前项目文件下使用 
>
> 具体表现为 全部安装可以随意使用`hexo`命令,而局部安装必须在项目文件下使用`npx hexo `

我们使用局部安装,记得在命令前+ `npx` ,命令的具体参数和hexo本体命令是一样的

# 初始化项目文件
找一个文件夹,

`npx hexo init `

初始化项目所有的资源和依赖

# 主题

整一个butterfly吧,在项目文件夹下:

`git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly`

安装butterfly 所需的依赖:

`npm install hexo-renderer-pug hexo-renderer-stylus --save`
(这也是局部安装,并且 --save参数会自动更新package依赖信息)

本质还是在我们的项目文件夹`/theme/`下放了一些东西而已，下好之后来到
`/_config.yml`中，翻到最低修改theme的值为 butterfly。

# 写一篇文档

在项目文件夹下 `/source/_posts/` 写一篇md吧。 
发现这里已经有一篇md了？没错那就是给我的参考模板。

# 启动网页

`npx hexo s` (s = server)

正常情况下控制台会启动服务器并输出提示信息和服务器地址，在浏览器中打开 `localhost:4000`

一个基本的网站就成了。网页文件是即时生成的，修改md后只需刷新网页，网站也会随之刷新，很方便本地调试。

不用就在控制台关了（ctrl+c），服务器就停止了


