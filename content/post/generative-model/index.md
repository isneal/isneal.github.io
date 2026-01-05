---
title: Summary of Generative Models
description: 生成模型总结
slug: GM
date: 2026-01-05 12:00:00+0800
image:
categories:
    - Research
tags:
    - algorithm
math: true
weight:       # You can add weight to some posts to override the default sorting (date descending)
---

## 高斯混合模型，GMM，Gaussian Mixture Module

### 定位

高斯混合模型 (GMM) 是一种概率模型，它将数据表示为多个高斯分布的组合，每个高斯分布都有自己的均值和方差，由混合系数加权。GMM 常用于聚类和密度估计，因为它们能够捕捉复杂的多峰分布，其中数据点可能自然地围绕不同中心聚集，而不是单一均值。

### 概率论基础

1. 高斯分布

概率密度是描述连续型随机变量分布特征的函数，表示随机变量在某点附近单位区间内取值的可能性大小。定义随机变量$X$服从数学期望$\mu$、方差为${\sigma}^2$的高斯分布，记为：

$$
 X\sim N(\mu,{\sigma}^2)
$$

则其概率密度为：

$$
f(x)=\frac{1}{{\sigma}\sqrt{2\pi}}exp(-\frac{(x-\mu)^2}{2{\sigma}^2})=\frac{1}{{\sigma}\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2{\sigma}^2}}
$$

<p align="center">
  <img src="Normal_Distribution_PDF.svg" width="400">
</p>

概率密度如图所示。横轴表示变量$x$，纵轴表示概率密度函数。数学期望$\mu$决定了分布的位置，$\sigma$决定了分布的幅度。均值$\mu=0$，标准差$\sigma=1$的正态分布为标准正态分布。随机变量的取值落在某个区域内的概率为概率密度函数在这个区域上的积分。

2. 期望
3. 方差
4. 标准差
5. 协方差

### 高斯混合模型
