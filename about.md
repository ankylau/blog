---
layout: page
title: About
permalink: /about/
published: true
---

<div class="page" markdown="1">

{% capture page_subtitle %}
<img
    class="me"
    alt="{{ author.name }}"
    src="{{ site.author.photo | relative_url }}"
    srcset="{{ site.author.photo2x | relative_url }} 2x"
/>
{% endcapture %}

{% include page/title.html title=page.title subtitle=page_subtitle %}

## Anky Lau 

啥都想玩啥都玩不好的主... 对感兴趣的事物有间断性热情。
宅但是又向往着外面的世界，97年的却有颗三岁的心。
牙套boy, 不善于表达，其他的想到再说。

<p style="text-align: center;"><span id="runtime_span">
</span>
<script type="text/javascript">function show_runtime(){window.setTimeout("show_runtime()",1000);X=new 
Date("12/02/2019 08:48:00");
Y=new Date();T=(Y.getTime()-X.getTime());M=24*60*60*1000;
a=T/M;A=Math.floor(a);b=(a-A)*24;B=Math.floor(b);c=(b-B)*60;C=Math.floor((b-B)*60);D=Math.floor((c-C)*60);
runtime_span.innerHTML="戴牙套的第: "+A+"天"+B+"小时"+C+"分"+D+"秒"}show_runtime();</script></p>

## GET IN TOUCH

<p style="text-align: center;"><audio src="//lhttp.qingting.fm/live/1007/64k.mp3" preload="preload" controls="controls"></audio></p>

</div>
