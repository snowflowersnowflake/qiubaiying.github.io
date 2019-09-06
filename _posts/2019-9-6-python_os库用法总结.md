---
layout:     post
title:      python_os库用法总结
subtitle:   #
date:       2019-09-06
author:     BY y00
header-img: img/asuna.jpg
catalog: true
tags:
    - python 
    - os
---

# python_os常用方法搬运

|    api    |annotation|
| ------ | ------ | 
|os.listdir()   |列出当前目录下的所有文件和文件夹（包括被隐藏的）|
|os.system()	|运行shell命令；可将 指令 以 字符串 / 字符串拼接 的形式喂进去|
|os.sep()	|更改操作系统中的路径分隔符|
|os.getcwd()	|获取当前路径(中间会自动添上一个路径分隔符)|
|os.walk	|循环遍历目录，返回tuple表，表中每一个tuple包含该层文件、文件夹及该层父节点|
|os.path.isfile()	|是否是文件|
|os.path.isdir()	|是否是文件夹|
|os.path.exists()	|路径是否存在|
|os.path.abspath()	|如果输入路径是相对路径，则转换为绝对路径|
|os.path.dirname()	|获取指定目录的父目录路径|
|os.path.pardir	|获取当前目录的父目录路径|
|os.pardir()	|获取当前目录的父目录路径|
|os.path.split()	|将目录和文件名分割开，组成二元组返回|
|os.remove()	|删除指定文件|
|os.rmdir()	|删除空文件夹|
|os.mkdir()	|新建文件夹|
|os.makedirs( , exist_ok=True)	|创建递归的目录树(exist_ok是py3.2才加入的参数)|
|os.chdir()	|改变当前目录到指定目录中|
|os.rename(path1 ,path2)	|重命名文件|
|os.chmod(path ,mode)	|改变文件权限模式|
|os.access(path ,mode)	|检验文件权限模式|
|os.sep	|输出操作系统特定的路径分隔符。win下为"\",macx下为"/"|
|os.linesep	|输出当前平台使用的行终止符|
|os.pathsep	|输出用于分割文件路径的字符串|
|os.name	|输出字符串指示当前使用平台。win->‘nt’; mac->‘posix’|
|os.environ	|获取系统环境变量|

# example

### os.listdir()

```

import os, sys

# 打开文件
path = "/var/www/html/"
dirs = os.listdir( path )

# 输出所有文件和文件夹
for file in dirs:
   print file

```
output:
```
#得到打印的目录结果
test.htm
stamp
faq.htm
_vti_txt
robots.txt
itemlisting
resumelisting
writing_effective_resume.htm
advertisebusiness.htm
papers
resume
``````

### os.system()
```
import os
import subprocess
#运行shell命令“打开记事本”
os.system('notepad')

```
output:
```
#系统打开记事本
```

### os.sep()

```

import os
a=os.sep
print(a) 

```
output:
```
\
```
### os.getcwd()	
```
import os
print(os.getcwd())
```
output:
```
C:\Users\user\AppData\Local\Programs\Python\Python37
```

### os.walk
os.walk() 方法是一个简单易用的文件、目录遍历器，可以帮助我们高效的处理文件、目录方面的事情。

os.walk(top[, topdown=True[, onerror=None[, followlinks=False]]])

* top -- 是你所要遍历的目录的地址, 返回的是一个三元组(root,dirs,files)。
* root 所指的是当前正在遍历的这个文件夹的本身的地址
* dirs 是一个 list ，内容是该文件夹中所有的目录的名字(不包括子目录)
* files 同样是 list , 内容是该文件夹中所有的文件(不包括子目录)
* topdown --可选，为 True，则优先遍历 top 目录，否则优先遍历 top 的子目录(默认为开启)。如果 topdown 参数为 True，walk 会遍历top文件夹，与top 文件夹中每一个子目录。
* onerror -- 可选，需要一个 callable 对象，当 walk 需要异常时，会调用。
* followlinks -- 可选，如果为 True，则会遍历目录下的快捷方式(linux 下是软连接 symbolic link )实际所指的目录(默认关闭)，如果为 False，则优先遍历 top 的子目录。
```
import os
for root, dirs, files in os.walk(".", topdown=False):
    for name in files:
        print(os.path.join(root, name))
    for name in dirs:
        print(os.path.join(root, name))

```
output:
```
./.bash_logout
./amrood.tar.gz
./.emacs
./httpd.conf
./www.tar.gz
./mysql.tar.gz
./test.py
./.bashrc
./.bash_history
./.bash_profile
./tmp
./tmp/test.py
```
### os.walk
