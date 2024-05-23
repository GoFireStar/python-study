# Sphinx常用命令

### 初始化项目：
```shell
sphinx-quickstart
```
这个命令用于初始化一个新的 Sphinx 项目，并通过交互式方式引导你设置项目的基本配置。

### 构建文档(1次)：
```shell
make html
```
这个命令用于构建 Sphinx 项目的 HTML 格式文档。构建后的文档将会保存在 _build/html 目录下。

### 自动构建文档：
```shell
sphinx-autobuild source build/html
```
这个命令用于自动构建 Sphinx 项目的文档。构建后的文档将会保存在 build/html 目录下。
默认情况下，当源文件发生更改时，构建过程会自动重新运行。
默认使用127.0.0.1:8000访问

### 清理构建：
```shell
make clean
```
这个命令用于清理构建过程生成的临时文件和目录。

