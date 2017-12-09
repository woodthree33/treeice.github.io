---
layout: post
title:  "Jekyll serve 运行解决出错进程被占方案!"
date:   2017-12-07 23:45:15 +0800
categories: jekyll update
---
# power shell运行jekyll serve出现问题后解决：
### 问题代码：
> error:permission denied -bind(2) for 127.0.0.1:4000

##### 本地环境： win10,(网络教程是win7，同适用)

### 原因：
 > 这个是由于127.0.0.1：4000这个端口被占用引起的；

### 解决方案：
 - 第一步：找到4000端口被哪个进程占用了,打开cmd，在输入
    > netstat -aon | findstr "4000"
 - 观察最后一列的PID进程号码

 - 第二步：关闭冲突进程快键键 ctrl+shift+esc），找到那些PID的进程后停止服务

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
