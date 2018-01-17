---
layout: splash
title:  "[未完]网页设计关于 header 的内容"
excerpt: "html对header的写法记录"
header:
  teaser: /image/img-post-rwd-header.png
categories: posts rwd
author: treeice
---
#### [来源](http://blog.csdn.net/wuyuehuayiyi/article/details/51144014)


## 一.DOCTYPE

 > html5 简洁 <!doctype html>	
 > - 文档进行有效性验证。
 > - 决定浏览器的呈现模式	

## 二.charset    声明文档使用的字符编码																					

 > ``` <meta charset="utf-8"> ```
 
## 三. lang属性

 - <html lang="zh-cmn-Hans">  简体中文
 - <html lang="zh-cmn-Hant"> 繁体中文

## 四.title 标签(head 头部必须)	
						
## 五.keywords 页面关键字																								

 - ```<meta name="keywords" content="your keywords"> ```																												
																																													
## 六.页面描述内容 description																						
	
 - ```<meta name="description" content="your description"> ```
																																																																						
## 七.定义网页作者 author

 - ```<meta name="author" content="author,email address">	```	

## 	八.viewport

 - 1. ```<meta name="viewport" content="width=device-width, initial-scale=1.0">```
 > - width=device-width 会导致 iPhone 5 添加到主屏后以 WebApp 全屏模式打开页面时出现黑边(http://bigc.at/ios-webapp-viewport-meta.orz)
 > - content:
参数|-
-|-
width viewport | 宽度(数值/device-width)
height viewport | 高度(数值/device-height)
initial-scale | 初始缩放比例
maximum-scale | 最大缩放比例
minimum-scale | 最小缩放比例
user-scalable |是否允许用户缩放(yes/no)

> - minimal-ui iOS 7.1 beta 2 中新增属性，可以在页面加载时最小化上下状态栏。这是一个布尔值，可以直接这样写：```<meta name="viewport" content="width=device-width, initial-scale=1, minimal-ui">```

 > - 而如果你的网站不是响应式的，请不要使用 initial-scale 或者禁用缩放。
   ```<meta name="viewport" content="width=device-width,user-scalable=yes">```
 > - 适配 iPhone 6 和 iPhone 6plus 则需要写：									
	```<meta name="viewport" content="width=375">```
	```<meta name="viewport" content="width=414">```
 > - - 大部分 4.7~5 寸的安卓设备的 viewport 宽设为 360px，iPhone 6 上却是 375px，
 > - - 大部分 5.5 寸安卓机器（比如说三星 Note）的 viewport 宽为 400，iPhone 6 plus 上是 414px。

								

									
						
