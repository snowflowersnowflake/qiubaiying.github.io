---
layout:     post
title:      python_os库用法总结
subtitle:   #
date:       2017-02-15
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

```
#os.sep

import os
a=os.sep
print(a) 

output:打印字符 \
```
