---
id: 1916
title: 在 WordPress 指定页面加载指定 JavaScript 或 CSS 代码
date: 2019-03-16T20:40:52+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1916
permalink: /wordpress-page-javascript-css-code/
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2019/03/1552740199-Using_Custom_Fields.png
categories:
  - 日常分享
tags:
  - wordpress
  - 主题
---
在做 WordPress 的主题的时候，我一直在想：**如果我有一段特定的 JavaScript 或者 CSS 代码要出现在 WordPress 某一特定的页面，而且只会用到一次。那该把那段代码放哪去？** style.css 或者 base.js ？但是这样做成本确实有点大了。

> <span style="font-size: 12pt;"><strong>实例一</strong>：就像前段时间我一直在想要不要把 <a href="http://highslide.com/" target="_blank" rel="nofollow noopener">Highslide</a> 的 JavaScript 效果弄到博客上来，但是一般要加 <a href="http://highslide.com/" target="_blank" rel="nofollow noopener">Highslide</a> 的只有部分由加图片或者需要的页面才用到，在没用到的页面加载一个 50多KB的 JavaScript 未免成本太大了点。</span>
> 
> <span style="font-size: 12pt;"><strong>实例二</strong>：在之前的一篇文章《<a href="http://loo2k.com/blog/2011-gaokao-flash/" target="_blank" rel="nofollow noopener">2011年高考倒计时</a>》里我在页面里面放了一个 Flash，普通兼容的方法是用<embed>标签插入，但是插入的<embed>标签将会让你的页面不能通过 <a href="https://www.baidu.com/s?wd=W3C&tn=24004469_oem_dg&rsv_dl=gh_pl_sl_csd" target="_blank" rel="noopener">W3C</a> 验证。有个好办法是用<a href="http://code.google.com/p/swfobject/" target="_blank" rel="nofollow noopener">SWFObject </a>这个 JavaScript 生成能通过 W3C 验证的代码，但是问题又来了：在 WordPress 每个页面都载入<a href="http://code.google.com/p/swfobject/" target="_blank" rel="nofollow noopener">SWFObject </a>是不是太浪费了，又不是每个页面都用到这个 JavaScript 文件。</span>

其实，我们可以利用 WordPress 强大的<a href="http://codex.wordpress.org/Using_Custom_Fields" target="_blank" rel="nofollow noopener">自定义字段</a>的功能来实现**不同的文章页面载入自定义的 JavaScript 或者 CSS 文件**。

这篇文章将介绍你**如何通过使用自定义字段实现在 WordPress 上自定义页面的 JavaScript 或者 CSS 文件**，如果你能弄明白的话，自定义字段的价值就不是一个 JavaScript 跟 CSS 文件这么简单的价值了。

## <a name="t0"></a>如何添加自定义字段到主题

用你常用的代码编辑器打开你的 WordPress 主题的 header.php文件，找到<?php wp_head(); ?>这句代码，在其后面添加上：

<pre class="pure-highlightjs"><code class="php">&lt;?php if (is_single() || is_page()) {
    $head = get_post_meta($post-&gt;ID, 'head', true); 
    if (!empty($head)) { ?&gt; 
        &lt;?php echo $head; ?&gt; 
&lt;?php } } ?&gt;
</code></pre>

代码中的head是自定义字段的名称，可以自定义；

## <a name="t1"></a>在文章页面或独立页面添加自定义字段

在 WordPress 后台编辑文章的页面的编辑器下面，有一个“自定义域”的小窗口，在名称处输入head，在值处输入你要在你所添加位置输出的代码；

<img class="alignnone size-full wp-image-1919" src="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2019/03/1552740276-Add_Custom_Fields.png?x-oss-process=image/resize,m_fill,w_1054,h_324#" alt="" width="527" height="162" /> 

点击了**添加自定义域**之后，更新你的文章就可以在你主题放置代码的地方输入这些自定义域的值了;

由于只是输出“值”里面的所有内容，所以需要自己在“值”里面输入

<pre class="pure-highlightjs"><code class="javascript">&lt;script type="text/javascript"&gt;...&lt;/script&gt;</code></pre>

或者

<pre class="pure-highlightjs"><code class="css">&lt;style type="text/css"&gt;...&lt;/style&gt;</code></pre>

来输出代码。

## <a name="t2"></a>WordPress 自定义字段的一点小结

明白了上面的原理之后，你会发现：WordPress 自定义字段不仅仅能实现自定义页面的自定义 JavaScript 或 CSS，还有**很多的功能都可以通过自定义字段来实现**，类似于：给文章添加缩略图、文章小提示 etc&#8230;

至于实现什么功能，或者怎么实现，用自定义字段试试。

via:<a href="http://loo2k.com/blog/wordpress-page-javascript-css-code/" target="_blank" rel="nofollow noopener">http://loo2k.com/blog/wordpress-page-javascript-css-code/</a>