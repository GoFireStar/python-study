# 用Sphinx生成文档，解决层级目录问题 

41 changes: 41 additions & 0 deletions 41 [docs/source/index.rst](#diff-4eec6cec5f6fab1548b85433ea8ca81315ae165db4b7f84019f287df9015699f "docs/source/index.rst")

 Show comments 

[View file](/klion26/futuquant/blob/540577105618113c49be1bc8f2ddd1951c1b65ff/docs/source/index.rst) Edit file Delete file

| Original file line number | Diff line number | Diff line change |
| --- | --- | --- |  
|  |  | @@ -0,0 +1,41 @@ |
|  |  | .. futuquant documentation master file, created by |
|  |  | sphinx-quickstart on Thu Aug 31 10:00:54 2017. |
|  |  | You can adapt this file completely to your liking, but it should at least |
|  |  | contain the root \`toctree\` directive. |

|  |  | ================================= |
|  |  | FutuQuant |version| Documentation |
|  |  | ================================= |
|  |  |   
 |
|  |  | This futuquant documentation. |
|  |  |   
 |
|  |  | .. toctree:: |
|  |  | :caption: 介绍 |
|  |  | :maxdepth: 2 |
|  |  | :hidden: |
|  |  |   
 |
|  |  | intro/intro |
|  |  |   
 |
|  |  | .. toctree:: |
|  |  | :caption: 安装 |
|  |  | :maxdepth: 2 |
|  |  | :hidden: |
|  |  |   
 |
|  |  | setup/setup |
|  |  | setup/Hist\_KLine\_Download_Intro |
|  |  |   
 |
|  |  | .. toctree:: |
|  |  | :caption: API |
|  |  | :maxdepth: 4 |
|  |  | :hidden: |
|  |  |   
 |
|  |  | api/Market\_API\_Python_Doc |
|  |  | api/Trade\_API\_Python_Doc |
|  |  | api/PLS\_API\_Intro |
|  |  |   
 |
|  |  | .. toctree:: |
|  |  | :caption: Q&A |
|  |  | :maxdepth: 2 |
|  |  | :hidden: |
|  |  |   
 |
|  |  | q&a/Q&A |