# Sphinx 教程文档

在本教程中，你将使用 Sphinx 建立一个简单的文档项目，并在浏览器中以 HTML 形式查看。该项目将包括叙述性的、手写的文档，以及自动生成的 API 文档。

该教程针对的是愿意学习如何创建和构建项目的基本原理的 Sphinx 新人。你将创建一个虚构的软件库来生成随机的食物食谱，它将作为整个过程的指南，目的是正确记录它。

为了展示 Sphinx 在代码文档方面的能力，你将使用 Python，它也支持 _自动_ 文档生成。

备注

其他几种语言在 Sphinx 中原生支持 _手动_ 代码文档，然而它们需要扩展到 _自动_ 代码文档，比如 [Breathe](https://breathe.readthedocs.io/)。

遵循说明，需要访问类似于 Linux 的命令行，并对其工作原理有基本的了解，还要有一个用于开发的工作的 Python 安装，因为你将使用 _Python 虚拟环境_ 来创建项目。

*   [入门](https://daobook.github.io/sphinx/tutorial/getting-started.html)
    *   [设置你的项目和开发环境](https://daobook.github.io/sphinx/tutorial/getting-started.html#setting-up-your-project-and-development-environment)
    *   [创建文档布局](https://daobook.github.io/sphinx/tutorial/getting-started.html#creating-the-documentation-layout)
*   [使用 Sphinx 记录你的项目的第一个步骤](https://daobook.github.io/sphinx/tutorial/first-steps.html)
    *   [构建你的 HTML 文档](https://daobook.github.io/sphinx/tutorial/first-steps.html#building-your-html-documentation)
    *   [以其他格式建立你的文件](https://daobook.github.io/sphinx/tutorial/first-steps.html#building-your-documentation-in-other-formats)
*   [更多的 Sphinx 定制](https://daobook.github.io/sphinx/tutorial/more-sphinx-customization.html)
    *   [启用内置插件](https://daobook.github.io/sphinx/tutorial/more-sphinx-customization.html#enabling-a-built-in-extension)
    *   [使用第三方 HTML 主题](https://daobook.github.io/sphinx/tutorial/more-sphinx-customization.html#using-a-third-party-html-theme)
*   [Sphinx 中的叙事文档](https://daobook.github.io/sphinx/tutorial/narrative-documentation.html)
    *   [在多个页面上构建你的文档结构](https://daobook.github.io/sphinx/tutorial/narrative-documentation.html#structuring-your-documentation-across-multiple-pages)
    *   [添加交叉引用](https://daobook.github.io/sphinx/tutorial/narrative-documentation.html#adding-cross-references)
*   [在 Sphinx 中描述代码](https://daobook.github.io/sphinx/tutorial/describing-code.html)
    *   [Python](https://daobook.github.io/sphinx/tutorial/describing-code.html#python)
        *   [记录 Python 对象](https://daobook.github.io/sphinx/tutorial/describing-code.html#documenting-python-objects)
        *   [交叉引用 Python 对象](https://daobook.github.io/sphinx/tutorial/describing-code.html#cross-referencing-python-objects)
        *   [在你的文档中包括 doctest](https://daobook.github.io/sphinx/tutorial/describing-code.html#including-doctests-in-your-documentation)
    *   [其他语言（C、C++、其他）](https://daobook.github.io/sphinx/tutorial/describing-code.html#other-languages-c-c-others)
        *   [记录和交叉引用的对象](https://daobook.github.io/sphinx/tutorial/describing-code.html#documenting-and-cross-referencing-objects)
*   [从代码中自动生成文档](https://daobook.github.io/sphinx/tutorial/automatic-doc-generation.html)
    *   [用 autodoc 复用使用签名和文档串](https://daobook.github.io/sphinx/tutorial/automatic-doc-generation.html#reusing-signatures-and-docstrings-with-autodoc)
    *   [生成全面的 API 参考资料](https://daobook.github.io/sphinx/tutorial/automatic-doc-generation.html#generating-comprehensive-api-references)
*   [附录：在线部署 Sphinx 项目](https://daobook.github.io/sphinx/tutorial/deploying.html)
    *   [对 Sphinx 友好的部署选项](https://daobook.github.io/sphinx/tutorial/deploying.html#sphinx-friendly-deployment-options)
    *   [拥护 “文档即代码” 理念](https://daobook.github.io/sphinx/tutorial/deploying.html#embracing-the-docs-as-code-philosophy)
    *   [发布你的文档源码](https://daobook.github.io/sphinx/tutorial/deploying.html#publishing-your-documentation-sources)
        *   [GitHub](https://daobook.github.io/sphinx/tutorial/deploying.html#id1)
        *   [GitLab](https://daobook.github.io/sphinx/tutorial/deploying.html#id2)
    *   [发布你的 HTML 文档](https://daobook.github.io/sphinx/tutorial/deploying.html#publishing-your-html-documentation)
        *   [Read the Docs](https://daobook.github.io/sphinx/tutorial/deploying.html#id4)
        *   [GitHub Pages](https://daobook.github.io/sphinx/tutorial/deploying.html#id5)
        *   [GitLab Pages](https://daobook.github.io/sphinx/tutorial/deploying.html#id6)
*   [今后的发展方向](https://daobook.github.io/sphinx/tutorial/end.html)