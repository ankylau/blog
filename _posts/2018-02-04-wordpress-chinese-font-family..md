---
id: 1221
title: WP国外主题设置font-family中文字体
date: 2018-02-04T01:19:53+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1221
permalink: /wordpress-chinese-font-family/
neverland_post_options:
  - 'a:8:{s:5:"title";s:4:"show";s:16:"sidebar_position";s:13:"right_sidebar";s:17:"post_format_video";s:0:"";s:21:"post_format_link_href";s:0:"";s:22:"post_format_link_title";s:0:"";s:22:"post_format_quote_text";s:0:"";s:24:"post_format_quote_author";s:0:"";s:17:"post_format_audio";s:0:"";}'
hestia_layout_select:
  - default
views:
  - "1"
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/02/Zhan_Wei_Tu.jpg
categories:
  - 日常分享
tags:
  - 主题
  - 字体
---
本站主题一直用的国外主题，英文字体可以选择好多种，唯一缺陷就是中文字符显示特别丑，为了文章的可读性今晚我就把主题的font-family换成中文字体。

在 Web 上应用字体是一项基本技术，同时也是一门艺术。对于英文字体来说可选择的范围实在是太广泛了，合理的使用它们将会为你的网站增色不少。

而真正的挑战在于中文字体，由于中文字体组成的特殊性导致其体积过于庞大，除了操作系统内置的字体之外，我们很难在网站上应用其他的字体。在可选性很差的前提之下，如何正确的使用中文字体呢？

本文灵感主要参考地址为 <a href="https://ruby-china.org/topics/14005" target="_blank" rel="noopener">https://ruby-china.org/topics/14005</a>

本站推荐的两个font-family 字体排序显示效果都是比较不错的。

<pre class="pure-highlightjs"><code class="cs">解决icon图标显示失效问题
 *:not([class*="icon"]):not(i) { 
}</code></pre>

<pre class="pure-highlightjs"><code class="cs">1.
font-family: -apple-system,BlinkMacSystemFont,"Lucida Grande","Helvetica Neue",Helvetica,Arial,
"PingFang SC","Hiragino Sans GB","Microsoft YaHei","WenQuanYi Zen Hei","WenQuanYi Micro Hei",
"Noto Sans CJK SC","Source Han Sans CN",SimSun,sans-serif!important;</code></pre>

<pre class="pure-highlightjs"><code class="cs">2.
font-family: Segoe UI, "Lucida Grande","Helvetica Neue",Helvetica,Arial,"PingFang SC",
"Hiragino Sans GB","Microsoft YaHei","WenQuanYi Zen Hei","WenQuanYi Micro Hei","Noto Sans CJK SC",
"Source Han Sans CN"!important;</code></pre>

设置前后对比效果：

<figure style="width: 1690px" class="wp-caption alignnone"><img src="//wx3.sinaimg.cn/large/73ed89cbgy1fo3rd0bcpzj21ay0r8x3i.jpg" alt="" width="1690" height="980" /><figcaption class="wp-caption-text">设置前</figcaption></figure>

<figure style="width: 1690px" class="wp-caption alignnone"><img class="size-full" src="//wx1.sinaimg.cn/large/73ed89cbgy1fo3rcymratj21ay0r84qp.jpg" width="1690" height="980" /><figcaption class="wp-caption-text">设置后</figcaption></figure>

未设置前字体是灰色的，阅读体验略差。因为是mac平台，显示效果一般，但是换到国产浏览器中的兼容模式灰色字体效果就惨不忍睹啦～明显可见换成中文font-family后阅读体验以及排版效果更加舒适。