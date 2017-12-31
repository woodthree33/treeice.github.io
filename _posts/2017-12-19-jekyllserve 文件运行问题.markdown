---
layout: default
title:  "jekyll-cannot load such file -- bundle/bundler/setup (LoadError)"
date:   2017-12-07 23:45:15 +0800
categories: post jekyll 
---
# power shell运行jekyll serve出现问题后解决：
### 问题代码：
> cannot load such file -- bundle/bundler/setup (LoadError)

##### 本地环境： win7,(网络教程是win10，同适用)

### 原因：
 > 不明白。。

### 解决方案：

#### 依次输入以下
```
gem install bundle
bundle install
bundle exec jekyll serve
```
