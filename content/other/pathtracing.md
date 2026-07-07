+++
date = "2024-09-09 05:30:35"
draft = false
title = "Games202 高质量实时渲染"
description = "跟随 GAMES202 学习实时阴影、环境光照、实时全局光照与实时降噪"
[taxonomies]
tags = ["GAMES202", "实时渲染", "降噪", "个人项目"]
[extra]
image = '/images/games202.png'
+++

### 项目描述

这是我跟随 GAMES202 高质量实时渲染课程进行的图形学练习，重点关注实时渲染中更进阶的算法问题，包括实时阴影、实时环境光照、实时全局光照、实时物理材质和实时光线追踪。

项目中主要完成了基础着色和实时降噪相关实践，用来理解高质量实时渲染中“效果质量、性能预算和时序稳定性”之间的取舍。

### 结果

![webgl](/images/games202.png)

*Blinn-Phong 着色模型练习。*

![House Sequence](/images/house-sequence.gif)

*实时降噪前的序列结果。*

![Denoised House Sequence](/images/denoised-house-sequence.gif)

*实时降噪后的序列结果。*

Github Link [<strong>games202</strong>](https://github.com/MomentaryRainY/RTDenosier)

### 成长 & 反思

这个项目让我开始理解实时渲染中更复杂的算法目标：很多效果并不是单帧算得越准越好，而是要在有限时间内获得稳定、可接受且可调的结果。

实践中最大的体会是，复刻图形学算法不能只看公式，还需要理解公式背后的假设、输入输出范围和工程约束。后续还需要继续补充实时阴影、PBR、全局光照和现代实时光追方向的实践。
