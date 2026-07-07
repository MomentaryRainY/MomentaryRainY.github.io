+++
date = "2024-05-02 08:20:35"
draft = false
title = "tiny renderer"
description = "复刻 tinyrenderer，使用 C++ 从零实现基础软件光栅化渲染流程"
[taxonomies]
tags = ["C++", "软件渲染器", "光栅化", "个人项目"]
[extra]
image = '/images/renderer.png'
+++

### 项目描述

这是我复刻 [tinyrenderer](https://github.com/ssloy/tinyrenderer) 时完成的软件渲染器练习。项目不依赖 OpenGL 或 DirectX，而是用 C++ 从零实现基础光栅化流程，用来理解图形 API 背后实际发生的事情。

练习内容包括线段绘制、三角形光栅化、重心坐标插值、深度测试、背面剔除、相机变换、纹理采样、法线贴图和阴影映射等。

### 结果

![black](/images/renderer.png)
*软件光栅化渲染结果。当前版本未实现间接光照。*

Github link [<strong>tinyRenderer</strong>](https://github.com/MomentaryRainY/tinyRenderer)

### 成长 & 反思 & 未来

这个项目进一步巩固了我对光栅化管线的理解。相比直接调用图形 API，从零实现软件渲染器能更清楚地看到坐标变换、插值、深度缓冲和纹理采样之间的关系。

实践中也发现，不同项目中的坐标系、矩阵约定和屏幕空间定义可能不同，不能简单搬运已有经验，必须从整体管线重新检查每一步。

后续如果继续完善，我会补充更清晰的渲染管线记录、调试可视化和模块拆分，并尝试加入更完整的光照模型。
