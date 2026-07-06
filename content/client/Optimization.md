+++
date = "2026-5-23 05:30:35"
draft = false
title = "优化"
description = "优化光栅渲染器"
[taxonomies]
tags = ["C++", "学校项目", "优化"]
[extra]
image = '/images/before.png'
+++

2025.12

### 课程描述

课程重点在于游戏相关各种技术的综合应用。其中包括游戏音频，游戏AI，数据库，图论，GPGPU，多线程，移动语法，网络，优化，SIMD，测试驱动开发，游戏窗口。

### 项目描述

项目要求使用多线程以及SIMD优化C++光栅化渲染器，以及使用ImGui和网络构建简单的在线聊天室。

### 结果

![After](/images/after.png)

如图经过优化，超出了CPU读写极限，出现规则性渲染失败, 高密度几何区域z-fight严重，需要提升至GPU或者更换渲染策略如分块渲染等，超出原本渲染逻辑极限

简单网络聊天室的，使用了Imgui作为聊天面板，客户端、服务端的C++实现,包括公共聊天以及私聊。使用了简单的网络协议。
![Connecting](/images/connecting.png)
![Chatroom](/images/chatroom.png)

Github Link [<strong>opt</strong>](https://github.com/GEShunyuYang/Optimization)

Github Link [<strong>server</strong>](https://github.com/GEShunyuYang/Server)

Github Link [<strong>client</strong>](https://github.com/GEShunyuYang/Client)

### 成长 & 反思 & 未来

对游戏相关技术领域有了初步理解，掌握了对于简单游戏架构的优化。

对于多线程的数据管理略显生疏，实际执行前的设计规划不足。

对于复杂游戏架构，如现代游戏引擎的优化还需进一步理解+学习。各种游戏概念在课程内只停留在了初步，进阶内容如GPGPU仍缺少实践。