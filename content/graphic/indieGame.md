+++
date = "2026-7-23 05:30:35"
draft = false
title = "独立游戏"
description = "Unity 回合制卡牌战棋游戏，结合网格战斗、牌组构筑、敌人 AI、PCG 环境摆放与风格化渲染"
[taxonomies]
tags = ["2D", "C++", "游戏", "学校项目"]
[extra]
image = '/images/GameStart.png'
+++

2026.6

### 项目描述

《Reaching the IcePeak》是一款基于Unity的，花费一个月时间制作的独立游戏。

游戏以回合制卡牌战棋为核心，玩家需要在网格战场中移动、规划手牌、攻击敌人，并通过牌组构筑应对不同关卡。

该项目承接对PCG与NPR综述的研究，将场景物品布置与风格化渲染应用到 Unity 游戏原型中，通过程序化环境摆放和雪、雨、水面、草地等 Shader，构建冰雪幻想主题的战棋场景。

### 主要实现

- 风格化渲染管线：基于 Unity URP 制作冰雪幻想风格的整体画面，统一角色、场景、卡牌与战斗界面的视觉基调
- 自定义 Shader：实现雪地、雨水、水面反射、涟漪、indirect instance草地、棋盘格、透明材质与卡牌背景等效果
- 雪地表现：通过雪面 Shader 与雪地变形绘制，让场景具备更强的冰雪主题反馈
- 天气与环境效果：结合雨水、反射、水面和后处理效果，强化不同战斗场景的氛围变化
- PCG 环境摆放：程序化生成树木、石块等场景元素，减少手工布置成本，并提升场景层次
- 卡牌渲染与数据可视化：3D卡牌攻击范围在拖动时显示，卡牌显示伤害实时变动，大大提升交互体验
- 视觉与玩法结合：将棋盘高亮、攻击范围、卡牌表现和场景氛围整合到战斗流程中，让图形效果服务于玩家决策

<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <img src="/images/footprint.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>例：表面细分shader配合RT展示雪地移动轨迹</em>
  </figcaption>
</figure>


<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <video controls autoplay muted loop playsinline width="100%">
    <source src="/videos/shader.mp4" type="video/mp4">
  </video>
  <figcaption style="margin-top:8px;">
    <em>1.噪音遮罩配合粒子系统的水面反射 2.噪音遮罩instance草地 3.粒子雨水在遮罩区域的涟漪扰动效果 4.简单卡背镭光效果</em>
  </figcaption>
</figure>

### 结果

项目已发布可试玩版本：

Github: [FGR](https://github.com/GEShunyuYang/FGR)  
Release: [ReachingIcePeak_1.0.0](https://github.com/GEShunyuYang/FGR/releases/tag/Release)

### 成长 & 反思 & 未来

这个项目让我把 PCG 与 NPR 从论文阅读推进到实际游戏场景中。相比独立图形 Demo，在完整游戏里实现视觉效果需要同时考虑风格统一、玩法可读性、性能成本和资源管理。

棋盘范围、攻击区域、卡牌反馈和环境氛围都需要服务玩家决策，因此视觉层级和信息清晰度同样重要，未来会进一步考虑运行性能的具体对比与提升

目前 PCG 主要用于环境装饰摆放，后续希望进一步让程序化生成影响关卡结构与战斗策略；渲染方面则计划继续优化 Shader 性能，并整理更统一的风格化材质流程。