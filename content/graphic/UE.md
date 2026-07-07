+++
date = "2026-05-22 05:30:35"
draft = false
title = "UE5 实时 IFFT 海面模拟"
description = "在 Unreal Engine 5 中使用 Compute Shader 实现基于频谱的实时海面模拟，输出位移、法线与泡沫控制贴图"
[taxonomies]
tags = ["UE5", "C++", "HLSL", "Compute Shader", "IFFT", "海面模拟", "图形学"]
[extra]
image = '/images/team.png'
+++

2026.5

### 项目描述

这是一个在 Unreal Engine 5.4.4 中实现的实时海面模拟模块，用于小组海战游戏项目中的海面表现。我主要负责海面模拟与渲染数据输出部分：基于频域波浪模型生成初始频谱，在 GPU 上通过 Compute Shader 执行 IFFT，并将结果写入 Render Target，最终传递给 UE 材质用于顶点位移、法线和泡沫表现。

相比使用预制水面资源，这个项目更关注从频谱生成到材质接入的完整实时渲染流程。

### 主要实现

- 使用 UE C++ 实现海面 Actor，生成可调分辨率的 Procedural Mesh 海面网格
- 基于 JONSWAP 频谱生成初始频域数据 H0，用于控制不同尺度的海浪形态
- 使用 Render Target 存储频谱、位移、斜率、Jacobian/variation 等中间结果
- 编写多阶段 Compute Shader 管线，包括 H0 生成、Ht 时间演化、横向 IFFT、纵向 IFFT 和结果组装
- 通过 Unreal Render Dependency Graph 派发 Compute Shader，并在渲染线程中完成 GPU 计算
- 使用多组频谱叠加大浪、中浪和细节波纹，提升海面层次感
- 将 IFFT 输出的 displacement texture 传入材质，用于海面顶点位移
- 将 slope texture / normal 信息传入材质，用于海面法线和光照表现
- 基于 Jacobian 或局部压缩强度生成泡沫控制信息，用于表现浪尖和破碎区域
- 使用双缓冲管理前后帧位移结果，为泡沫累积和衰减提供基础
- 使用 RenderDoc 调试渲染管线、Render Target 内容和 Compute Shader 输出


### 结果

<figure style="width:50%; margin:0px auto 0px auto; text-align:center;">
  <img src="/images/displacement.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>IFFT 后得到的主波位移贴图。</em>
  </figcaption>
</figure>

模块最终在 UE 材质中接入多尺度 displacement、slope 和 foam 数据，形成实时海面效果。由于项目需要配合低难度开船玩法，最终海浪幅度被控制在较低范围，避免过强的波动影响玩家操作。

<video controls playsinline preload="metadata" width="100%">
  <source src="/videos/ocean.mp4" type="video/mp4">
</video>

Github Link: [GEDD_Level3](https://github.com/GEShunyuYang/GEDD_Level3)


### 成长 & 反思 & 未来

这个项目让我第一次在 UE 中完整实践了从数学模型、GPU 计算到材质表现的实时渲染流程。相比在离线程序中实现 FFT，UE 项目需要额外处理 Render Target、RDG、渲染线程、材质参数绑定和资源生命周期等工程问题。

开发中最大的难点是尺度统一。频谱采样、纹理分辨率、世界坐标映射和 UE 物理单位之间需要保持一致，否则海浪频率、波长和视觉尺度很容易失真。这也让我意识到，图形学算法进入引擎后，工程参数管理和调试工具同样重要。

目前项目仍有几个不足：HLSL 和参数管理比较硬编码，对 DX12 依赖较强；泡沫与船体交互主要依赖屏幕空间深度差，缺少更真实的物理拖尾；海洋着色还没有充分利用水深、透射和环境反射信息。后续如果继续迭代，我会优先整理参数系统，完善 CPU-GPU 同步与调试流程，并进一步研究船体扰动、尾迹和更完整的海洋材质表现。