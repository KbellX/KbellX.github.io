---
title: git常用命令
date: 2017-07-05 20:30:49
tags: 
- git
categories:
- git
---
## 前言
总结git常用命令，持续更新
<!--more-->
## 必要说明
+ 远程主机名默认为 origin
+ 绝大部分命令在项目目录下执行

## 命令
### 配置
```bash
$ git config --global user.name "xxx"			## 配置用户名
$ git config --global user.email "xxx@xxx.com"		## 配置邮件
$ git config --global push.default matching		## 设置成matching模式：不带任何参数的git push 推送 对应远程分支 
$ git config --global push.default simple		## 设置成simple模式：不带任何参数的git push 仅推送 当前分支
```
### 初始化
```bash
$ git init					## 新建本地仓库
```
### 提交
```bash
$ git add <file>				## 提交到stage
$ git commit -m "说明"				## 提交到本地仓库
$ git commit -am '说明'				## add并commit
```
### 撤销修改
```bash
$ git clean -f					## 删除untracked files
$ git checkout -- <file>			## 根据 stage 撤销 工作区 修改
$ git reset HEAD <file>				## 根据 本地仓库 回退 stage 修改
```
### 回退
```bash
$ git reset HEAD^				## 退回上一个版本
$ git reset HEAD~2				## 退回到前2个版本，依次类推
$ git reset fc7098				## 退回到版本号 fc7098 版本
$ git reset fc7098 --soft			## 版本库退回指定版本，stage与工作区不退
$ git reset fc7098 				## 默认参数为 mixed，版本库与stage退回，工作区不退
$ git reset fc7098 --hard 			## 三区都退回指定版本
```
### 分支
```bash
$ git branch					## 查看分支
$ git branch -r					## 查看远程分支
$ git branch -a 				## 查看所有分支
$ git branch <name>				## 创建分支不切换
$ git branch -d <name>				## 删除分支
$ git checkout <name>				## 切换分支
$ git checkout -b <name>			## 创建并切换分支
```
### 远程
```bash
$ git remote add origin git@github.com:username/repositories.git	## 关联已存在远程仓库
$ git branch --set-upstream master origin/next				## 当前master分支与远程主机origin的next建立追踪关系
### push ###
$ git push origin master:master 					## 将本地master分支(冒号前)推送到远程主机origin的master分支(冒号后)
$ git push origin master						## 将本地master分支推送到远程主机origin中与之有“追踪关系”的分支，不存在则新建
$ git push origin :master						## 推送空分支到远程master分支，即删除远程master分支
$ git push origin --delete master					## 删除远程master分支
$ git push -u origin <name>						## 将分支发布到远程主机origin，-u表示指定该主机为默认主机，给两分支"追踪关系"
$ git push origin 							## 推送当前分支到远程主机origin与之有“追踪关系”的分支
$ git push								## 推送当前分支到（只存在一个或默认主机）的与之有"追踪关系"的分支
### fetch ###
$ git fetch origin master						## 取回不合并
### pull ###
$ git pull origin dev:master						## 取回远程主机origin的dev分支，与本地master分支合并
$ git pull origin dev							## 取回远程主机origin的dev分支，并与当前分支合并
$ git pull origin							## 取回与当前分支有追踪关系的远程分支并合并
### clone ###
$ git clone git@github.com:username/repositories.git 			## 克隆远程仓库
$ git clone git@github.com:username/repositories.git dir 		## 克隆远程仓库到dir文件夹
```
### 合并
```bash
$ git merge origin/master 	## 合并远程分支master到当前分支
$ git merge dev			## 合并本地dev分支到本地当前分支
```
### 标签
```bash
$ git tag 					## 列出当前所有标签
$ git tag v1					## 给当前commit新建v1标签
$ git tag v1 16df112				## 给版本号16df112的commit v1标签
$ git tag -d v1 				## 删除本地v1标签
$ git push origin refs/tags/v1:refs/tags/v1 	## 推送远程标签格式
$ git push origin refs/tags/v1:refs/tags/v2 	## 新建远程标签v2，对应提交为本地v1标签对应的提交
$ git push origin v1 				## 新建远程标签v1，对应提交为本地v1标签对应的提交
$ git push origin :refs/tags/v1 		## 删除远程v1标签
$ git push --tags				## 推送所有标签
```
### 查看
```bash
$ git status 					## 查看修改
$ git branch					## 查看分支
$ git log 					## 查看版本历史
$ git diff					## 查看工作区与stage区别
$ git diff <file>				## 查看某文件在工作区与stage区别
$ git diff --cached				## 查看stage与版本库区别
$ git diff da4687:<file> ad8753:<file> 		## 查看两版本该文件区别
$ git show 16df112				## 查看版本号16df112的信息
$ git tag 					## 列出当前所有标签
```

## 相关链接
+ [git命令大全](https://gist.github.com/guweigang/9848271#file-git_toturial-L9)
+ [Git远程操作详解-阮一峰](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
+ [常用 Git 命令清单-阮一峰](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
+ [Git教程-廖雪峰](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
