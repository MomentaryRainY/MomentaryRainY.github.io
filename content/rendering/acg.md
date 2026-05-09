+++
date = "2026-4-27 05:30:35"
draft = false
title = "高级图形学"
description = "光线追踪、路线追踪，材质，分块渲染，多线程加速，环境光照到全局光照的C++ CPU端实现"
[taxonomies]
tags = ["3D", "C++", "路径追踪", "学校项目", "CPU"]
[extra]
image = '/images/cornellbox.png'
+++

### 课程描述

从光线追踪出发、到滤波后处理、空间数据结构、随机数、蒙特卡洛积分、光线追踪、真实相机、体积渲染、材质、
进阶实时渲染算法如辐照度缓存、光子映射等

### 项目描述

在C++端产出正确的路径渲染结果，实现正确的材质函数，拥有一定的渲染加速，路径追踪内补充环境光照。
具体包含计算直接光照，间接光照，多重重要性采样；GGX微表面金属BRDF，玻璃BRDF，漫反射、镜面材质: 
分块+多线程渲染加速，BVH，矩形环境贴图采样等。

### 结果

图像均为低SPP产出，未降噪。侵入式渲染，

![Cornellbox](/images/cornellbox.png)
多线程配合BVH8倍加速
![Bathroom](/images/bathroom.png)
包含了镜面反射，不使用BVH渲染时间超过5分钟
![Material](/images/material.png)
包含了玻璃材质与微表面金属，25倍加速

降噪效果,使用了intel降噪库，输入了法向、基本色作为参考

![Cornellbox](/images/dcornellbox.png)
![Bathroom](/images/dbathroom.png)
![Material](/images/dmaterial.png)

Github Link [<strong>path</strong>](https://github.com/GEShunyuYang/AdvancedCG)

### 成长 & 反思 & 未来

对基本路径追踪、材质、光照、滤波算法以及相关加速的综合掌握，渲染各流程的数学理论掌握，以及对横向技术分类的认识与理解

对于基本渲染算法准确的数学表达，数值收敛以及边缘情况处理的综合运用

很多开发时间浪费到了没有了解算法细节，如特殊情况处理、常数合理性，编写代码途中多次回顾和尝试。

短时间内没有进一步研究的计划。
