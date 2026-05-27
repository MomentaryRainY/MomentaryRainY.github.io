+++
date = "2026-05-22 05:30:35"
draft = false
title = "UE小组项目"
description = "FFT海洋渲染"
[taxonomies]
tags = ["3D", "C++", "UE", "学校项目", "流体模拟"]
[extra]
image = '/images/team.png'
+++

### 课程描述

要求Unreal引擎，班级合作，制作一款游戏。 游戏要求包含多个子关卡，玩家可以在不同子关卡之间切换。学员将被分成若干小组，小组成员由课程导师指定。每个小组负责开发一个子游戏，要求最短运行5分钟，最终会将所有子游戏将合并成一个最终产品。

### 项目描述

游戏要求现实风格，作者被分配到了海战部分，在组内负责海面模拟。

具体使用了随机JSONWAP频谱，实时使用compute shader进行IFFT计算，模拟现实海面。

具体生成的数据包括，位移贴图、法线贴图、jacobian泡沫从而计算顶点位移，法线以及具体真实泡沫的海洋着色。

### 结果

<figure style="width:50%; margin:0px auto 0px auto; text-align:center;">
  <img src="/images/displacement.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>IFFT后，主波型的位移贴图</em>
  </figcaption>
</figure>


6张基本频谱，傅里叶变换后，权重加和构成的海洋高度，法线，海面挤压强度，传递到UE材质，最终接合。纯C++实现。

<video controls playsinline preload="metadata" width="100%">
  <source src="/videos/ocean.mp4" type="video/mp4">
</video>

为了配合低难度的开船逻辑，海浪波形调整的并不高，场景整体打光设计也较为压抑。

其他人部分包括关卡，UI，玩家控制、敌人AI以及特效，以作者观点，还有很多提升空间。

UE版本5.4.4，Github 代码: [<strong> link</strong>](https://github.com/GEShunyuYang/GEDD_Level3)

### 成长 & 反思 & 未来

在小组内合作，掌握、管理团队进度变得更加成熟，做到了即时沟通以及提早发现问题。熟悉了UE C++基本库、接口以及语法。RenderDoc运行时debug渲染管线状态，性能。掌握UE的compute shader配置，以及基础UE管线知识。回顾了傅里叶变换。

1.对于UE的物理单位和实际C++内的数值没有做到对应，在开发期间造成了严重阻碍，具体是频率采样率以及纹理在世界映射比例问题。

2.目前泡沫物体交互的实现方式是基于屏幕空间的。

3.虽然海洋着色不属于作者职责范围，但是着色依赖于作者输出，目前海洋没有在着色上反应出海洋深度

4.目前HLSL写法只限于了DX12，且没有扩展性，参数管理也有些硬编码

5.还有CPU-GPU的通讯fence问题

当前泡沫物理，如船体与海面的交互计算只靠材质内深度求差模拟交互的白缝，进一步船体在海面的物理拖尾效果还没有实现，需要进一步研究。
