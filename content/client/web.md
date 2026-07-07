+++
date = "2026-5-1 05:30:35"
draft = false
title = "C++ 网络聊天室"
description = "基于 Winsock TCP、ImGui 和 DirectX12 实现的客户端/服务端聊天室，支持登录、在线用户列表、群聊与私聊"
[taxonomies]
tags = ["C++", "网络", "TCP", "ImGui", "DirectX12", "学校项目"]
[extra]
image = '/images/chatroom.png'
+++

2025.12

### 项目描述

这是一个使用 C++ 实现的网络聊天室项目，包含独立的客户端与服务端。客户端使用 Dear ImGui 搭建聊天界面，并通过 DirectX12 后端渲染窗口；网络通信部分基于 Winsock TCP socket，实现用户连接、消息收发、公共聊天和私聊功能。

服务端负责维护在线客户端列表，为每个连接创建处理线程，并根据简单的文本协议转发群聊和私聊消息。

### 主要实现

- 使用 Winsock TCP socket 实现客户端与服务端通信
- 客户端支持用户名登录、连接状态显示和断线处理
- 使用独立接收线程监听服务端消息，避免阻塞 UI 主循环
- 使用 ImGui 实现公共聊天室、私聊窗口、输入框和在线用户列表
- 服务端维护在线用户列表，并在用户连接/断开时广播更新
- 实现简单文本协议，例如 `clients/`、`public/`、`private/` 区分消息类型
- 支持群聊广播和指定用户私聊转发
- 使用 FMOD 为公共消息和私聊消息添加提示音反馈

### 结果

![Connecting](/images/connecting.png)
*客户端登录与连接界面。*

![Chatroom](/images/chatroom.png)
*聊天室界面，支持公共聊天和私聊窗口。*

Github Link: [Client](https://github.com/GEShunyuYang/Client)  
Github Link: [Server](https://github.com/GEShunyuYang/Server)

### 成长 & 反思 & 未来

这个项目让我从客户端和服务端两个方向理解了基础网络通信流程，包括 socket 初始化、连接建立、消息收发、客户端列表维护和多线程处理。

相比只写单端逻辑，聊天室项目更强调状态同步和异常处理。例如用户断开连接后，服务端需要更新在线列表并通知其他客户端；客户端也需要在接收线程和 UI 线程之间安全地传递消息。

目前协议设计仍比较简单，消息格式依赖字符串解析，缺少更严格的封包、错误处理和身份验证。后续如果继续完善，我会考虑加入结构化消息格式、消息长度头、断线重连、聊天记录保存，以及更清晰的客户端状态管理。