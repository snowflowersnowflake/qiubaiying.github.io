---
layout:     post
title:      r语言初学入门
subtitle:   #1
date:       2019-05-27
author:     y00
header-img: img/1.jpg
catalog: true
tags:
    - R
    - 统计
    - 语言学习
---

# r-

向量
向量是 R 语言中最基本的数据类型，在 R 中没有单独的标量

赋值  <-
```markdown
killer<-c(1,1,2,2)
```
x <- 1:10
y <- x+rnorm(10, 0, 1)
fit <- lm(y ~ x)
summary(fit)
 
