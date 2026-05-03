+++
date = "2026-4-27 05:30:35"
draft = false
title = "高级图形学"
description = "光线追踪、路线追踪，材质，分块渲染，多线程加速，环境光照到全局光照的C++ CPU端实现"
[taxonomies]
tags = ["3D", "C++", "光线追踪", "学校项目", "CPU端"]
[extra]
image = '/images/cornellbox.png'
+++

图像均为低SPP产出，未降噪

![Cornellbox](/images/cornellbox.png)
![Bathroom](/images/bathroom.png)
![Material](/images/material.png)

降噪效果,使用了intel降噪库，输入了法向、基本色作为参考

![Cornellbox](/images/dcornellbox.png)
![Bathroom](/images/dbathroom.png)
![Material](/images/dmaterial.png)

技术点包含直接光照，间接光照，多重重要性采样；GGX微表面金属BRDF，玻璃BRDF，漫反射、镜面材质；分块+多线程渲染加速，BVH，矩形环境贴图采样等

Github Link [<strong>path</strong>](https://github.com/GEShunyuYang/AdvancedCG)
