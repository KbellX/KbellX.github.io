---
title: mrakdown常用语法
date: 2017-07-05 10:00:42
tags: 
- 杂
categories: 
- 杂
---
## 前言
markdown是一种轻量级标记语言，其语法简单，写好即排版。

## 标题
```
## 标题2
### 标题3
#### 标题4
##### 标题5
###### 标题6；#后要空一格
```
## 标题2
### 标题3
#### 标题4
##### 标题5
###### 标题6；#后要空一格

## 引用
```
> 这是一个引用
> 
> 引用
```
> 这是一个引用
> 
> 引用

## 修饰
```
*斜体*
**加粗**
```
*斜体*
**加粗**

## 链接
```
[这是一个链接:我的博客](https://kbellx.github.io/)
```
[这是一个链接:我的博客](https://kbellx.github.io/)

## 代码
```
I strongly recommend against using any `<blink>` tags.
I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.
```
I strongly recommend against using any `<blink>` tags.
I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.

```
	一个tab键或4个空格键表示该行为代码	
		第二行起要2个tab才能与第一行列对齐
没有tab的行就不是代码
```
	一个tab键或4个空格键表示该行为代码	
		第二行起要2个tab才能与第一行列对齐
没有tab的行就不是代码

```
被上下包围的是一段代码
	同样，第二行起要1个tab键才能对齐
这行没tab，没对齐
```	

## 换行
第一行
在第一行后敲回车 对应html为 `<br >`
一个空行 则上下分成2个`<p>`

## 分割线
三个以上的`*`或`-`或`_`,该行不能有任何其它东西
`*******************`
*******************

## 列表
+ `+`,`-`,`*` 都可以表示列表 
+ 一级
+ 一级
	+ `tab`再 `+` 就表示二级（下一级）
- 若不同，前`+`后`-`就是2个同级ul

1. 一
2. 二
3. 三

## 反斜杠
\*被`*`包围的不再是斜体了\*