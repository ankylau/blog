---
id: 1395
title: 一键填写评论相关信息，适合wp和typecho
date: 2018-03-09T11:18:23+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1395
permalink: /automatically-fill-in-personal-information/
hestia_layout_select:
  - default
post_extend:
  - 'a:12:{s:14:"push_slide_img";s:0:"";s:20:"push_slide_below_img";s:0:"";s:16:"seo_custom_title";s:0:"";s:19:"seo_custom_keywords";s:0:"";s:15:"seo_custom_desc";s:0:"";s:11:"post_layout";s:3:"one";s:8:"head_img";s:0:"";s:12:"post_gallery";s:0:"";s:14:"post_video_url";s:0:"";s:10:"push_slide";b:0;s:16:"push_slide_below";b:0;s:19:"post_layout_gallery";b:0;}'
views:
  - "1"
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/03/cms-265128_1280.jpg
categories:
  - 日常分享
tags:
  - 浏览器
---
> ###### 今天，要介绍的也是同样的把 Javascript 代码存为书签来使用的方法，但又有很大的不同，因为网上的所有方法都有很大缺陷，他们不能实现跨平台跨网站，也就是说，可能适用于 wordpress、Typecho、zblog 和 emlog 等平台中的一个或几个，但都不能全部通用！我这里介绍的就是全平台全网通用的留言评论自动填写个人信息方法
> 
> <cite>Anky Lau</cite>

我们在访问网站时，看到一篇文章，想发表评论时，是否经常要在评论框里手动填写自己的昵称、E-mail 和网址等留言评论信息？重复的打字会让我们感到很乏味。 为了解决这个问题，我在网上搜索相关资料，找到了很多使用 Javascript 代码的教程方法文章，操作方法是将这段代码作为书签的 URL 字段保存在书签栏中，即可实现点击书签栏上的按钮自动填充自己的信息。

<pre class="pure-highlightjs"><code class="java">javascript: void
function() {
    var lauthor = ["#author","input[name='comname']","#inpName","input[name='author']","#ds-dialog-name","#name"],
    lmail =["#mail","#email","input[name='commail']","#inpEmail","input[name='email']","#ds-dialog-email","input[name='mail']"],
    lurl =["#url","input[name='comurl']","#inpHomePage","#ds-dialog-url","input[name='url']","#website"];
    for (i = 0; i &lt; lauthor.length; i++) {
        var author = document.querySelector(lauthor[i]);
        if (author != null) {
            author.value = '你的姓名';
            break;
        }
    }
    for (j = 0; j &lt; lmail.length; j++) {
        var mail = document.querySelector(lmail[j]);
        if (mail != null) {
            mail.value = '你的邮箱';
            break;
        }
    }
    for (k = 0; k &lt; lurl.length; k++) {
        var url = document.querySelector(lurl[k]);
        if (url != null) {
            url.value = '你的网址';
            break;
        }
    }
    return ! 1;
} ()</code></pre>

使用方法：在浏览器新建一个书签,然后把下面这段代码粘贴到网址一栏，每次评论需要填写信息的时候，直接点击这个书签即可。

_via:https://www.liushichao.com/164.html_