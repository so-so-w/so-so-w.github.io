---
title: hexo+nexT相关配置
categories: 博客配置
tags: 博客配置
abbrlink: 989318273
date: 2020-11-02 13:34:45
---

惆怅，搭建好这个静态网站以后，为了好看，又去搜索了各种主题和配置。。。这里简单记录下吧。

<!-- more -->

首先，区别两个配置文件，一个是hexo的 _config.yml，这里我们叫它 站点配置文件，一个是nexT里面的 _config.yml,这里我们叫它 主题配置文件。

## 站点配置

hexo相关操作api
官网地址：[https://hexo.io/zh-cn/docs/writing](https://hexo.io/zh-cn/docs/writing)

1.取消代码块行号：
```
highlight:
  line_number: false
```
2.取消网页底部的powerby,及修改展示文字。
```
footer:
  # If not defined, `author` from Hexo `_config.yml` will be used.
  copyright: "SO-SO"
  # Powered by Hexo & NexT
  powered: false
```
3.本地搜索
1）安装插件hexo-generator-searchdb,执行以下命令:
`npm install hexo-generator-searchdb --save`
2)修改hexo/_config.yml站点配置文件，新增以下内容到任意位置：
```
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```
3)编辑 主题配置文件，启用本地搜索功能：
```
# Local search
local_search:
  enable: true
```
4.图片延迟加载
1）本地安装hexo-lazyload-image，执行以下命令：
`npm install hexo-lazyload-image --save`
2)添加站点配置文件
```
# Lazyload
## Depends on hexo-lazyload-image
lazyload:
  enable: true
  onlypost: false
  # 图片尚未加载完时，显示指定图片。目录地址为博客根目录下的 source/
  loadingImg: /uploads/loading.gif
```
5.链接持久化
1）本地安装hexo-abbrlink，执行以下命令：
`npm install hexo-abbrlink --save`
2)添加站点配置文件（注释掉原有的permalink）
```
permalink: posts/:abbrlink/

# abbrlink config
abbrlink:
  alg: crc32  #support crc16(default) and crc32
  rep: dec    #support dec(default) and hex
```

## nexT主题配置

[官方讲解地址](https://theme-next.js.org/)

1.选择一个喜欢的主题样式  
搜索 Schemes ，去除掉选择样式前面的 # 即可。
这里我把暗黑模式打开了（在手机上调整为暗黑模式后查看）。
```
# Schemes
#scheme: Muse
#scheme: Mist
scheme: Pisces
#scheme: Gemini

# Dark Mode
darkmode: true
```
代码块开启深色配色
```
codeblock:
  highlight_theme: night eighties
```

2.显示文章浏览进度
```
back2top:
  # Scroll percent label in b2t button.
  scrollpercent: true
```

3.设置网站图标
找一张（32 * 32）的 ico 图标，并将图标名称改为 favicon.ico，然后把图标放在 `/themes/next/source/images` 里，并且修改主题配置文件：
```
favicon:
  small: /images/favicon-16x16-next.png
  medium: /images/favicon-32x32-next.png
  apple_touch_icon: /images/apple-touch-icon-next.png
  safari_pinned_tab: /images/logo.svg
```

4.修改文章底部的#号的标签，改为图标
```
# Use icon instead of the symbol # to indicate the tag at the bottom of the post
tag_icon: true
```

5.代码块复制按钮
```
codeblock:
  # Add copy button on codeblock
  copy_button:
    enable: true
    # Show text copy result.
    show_result: true
    # Available values: default | flat | mac
    style:
```

6.文章版权
```
creative_commons:
  license: by-nc-nd
  post: true
  language: deed.zh
```

7.访问量统计
```
busuanzi_count:
  enable: true
  total_visitors: true
  total_visitors_icon: fa fa-user
  total_views: true
  total_views_icon: fa fa-eye
  post_views: true
  post_views_icon: fa fa-eye
```

8.右上角的github
```
github_banner:
  enable: true
  permalink: https://github.com/so-so-w
  title: Follow me on GitHub
```