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
<br>

 api | annotation 
 - | - |
os.listdir()   |列出当前目录下的所有文件和文件夹（包括被隐藏的）
os.system()	|运行shell命令；可将 指令 以 字符串 / 字符串拼接 的形式喂进去
os.sep()	|更改操作系统中的路径分隔符|
os.getcwd()	|获取当前路径(中间会自动添上一个路径分隔符)
os.walk	|循环遍历目录，返回tuple表，表中每一个tuple包含该层文件、文件夹及该层父节点
os.path.isfile()	|是否是文件
os.path.isdir()	|是否是文件夹
os.path.exists()	|路径是否存在
os.path.abspath()	|如果输入路径是相对路径，则转换为绝对路径
os.path.dirname()	|获取指定目录的父目录路径
os.path.pardir	|获取当前目录的父目录路径
os.pardir()	|获取当前目录的父目录路径
os.path.split()	|将目录和文件名分割开，组成二元组返回
os.remove()	|删除指定文件
os.rmdir()	|删除空文件夹
os.mkdir()	|新建文件夹
os.makedirs( , exist_ok=True)	|创建递归的目录树(exist_ok是py3.2才加入的参数)
os.chdir()	|改变当前目录到指定目录中
os.rename(path1 ,path2)	|重命名文件
os.chmod(path ,mode)	|改变文件权限模式
os.access(path ,mode)	|检验文件权限模式
os.sep	|输出操作系统特定的路径分隔符。win下为"\",macx下为"/"
os.linesep	|输出当前平台使用的行终止符
os.pathsep	|输出用于分割文件路径的字符串
os.name	|输出字符串指示当前使用平台。win->‘nt’; mac->‘posix’
os.environ	|获取系统环境变量

| 左对齐标题 | 右对齐标题 | 居中对齐标题 |
| :------| ------: | :------: |
| 短文本 | 中等文本 | 稍微长一点的文本 |
| 稍微长一点的文本 | 短文本 | 中等文本 |

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

### os.walk()
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
### path.isfile()
```
print(os.path.isfile('test.py'))
```
output:
```
true
```

### path.isdir()
```
import os
print(os.path.isdir('../Python37'))

```
output:
```
ture
```

### os.path.exists()	
**判断文件是否存在，相当于之前两个命令的作用总和**

### os.path.abspath()

```
import os
print(os.path.abspath('../Python37'))

```

output:
```
C:\Users\user\AppData\Local\Programs\Python\Python37
```

### os.path.split()

```
import os
print(os.path.split('../Python37'))

```
output:
```
('..', 'Python37')
```

### os.makedir

补充：makedirs可以创建多级目录

```
import os,sys
os.makedirs('d:\\books\\book')
```
output:
**D盘出现book\\book 二级目录**

### os.chdir() 

```
import os, sys

path = "/tmp"

# 查看当前工作目录
retval = os.getcwd()
print "当前工作目录为 %s" % retval

# 修改当前工作目录
os.chdir( path )

# 查看修改后的工作目录
retval = os.getcwd()

print "目录修改成功 %s" % retval
```

### os.chmod(path ,mode)
权限模式汇总：
```
stat.S_IXOTH: 其他用户有执行权0o001
stat.S_IWOTH: 其他用户有写权限0o002
stat.S_IROTH: 其他用户有读权限0o004
stat.S_IRWXO: 其他用户有全部权限(权限掩码)0o007
stat.S_IXGRP: 组用户有执行权限0o010
stat.S_IWGRP: 组用户有写权限0o020
stat.S_IRGRP: 组用户有读权限0o040
stat.S_IRWXG: 组用户有全部权限(权限掩码)0o070
stat.S_IXUSR: 拥有者具有执行权限0o100
stat.S_IWUSR: 拥有者具有写权限0o200
stat.S_IRUSR: 拥有者具有读权限0o400
stat.S_IRWXU: 拥有者有全部权限(权限掩码)0o700
stat.S_ISVTX: 目录里文件目录只有拥有者才可删除更改0o1000
stat.S_ISGID: 执行此文件其进程有效组为文件所在组0o2000
stat.S_ISUID: 执行此文件其进程有效用户为文件所有者0o4000
stat.S_IREAD: windows下设为只读
stat.S_IWRITE: windows下取消只读
```
```
import os, sys, stat

# 假定 /tmp/foo.txt 文件存在，设置文件可以通过用户组执行

os.chmod("/tmp/foo.txt", stat.S_IXGRP)

# 设置文件可以被其他用户写入
os.chmod("/tmp/foo.txt", stat.S_IWOTH)

print "修改成功!!"
```
<br>
