---
layout: post
title: 博客搭建小结
tag: Other
---

本博客初步搭建耗时11天，使用的平台和技术主要包括：<br>
<strong style="color:#B90000;">Github Pages,Jekyll-2.1.0,Markdown,Pygments-0.5.0</strong><br>

基本介绍如下：<br>

+ <p>Github Pages: Github设计了Pages功能，允许用户自定义项目首页，用来替代原来的源码列表。Github Pages可以被认为是用户编写的，托管在Github上的
静态网页。</p>

+ <p>Jekyll: 是一种简单的、适用于博客的、静态网站生成引擎，它使用一个模版目录作为网站布局的基本框架，提供了模版、变量、插件等功能，
最终生成一个完整的静态Web站点。<br>
Jekyll使用Liquid模版语言，包括两种Liquid标记语言：输出标记(output markup)和标签标记 (tag markup)。输出标记会输出文本(如果被引用的变量存在)，而标签标记不会。输出标记是用双花括号分隔，而标签标记是用花括号-百分号对分隔。</p>

+ <p>Github Pages和Jekyll的关系: Github Pages提供用于托管项目主页或博客的服务，Jekyll是后台所运行的引擎。</p>

+ <p>Markdown: 一种轻量级标记语言，允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)
文档”。这里，我使用的是C写的模版解释器RDiscount，其效率比默认模版Maruku更高。</p>

+ <p>Pygments: 是一种通用的语法高亮显示功能，使用在各种软件上，比如论坛系统、维基百科或其他需要美化代码的应用程序里。</p>