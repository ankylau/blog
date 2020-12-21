---
id: 526
title: 本站已全面开启HTTPS化
date: 2016-12-09T19:08:31+08:00
author: Anky
layout: post
guid: http://anky.cc/?p=526
permalink: /the-site-enabled-https/
neverland_post_options:
  - 'a:8:{s:5:"title";s:4:"show";s:16:"sidebar_position";s:13:"right_sidebar";s:17:"post_format_video";s:0:"";s:21:"post_format_link_href";s:0:"";s:22:"post_format_link_title";s:0:"";s:22:"post_format_quote_text";s:0:"";s:24:"post_format_quote_author";s:0:"";s:17:"post_format_audio";s:0:"";}'
post_views:
  - "4"
views:
  - "1"
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2016/12/https.jpg
categories:
  - 生活方式
tags:
  - Chrome
  - 安全协议
  - 浏览器
---
<!--more-->

> <span style="color: #800000;">2017-03-04因为服务器问题取消了https服务，2017-10-28重新使用https服务</span>

前几天查看邮件，突然看到七牛发的“ 2017 年 1 月 1 日苹果 iOS 应用推行 ATS 安全标准，将强制使用 HTTPS 安全连接；谷歌 Chrome 将把所有的 HTTP 网站标记为「不安全」。全站 HTTPS 化是大势所趋。”  看完后吓得我赶紧到百度上查了查SSL证书，发现都好贵好贵的，我这个穷斯可用不起收费的，百度查了查找到好多free的ssl证书，看完后纠结到底用那个好。 然后打开阿里云的官网后发现阿里云也有免费的 Symantec 证书提供申请~ 我立即给当前域名申请了一个，我也要给本站HTTPS化咯！！

### **<span style="color: #ff0000;">#</span>**流程

**一、注册申请HTTPS证书**

网上有很多教程和免费的证书，我是申请的阿里云CA证书，传送门 <span style="color: #ff0000;"><a style="color: #ff0000;" href="https://www.aliyun.com/product/cas?spm=5176.8142029.388261.121.8TO7q4" target="_blank" rel="noopener">证书服务</a> </span>。购买时选择 “<span class="bk-items-item"><span class="bk-items-item-value ">免费型DV SSL”的证书可以给一个域名免费使用一年时间。</span></span>

购买完之后 验证域名-等待签发(十分钟左右就签发)，签发完后你会获得XXX.pme 和 XXX.key 等多个文件。(KEY为私钥，crt为公钥，pfx为包含了公钥和私钥的二进制格式的证书，用于SSL证书发布网站的登录允许。）

**二、在Nginx服务器环境中配置证书**

首先把公钥和私钥放置到服务器，位置是自己定义的，打个比方存放在根目录的www文件夹下。进入wdcp的nginx的配置文件/www/wdlinux/nginx/conf/vhost/anky.cc.conf(此处讲解下，nginx的配置文件应该是在/nginx/conf/nginx.conf，修改也是修改nginx.conf。但是wdcp是多域名的虚拟主机管理系统，在内容分发上要管理多个站点，所以nginx.conf文件最下面引用了一句话，意思是不同的域名需要在vhost文件夹下使用单独的配置文件。)

配置完全后重启nginx,指令如下：

service httpd restart 重启Apache的命令

service nginxd restart 重启Nginx的命令

<span style="color: #ff0000;">重启完全nginx后直接访问https地址还是不行，要进iptables开启443端口，因为https默认使用的就是443端口。</span>

&nbsp;

**三、修改站点地址**

方法一、在Wordpress后台-设置-常规中更换Wordpress地址和站点地址为https协议的，这样一来，由WordPress自动创建的链接就都变成https了.

方法二、进入到Wordpress安装目录下，打开wp-config.php进行添加修改

//Set HTTPS as home address define(&#8216;WP_HOME&#8217;,&#8217;https://anky.cc&#8217;);

//Set HTTPS as siteurl define(&#8216;WP_SITEURL&#8217;,&#8217;https://anky.cc&#8217;);

<span style="color: #ff0000;">用方法二后方法一就无法修改站点地址了</span>

&nbsp;

**四、关于chrome浏览器的小绿锁**

如果引用第三方http文件会显示 “与此网站建立的不是私密链接” 想要全站HTTPS的话需要把网站http链接改为https把引用第三方的http文件全部取消掉就可以了。

这里要感谢一下 <span style="color: #ff0000;"><a style="color: #ff0000;" href="https://www.mengdodo.com/" target="_blank" rel="noopener">@萌嘟嘟</a> </span>大哥的帮助，本人零基础更换HTTPS，耗时一下午！

&nbsp;

### <span style="color: #ff0000;"><strong>#</strong></span>整体过程参考于以下文章

https://www.mengdodo.com/?p=509

http://www.wdlinux.cn/bbs/thread-39845-1-5.html

https://www.gubo.org/wordpress-enable-https/