---
titel : gitPage部署
---

# deploy 部署原理
我们的项目文件如你所见。注意其中的/public文件夹。

hexo的原理是把所写的md文件渲染为一组静态html文件，再把这些html交给服务器构成我们的博客网站。

部署过程，即是把所需的html提交给服务器。

# 利用hexo+gitPage部署：

## 配置hexo的提交路径
在config中修改deploy
```hexo
deploy:
  type: git
  repository: git@github.com:chdloser/hexo-blog.git
  branch: public
```

似乎仓库名不填或填错也没关系，当前项目同时只能连接一个远程仓库。当branch名要填对，若分支不存在hexo会创建分支。

## 一键部署

使用hexo 命令一键部署

`hexo g -d` 或 `hexo d -g`

具体执行了：

`hexo g` 生成静态文件

我们编写的md会按照配置生成一系列html，放在 /public下。

`hexo d` 提交到github

实质是
```bash
cd /public
git reset
git add .
git commit
git push -f
```
即是进入public目录，提交此目录下的所有文件并覆盖远程分支。

远程仓库中的对应分支具备了应有的静态文件。打开github仓库。setting-page->选择对应的分支和目录->save 部署完成。博客便托管到了gitPage上，供随时访问。

> 注意：gitPage 只适合托管静态页面
