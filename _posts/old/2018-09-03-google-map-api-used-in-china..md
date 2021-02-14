---
id: 1711
title: Google Map Api 在国内使用
date: 2018-09-03T22:35:23+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1711
permalink: /google-map-api-used-in-china/
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/09/maxresdefault.jpg
categories:
  - 日常分享
tags:
  - Google
  - 地图
---
最近装了几个国外主题都有调用的谷歌地图api服务，导致使用以下api地址的主题在国内打开的速度超级慢。

只要在主题内找到api地址的位置替换成国内地址即可。

<pre class="pure-highlightjs"><code class="null">//maps.google.com/maps/api/js?sensor=false</code></pre>

换成以下地址就可以在完美在国内使用了。

<pre class="pure-highlightjs"><code class="null">//maps.google.cn/maps/api/js?sensor=false</code></pre>

&nbsp;