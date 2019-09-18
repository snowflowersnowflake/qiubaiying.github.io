---
layout:     post
title:      logistic进行分类实例
subtitle:   #学校作业w
date:       2019-9-18
author:     y00
header-img: img/=-=.jpg
catalog: true
tags:
    - python
    - logistic
    - 机器学习
    - 练习题
    - numpy
---

# 引言
* 所采用的数据集：[Banknote Dataset(钞票数据集)](https://blog.csdn.net/fengbingchun/article/details/78624358)
* 环境：python3、numpy库
* 核心算法： [logistic对数几率回归算法](https://zhuanlan.zhihu.com/p/36670444) 

* [为什么使用随机梯度上升法优化求函数极大值?](https://www.cnblogs.com/chenyang920/p/7426187.html)

* 我的源码与结果：[logisticFordata_banknote_authentication-master](https://github.com/snowflowersnowflake/logisticFordata_banknote_authentication-master)


# 摘要

1. 手动将data分为两部分，用作训练和测试（没统计行数，手动随机的），可以参见*我的源码与结果*中的目录结构。
2. 编写load函数用于加载文件、算法函数用以训练、测试函数，在主函数中加载后调用算法优化权值（训练），然后用该函数加载测试集输出结果。
3. 采用随机梯度上升优化，优化前优化后输出两次分类结果比较优化效果。
4. 源文件中有详细注释，算法部分参考外链。在我的机器上运行结果复制在res.txt中
