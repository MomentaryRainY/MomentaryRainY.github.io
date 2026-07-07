+++
date = "2024-05-02 08:20:35"
draft = false
title = "NeRF 实时真实感渲染方法综述"
description = "围绕 NeRF-based real-time photorealistic rendering 的文献综述，比较 volume-based、surface-based 与 hybrid methods 的技术路线和应用潜力"
[taxonomies]
tags = ["论文", "NeRF", "神经渲染", "实时渲染", "图形学"]
[extra]
image = '/images/nerf.png'
+++

2024.4

### 项目描述

这是我围绕 NeRF-based real-time photorealistic rendering 完成的文献综述论文。论文关注 NeRF 及其变体如何从离线神经场景表示，逐步走向实时真实感渲染，并分析其在游戏、AR/VR、移动端和实时图形应用中的潜力。

文章将相关方法整理为 volume-based、surface-based 与 hybrid methods 三类技术路线，并从渲染速度、存储占用、输出分辨率、数据集、硬件需求和场景适用性等维度进行比较。

### 主要内容

- 梳理 NeRF 的基本思想：使用 5D 输入表示空间位置与观察方向，并预测颜色和密度
- 总结 NeRF-like 方法在静态场景重建、隐式表示和新视角合成中的优势
- 比较 volume-based 方法在质量、训练成本和实时渲染速度上的取舍
- 比较 surface-based 方法在几何表达、渲染效率和实时应用中的优势
- 分析 hybrid methods 如何结合体渲染质量与表面渲染效率
- 从 FPS、模型大小、分辨率、数据集和硬件平台等指标比较不同方法
- 讨论 NeRF 在游戏、AR/VR、移动端渲染中的应用限制，包括动态场景、艺术可控性和硬件适配问题


### 成果

论文已发表：[Paper](https://doi.org/10.62051/26c21r61)

### 成长 & 反思 & 未来

这是我第一篇发表的论文，让我第一次完整经历了选题、文献阅读、技术分类、对比分析和学术写作流程。相比只阅读单篇论文，综述写作要求我从更高层次理解一个方向的发展脉络，并建立清晰的评价维度。

这篇论文也让我意识到，阅读图形学论文不能只关注单个方法的效果图或指标，而需要持续追问：它和前人方法相比解决了什么问题，代价是什么，适合什么场景，是否真的具备实时应用价值。

不足之处在于，当时对神经渲染和实时图形管线的理解还不够深入，部分分析更偏文献整理，缺少代码复现和实验验证。后续我希望继续阅读并复现 Instant-NGP、3D Gaussian Splatting 等方向的代表性方法，把神经表示和实时渲染的理解落到实际工程中。
