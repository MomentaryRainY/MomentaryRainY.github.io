+++
date = "2026-4-27 05:30:35"
draft = false
title = "CPU 路径追踪渲染器"
description = "使用 C++ 实现路径追踪、材质系统、环境光照、BVH 加速、多线程渲染与 OIDN 降噪"
[taxonomies]
tags = ["3D", "C++", "路径追踪", "学校项目", "CPU"]
[extra]
image = '/images/cornellbox.png'
+++

2026.4

### 项目描述

这是一个使用 C++ 实现的 CPU 路径追踪渲染器项目，覆盖了从场景加载、光线求交、材质采样、直接/间接光照计算，到多线程渲染加速和图像降噪的完整离线渲染流程。

项目重点不只是渲染出正确图像，而是理解路径追踪中不同模块之间的关系：BSDF 采样、光源采样、MIS、多次反弹、BVH 加速、环境贴图采样、AOV 输出和后处理降噪。

### 主要实现

- 实现基础路径追踪流程，支持直接光照、间接光照和多次反弹
- 实现多重重要性采样，用于平衡 BSDF 采样与光源采样
- 支持区域光与 HDR 环境贴图光照，并实现环境贴图采样
- 实现多种 BSDF 材质，包括漫反射、镜面、玻璃和 GGX 微表面金属材质
- 实现 Fresnel、GGX 法线分布、几何遮蔽项等材质计算
- 使用 BVH 加速场景求交，降低复杂场景渲染时间
- 使用 tile-based 多线程渲染和 job stealing 提升 CPU 利用率
- 实现 normal / albedo / color AOV 输出，为降噪提供辅助通道
- 接入 Intel Open Image Denoise，对低 SPP 渲染结果进行降噪
- 实现 tone mapping、gamma correction 和 HDR/PNG 输出
- 尝试 irradiance cache，用于进一步加速间接光照计算

### 结果

以下图像均为低 SPP 渲染结果，部分结果未降噪，用于展示路径追踪原始收敛效果和加速结构效果。

![Cornellbox](/images/cornellbox.png)
*Cornell Box：测试直接光照、间接光照、漫反射材质和 BVH 加速。*

![Bathroom](/images/bathroom.png)
*Bathroom：复杂场景中的镜面反射与 BVH 求交加速。不使用 BVH 时渲染时间明显增加。*

![Material](/images/material.png)
*Material Scene：测试玻璃材质、GGX 微表面金属和环境光照。*

降噪效果使用 Intel Open Image Denoise，并输入 color、normal 和 albedo 作为参考通道：

![Cornellbox Denoised](/images/dcornellbox.png)
![Bathroom Denoised](/images/dbathroom.png)
![Material Denoised](/images/dmaterial.png)

Github Link: [AdvancedCG](https://github.com/GEShunyuYang/AdvancedCG)

### 成长 & 反思 & 未来

这个项目让我系统理解了路径追踪渲染器的核心流程。相比只实现单个算法，完整渲染器需要把相机、求交、材质、采样、光照、加速结构和图像输出组织成稳定的管线。

开发过程中我最深的体会是，路径追踪的难点不只在公式本身，也在大量边界情况和数值稳定性。例如玻璃材质中的全反射、GGX 采样中的极小 PDF、阴影偏移、Russian Roulette 终止策略，以及 MIS 权重都可能明显影响结果。

项目也让我更直观地理解了性能优化的重要性。BVH、多线程 tile 渲染和 job stealing 对 CPU 路径追踪的影响非常明显，而低 SPP 下的噪声问题也让我认识到 AOV 与降噪流程在实际渲染中的价值。

不足之处在于，目前渲染器仍偏课程框架式实现，参数管理、材质扩展、场景编辑和调试工具还不够工程化。后续如果继续迭代，我会优先完善性能数据对比、采样策略分析和材质系统结构。
