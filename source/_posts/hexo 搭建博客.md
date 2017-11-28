---
title: hexo 搭建博客
date: 2017-07-04 09:43:26
tags: 
- hexo
- node.js
categories: 
- node.js
- hexo
---
## 前言
本文介绍 hexo 搭建个人博客，涉及node.js, Github.pages, next, markdown。
<!--more-->
## 教程 ： 
1. ### 安装 node，github，并完成相关配置（略）
2. ### 本地操作 hexo
```bash
#安装 Hexo
$ npm install -g hexo-cli

#hexo安装文件
#在项目目录下
$ hexo init
$ npm install

#本地访问
$ hexo server
#浏览器输入 http://localhost:4000/，不报错则成功
```
3. ### 下载并配置 next 主题
	- #### 下载
	```bash
	$ git clone https://github.com/tufu9441/maupassant-hexo.git themes/maupassant
	#该主题需安装另外2个modules
	$ npm install hexo-renderer-jade@0.3.0 --save 
	$ npm install hexo-renderer-sass --save
	```
	- #### 配置
	把项目目录下 *_config.yml* 文件 改为
	```
	theme：maupassant 
	```
4. ### 部署到 Github.page
	- #### github上新建username.github.io仓库，如KbellX.github.io
	- #### 下载 hexo-deployer-git
	```bash
	$ npm install hexo-deployer-git --save
	```
	- #### 配置 
	在./config.yml 配置
	**注意冒号后要空格！**
	```bash
	deploy:
	 type: git
	 repo: 仓库地址
	 branch: master
	```
	- #### 正式部署
	```bash
	$ hexo deploy
	```
	- #### 通过 http://username.github.io 访问
5. ### 发博文
```bash
#./source/_posts/下生成my-first-article.md
$ hexo new my-first-article

#用 markdown 语法写博文
# 将 my-first-article.md 生成 ./public/多个my-first-article/index.html
$ hexo generate 

#看一看
$ hexo server

#发布到远程
$ hexo deploy 
```

## 我的理解
- hexo ：node.js的一个module
- next ：主题，通过 git clone 下载，再配置即可用；切换方便，对 主题 外文件改动小（未实践）
- Github.pages ：是代表 **当前用户** 的仓库（网站），部署后可通过 http://username.github.io 访问
- markdown ：一种轻量级标记语言，易读易写，写好即排版
- hexo搭建过程简单，重点在习惯markdown语法写博文
- hexo方式搭博客最终生成的是静态网页，一篇博文是一个纯html文件，因此速度极快
- 牺牲空间，如一篇博文的html在archives，categories，tags等目录下都有储存
- 对于个人博客（面向一个对象存储数据）来说，十分适用

## Notice
1. 目录结构
```
.
├── _config.yml  	//hexo的配置文件
├── package.json
├── node_modules	
├── public		//github仓库会显示的文件，即网页上能访问的部分
├── scaffolds		//生成 md文件 页面的模板
├── source 		//md文件，页面（如博文，about）的源文件
|   ├── _drafts
|   └── _posts
└── theme： 		//主题
```
	theme里也有*_config.yml*文件，注意区分；
	配置文件格式要注意，如冒号后空格；
2. hexo命令
```
hexo generate ~ hexo g 
hexo server ~ hexo s 
hexo deploy ~ hexo d
```
	hexo server 输入后只要不退出或关闭bash，node处于监听状态，类似打包工具webpack -w（即修改博文后刷新页面即能看到修改，不用再次输hexo server)
3. 但hexo d前 最好先 hexo g 一下，因为 监听 状态下 刷新页面 看到的修改是临时的。
4. 尽量通过 hexo new 生成md文件（直接新建md，有些地方好像没有关联）
5. 分类categories 与 标签tags 区别：标签都是同级的，分类有从属关系，前父后子	

## 相关链接
重点：
- [Github.pages 官网](https://pages.github.com/)
- [hexo 官方教程](https://hexo.io/zh-cn/docs/setup.html)
- [next 使用手册](http://theme-next.iissnan.com/)
- [markdown 手册](http://wowubuntu.com/markdown/basic.html)
- [本博客主题](https://github.com/tufu9441/maupassant-hexo)

可选：
- 小图标 : [Font Awesome icons](http://fontawesome.io/3.2.1/icons/)
