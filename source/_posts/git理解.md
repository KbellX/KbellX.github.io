---
title: git理解
date: 2017-07-06 11:19:04
tags:
- git
categories:
- git
---
## 前言
本人对git的理解，若有不当，欢迎指出

### 文件
tags，branch都是指向提交commit的

### 标签
标签 实质 是 ./refs/tags/ 下的一个文件，其内容 是一个提交的 SHA值。
即 2个值 确定一个标签：标签名 和提交SHA值 
推送远程标签格式
```bash
$ git push origin refs/tags/v1:refs/tags/v3
```
v3 即为远程标签名，SHA值为 本地v1 标签对应的SHA值
```bash
$ git push origin v1
```
v1为远程标签名，SHA值为本地v1标签对应的SHA值
```bash
$ git push origin :refs/tags/v1 
```
远程标签名为v1，SHA值为空，无意义，便删除

### 远程（push&pull）