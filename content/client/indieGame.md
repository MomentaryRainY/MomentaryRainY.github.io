+++
date = "2026-7-23 05:30:35"
draft = false
title = "独立游戏(客户端向)"
description = "Unity 回合制卡牌战棋游戏，结合网格战斗、牌组构筑、敌人 AI、PCG 环境摆放与风格化渲染"
[taxonomies]
tags = ["2D", "C++", "游戏", "学校项目"]
[extra]
image = '/images/GameStart.png'
+++

2026.5

### 项目描述

《Reaching the IcePeak》是一款基于Unity的，花费一个月时间制作的独立游戏。

游戏以回合制卡牌战棋为核心，玩家需要在网格战场中移动、规划手牌、攻击敌人，并通过牌组构筑应对不同关卡。

项目将前置图形学研究方向落到实际游戏中：使用风格化渲染强化冰雪幻想氛围，并结合程序化环境摆放生成场景中的树木、石块等装饰元素。

### 主要实现


- 回合制网格战斗：战斗流程、移动范围、攻击范围、伤害结算与胜负判断
- 卡牌系统：手牌、抽牌堆、弃牌堆、卡牌费用、目标选择与效果触发
- 敌人行为：根据战场状态执行移动、攻击等回合行为
- 客户端 UI：战斗界面、卡牌交互、状态显示、教程提示与场景过渡
- 本地化模块：将界面文本、教程内容和卡牌描述从逻辑中拆分，支持多语言内容管理
- 游戏流程：开始界面、教程关卡、多个战斗场景、过场与结局
- 表现与反馈：音频、动画、天气效果和风格化场景表现
- 教程系统：UI高光区域配合文字，制作了教程UI序列，提供详尽指导和建议

<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <img src="/images/csv.png" style="width:100%; display:block;">
  <figcaption style="margin-top:8px;">
    <em>例：卡牌数据与csv文件</em>
  </figcaption>
</figure>


<figure style="width:100%; margin:0 0 0 0; text-align:center;">
  <video controls autoplay muted loop playsinline width="100%">
    <source src="/videos/demo.mp4" type="video/mp4">
  </video>
  <figcaption style="margin-top:8px;">
    <em>Gameplay Demo</em>
  </figcaption>
</figure>

### 结果

项目已发布可试玩版本：

Github: [FGR](https://github.com/GEShunyuYang/FGR)  
Release: [ReachingIcePeak_1.0.0](https://github.com/GEShunyuYang/FGR/releases/tag/Release)

### 成长 & 反思

这个项目让我把游戏设计、系统开发和图形表现放进同一个完整流程中实践。相比单独实现某个技术点，这次更接近真实游戏项目：需要同时考虑玩法反馈、数据组织、UI 引导、资源管理和最终可运行版本。

后续如果继续迭代，我会优先扩展卡牌多样性、敌人种类，关卡复杂度以继续加深游戏性，目前仍然只是一个极具潜力的雏形，以及把 PCG 和关卡目标结合得更紧密。