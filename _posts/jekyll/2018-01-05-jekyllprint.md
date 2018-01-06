---
layout: splash
header:
  overlay_image: /assets/images/bg_tree_1_half.jpg
  overlay_filter: rgba(64,224,208, 0.5)
  image_description: "Waldeinsamkeit 置身森林深处,与自然水乳交融的孤独"
  cta_label: "More Info"
  cta_url: "https://unsplash.com"
title:  "Jekyll-关于打印的设置"
excerpt: "关于老师的模板在print打印的修改"
author: treeice
categories: posts jekyll
---

# 关于个人github的网页打印的问题
 > 这个教程是依照汉腾老师的skiny bones的[Jekyll模板](https://hanteng.github.io)的例子
 
 > 就算是其它模板的也可以拿做参考
 
 > 如果使用minial mistake模版的可以来找我或者文浩 一起讨论

 > ##### 老师模板打印的修改记录:
 
 - [media print CSS 移除不印的並A4](https://github.com/hanteng/hanteng.github.io/commit/124b98a7edb53ccdafdf71d06afbfc044b0f2bed)
 - [解決Bourbon Neat打印問題](https://github.com/hanteng/hanteng.github.io/commit/124b98a7edb53ccdafdf71d06afbfc044b0f2bed)
 
### 打印的意思就是
 - 当你在自己的网页,鼠标右键点击打印的时候,网页会启动另外一种css样式表,所以我们要加入一个新的css布局给打印的情况,修改完后,打印出pdf档,提交作业

 - 打印三张 :
 - 截图来源[老师的网站](https://hanteng.github.io)和[某位同学](https://jamieyin.github.io)的网站
 - 1.**网页的文章页面**(类似)
 - - - ![打印的网页的文章页面](/image/post_print_04.png)
 - 2.**网页设计作品集页** 和 **可视化作品集页面**(类似)
 - - - ![打印的网页的可视化作品页面](/image/post_print_00.png)

## 具体 

## 总的修改文件以下：

 -  _sass/_layout.scss
 - _sass/vendor/neat/grid/_media.scss
 - Gemfile 
 - Gemfile.lock

### 第一步
  
####  [要改]在你的网页文件夹_sass/vendor/neat/grid/_media.scss当中**补上**print

 - - - ![老师的打印步骤](/image/post_print_01.png)

#### [要改]把print写上去的具体修改的代码,整行复制代替: 

```
    @media  print, screen and ($default-feature: nth($query, 1)) {

    $mediaQuery: 'print , screen and ';
    
```

---
---

#### [不用改]以下是老师的这一步修改的笔记和想法,我看不大懂,如果你看懂了,和我分享一下谢谢:

```
@media screen and (min-width: 30em)
main.css:4
.tile {
    float: left;
    display: block;
    margin-right: 2.3576515979%;
    width: 23.2317613015%;
}
.tile {
    max-width: 68em;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 1.618em;
}
```

##### [不用改]想法

- 讓 @media print 同某一screen 
- in 96dpi: A4 (21 × 29.7 cm), you should use 794 × 1122 pixels
- _grid-settings.scss 中794對映到的是small


```
@media screen 
```
##### [不用改]改成

```
@media print, screen 
```

##### [不用改]問題

- 問題找到了在 tile，但_tiles.scss 中 沒有可改的地方
- 其他人有遇到同樣的問題[Bourbon Neat media() not working for print media](https://cmsdk.com/css3/bourbon-neat-media-not-working-for-print-media.html)
- 要去改neat\grid\_media.scss
- 成果：[解決Bourbon Neat打印問題](https://github.com/hanteng/hanteng.github.io/commit/124b98a7edb53ccdafdf71d06afbfc044b0f2bed)

---
---

### 第二步

#### [要改]在你的网页文件夹_sass/_layout.scss中补上print打印的具体css样式内容

- 代码如下 ctrl+A复制:

```

 /*
   Printer Setup
   ======================================================================= */
@page {
  size: A4;
  margin: 0;
}

@media print {
    #masthead, nav, button, html [type=button], .menu-screen {
        display: none;
    }
    html, body {
        width: 210mm;
        height: 297mm;
        margin: 0;
        padding: 0;
        border: 1px #D3D3D3 solid;
        border-radius: 5px;
        box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    }
    #page-wrapper {
        border: initial;
        border-radius: initial;
        width: initial;
        min-height: initial;
        box-shadow: initial;
        background: initial;
        page-break-after: always;
        max-width: 190mm;
        min-height: 250mm;
        max-height: 256mm;
        padding: 10mm;
        margin: 20mm auto;
		border: 1px white dotted;
		height: 256mm;
		outline: 2cm #cbecff solid;
	}
	
    p {
	    font-size: 0.625rem !important;		
	}
	
	h1 {
	    font-size: 1rem !important;		
	}
	
	h2, h3, h4, h5, h6 {
	    font-size: 0.75rem !important;		
	}
}

```

### css的设计的原由:

 - 只保留一定数量的网页文章和文章照片(如果你有)
 - 不显示任何链接,不显示任何导航栏, 不显示其他按键

### css具体的做法:

#### @page 把页面容器的大小设计为a4

#### @media print 增加媒体查询选择

#### 在body和html中设置高宽度大小等

```
       width: 210mm;
       height: 297mm;
```

#### 接着,查看网页的导航,按钮的元素哪里

 - 打开自己的网页,按f12,进去开发者工具,
 - 网页中选择所有导航,按钮之类,查看元素和class名称,
 - 找到以下内容为不需要显示的
 - - #masthead
 - -  nav
 - -  button
 - -  html [type=button] 
 - -  .menu-screen
 - - - 做法:不显示
 
```
#masthead, nav, button, html [type=button], .menu-screen {
        display: none;
    }
```

#### 页面中的主要内容在这个元素之中,包括文章

 - - #page-wrapper 
 - - - 做法:单独设置格式,
 - - - - [加框](http://www.w3school.com.cn/cssref/pr_border.asp),[盒阴影](http://www.w3school.com.cn/cssref/pr_box-shadow.asp),[行分页的分页行为](http://www.w3school.com.cn/cssref/pr_print_page-break-after.asp)

```
border: initial
box-shadow: initial;
page-break-after: always;
```

#### 页面中的文字,按照标等级,文章题目和描述等情况,划分不同的字体大小

 - - p , h1 , h2~h6 这几个元素划分
 - - - 做法:每个都单独设置字体大小,期中
 - - - !important 的语法是提高css样式表的应用优先等级,保证设置的字体被应用
 
```
font-size: 1rem !important;	
```


### 具体的的不理解的css内容都可以自行百度在[w3school](http://www.w3school.com.cn/)找到语法解释


### 第三步

#### [要改]修改Gemfile 和 Gemfile.lock 两个文件
 
 > [关于gemfile的官方解释文档](https://jekyllrb.com/docs/quickstart/#about-bundler)

 > bundler is a gem that manages other Ruby gems. It makes sure your gems and gem versions are compatible, and that you have all necessary dependencies each gem requires.
 
 > The Gemfile and Gemfile.lock files inform Bundler about the gem requirements in your site. If your site doesn’t have these Gemfiles, you can omit bundle exec and just run jekyll serve.

 > When you run bundle exec jekyll serve, Bundler uses the gems and versions as specified in Gemfile.lock to ensure your Jekyll site builds with no compatibility or dependency conflicts.

#### [要改]用notepad++打开 Gemfile文件中补上:

 > 在本地运行时候,可能需要安装补上这个gem

```
gem 'github-pages'
```

#### [要改]在 Gemfile.lock文件中补上

 - 以下可以直接ctrl+A:
 
```
GEM
  remote: https://rubygems.org/
  specs:
    activesupport (4.2.9)
      i18n (~> 0.7)
      minitest (~> 5.1)
      thread_safe (~> 0.3, >= 0.3.4)
      tzinfo (~> 1.1)
    addressable (2.5.2)
      public_suffix (>= 2.0.2, < 4.0)
    coffee-script (2.4.1)
      coffee-script-source
      execjs
    coffee-script-source (1.11.1)
    colorator (1.1.0)
    commonmarker (0.17.7.1)
      ruby-enum (~> 0.5)
    concurrent-ruby (1.0.5)
    ethon (0.11.0)
      ffi (>= 1.3.0)
    execjs (2.7.0)
    faraday (0.13.1)
      multipart-post (>= 1.2, < 3)
    ffi (1.9.18)
    ffi (1.9.18-x64-mingw32)
    forwardable-extended (2.6.0)
    gemoji (3.0.0)
    github-pages (172)
      activesupport (= 4.2.9)
      github-pages-health-check (= 1.3.5)
      jekyll (= 3.6.2)
      jekyll-avatar (= 0.5.0)
      jekyll-coffeescript (= 1.0.2)
      jekyll-commonmark-ghpages (= 0.1.3)
      jekyll-default-layout (= 0.1.4)
      jekyll-feed (= 0.9.2)
      jekyll-gist (= 1.4.1)
      jekyll-github-metadata (= 2.9.3)
      jekyll-mentions (= 1.2.0)
      jekyll-optional-front-matter (= 0.3.0)
      jekyll-paginate (= 1.1.0)
      jekyll-readme-index (= 0.2.0)
      jekyll-redirect-from (= 0.12.1)
      jekyll-relative-links (= 0.5.2)
      jekyll-remote-theme (= 0.2.3)
      jekyll-sass-converter (= 1.5.0)
      jekyll-seo-tag (= 2.3.0)
      jekyll-sitemap (= 1.1.1)
      jekyll-swiss (= 0.4.0)
      jekyll-theme-architect (= 0.1.0)
      jekyll-theme-cayman (= 0.1.0)
      jekyll-theme-dinky (= 0.1.0)
      jekyll-theme-hacker (= 0.1.0)
      jekyll-theme-leap-day (= 0.1.0)
      jekyll-theme-merlot (= 0.1.0)
      jekyll-theme-midnight (= 0.1.0)
      jekyll-theme-minimal (= 0.1.0)
      jekyll-theme-modernist (= 0.1.0)
      jekyll-theme-primer (= 0.5.2)
      jekyll-theme-slate (= 0.1.0)
      jekyll-theme-tactile (= 0.1.0)
      jekyll-theme-time-machine (= 0.1.0)
      jekyll-titles-from-headings (= 0.5.0)
      jemoji (= 0.8.1)
      kramdown (= 1.14.0)
      liquid (= 4.0.0)
      listen (= 3.0.6)
      mercenary (~> 0.3)
      minima (= 2.1.1)
      rouge (= 2.2.1)
      terminal-table (~> 1.4)
    github-pages-health-check (1.3.5)
      addressable (~> 2.3)
      net-dns (~> 0.8)
      octokit (~> 4.0)
      public_suffix (~> 2.0)
      typhoeus (~> 0.7)
    html-pipeline (2.7.1)
      activesupport (>= 2)
      nokogiri (>= 1.4)
    i18n (0.9.1)
      concurrent-ruby (~> 1.0)
    jekyll (3.6.2)
      addressable (~> 2.4)
      colorator (~> 1.0)
      jekyll-sass-converter (~> 1.0)
      jekyll-watch (~> 1.1)
      kramdown (~> 1.14)
      liquid (~> 4.0)
      mercenary (~> 0.3.3)
      pathutil (~> 0.9)
      rouge (>= 1.7, < 3)
      safe_yaml (~> 1.0)
    jekyll-avatar (0.5.0)
      jekyll (~> 3.0)
    jekyll-coffeescript (1.0.2)
      coffee-script (~> 2.2)
      coffee-script-source (~> 1.11.1)
    jekyll-commonmark (1.1.0)
      commonmarker (~> 0.14)
      jekyll (>= 3.0, < 4.0)
    jekyll-commonmark-ghpages (0.1.3)
      commonmarker (~> 0.17.6)
      jekyll-commonmark (~> 1)
      rouge (~> 2)
    jekyll-default-layout (0.1.4)
      jekyll (~> 3.0)
    jekyll-feed (0.9.2)
      jekyll (~> 3.3)
    jekyll-gist (1.4.1)
      octokit (~> 4.2)
    jekyll-github-metadata (2.9.3)
      jekyll (~> 3.1)
      octokit (~> 4.0, != 4.4.0)
    jekyll-mentions (1.2.0)
      activesupport (~> 4.0)
      html-pipeline (~> 2.3)
      jekyll (~> 3.0)
    jekyll-mermaid (1.0.0)
    jekyll-optional-front-matter (0.3.0)
      jekyll (~> 3.0)
    jekyll-paginate (1.1.0)
    jekyll-readme-index (0.2.0)
      jekyll (~> 3.0)
    jekyll-redirect-from (0.12.1)
      jekyll (~> 3.3)
    jekyll-relative-links (0.5.2)
      jekyll (~> 3.3)
    jekyll-remote-theme (0.2.3)
      jekyll (~> 3.5)
      rubyzip (>= 1.2.1, < 3.0)
      typhoeus (>= 0.7, < 2.0)
    jekyll-sass-converter (1.5.0)
      sass (~> 3.4)
    jekyll-seo-tag (2.3.0)
      jekyll (~> 3.3)
    jekyll-sitemap (1.1.1)
      jekyll (~> 3.3)
    jekyll-swiss (0.4.0)
    jekyll-theme-architect (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-cayman (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-dinky (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-hacker (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-leap-day (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-merlot (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-midnight (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-minimal (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-modernist (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-primer (0.5.2)
      jekyll (~> 3.5)
      jekyll-github-metadata (~> 2.9)
      jekyll-seo-tag (~> 2.2)
    jekyll-theme-slate (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-tactile (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-theme-time-machine (0.1.0)
      jekyll (~> 3.5)
      jekyll-seo-tag (~> 2.0)
    jekyll-titles-from-headings (0.5.0)
      jekyll (~> 3.3)
    jekyll-watch (1.5.1)
      listen (~> 3.0)
    jemoji (0.8.1)
      activesupport (~> 4.0, >= 4.2.9)
      gemoji (~> 3.0)
      html-pipeline (~> 2.2)
      jekyll (>= 3.0)
    kramdown (1.14.0)
    liquid (4.0.0)
    listen (3.0.6)
      rb-fsevent (>= 0.9.3)
      rb-inotify (>= 0.9.7)
    mercenary (0.3.6)
    mini_portile2 (2.3.0)
    minima (2.1.1)
      jekyll (~> 3.3)
    minitest (5.10.3)
    multipart-post (2.0.0)
    net-dns (0.8.0)
    nokogiri (1.8.1)
      mini_portile2 (~> 2.3.0)
    nokogiri (1.8.1-x64-mingw32)
      mini_portile2 (~> 2.3.0)
    octokit (4.8.0)
      sawyer (~> 0.8.0, >= 0.5.3)
    pathutil (0.16.1)
      forwardable-extended (~> 2.6)
    public_suffix (2.0.5)
    rb-fsevent (0.10.2)
    rb-inotify (0.9.10)
      ffi (>= 0.5.0, < 2)
    rouge (2.2.1)
    ruby-enum (0.7.1)
      i18n
    rubyzip (1.2.1)
    safe_yaml (1.0.4)
    sass (3.5.4)
      sass-listen (~> 4.0.0)
    sass-listen (4.0.0)
      rb-fsevent (~> 0.9, >= 0.9.4)
      rb-inotify (~> 0.9, >= 0.9.7)
    sawyer (0.8.1)
      addressable (>= 2.3.5, < 2.6)
      faraday (~> 0.8, < 1.0)
    terminal-table (1.8.0)
      unicode-display_width (~> 1.1, >= 1.1.1)
    thread_safe (0.3.6)
    typhoeus (0.8.0)
      ethon (>= 0.8.0)
    tzinfo (1.2.4)
      thread_safe (~> 0.1)
    unicode-display_width (1.3.0)

PLATFORMS
  ruby
  x64-mingw32

DEPENDENCIES
  github-pages
  jekyll
  jekyll-feed
  jekyll-gist
  jekyll-mermaid
  jekyll-sitemap

BUNDLED WITH
   1.16.0
```


  
# 以上就是老师的修改,大家回去试一试,有问题,马上和我说一下.谢谢