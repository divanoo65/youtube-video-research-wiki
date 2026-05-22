---
title: Base URL
type: entity
tags:
  - Configuration
  - API
  - Deployment
summary: Base URL 是配置 [[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]] 时用于指定 API 服务端点的重要参数，它定义了模型或服务的网络访问地址。
sources:
  - "raw/notebooklm-analysis/赫美斯-Agent-Hermes-Agent-高级应用与部署简报.md"
created: 2024-07-29
updated: 2024-07-29
layer: L1
confidence: high
reasoning: The entity "Base URL"是源报告中明确提及的关键配置参数，用于部署和使用 [[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]]。其功能在API和模型配置的上下文中得到了清晰定义。
---
Base URL（基础URL）是计算机网络中用于指定特定资源或服务访问起点的一个统一资源定位符。在API（应用程序编程接口）和网络服务的语境中，Base URL通常指代API服务器的根地址，所有具体的API端点（endpoints）都将基于这个基础地址进行构建。例如，如果一个API的Base URL是`https://api.example.com/v1`，那么获取用户信息的端点可能是`https://api.example.com/v1/users`。

在[[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]]的部署和配置中，Base URL是一个至关重要的参数。它用于指定Agent连接外部模型或[[API service]]的服务器地址。用户需要根据所使用的模型提供商（如OpenAI、Ollama等）或自建服务的实际部署情况，在配置文件（如[[config.toml]]）中精确设置对应的Base URL。这个参数与[[API Key]]和[[Model ID]]一同，构成了Agent与外部智能服务进行通信的核心凭证和寻址信息。正确配置Base URL是确保[[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]]能够成功调用外部模型、执行任务并实现其[[高级功能]]的前提。它允许Agent灵活地切换和管理不同的模型后端，无论是商业API还是本地部署的开源模型。

### 在本视频中的角色

在《赫美斯 Agent (Hermes Agent) 高级应用与部署简报》中，Base URL 被明确指出是配置 [[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]] 时不可或缺的参数之一。视频强调，用户需要在配置文件中针对不同的任务（Task）指定对应的 [[API Key]]、Base URL 以及 [[Model ID]]。这意味着 Base URL 在视频中扮演着连接 Agent 与外部 AI 模型或服务（即 [[API service]]）的“桥梁”角色，是实现 Agent 功能的关键寻址信息。