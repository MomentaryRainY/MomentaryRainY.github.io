+++
date = "2025-05-02 08:20:35"
draft = false
title = "Unity URP 风格化角色渲染"
description = "在 Unity URP 中复刻类原神角色渲染，实践 Ramp 光照、SDF 面部阴影和描边效果"
[taxonomies]
tags = ["Unity", "URP", "Shader", "NPR", "个人项目"]
[extra]
image = '/images/furina.png'
+++

### 项目描述

这是一个在 Unity URP 管线中进行的 NPR 角色渲染练习，目标是复刻类原神角色的风格化光照效果。项目参考了 B 站教程 [原视频](https://www.bilibili.com/video/BV1HN4y1X7uS/) 以及多篇知乎技术文章，并以芙宁娜角色模型作为测试对象。

练习重点包括 Ramp 贴图光照、SDF 面部阴影、描边和角色材质参数调试。相比简单 Shader 练习，这个项目更接近完整角色渲染效果的拆解与复现。

### 结果

![Furina](/images/furina.png)
*Unity URP 中的风格化角色渲染结果。当前版本缺少原作中更完整的全局光照和暖色环境氛围。*

Github Link [FurinaRender](https://github.com/MomentaryRainY/FurinaRender)

### 成长 & 反思 & 未来

这个项目让我理解了风格化角色渲染中多个关键模块的配合方式：Ramp 贴图负责控制明暗分层，SDF 面部阴影用于获得更稳定的脸部阴影过渡，描边则强化角色轮廓和动画风格。

相比过去只会写简单 Shader 语法，这次练习让我开始理解如何把复杂视觉目标拆成多个可调模块，并通过材质参数逐步接近目标风格。

后续如果继续迭代，我希望在自己的渲染框架或 Unity 项目中整理一套更完整的 NPR 管线，包括角色光照、阴影、描边、后处理和场景氛围统一控制。
