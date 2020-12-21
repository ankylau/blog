---
id: 1591
title: MAC安装Hexo到Github Pages
date: 2018-05-18T12:26:14+08:00
author: Anky
layout: post
guid: https://anky.cc/?p=1591
permalink: /in-mac-install-hexo/
hestia_layout_select:
  - default
views:
  - "1"
bigger_cover:
  - https://anky.oss-cn-qingdao.aliyuncs.com/wp-content/uploads/2018/05/bigger-5b15378f4fd44.png
bigger_cover_share:
  - 'https://service.weibo.com/share/share.php?url=https%3A%2F%2Fanky.cc%2Fin-mac-install-hexo%2F&type=button&language=zh_cn&searchPic=true&pic=https%3A%2F%2Fanky.oss-cn-qingdao.aliyuncs.com%2Fwp-content%2Fuploads%2F2018%2F05%2Fbigger-5b15378f4fd44.png&title=【MAC安装Hexo到Github Pages】今天突发奇想，想在Github Pages上部署一个Hexo博客，于是记录一下，这篇文章是基于 Mac 的，所...'
post_extend:
  - 'a:12:{s:14:"push_slide_img";s:0:"";s:20:"push_slide_below_img";s:0:"";s:16:"seo_custom_title";s:0:"";s:19:"seo_custom_keywords";s:0:"";s:15:"seo_custom_desc";s:0:"";s:11:"post_layout";s:3:"one";s:8:"head_img";s:0:"";s:12:"post_gallery";s:0:"";s:14:"post_video_url";s:0:"";s:10:"push_slide";b:0;s:16:"push_slide_below";b:0;s:19:"post_layout_gallery";b:0;}'
image: https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/05/hexo-1.jpg
categories:
  - 日常分享
---
今天突发奇想，想在Github Pages上部署一个Hexo博客，于是记录一下，这篇文章是基于 Mac 的，所以接下来所有准备工作都是指在 Mac 系统环境下的。

#### **环境安装**

  1. <a href="https://nodejs.org/zh-cn/" target="_blank" rel="noopener noreferrer">Node.js</a>
  2. <a href="https://git-scm.com/" target="_blank" rel="noopener noreferrer">Git (安装过X-Code就不用安装了)</a>
  3. <a href="https://hexo.io" target="_blank" rel="noopener noreferrer">hexo</a>

#### **安装教程**

一、安装Git安装Git请参考教程：<a href="https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git" target="_blank" rel="noopener noreferrer">https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git</a>

二、安装Node.js安装Node.js请访问官网下载并安装：<a href="https://nodejs.org/zh-cn/" target="_blank" rel="noopener noreferrer">https://nodejs.org/zh-cn/</a>

上面两个环境在官网下载安装即可。

三、安装hexo-cli

**打开OS系统终端**

  * 取得mac root权限

由于安装hexo-cli会写入mac系统文件，所以需要root权限安装。 首先，打开mac终端，输入命令：

<pre class="pure-highlightjs"><code class="null">sudo -i</code></pre>

_根据提示输入mac密码回车即可（输入密码不会显示在终端上，只管输入完后回车即可）_

**接下来在取得root权限的终端中输入命令**

<pre class="pure-highlightjs"><code class="null">npm install -g hexo-cli
</code></pre>

_千万不要忘记加上 -g 这个选项，这是用于全局安装的_

当出现如下所示界面即表示安装成功：

<img class="alignnone size-full wp-image-2046" src="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/05/1585303498-73ed89cbly1frferbi6g9j21kw0sxapd.jpg?x-oss-process=image/resize,m_fill,w_4096,h_2082#" alt="" width="2048" height="1041" /> 

**初始化hexo**

新开一个终端窗口，以普通用户身份运行（为什么要新开窗口以普通用户身份运行？因为如果以root身份初始化hexo会将“hexo”目录下的所有文件权限设置为只有System用户才有读写权限，极不方便后续的修改操作）执行如下命令初始化hexo

首先，你需要创建一个新的路径，并且进入这个路径（以blog为例）：

<pre class="pure-highlightjs"><code class="null">$ mkdir blog
$ cd blog/
</code></pre>

在这个新的路径就可以开始 Hexo 的初始化：

<pre class="pure-highlightjs"><code class="null">$ hexo init
</code></pre>

如果出现任何关于 “dependence” 的提示，这是在提示你安装依赖包，那么执行：

<pre class="pure-highlightjs"><code class="null">npm install
</code></pre>

如果，没有，则不执行。

当出现如下所示界面时即表示初始化完成：

<img class="alignnone size-full wp-image-2047" src="https://anky.oss-cn-shanghai.aliyuncs.com/wp-content/uploads/2018/05/1585303531-73ed89cbly1frffy6zsd6j21g80u814c.jpg?x-oss-process=image/resize,m_fill,w_3760,h_2176#" alt="" width="1880" height="1088" /> 

#### **运行 Hexo**

<pre class="pure-highlightjs"><code class="null">$ hexo server
或
$ hexo s</code></pre>

运行这条命令可以启动 Hexo 的本地服务器功能，不要关闭终端，启动浏览器，在地址框内输入：localhost:4000 来访问你的本地 Hexo 博客 你会看到里面目前只有一篇 Hello World 文章，这是 Hexo 初始化的，里面包含了基础的操作

<pre class="pure-highlightjs"><code class="null">提示如下运行成功：
MacBook-Pro:blog ankylau$ hexo server
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.</code></pre>

浏览完你的初始化博客后，回到命令行，按下 Ctrl+C 停止运行。

至此，你已经在本地运行起来了hexo!

**配置**

可能刚刚你有注意到，网站的标题有问题，作者也不是自己 这时候我们就需要配置：用自己习惯的编辑器打开 Hexo 文件根目录下的 _config.yml 按照以下格式编辑

<pre class="pure-highlightjs"><code class="null"># Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/
# Site 站点配置
title: Hexo-demo #网站标题
subtitle: hexo is simple and easy to study #网站副标题
description: this is hexo-demo #网栈描述
author: pomy #你的名字
language: zh-CN #网站使用的语言
timezone: Asia/Shanghai #网站时区
# URL #可以不用配置
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://yoursite.com #网址，搜索时会在搜索引擎中显示
root: / #网站根目录
permalink: :year/:month/:day/:title/ #永久链接格式
permalink_defaults: #永久链接中各部分的默认值
# Directory 目录配置
source_dir: source #资源文件夹，这个文件夹用来存放内容
public_dir: public #公共文件夹，这个文件夹用于存放生成的站点文件
tag_dir: tags #标签文件夹
archive_dir: archives #归档文件夹
category_dir: categories #分类文件夹
code_dir: downloads/code #Include code 文件夹
i18n_dir: :lang #国际化文件夹
skip_render: #跳过指定文件的渲染，您可使用 glob 来配置路径
# Writing 写作配置
new_post_name: :title.md # 新文章的文件名称
default_layout: post #默认布局
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0 #把文件名称转换为 (1) 小写或 (2) 大写
render_drafts: false #显示草稿
post_asset_folder: false #是否启动资源文件夹
relative_link: false #把链接改为与根目录的相对位址
future: true
highlight: #代码块的设置
enable: true
line_number: true
auto_detect: true
tab_replace:
# Category & Tag 分类 & 标签
default_category: uncategorized #默认分类
category_map: #分类别名
tag_map: #标签别名
# Date / Time format 时间和日期
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss
# Pagination 分页
## Set per_page to 0 to disable pagination
per_page: 10 #每页显示的文章量 (0 = 关闭分页功能)
pagination_dir: page #分页目录
# Extensions 扩展
## Plugins: http://hexo.io/plugins/ 插件
## Themes: http://hexo.io/themes/ 主题
theme: landscape #当前主题名称
# Deployment #部署到github
## Docs: http://hexo.io/docs/deployment.html
deploy:
type:</code></pre>

**创建一篇新的文章**

刚刚配置完了，也就把信息矫正过来了，接下来就要写一篇自己的博文（以“你好”为例)： **（注意：本地服务器要使新的配置生效，需要重启 hexo s 服务）**

<pre class="pure-highlightjs"><code class="null">$ hexo new 你好
</code></pre>

这样就创建了一篇叫做 你好 的文章，在 ./source/_posts 当中

**编辑新文章**

打开新文章 你好.md，会发现里面已经存在5行代码，那都是初始化数据，而我们要写的内容，在第5行代码 **“—”** 之后。

Hexo 的文章全部采用 Markdown 语法编辑，简单便捷

**生成文章**

编辑完 你好.md 之后，我们就需要生成这篇博文：

<pre class="pure-highlightjs"><code class="null">$ hexo generate
</code></pre>

这样，我们的文章就在 public 目录下生成 html 了

**预览文章**

写完整个文章，当然要看一下成果，我们再执行一遍运行指令：

<pre class="pure-highlightjs"><code class="null">$ hexo server
</code></pre>

打开 **localhost:4000**，就可以看到新文章了

#### **部署到Github Pages**

创建完GitHub仓库后

**安装<a href="https://github.com/hexojs/hexo-deployer-git" target="_blank" rel="noopener noreferrer">hexo-deployer-git</a>**

命令如下：

<pre class="pure-highlightjs"><code class="null">npm install hexo-deployer-git --save</code></pre>

安装完成后，将如下配置添加到你的`_config.yml`文件中：

<pre class="pure-highlightjs"><code class="null">deploy:
 type: git
 repo: &lt;repo&gt;</code></pre>

其中`<repo>`为刚创建的Github Pages仓库的地址，格式为：`https://github.com/你的Github用户名/仓库名.git`

配置完成后，运行命令`hexo g`或`hexo generate`生成静态文件(如果觉得文件有缓存，还可以先运行`hexo clean`命令，再运行`hexo g`)：

<pre class="pure-highlightjs"><code class="null">hexo g</code></pre>

再运行`hexo d`或`hexo deploy`命令发布hexo到Github pages:

<pre class="pure-highlightjs"><code class="null">exo d</code></pre>

回车后会提示你输入Github账户名及密码，输入后回车即可。

**至此，你已成功部署到Github Pages，访问`你的Github用户名.github.io`即可访问你的hexo网站。**

> **我的HEXO博客站 https://ankylau.github.io/**

#### **绑定域名**

<li id="域名解析CNAME到你的Github用户名-github-io">
  域名解析CNAME到你的<span style="color: #ff0000;">Github用户名.github.io</span>
</li>
  1. 进入public文件夹里,新建一个CNAME文件
  2. 把域名写在CNAME里
  3. 为了防止域名解析出问题博主建议将blog下的public下的CNAME文件，复制到blog下的source文件夹里，这样更新public，不会出现CNAME文件丢失的情况
  4. 再次运行命令hexo g与hexo d发布到Github Pages，待域名解析生效后即可用你的域名访问你的hexo网站。

&nbsp;

&nbsp;

常用hexo命令

https://hexo.io/zh-cn/docs/commands.html

本文中所有参考文档

http://hujun.site/2017/08/20/hexo-install/

https://billts.site/2018/01/24/hexomac/

&nbsp;