---
layout: splash
header:
  overlay_image: /assets/images/bg_tree_1_half.jpg
  overlay_filter: rgba(64,224,208, 0.5)
  image_description: "Waldeinsamkeit 置身森林深处,与自然水乳交融的孤独"
  cta_label: "More Info"
  cta_url: "https://unsplash.com"
title:  "Jekyll-的基础信息修改和博文格式"
excerpt: "在skiny-bones的模板为例子的基础信息修改和文章结构规格"
author: treeice
categories: posts jekyll
---
# 首先做这个，最重要的一步，用notepad++打开_config.yml文件

	- 在文件里面把个人信息修改掉。
	
## 一。你现在看到的就是放文章的博文

 - 你现在看到的就是我写的博文，存放在_post文件夹里面
 - 支持[markdown格式](https://www.jianshu.com/p/q81RER)
 - 文件后缀就是markdown的缩写md结尾。
 
#### 1.有道云

 - 可以看到markdown格式的效果，
 - 所以先写在有道云
 - 如果效果正确，就再copy过来
 
#### 2.博文的文件名字格式是固定的格式：

```
年-月-日-文件名.md
```

## 二。可视化的博文和网页设计的博文有区别

 1. 在_post文件夹里面找到我写的这个【2017-11-30-一些建议.md】
 2. 用notepad+ 打开
 3. 这个文件的最开始有几行被三个---围起来的代码

```
 layout: default
 title:  "博客文章标题"
 categories:  "未填"
```

 - 每个博文都要这几行内容，要不然不显示
 - 【必填的】第一个意思是网页布局为_layout文件夹default.html文件，default.html文件是准备好的网页格式，你在这 里写layout: default，你写的markdown就会引向这个布局格式
 - - 老师在GitHub上在自己的网页的修改历史有把自己博文从default修改为article，意思也就是布局从default.html文件变为同一个位置另一个准备好的网页格式的article.html文件
 - 【必填的】接着的title就是标题，就是这篇博文在网页显示的标题，
 - 【必填的】第三个就是categories：这里**用英文**填写几个关键词，记得用空格分开，这里就是按从左到右的顺序填写的词就会变成打开网页看自己的博文时候的网页地址出现
 - - 例如：
 - - 老师的其中一篇博客文章 [先自裝Ruby](https://hanteng.github.io/notes_tech/jekyll/Ruby/) ，看这个文件的时候，你会看到老师的 [博客文件](https://github.com/hanteng/hanteng.github.io/blob/master/_posts/2017-11-30-Ruby.md)在categories 后面填写notes_tech和 Jekyll,注意[先自裝Ruby](https://hanteng.github.io/notes_tech/jekyll/Ruby/)网址最后面出现了/notes_tech/jekyll//Ruby，其中最后的ruby是老师的博客文件名，而前两个notes_tech和 Jekyll就是老师在博客里写的
 - 所以对应的博文categories按照下面的填

分类|对应的内容
-|-
信息可视化笔记 分类(categories)| posts  infovis
Web  分类(categories)|p osts rwd 

 - 记得空格，例如：
 - 可视化的笔记要这样子要修改为：

	categories: posts  infovis

----

# 三。作品放在

- 这个模板的目录已经改好为两个个人作品集
- 具体的文件是在_data文件的navigation.yml
- infovis 文件夹放信息可视化作品集，放在index.md
- portfolio 文件夹放网页设计作品集，放在index.md


----

# 具体老师的要求看他的[提交内容](https://github.com/hanteng/hanteng.github.io/commits/master)，再对应文件上做修改