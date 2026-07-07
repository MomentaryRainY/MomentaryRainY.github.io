+++
date = "2025-06-03 05:30:35"
draft = false
title = "Learn OpenGL"
description = "跟随 LearnOpenGL 完成的 OpenGL 渲染基础与进阶功能练习"
[taxonomies]
tags = ["OpenGL", "C++", "实时渲染", "个人项目"]
[extra]
image = '/images/opengl.png'
+++

### 项目描述

这是我跟随 [LearnOpenGL](https://learnopengl.com/) 完成的 OpenGL 学习项目，目标是建立实时渲染管线的基础理解，并通过代码实践连接图形学概念和实际 API 使用。

项目覆盖了 OpenGL 基础语法、窗口创建、三角形绘制、纹理、相机、光照、材质和模型加载，也实践了深度测试、模板测试、面剔除、帧缓存、几何 Shader、实例化、反锯齿、阴影、后处理和法线贴图等进阶内容。

### 结果

![path tracing](/images/opengl.gif)

完成了基础章节和大部分进阶章节的代码实践，形成了一个包含模型、相机、光照和多种渲染效果的 OpenGL 学习工程。


Github Link [learnOpenGL](https://github.com/MomentaryRainY/learnOpenGL)

### 成长 & 反思 & 未来

这个项目让我第一次比较系统地理解实时光栅化渲染流程，也熟悉了图形学概念如何落到具体渲染 API 中。

不足之处在于，早期代码更偏跟随教程逐步堆叠，模块划分和资源管理不够清晰，后期功能之间耦合较高。

后续如果重构，我会把窗口、相机、模型、材质、Shader、纹理和渲染 pass 拆成更独立的模块，为之后的 DX12 或自研渲染框架打基础。
