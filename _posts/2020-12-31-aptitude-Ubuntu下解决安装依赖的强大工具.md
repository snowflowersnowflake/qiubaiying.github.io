---
layout:     post
title:      aptitude-Ubuntu下解决安装依赖的强大工具
subtitle:   #
date:       2020-12-31
author:     y00
header-img: img/1.jpg
catalog: true
tags:
    - Linux
---

起因是最近在新公司里安装ros的时候，发现安装依赖版本冲突，一点头绪都没有。
```
下列软件包有未满足的依赖关系：
python-roslaunch : 依赖: python-roslib 但是它将不会被安装
E: 无法修正错误，因为您要求某些软件包保持现状，就是它们破坏了软件包间的依赖关系。
5.继续：sudo apt-get install python-roslib
sudo apt-get install catkin
sudo apt-get install python-catkin-pkg
sudo apt-get install catkin
测试仍然不行
```
随后经过了一系列的搜集资料，找到了一个很方便的工具可以解决这样的问题。
```
sudo apt-get install aptitude
sudo aptitude install python-roslaunch
```
然后选择一个降级的方案接受，就可以一建解决这样的依赖冲突了。还是以ros的安装为例：
```
下列软件包存在未满足的依赖关系：
 python-catkin-pkg-modules : 冲突: catkin 但是 0.6.16-4 将被安装。
 python-catkin-pkg : 冲突: catkin 但是 0.6.16-4 将被安装。
下列动作将解决这些依赖关系：

     保持 下列软件包于其当前版本：
1)     catkin [未安装的]          
2)     python-roslaunch [未安装的]
3)     python-roslib [未安装的]   



是否接受该解决方案？[Y/n/q/?] n
下列动作将解决这些依赖关系：

      删除 下列软件包：                                                  
1)      python-catkin-pkg-modules                                        
2)      python-rosdep-modules                                            
3)      python-rosdistro-modules                                         
4)      python-rospkg-modules                                            

      安装 下列软件包：                                                  
5)      python-funcsigs [0.4-2 (xenial)]                                 
6)      python-mock [1.3.0-2.1ubuntu1 (xenial)]                          
7)      python-pbr [1.8.0-4ubuntu1 (xenial)]                             

      降级 下列软件包：                                                  
8)      python-catkin-pkg [0.4.23-100 (now, xenial) -> 0.2.10-2 (xenial)]
9)      python-rosdep [0.20.0-1 (now, xenial) -> 0.11.4-2 (xenial)]      
10)     python-rosdistro [0.8.3-100 (now, xenial) -> 0.4.4-1 (xenial)]   
11)     python-rospkg [1.2.9-100 (now, xenial) -> 1.0.38-1 (xenial)]     


是否接受该解决方案？[Y/n/q/?] Y
```

