---
layout: splash
title:  "关于font字体的属性记录"
excerpt: "CSS 中font-style元素的属性记录"
header:
  teaser: /images/img-post-rwd-fontstyle.png
categories: posts rwd
author: treeice
---

# font-style的三个属性

 > - p.normal {font-style:normal;}
 > - p.italic {font-style:italic;}
 > - p.oblique {font-style:oblique;}
 
```
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

 - 字体有粗体、斜体、下划线、删除线等诸多属性。
 - 但是并不是所有字体都做了这些，一些不常用的字体，或许就只有个正常体，如果你用Italic，就没有效果了~这时候你就要用Oblique.
 - 可以理解成Italic是使用文字的斜体，Oblique是让没有斜体属性的文字倾斜！

### 另外附上CSS2.0上边的解释你参考下：

 - italic和oblique都是向右倾斜的文字,
 - 但区别在于Italic是指斜体字，而Oblique是倾斜的文字，
 - 对于没有斜体的字体应该使用Oblique属性值来实现倾斜的文字效果.


[百度来源](https://zhidao.baidu.com/question/85429500)
