---
title: Diffusion Policy for Robot Manipulation
description: Diffusion Policy 机器人操控
slug: DP
date: 2025-10-29 12:00:00+0800
image:
categories:
    - Research
tags:
    - manipulation
weight:       # You can add weight to some posts to override the default sorting (date descending)
---

## 大模型多模态信息融合的方法

### CNN-based（发源自视觉推理/视觉问答）

1. 问题
    
    实现文本条件下的图像输出
    
2. 方法
    
    FiLM (Feature-wise Linear Modulation)
    
    条件编码器（文本、图像等）经过FIlM，产生仿射变换的参数。仿射变换的参数在每个resnet的block中都可以加入，相当于做了一次 attention，可以理解为拿文本信息去attention视觉的内容，而且是从每级的feature上面都是如此。
    

### Transformer-based

1. 常规方法
    
    Transformer架构：文本作为值多头注意到图像上
    
2. CLIP
    
    图像条件下的文本（类别）输出
    

## 创新点/立足点/贡献

1. 闭环动作生成？？预测与执行的关系+优化推理速度，何为闭环？？
2. 状态动作条件概率分布 | 联合分布——条件分布
3. transformer架构的diffusion policy | cnn diffusion —— transformer diffusion

## 前序工作

1. CNN-based diffusion model for planning
    
    Planning with Diffusion for Flexible Behavior Synthesis
    
    [Michael Janner](https://jannerm.github.io/)*, [Yilun Du](https://yilundu.github.io/)*, [Joshua Tenenbaum](https://cocosci.mit.edu/josh), and [Sergey Levine](https://people.eecs.berkeley.edu/~svlevine/)
    
2. Behavior transformer w/o diffusion
    
    Behavior Transformers: Cloning k modes with one stone
    
    [Nur Muhammad (Mahi) Shafiullah,](https://mahis.life/) [Zichen Jeff Cui,](https://jeffcui.com/) [Ariuntaya Altanzaya,](https://artys.page/) [Lerrel Pinto](https://lerrelpinto.com/)
    
3. 引申学习
    
    [Attention Is All You Need 2017](https://arxiv.org/pdf/1706.03762)
    
    [ViT 2020](https://arxiv.org/pdf/2010.11929)
    
    Diffusion Model [[1-2015]](https://arxiv.org/pdf/1503.03585) [[2-2019]](https://arxiv.org/pdf/1907.05600) [[3-DDPM-2020]](https://arxiv.org/pdf/2006.11239)
    
    [Diffusion Transformer 2023](https://arxiv.org/pdf/2212.09748)
    
    [RDT 2024](https://arxiv.org/pdf/2410.07864)
    
    [ACT 2023](https://arxiv.org/pdf/2304.13705)
    
    Flow Matching [[1-2024]](https://arxiv.org/pdf/2409.01083v1) [[2-pi0-2024]](https://arxiv.org/pdf/2410.24164)
