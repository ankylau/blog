---
id: 1593
title: MAC终端(Shell)SSH连接远程服务器
date: 2018-05-20T22:58:41+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1593
permalink: /mac-terminal-ssh-connection-to-remote-server/
hestia_layout_select:
  - default
views:
  - "1"
bigger_cover:
  - https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2018/05/bigger-5b1548a135ac2.png
bigger_cover_share:
  - 'https://service.weibo.com/share/share.php?url=https%3A%2F%2Fanky.cc%2Fmac%25e7%25bb%2588%25e7%25ab%25afshellssh%25e8%25bf%259e%25e6%258e%25a5%25e8%25bf%259c%25e7%25a8%258b%25e6%259c%258d%25e5%258a%25a1%25e5%2599%25a8%2F&type=button&language=zh_cn&searchPic=true&pic=https%3A%2F%2Fanky.oss-cn-qingdao.aliyuncs.com%2Fwp-content%2Fuploads%2F2018%2F05%2Fbigger-5b1548a135ac2.png&title=【MAC终端(Shell)SSH连接远程服务器】以前SSH链接使用的默认端口(ssh root@119.00.00.00)直接链接就可以，自从修改了SSH端口...'
post_extend:
  - 'a:12:{s:10:"push_slide";b:1;s:14:"push_slide_img";s:0:"";s:20:"push_slide_below_img";s:0:"";s:16:"seo_custom_title";s:0:"";s:19:"seo_custom_keywords";s:0:"";s:15:"seo_custom_desc";s:0:"";s:11:"post_layout";s:3:"one";s:8:"head_img";s:0:"";s:12:"post_gallery";s:0:"";s:14:"post_video_url";s:0:"";s:16:"push_slide_below";b:0;s:19:"post_layout_gallery";b:0;}'
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/05/2018022121202532.jpg
categories:
  - 日常分享
---
以前SSH链接使用的默认端口(ssh root@119.00.00.00)直接链接就可以，自从修改了SSH端口后链接超时怎么办？只要加上你修改的端口号就可以链接上了～

ssh -p 端口号 服务器用户名@ip （例如ssh -p 22 username@119.00.00.00 ）回车，到这会让你输入yes或者no来确认是否连接，输入yes回车即可，然后输入在服务器上的用户密码回车.