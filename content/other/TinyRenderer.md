+++
date = "2024-05-02 08:20:35"
draft = false
title = "tiny renderer"
description = "500行内的C++渲染器, 著名github项目(https://github.com/ssloy/tinyrenderer)"
[taxonomies]
tags = ["复刻", "项目"]
[extra]
image = '/images/renderer.png'
+++

### 项目描述

类似Games101，但聚焦于图形接口的应用，包括线条绘制、光栅化三角形，背面剔除，相机控制，着色，数据处理，法相映射，阴影映射，间接光照

### 结果

![black](/images/renderer.png)
未实现间接光照

Github link [<strong>tinyRenderer</strong>](https://github.com/MomentaryRainY/tinyRenderer)

### 成长 & 反思 & 未来

进一步熟悉OpenGL编写，巩固了图形学知识。

使用了与101不同的坐标系定义，经验搬运不完全有效

要进行有全局视野的设计，记录，验证