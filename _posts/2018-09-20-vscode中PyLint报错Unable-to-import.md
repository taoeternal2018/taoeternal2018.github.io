---
layout:     post
title:      vscode中PyLint报错Unable-to-import
subtitle:   vscode中PyLint报错Unable-to-import
date:       2018-09-04
author:     Taoeternal
header-img: img/post-bg-coffee.jpeg
catalog: true
tags:
    - vscode中PyLint报错Unable
    - 开发技巧
---
vscode中PyLint报错Unable to import解决方案
在导入其它文件夹中py文件的时候，即使在代码中添加了指定路径，由于Pylint 无法检测到该文件，会给出Unable to import 'xxx'的错误提示

需要在项目目录下添加.pylintrc文件指定要引用文件所在的目录

init-hook='base_dir="/home/bruce/Desktop/Workspace/BruceVirtualEnvs/venv3.6/lib/python3.6/site-packages"; import sys,os,re; _re=re.search(r".+\/" + base_dir, os.getcwd()); project_dir = _re.group() if _re else os.path.join(os.getcwd(), base_dir); sys.path.append(project_dir)'

init-hook='base_dir="D:\Envs\venv37\Lib\site-packages"; import sys,os,re; _re=re.search(r".+\/" + base_dir, os.getcwd()); project_dir = _re.group() if _re else os.path.join(os.getcwd(), base_dir); sys.path.append(project_dir)'
