---
layout:     post
title:      Linux上glog.info的数据重定向问题
subtitle:   #
date:       2021-2-24
author:     y00
header-img: img/1.jpg
catalog: true
tags:
    - Linux
---

# 描述

*  用shell命令存储一个slam精度计算结果，但是发现command>>file进行数据重定向失败

# 原因

* 生成该信息的c++源码使用了glog，但生成的数据会缓存到标准错误流**stderr**而不是标准输出流**stdin**，这是glog.info用于返回错误信息的设计决定。因此在重定向的时候要使用shell中的stderr的输出
* 在该问题解决上用command&>file实现，&>会同时定位错误流和输出流的数据。
