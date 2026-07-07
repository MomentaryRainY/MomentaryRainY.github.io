+++
date = "2026-6-25 05:30:35"
draft = false
title = "Frantic Pinball GameJam"
description = "48 小时 Game Jam 团队项目，一款结合弹珠台与空气曲棍球的双人对抗游戏"
[taxonomies]
tags = ["Unity", "C#", "2D", "Game Jam", "团队项目"]
[extra]
image = '/images/frantic.png'
+++

2025.11

### 项目描述

《Frantic Pinball》是我在华威大学 Game Jam 中参与制作的 48 小时团队项目，主题为 “Frantic / 疯狂”。游戏将弹珠台和空气曲棍球结合成 1v1 对抗玩法，玩家需要操控挡板击球、争夺得分或干扰对手，在快速变化的球速、道具和场地状态中保持节奏。

项目最终发布到 itch.io，支持浏览器运行与 Windows / Linux 下载版本，需要两个手柄进行游玩。

### 游戏设计

游戏包含两种模式：

- **Split Mode**：两名玩家分别在自己的区域中进行弹珠台式对抗，通过击中怪物获得分数。
- **Joint Mode**：两名玩家在同一场地中直接竞争，以生命值和场地控制作为胜负核心。

游戏中加入了多种碰撞道具，包括增大、减小、加速、增加球数和传送等效果。道具不仅影响玩家自己的场地，也可能改变对手区域的局势，从而强化 Game Jam 主题中“疯狂”和不可预测的体验。

![Split](/images/split.png)
*Split Mode：双方在独立区域内竞争分数。*

![Joint](/images/joint.png)
*Joint Mode：双方在同一场地中争夺生存空间。*

### 主要实现

- 使用 Unity / C# 完成 2D 游戏原型开发
- 实现双人手柄输入、挡板移动与旋转控制
- 实现弹球物理、碰撞反馈、得分与生命值逻辑
- 制作 Split Mode 与 Joint Mode 两套玩法场景
- 实现多种碰撞道具与场地干扰效果
- 完成菜单、暂停界面、场景切换和基础游戏流程
- 在 48 小时内完成可发布版本并上传 itch.io

### 结果

项目发布地址：[Frantic Pinball](https://hypersycos.itch.io/frantic-pinball)

Github Link: [PinballAirHockey](https://github.com/Games-Engineering-Grp-Game-Jam/PinballAirHockey)

**获奖：最疯狂奖**

### 成长 & 反思 & 未来

这是我早期参与的完整 Game Jam 项目之一，让我实践了从玩法设计、快速原型、团队协作到最终发布的完整流程。相比课程作业，Game Jam 更强调在极短时间内找到清晰的核心乐趣，并围绕它快速取舍功能。

这个项目中最有价值的部分是玩法设计：通过双人竞争、弹球物理和道具干扰制造紧张感，让主题“疯狂”不只是视觉表现，而是直接进入了玩家交互。

不足之处在于美术和反馈仍比较粗糙，部分资源选择不够统一。后续如果继续迭代，我会优先提升击球反馈、道具提示、UI 清晰度和视觉风格一致性。