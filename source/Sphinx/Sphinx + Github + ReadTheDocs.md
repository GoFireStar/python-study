# Sphinx + Github + ReadTheDocs

10个优秀的程序员里，有9个人都有写博客的习惯。这是非常好的习惯，值得每个程序员，投入时间和精力去坚持做下去。

写博客的平台有很多，CSDN，博客园，51CTO，还有人会使用Hexo+GitHub，WordPress，比较会折腾的人还会自己使用Java，Python搭建，我就干过这样的事，不过每年还要支付域名和服务器，比较麻烦而且浪费钱。

以上博客我都有注册使用过，不过最终还是放弃。博客文章，比较零散，无法形成一个系统性的知识体系，不便索引。

为了使自己的文章能有一个比较完整的体系。经过一番探索之后，能满足我的基本要求的有如下两种：

*   GitHub Wiki，适合做知识整理，但排版一般，不方便查看。
*   GitBook，样式不好看，访问速度慢。

由于以上两种都有各自的不足的地方，所以我最后选择了一个完美的解决方案：Markdown+Pandoc+Sphinx+GitHub+ReadtheDocs  
来管理我的文章。

*   Markdown：书写文档
*   Pandoc：格式转化
*   Sphinx：生成网页
*   GitHub：托管项目
*   ReadtheDocs：发布网页

1\. 成品展示
--------

以我的博客(`python.iswbm.com`)为例，先给大家展示一下。

这是首页。显示了你所有的文章索引。  
![](http://image.iswbm.com/20190511160523.png)

这是我的导航栏。是不是结构很清晰，很方便索引。  
![](http://image.iswbm.com/20190511161056.png)

点击文章后，还可以很方便查看标题，跳转。  
![](http://image.iswbm.com/20190511161130.png)

体验下搜索功能，速度很快。

![](http://image.iswbm.com/20190511161147.png)

看完这些你是不是也很想拥有这样一个博客呢？

只要你认真往下看，30分钟搭建这样一个博客不在话下。

2\. 安装Sphinx
------------

安装之前，请确认下Python版本。我这里使用的是Python 2.7.14，其他版本请自行尝试噢，Python3.6好像有些坑，你需要踩一下。

安装Python工具包

```
$ pip install sphinx sphinx-autobuild sphinx_rtd_theme -i https://pypi.douban.com/simple/

```

初始化

```
# 先创建一个工程目录:F:\mkdocs
cd F:\mkdocs sphinx-quickstart

```

执行这个命令sphinx-quickstart的时候，会让你输入配置。除了这几个个性化配置，其他的都可以按照默认的来。

```
> Project name: MING's BLOG
> Author name(s): MING
> Project release []: 1.0
> Project language [en]: zh_CN

```

完了后，就可以看见创建的工程文件。

```
F:\mkdocs
(mkdocs) λ ls -l
total 5
-rw-r--r-- 1 wangbm 1049089 610 Jun 23 16:57 Makefile
drwxr-xr-x 1 wangbm 1049089   0 Jun 23 16:57 build/
-rw-r--r-- 1 wangbm 1049089 817 Jun 23 16:57 make.bat
drwxr-xr-x 1 wangbm 1049089   0 Jun 23 16:57 source/

F:\mkdocs
(mkdocs) λ tree
卷 文档 的文件夹 PATH 列表
卷序列号为 0002-B4B9
F:.
├─build
└─source
    ├─_static
    └─_templates

```

解释下这些文件/夹：

*   build：文件夹，当你执行make html的时候，生成的html静态文件都存放在这里。
*   source：文件夹：你的文档源文件全部应全部放在source根目录下。
*   Makefile：编译文件。完全不用管。
*   make.bat：bat脚本。你也不用管。

3\. 配置及扩展
---------

Sphinx 的配置文件是 source\\conifg.py

由于修改的内容比较多而杂，为了使这个搭建过程，更加顺畅。

小明已经给你精心准备了一份配置文件。你只要关注我的公众号「`Python编程时光`」，后台直接回复 「Sphinx」即可获取。

关于配置文件，我做了哪些事：

*   配置主题
*   支持LaTeX
*   支持中文检索

以上配置文件，需要搭配扩展模块才能使用。扩展模块同样我也给你准备好了，在你回复「Sphinx」后，获取压缩包后，里面有个 exts 文件夹。你只要将这个文件夹原封不动的放置在与source的同级目录下即可。

由于扩展模块会用到一些第三方依赖包，需要你去包装它。requirements.txt 同样我也给你准备好了，在压缩包里有。

你只要执行这个命令，即可安装。

```
pip install -r requirements.txt -i https://pypi.douban.com/simple/

```

4\. 撰写文章
--------

万事俱备，接下来要写文档了。

在source目录下，新增文件 how\_to\_be\_a\_rich_man.rst（至于什么是rst格式呢，请自行搜索引擎噢）

文件内容如下

```
第一章 如何成为有钱人
======================

1.1 财富继承法
---------------------

有个有钱的老爸。


1.2 财富共享法
---------------------

有个有钱的老婆。

```

写好文档后，千万记得要把这个文档写进，目录排版里面。

排版配置文件是 source\\index.rst，千万要注意中间的空行不可忽略。

```
.. toctree::
   :maxdepth: 2
   :caption: Contents:

   how_to_be_a_rich_man

```

然后删除这几行吧，没啥用。

```
Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

```

然后执行make html 生成html静态文件。

```
F:\mkdocs
(mkdocs) λ make html
Running Sphinx v1.7.4
loading translations [zh_CN]... done
loading pickled environment... done
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 2 source files that are out of date
updating environment: [extensions changed] 2 added, 0 changed, 0 removed
reading sources... [100%] index
looking for now-outdated files... none found
pickling environment... done
checking consistency... done
preparing documents... done
writing output... [100%] index
generating indices... genindex
writing additional pages... search
copying static files... done
copying extra files... done
dumping search index in English (code: en) ... done
dumping object inventory... done
build succeeded.

The HTML pages are in build\html.

```

执行完了后，你可以发现原先的build，不再是空文件夹了。

我们点进去 build\\html\ 目录，使用浏览器打开index.html文件。  
![](http://image.iswbm.com/20190511161212.png)

真棒，已经完成了一半了。点击 我们刚写的 暴富指南。  
![](http://image.iswbm.com/20190511161240.png)

5\. 托管项目
--------

看到网页的那一刻是不是相当激动。

不过别激动，这只是本地的，我们需要将其发布在线上。

这里我将工程文件，托管在GitHub上，然后由Read the Docs发布。

在托管之前呢，我们需要准备工作。在mkdocs根目录下，添加文件.gitignore（聪明的你，肯定知道这是什么），内容如下

```
build/
.idea/
*.pyc

```

接下来，在你的GitHub上新建一个仓库。然后把mkdocs这个目录下的所有文件都提交上去。步骤很简单，这里就不细讲了。

6\. 发布上线
--------

托管完成后，我们要发布它，让别人也可以使用公网访问。

你需要先去 Read the Docs 注册下帐号。

关联一下GitHub  
![](http://image.iswbm.com/20190511161255.png)

![](http://image.iswbm.com/20190511161311.png)

导入代码库。填好与你对应的信息。  
![](http://image.iswbm.com/20190511161334.png)

![](http://image.iswbm.com/20190511161414.png)

构建网页后。右下方，你可以看见你的在线地址。

![](http://image.iswbm.com/20190511161426.png)

这里要提醒一下的是，Sphinx的文档格式，默认是 rst 格式，如果你习惯了使用Markdown来写文章，可以使用 Pandoc 这个神器转换一下。

这里给出格式转换命令。

```
pandoc -V mainfont="SimSun" -f markdown -t rst hello.md -o hello.rst

```

或者你也可以在 Sphinx 上添加支持 Markdown 渲染的扩展模块。这需要你自己去折腾了。

到这里，属于你的个人博客就搭建好了，快去试一下吧。

附录：参考文档
-------

*   [Sphinx配置MarkDown解析](http://www.sphinx-doc.org/en/master/usage/markdown.html)
*   [Sphinx使用手册(部分汉化)](http://www.pythondoc.com/sphinx/contents.html)
*   [搭建参考文章](https://www.xncoding.com/2017/01/22/fullstack/readthedoc.html)
*   [Sphinx conf.py 配置详解](https://www.sphinx-doc.org/zh_CN/master/usage/configuration.html)