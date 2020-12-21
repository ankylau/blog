---
id: 1226
title: wordpress搬家导入数据库失败
date: 2018-02-11T23:41:28+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1226
permalink: /wordpress-import-mysql-sql-error/
neverland_post_options:
  - 'a:8:{s:5:"title";s:4:"show";s:16:"sidebar_position";s:13:"right_sidebar";s:17:"post_format_video";s:0:"";s:21:"post_format_link_href";s:0:"";s:22:"post_format_link_title";s:0:"";s:22:"post_format_quote_text";s:0:"";s:24:"post_format_quote_author";s:0:"";s:17:"post_format_audio";s:0:"";}'
hestia_layout_select:
  - default
views:
  - "1"
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/02/Zhan_Wei_Tu.jpg
categories:
  - 日常分享
---
今天给一个wp网站搬家从万网免费主机中搬到阿里云服务器里，环境全都搭建好了一切顺利，却在导入数据库的环节中出现以下错误

<pre class="pure-highlightjs"><code class="null">错误
SQL 查询：


T FOREIGN_KEY_CHECKS = 0;
MySQL 返回： 文档

#1064 - You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'T FOREIGN_KEY_CHECKS = 0' at line 1 </code></pre>

查了半天百度，最后问题是mysql版本不一样，导致不兼容。

解决办法：

使用wp数据库备份插件备份数据库，而不要在phpmyadmin直接导出。

插件下载地址 WP-DB-Backup <a href="https://wordpress.org/plugins/wp-db-backup/" target="_blank" rel="noopener"> https://wordpress.org/plugins/wp-db-backup/</a>