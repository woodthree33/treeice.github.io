---
layout: splash
header:
  overlay_image: /assets/images/bg_tree_1_half.jpg
  overlay_filter: rgba(64,224,208, 0.5)
  image_description: "Waldeinsamkeit 置身森林深处,与自然水乳交融的孤独"
  cta_label: "More Info"
  cta_url: "https://unsplash.com"
title:  "Jekyll-的logo图标增添"
excerpt: "在自己的jekyll模板主题当中进行logo替换"
author: treeice
categories: posts jekyll
---

# 在网页打开时候，浏览器出现你的logo

### 老师的网页的中出现的是![Keble College Icon](https://raw.githubusercontent.com/hanteng/hanteng.github.io/cf9691a940e8d9527d64553501a90991e9c5f1ab/apple-touch-icon.png)

#### 我们需要给自己的网页定制一个logo 

 - 具体我们看老师的模板第一次[提交内容](https://github.com/hanteng/hanteng.github.io/commit/cf9691a940e8d9527d64553501a90991e9c5f1ab),老师对图标的修改内容。
 - logo可以由ai做，导出png档
 - 老师提供了一个logo制作网页[Favicon Generator. For real.]("https://realfavicongenerator.net/favicon_result?file_id=p1c0fpm1o81ht6kse1cl5187h1bi06")
 - 把自己的logo的png档提交上去
 - ![提交步骤一](/image/Step01.png)
 - ![提交步骤二](/image/Step02.png)
 - ![提交步骤三](/image/Step03.png)
 
## 以下步骤，该模板以完成

 - - 生成后，把文件压缩包下载下来，其中黑框的代码，是引用logo的代码，在jekyll里面，网页的各种信息是存放在不同位置，然后通过统一的引用就能加入所有的网页中去
 - - 这里，我们在_includes文件夹中创建一个名为favicon.html的文件。在里面把那几行代码填入：
 - - ![提交步骤四](/image/Step04.png)
 - - 然后打开_layout文件夹下的_default.html文件，把刚刚创建的favicon.html的文件加入网页之中，格式是大括号{\% \%}，里面填写引用代码的文件位置，这里是 include favicon.html 两个位置。
 - - ![提交步骤五](/image/Step05.png)
 
## 以上步骤，该模板以完成
## 若想修改这些图标文件位置,去_layout文件夹下的_default.html文件,修改相对位置即可

 
 ---
 
## 最后接下去
 
 - 引用代码填写完后，把刚刚压缩包的文件打开，直接把六个文件放入你的网页文件夹之中，位置观看老师[提交内容](https://github.com/hanteng/hanteng.github.io/commit/cf9691a940e8d9527d64553501a90991e9c5f1ab)，不需要单独放入一个文件夹
 + + apple-touch-icon-precomposed.png
 + + apple-touch-icon.png
 + + favicon-16x16.png
 + + favicon-32x32.png
 + + favicon.ico
 + + manifest.json
 - ![提交步骤六](/image/Step06.png)
# 然后logo就生成换好了。