---
id: 1135
title: 使用ESP-8266模块做一个便携式wifi杀手
date: 2017-11-24T23:58:50+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1135
permalink: /esp8266-deauther-wifi-jammer/
neverland_post_options:
  - 'a:8:{s:5:"title";s:4:"show";s:16:"sidebar_position";s:13:"right_sidebar";s:17:"post_format_video";s:0:"";s:21:"post_format_link_href";s:0:"";s:22:"post_format_link_title";s:0:"";s:22:"post_format_quote_text";s:0:"";s:24:"post_format_quote_author";s:0:"";s:17:"post_format_audio";s:0:"";}'
views:
  - "1"
post_extend:
  - 'a:15:{s:14:"push_slide_img";s:0:"";s:20:"push_slide_below_img";s:0:"";s:16:"seo_custom_title";s:0:"";s:19:"seo_custom_keywords";s:0:"";s:15:"seo_custom_desc";s:0:"";s:11:"post_layout";s:4:"four";s:8:"head_img";s:0:"";s:12:"post_gallery";s:0:"";s:14:"post_video_url";s:0:"";s:15:"bigger_head_img";s:0:"";s:12:"bigger_title";s:0:"";s:11:"bigger_desc";s:0:"";s:10:"push_slide";b:0;s:16:"push_slide_below";b:0;s:19:"post_layout_gallery";b:0;}'
suxing_ding:
  - "9"
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/wifijammer.jpg
categories:
  - 日常分享
tags:
  - 安全协议
---
前段时间在bilibili看到了用esp8266开发板做了一个wifi Jammer（wifi杀手），当时觉得好牛逼好新奇于是就自己也搞了一个板子。（如果嫌麻烦可以淘宝购买刷好固件的成品）

成品非常迷你小巧，使用充电宝供电即可。只不过散热非常差，长时间运行担忧啊。

> ###### 原理是通过发送取消认证报文让客户端以为路由器需要让自己断开连接从而断开wifi，伪造路由器向客户端发送取消认证报文，使客户端主动断开wifi连接。并且支持自定义热点伪造（批量生成假Wi-Fi信号）。

也就是说你可以无需知道对方wifi密码不需要连接对方的wifi就可以攻击干扰对方wifi，并且可以生成48个wifi热点干扰!支持自定义wifi名称，真是表白神器啊！也是整蛊必备！

**<span style="color: #ff0000;">本文教程仅供学习和安全测试实验，请勿非法使用</span>**

#### 这是基于Github上Spacehuhn的开源项目 esp8266_deauther

固件项目地址：<a href="https://github.com/spacehuhn/esp8266_deauther" target="_blank" rel="noopener">https://github.com/spacehuhn/esp8266_deauther</a>

固件汉化版地址: <a href="https://pan.baidu.com/s/1bo7VHb5" target="_blank" rel="noopener">https://pan.baidu.com/s/1bo7VHb5</a> 密码: 5ktp

<p class="p1">
  <span class="s1">本文中板子使用的是相对便宜的node mcu（约15元-25元左右包邮）由于esp8266只支持802.11bgn,所以以下实验只针对2.4GWiFi测试。不支持5GWi-Fi！</span>
</p>

<figure id="attachment_1136" aria-describedby="caption-attachment-1136" style="width: 800px" class="wp-caption alignnone"><img class="wp-image-1136 size-full" src="https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641.png" alt="" width="800" height="800" srcset="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641.png 800w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-300x300.png 300w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-100x100.png 100w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-600x600.png 600w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-150x150.png 150w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-768x768.png 768w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/TB2motVXIIa61Bjy1zeXXX7wXXa_44390641-200x200.png 200w" sizes="(max-width: 800px) 100vw, 800px" /><figcaption id="caption-attachment-1136" class="wp-caption-text">ESP-8266 WIFI模块开发版</figcaption></figure>

### 简单说一下部署方法和注意事项。

esp8266_deauther是使用arduino开发的因此也是开源的我们需要准备arduion IDE、esp8266开发包、nodemcu一块。

下面开始

1.安装arduino。 可以在这里下载最新版<a href="https://www.arduino.cc/en/Main/Software" target="_blank" rel="noopener">https://www.arduino.cc/en/Main/Software</a>

2.安装后打开arduino，菜单依次打开 文件\首选项,找到附加开发板管理器网址选项，填入<span style="color: #0000ff;">http://arduino.esp8266.com/stable/package_esp8266com_index.json</span>

<img class="alignnone size-full wp-image-1137" src="https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2017/11/14930322064891.png" alt="" width="707" height="675" srcset="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930322064891.png 707w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930322064891-300x286.png 300w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930322064891-600x573.png 600w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930322064891-150x143.png 150w" sizes="(max-width: 707px) 100vw, 707px" /> 

3.打开菜单 工具\开发板\开发板管理器，找到esp8266模块，选择版本2.0.0（必须2.0.0）安装

<img class="alignnone size-full wp-image-1138" src="https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2017/11/14930335205356.png" alt="" width="800" height="450" srcset="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930335205356.png 800w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930335205356-300x169.png 300w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930335205356-600x338.png 600w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930335205356-150x84.png 150w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930335205356-768x432.png 768w" sizes="(max-width: 800px) 100vw, 800px" /> 

安装的时候由于防火墙的原因很难下载，有时需要翻墙，你懂得。

4.再次打开菜单 文件\首选项，点击这里进入sdk的编辑目录

<img class="alignnone size-full wp-image-1139" src="https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2017/11/14930337826590.png" alt="" width="707" height="675" srcset="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930337826590.png 707w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930337826590-300x286.png 300w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930337826590-600x573.png 600w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930337826590-150x143.png 150w" sizes="(max-width: 707px) 100vw, 707px" /> 

5.找到packages\esp8266\hardware\esp8266\2.0.0\tools\sdk\include目录将下载的esp8266\_deauther源码里的sdk\_fix下的user_interface.h复制到该目录，替换原来的文件。

6.找到packages\esp8266\hardware\esp8266\2.0.0\libraries\ESP8266WiFi\src目录将下载的esp8266\_deauther源码里的sdk\_fix下的ESP8266WiFi.cpp和ESP8266WiFi.h复制到该目录，替换原来的文件。

7.用arduino IDE打开下载的esp8266\_deauther源码包里的esp8266\_deauther\esp8266_deauther.ino

8.菜单操作 “工具\开发板\NodeMcu 1.0 (ESP-12E Module)”,这里根据自己购买的esp8266开发板选择对应的板子。注意开发板的端口要选择正确，否则不能下载编译好的固件，然后点工具栏里的上传按钮，编译和上传固件。

9.如果如前面所示你已经将固件烧写进开发板里，你可以使用手机或者pc搜索wifi热点，你会发现一个名为“pwned”的热点，此热点默认密码“deauther”，连接后，在浏览器打开<span style="color: #0000ff;">192.168.4.1</span>即可开始使用。

<img class="alignnone size-full wp-image-1140" src="https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2017/11/14930348454758.jpg" alt="" width="720" height="1280" srcset="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758.jpg 720w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758-300x533.jpg 300w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758-600x1067.jpg 600w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758-84x150.jpg 84w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758-169x300.jpg 169w, https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2017/11/14930348454758-576x1024.jpg 576w" sizes="(max-width: 720px) 100vw, 720px" /> 

这玩意有啥用？嗯，到女神家门口让女神上不了网，然后打电话向你求助。现在很多酒店的点菜机都是WiFi的，不能点菜，酒店被ddos？这种WiFi deauth攻击由于WiFi自身协议漏洞导致无法预防，攻击只要是信号覆盖范围内的，几乎是100%有效的。希望新的无线通讯协议出来时能考虑此类问题解决吧。

> ###### <span style="color: #339966;">spacehuhn：</span>esp8266有一个通用的毛病，如果你在刷入了一次固件，wfi密码和热点名称会保留，下一次修改密码和热点名称后刷入固件你会发现，密码和热点名称无法改变。那么怎么办呢？用Winhex制作一个大小为4MB，内容全为FF的文件，然后用nodemcu-flasher刷入，会刷入失败，但是密码已经被清除，然后你就可以刷入修改密码和热点名称后的固件。
> 
> ###### <cite>spacehuhn</cite>

via:http://www.freebuf.com/geek/133161.html

#### 供电方式：

支持的电压范围为：3V-12V，自带稳压模块。电流3A以下。常见的供电方式有：1节18650电池，移动电源供电、电脑USB接口供电、安卓手机充电器供电、支持OTG功能的手机可以直接手机供电。

<cite><em>我整理网上的参考教程</em></cite>

_http://tieba.baidu.com/p/5120958849?see_lz=1_

_http://tieba.baidu.com/p/5084353799?see_lz=1_