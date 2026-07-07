+++
date = "2026-5-23 05:30:35"
draft = false
title = "CPU 光栅化渲染器优化"
description = "使用多线程、SIMD 和数据布局优化提升 C++ 软件光栅化渲染器性能"
[taxonomies]
tags = ["C++", "图形学", "性能优化", "SIMD", "多线程"]
[extra]
image = '/images/before.png'
+++

2025.12

### 项目描述

该项目是一个 C++ 软件光栅化渲染器优化实践，目标是在 CPU 上提升三角形光栅化、顶点变换、深度测试和像素着色等流程的执行效率。

项目围绕课程提供的基础光栅器进行扩展，重点尝试多线程任务分发、SIMD 向量化、缓存友好的数据布局和性能测量。相比只追求最终画面，本项目更关注渲染管线中不同阶段的性能瓶颈，以及优化策略对正确性和稳定性的影响。

### 主要实现

- 使用 `PerformanceMeter` 统计帧时间、平均 FPS、最大/最小帧耗时和稳定性
- 使用线程池将渲染任务分配到多个 worker 线程
- 实现 tile-based rendering，将屏幕划分为局部区域以减少线程间写入冲突
- 使用局部 tile buffer 管理颜色、深度和 frame tag，降低共享 z-buffer 的竞争
- 将部分顶点数据改为 SIMD 友好的 SoA 布局
- 使用 AVX 指令优化矩阵变换、透视除法、法线归一化、重心坐标插值和像素着色
- 对比 CPU baseline、SIMD、多线程、多线程 + SIMD 等不同实现路径

### 结果

![After](/images/after.png)

经过优化后，渲染器在部分场景中获得了明显的性能提升，同时也暴露出软件光栅化在高密度几何和大量像素写入下的瓶颈。

在高复杂度场景中，渲染结果出现了规则性错误和较明显的 z-fighting。这个问题说明优化不仅是提高速度，也需要重新审视并行写入、深度缓冲一致性、tile 边界处理和渲染顺序等正确性问题。

<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <img src="/images/threads.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>具体对比数据（单位FPS）</em>
  </figcaption>
</figure>

<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <img src="/images/speedup.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>结果</em>
  </figcaption>
</figure>


Github Link: [Optimization](https://github.com/GEShunyuYang/Optimization)

### 成长 & 反思 & 未来

这个项目让我更具体地理解了 CPU 渲染管线中的性能瓶颈。很多优化并不是简单地“加线程”或“使用 SIMD”就能稳定提升性能，还需要配合数据布局、任务粒度、缓存行为和同步策略一起设计。

多线程部分让我意识到，渲染任务拆分必须同时考虑负载均衡和写入冲突。SIMD 部分则让我理解了 SoA 数据布局、批量处理和分支减少对性能的重要性。

目前项目仍存在并行渲染正确性和复杂场景稳定性的问题。后续如果继续迭代，我会优先完善 tile 边界合并、z-buffer 一致性和性能数据对比表；更进一步则可以尝试 GPU 渲染、compute shader 或更完整的分块渲染架构。