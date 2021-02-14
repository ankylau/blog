---
id: 1766
title: Nginx调用wordpress主题自带404页面
date: 2018-09-08T17:48:05+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1766
permalink: /nginx-wordpress-404/
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/09/404-error-page-not-found.jpg
categories:
  - 日常分享
tags:
  - wordpress
---
使用宝塔面板过程中发现WordPress不能跳转到主题自带的404页面。查看Nignx的配置文件后找到了问题解决办法。默认安装下，出现404错误时会默认使用nignx自带的404页面。如图所示：

<img class="aligncenter" src="//photocdn.sohu.com/20151020/mp36728249_1445327200688_2.jpeg" alt="" width="495" height="174" /> 

**正确解决方案**

1.打开宝塔面板的网站配置

2.找到配置文件

将error_page 404 /404.html这个段注释掉（在前面加入＃即可）

3.保存重启nginx服务

<img class="alignnone size-thumbnail" src="https://ww2.sinaimg.cn/large/005YhI8igy1fv29y2dcd7j30zw0vwq8e" width="1292" height="1148" />