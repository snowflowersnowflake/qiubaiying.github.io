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

<tbody><tr><td>os.listdir()</td><td>列出当前目录下的所有文件和文件夹（包括被隐藏的）</td></tr><tr><td>os.system()</td><td>运行shell命令；可将 指令 以 字符串 / 字符串拼接 的形式喂进去</td></tr><tr><td>os.sep()</td><td>更改操作系统中的路径分隔符</td></tr><tr><td>os.getcwd()</td><td>获取当前路径(中间会自动添上一个路径分隔符)</td></tr><tr><td>os.walk</td><td>循环遍历目录，返回tuple表，表中每一个tuple包含该层文件、文件夹及该层父节点</td></tr><tr><td>os.path.isfile()</td><td>是否是文件</td></tr><tr><td>os.path.isdir()</td><td>是否是文件夹</td></tr><tr><td>os.path.exists()</td><td>路径是否存在</td></tr><tr><td>os.path.abspath()</td><td>如果输入路径是相对路径，则转换为绝对路径</td></tr><tr><td>os.path.dirname()</td><td>获取指定目录的父目录路径</td></tr><tr><td>os.path.pardir</td><td>获取当前目录的父目录路径</td></tr><tr><td>os.pardir()</td><td>获取当前目录的父目录路径</td></tr><tr><td>os.path.split()</td><td>将目录和文件名分割开，组成二元组返回</td></tr><tr><td>os.remove()</td><td>删除指定文件</td></tr><tr><td>os.rmdir()</td><td>删除空文件夹</td></tr><tr><td>os.mkdir()</td><td>新建文件夹</td></tr><tr><td>os.makedirs( , exist_ok=True)</td><td>创建递归的目录树(exist_ok是py3.2才加入的参数)</td></tr><tr><td>os.chdir()</td><td>改变当前目录到指定目录中</td></tr><tr><td>os.rename(path1 ,path2)</td><td>重命名文件</td></tr><tr><td>os.chmod(path ,mode)</td><td>改变文件权限模式</td></tr><tr><td>os.access(path ,mode)</td><td>检验文件权限模式</td></tr><tr><td>os.sep</td><td>输出操作系统特定的路径分隔符。win下为"\",macx下为"/"</td></tr><tr><td>os.linesep</td><td>输出当前平台使用的行终止符</td></tr><tr><td>os.pathsep</td><td>输出用于分割文件路径的字符串</td></tr><tr><td><a href="http://os.name" rel="nofollow" data-token="cd3a173c3dbf84d87c7f667acaaaf522">os.name</a></td><td>输出字符串指示当前使用平台。win-&gt;‘nt’; mac-&gt;‘posix’</td></tr><tr><td>os.environ</td><td>获取系统环境变量</td></tr></tbody>
