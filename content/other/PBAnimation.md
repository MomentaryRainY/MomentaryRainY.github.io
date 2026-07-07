+++
date = "2024-08-10 05:20:35"
draft = false
title = "Games103 物理动画入门"
description = "基于 Unity 复现 GAMES103 中的刚体、布料和流体模拟练习"
[taxonomies]
tags = ["GAMES103", "Unity", "物理动画", "布料模拟", "流体模拟"]
[extra]
image = '/images/games103.png'
+++

### 项目描述

这是我跟随 GAMES103 物理动画课程完成的 Unity 练习项目，目标是理解基于物理的动画模拟如何从数学模型落到实时交互程序中。

项目覆盖了刚体动力学、布料模拟和基础流体模拟。相比手工关键帧动画，物理动画更关注约束、力、积分和碰撞对运动结果的影响。

### 结果

![Bouncing House](/images/house.gif)

*刚体动力学练习。*

![Cloth Simulation](/images/cloth.gif)

*基于物理的布料模拟。*

![Pool Simulation](/images/pool.gif)

*基础流体模拟。*

Github Link [<strong>games103</strong>](https://github.com/MomentaryRainY/PBAnimation)

### 成长 & 未来

这个项目让我熟悉了物理动画中常见的建模方式：用数值积分更新状态，用约束和碰撞控制运动边界，再通过实时渲染观察系统是否稳定。

后续如果继续迭代，我希望在自研或 Unity 项目中实现更完整的碰撞系统，并进一步学习 PBD、XPBD 和更稳定的实时布料/软体模拟方法。
