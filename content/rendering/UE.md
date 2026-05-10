+++
date = "2026-05-22 05:30:35"
draft = false
title = "UE小组项目(进行中)"
description = "小组作业，长游戏逻辑线，每个小组负责一个场景"
[taxonomies]
tags = ["3D", "C++", "UE", "学校项目", "流体模拟"]
[extra]
image = '/images/team.png'
+++
锐意制作中...

### 项目描述
对于班级进行随机分组，分配随机关卡，要求UE引擎，最终全班关卡组合成为成品游戏。
作者被分配到了海战部分，在组内自行选择了海面模拟。

### 计划 & 进展

计划使用FFT制作无限海面，在玩家近处lerp Gerstner waves，再配合海面、船体交碰撞，生成最终实时海面

![Water](/images/water.png)
当前进度，简单三个Gerstner waves, 以及简单的噪声海面着色。

compute shader在UE内的配置完毕，暴力IFFT生成基本海浪高度完毕，优化butterfly中...