# Read the Docs+GitHub 文档托管教程 - 知乎

目的：打算系统地整理一份计算机体系结构知识点的**总结**文档，供自己学习，且文档公开。使用markdown编写文档，GitHub托管文档，Read the Docs生成在线文档。在使用Read the Docs+GitHub进行文档托管时经常构建失败，故想写一篇教程记录正确（顺畅x）的文档托管方法。

如有错误或需补充的内容，请不吝赐教:）

1\. Read the Docs快速入门
---------------------

Read the Docs快速教程请阅读下面这篇文章的前4节，此处不再赘述，直接进入正题。

2\. Read the Docs+GitHub
------------------------

以下内容基本来自官方教程[Read the Docs tutorial](https://docs.readthedocs.io/en/stable/tutorial/)。

### 2.1 新建repository

在GitHub中使用下面的template创建repository。

![](https://pic3.zhimg.com/v2-e6a91a5a4c61f31e3e8d325c0d1fc88e_b.jpg)

创建repository

README.rst->README.md，并把其修改成自己想要的内容。

![](https://pic1.zhimg.com/v2-03b66bf103fcb0bcc278d8214d76350c_b.jpg)

完成项目初步创建工作

### 2.2 导入项目到Read the Docs并进行设置

注册[Read the Docs](https://readthedocs.org/)账号，并在「设置」->「已连接的服务」中绑定GitHub账号。

在「我的项目」中点击「Import a Project」，绑定GitHub账号后会显示自己所拥有的的所有repository，选择指定的repository，点击「➕」导入GitHub项目。

![](https://pic1.zhimg.com/v2-8460186a2ae5ba8c9312076bcbf28fe0_b.jpg)

点击「下一步」

一般情况下能够成功构建，点击「阅读文档」跳转到链接[https://computer-architecture-notebook.readthedocs.io/en/latest/](https://computer-architecture-notebook.readthedocs.io/en/latest/)，可以看到示例文档。

![](https://pic1.zhimg.com/v2-4a3dc9a23d45a8647a7728cc09b2c268_b.jpg)

构建成功

![](https://pic4.zhimg.com/v2-3c93b4d0f967d47168e85483e259cbc7_b.jpg)

示例文档

点击「管理」->「设置」进行简单设置，并点击「Save」保存设置。

![](https://pic3.zhimg.com/v2-5ac495f128bbb8166af989333ce0886a_b.jpg)

基础设置

点击「高级设置」，进行如下设置，并点击「Save」保存设置。

![](https://pic4.zhimg.com/v2-5f1ea2acb1823754eed21ca11277ba8f_b.jpg)

![](https://pic2.zhimg.com/v2-02c470f0c13253e1e5b5107cab512915_b.jpg)

高级设置

点击「域」可以[自定义域](https://docs.readthedocs.io/en/stable/custom_domains.html)。（个人网站还没有完全搭建好，这里的内容后面会更新QAQ）

![](https://pic1.zhimg.com/v2-1ae97874b0b54d7ead2f26170f4c171c_b.jpg)

域设置

点击「Email Notifications」新建电子邮件通知，点击「添加」保存设置。

![](https://pic1.zhimg.com/v2-334f16cdb30f1f680390ffaa2c090944_b.jpg)

新增电子邮件

点击「Traffic Analytics」可以查看文档流量分析。

![](https://pic2.zhimg.com/v2-24a81c296f6a19418f99ba89ff47f8c9_b.jpg)

流量分析

点击「Search Analytics」可以查看文档检索情况。

在示例文档左上角搜索栏处搜索关键词”hello“，Search Analytics处显示的效果如下。

![](https://pic2.zhimg.com/v2-5eea966f9f6469578e87f6d360aaaf99_b.jpg)

搜索关键词

![](https://pic1.zhimg.com/v2-46db9598117b52bff8f300d1904c4c24_b.jpg)

检索统计情况

3\. 构建个人文档
----------

### 3.1 版本管理

在GitHub项目中创建1.0.0版本分支，当完成一定量的新内容后，再将1.0.x分支合并到main分支。

![](https://pic2.zhimg.com/v2-0d21801257bf477133f8ddc33fd2d3bd_b.jpg)

创建1.0.0branch

从main分支创建完新分支后，可以在Read the Docs中看到如下内容：

![](https://pic3.zhimg.com/v2-7f890779edd649b397db59741a22c21a_b.jpg)

点击「阅读文档」，在网页左侧最下方可以选择想要查看的版本。

![](https://pic2.zhimg.com/v2-64c4491756a2c6017563eda7296a23a5_b.jpg)

选择不同的版本

还可以激活该1.0.0版本，当1.0.0分支中的内容更新时，可以在在线文档中实时看到1.0.0版本中的最新内容。

![](https://pic4.zhimg.com/v2-35359630dc3d11ac810d87f76a99e0fb_b.jpg)

点击Activate

![](https://pic1.zhimg.com/v2-20fcb7eb2b97cb337aab322417b0fbb0_b.jpg)

激活1.0.0版本

当前激活版本新增了1.0.0。

![](https://pic1.zhimg.com/v2-70d124bc056b68eb3eb9a064c6f9f5d0_b.jpg)

点击「阅读文档」，在网页左侧最下方可以看到可供阅读的1.0.0版本。

![](https://pic4.zhimg.com/v2-188603c279f0602846b975dd6cf05643_b.jpg)

### 3.2 修改template

将GitHub中的项目clone到本地。

```powershell
git clone https://github.com/zhangkanqi/Computer_Architecture_Notebook.git
cd Computer_Architecture_Notebook
git checkout 1.0.0
```

修改docs/source/conf.py为：

```python
# Configuration file for the Sphinx documentation builder.

# -- Project information

project = 'Computer_Architecture_Notebook'
copyright = '2022, kkqq'
author = 'kkqq'

release = '1.0'
version = '1.0.0'

# -- General configuration

extensions = [
    'sphinx.ext.duration',
    'sphinx.ext.doctest',
    'sphinx.ext.autodoc',
    'sphinx.ext.autosummary',
    'sphinx.ext.intersphinx',
    'recommonmark',
    'sphinx_markdown_tables',
]

intersphinx_mapping = {
    'python': ('https://docs.python.org/3/', None),
    'sphinx': ('https://www.sphinx-doc.org/en/master/', None),
}
intersphinx_disabled_domains = ['std']

templates_path = ['_templates']

# -- Options for HTML output
html_theme = 'sphinx_rtd_theme'

# -- Options for EPUB output
epub_show_urls = 'footnote'

# -- Options for PDF output
latex_engine = 'xelatex'
latex_use_xindy = False
latex_elements = {
    'preamble': '\\usepackage[UTF8]{ctex}\n',
}
```

其中extensions中的recommonmark用于支持markdown，sphinx\_markdown\_tables用于支持markdown中的表格。此外，该conf.py文件也可以在上述内容的基础上增加以下内容来支持markdown中的表格。（不加也行）

```text
source_parsers = {
    '.md': 'recommonmark.parser.CommonMarkParser',
}

source_suffix = ['.rst', '.md']
```

删除lumache.py、pyproject.toml，docs/source/{api.rst、index.rst、usage.rst}文件。

在docs文件中新增make.bat和Makefile文件。

make.bat文件：

```bat
@ECHO OFF

pushd %~dp0

REM Command file for Sphinx documentation

if "%SPHINXBUILD%" == "" (
	set SPHINXBUILD=sphinx-build
)
set SOURCEDIR=source
set BUILDDIR=build

if "%1" == "" goto help

%SPHINXBUILD% >NUL 2>NUL
if errorlevel 9009 (
	echo.
	echo.The 'sphinx-build' command was not found. Make sure you have Sphinx
	echo.installed, then set the SPHINXBUILD environment variable to point
	echo.to the full path of the 'sphinx-build' executable. Alternatively you
	echo.may add the Sphinx directory to PATH.
	echo.
	echo.If you don't have Sphinx installed, grab it from
	echo.http://sphinx-doc.org/
	exit /b 1
)

%SPHINXBUILD% -M %1 %SOURCEDIR% %BUILDDIR% %SPHINXOPTS% %O%
goto end

:help
%SPHINXBUILD% -M help %SOURCEDIR% %BUILDDIR% %SPHINXOPTS% %O%

:end
popd
```

Makefile文件：

```make
# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

```

在**根目录**执行以下命令，会在根目录下生成requirements.txt文件。

```powershell
python3 -m pip freeze > requirements.txt
```

最后按照本文中第一节中的教程，创建需要的rst和md文件，我的项目内容如下：

![](https://pic1.zhimg.com/v2-ba403de8295d519e921a68e3caa47df4_b.jpg)

项目结构（1.0.0分支）

完成以上内容后，将新内容更新到GitHub中：

```powershell
git add .
git commit -m "修改template"
git push origin 1.0.0
```

Read the Docs会自动构建文档，文档构建通过后，点击「阅读文档」可查看最新的文档详情。

![](https://pic4.zhimg.com/v2-7ba8bd21ed17ee5a675435e2a1682b23_b.jpg)

![](https://pic3.zhimg.com/v2-3d7baf4b88f0bfaddada0a96127c88e6_b.jpg)

可以看到，在1.0.0版本的文档中，有些markdown语法Read the Docs（或者说sphnix）并不支持。

完成满意的内容后，再把1.0.0分支merge到main分支。

**_⚠️Tips!!!：_**

*   当在浏览器中无法查看到markdown表格时，**清空浏览器缓存!!!**再加载网页。
*   可以先在本地查看生成的最新文档的信息，满意后再push到GitHub上。具体方法如下：

先在本地安装本文第一步的教程中所需的环境，然后执行以下命令，最后用浏览器打开docs/build/html/index.html。使用这种方法记得在.gitignore文件中加上一句docs/build。

### 3.3 导出文档

由于已经在conf.py中添加了以下配置信息，故只需要在在线文档网页的左下角直接导出pdf即可。

```python3
# -- Options for PDF output
latex_engine = 'xelatex'
latex_use_xindy = False
latex_elements = {
    'preamble': '\\usepackage[UTF8]{ctex}\n',
}
```

![](https://pic2.zhimg.com/v2-3980ab25ff1de94edc6c43c90faf001d_b.jpg)

导出pdf格式的文档

4\. 项目链接
--------

项目链接在这里~欢迎star☆ (*｀∀´*)ノ

完结撒花✿✿ヽ(°▽°)ノ✿✿，接下来就可以顺畅地使用Read the Docs+GitHub编写文档啦~

参考资料
----

1.  [Read the Docs 从懵逼到入门](https://luhuadong.blog.csdn.net/article/details/109006380?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_antiscan&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_antiscan&utm_relevant_index=1)
2.  [Read the Docs tutorial](https://docs.readthedocs.io/en/stable/tutorial/)
3.  [read the docs - HolaWorld - 博客园](https://www.cnblogs.com/holaworld/p/15673814.html)
4.  [TOMOCAT：ReadTheDocs搭建第一本电子书](https://zhuanlan.zhihu.com/p/388640347)
5.  [Python sphinx-markdown-tables包_程序模块 - PyPI - Python中文网](https://www.cnpython.com/pypi/sphinx-markdown-tables)