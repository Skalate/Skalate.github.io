# 欢迎来到李峦的个人博客

本博客是基于MkDocs开发完成的。完整的文档（英文）可以区参考[mkdocs.org](https://www.mkdocs.org)。这里我简要写一下MkDocs的基本用法，主要是方便自己修改。

## MkDocs Guide

### Install

主要介绍在Windows平台进行安装，需要 Python 和 Python package manager pip 来安装 MkDocs . 可以通过以下命令查看是否安装了上述依赖:

```
$ python --version
Python 3.9.6
$ pip --version
pip 21.2.2
$ pip install mkdocs

$ mkdocs -h
```

### Start

```
$ mkdocs new my-project
$ cd my-project 
$ mkdocs serve
$ mkdocs build
```

http://127.0.0.1:8000/


mkdocs.yml文件内是这样的形式

```
site_name: My_Name
nav:
- 主页: 'index.md' 
- 关于: 'about.md'
theme: readthedocs
```


### Git



