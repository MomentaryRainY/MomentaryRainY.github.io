+++
date = "2025-12-23 05:30:35"
draft = false
title = "优化"
description = "优化光栅渲染器"
[taxonomies]
tags = ["C++", "学校项目", "优化"]
[extra]
image = '/images/before.png'
+++

优化包括逻辑优化，SIMD并行，多线程

![After](/images/after.png)

经过优化，超出了CPU读写极限，出现规则性渲染失败, 高密度几何区域z-fight严重，需要提升至GPU或者更换渲染策略如分块渲染等，超出原本渲染逻辑极限

同时还包括了一个简单网络聊天室的实现，使用了Imgui作为聊天面板，客户端、服务端的C++实现,包括公共聊天以及私聊。使用了简单的网络协议。
![Connecting](/images/connecting.png)
![Chatroom](/images/chatroom.png)

Github Link [<strong>opt</strong>](https://github.com/GEShunyuYang/Optimization)

Github Link [<strong>server</strong>](https://github.com/GEShunyuYang/Server)

Github Link [<strong>client</strong>](https://github.com/GEShunyuYang/Client)