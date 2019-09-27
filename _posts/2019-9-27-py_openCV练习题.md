---
layout:     post
title:      py_openCV练习题
subtitle:   #图片轮廓框选
date:       2019-9-27
author:     y00
header-img: img/asuna.jpg
catalog: true
tags:
    - python
    - openCV
    - 练习题
---



<iframe
  frameborder="no"
  border="0"
  marginwidth="0"
  marginheight="0"
  width="330"
  height="86"
  src="//music.163.com/outchain/player?type=2&id=133998&auto=0&height=66"
></iframe>



# 引言
## openCV是什么

OpenCV的全称是：Open Source Computer Vision Library。OpenCV是一个基于（开源）发行的跨平台计算机视觉库，可以运行在Linux、Windows和Mac OS操作系统上

它轻量级而且高效——由一系列 C 函数和少量 C++ 类构成，同时提供了Python、Ruby、MATLAB等语言的接口，实现了图像处理和计算机视觉方面的很多通用算法

## 参考链接
[官网网站](https://opencv.org/)
[中文网站](http://wiki.opencv.org.cn/index.php/%E9%A6%96%E9%A1%B5)
[opencv-python教程库](https://github.com/ex2tron/OpenCV-Python-Tutorial)

#  题目

帮朋友做一道题目要用到python-openCV库，花了一晚上上手，题目就是用所给的图片，框选出其中的轮廓并且标注

# 解决思路

* 找出n个角点
* 找寻中获得所有角点中最大最小的坐标
* 画出矩形

对于颜色的提取标注，时间关系没有做。

# 源码

[这个链接](https://github.com/snowflowersnowflake/ATestByopenCV)
