---
title: MCP协议
type: concept
tags: [protocol, tool-integration, hermes-agent]
summary: Model Context Protocol，一种用于智能体与外部工具、数据源交互的标准化协议，Hermes Agent 深度集成该协议。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: medium
reasoning: 视频提及 MCP 协议的凭证过滤功能，但未深入介绍协议细节。
---

## 定义

MCP（Model Context Protocol）是一种开放协议，定义了 AI 智能体如何与外部工具、API、数据库等资源进行标准化交互。Hermes Agent 利用 MCP 协议实现可扩展的工具调用，并内置凭证过滤以保障安全。

## 在本库的具体例子

- 在 [[Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛起]] 中，描述 Hermes Agent 的 GitHub 分诊助手通过 MCP 连接 GitHub API，自动聚类 Issue。

## 技术实现细节

- MCP 定义了一套 JSON-RPC 格式的请求/响应规范。
- 智能体通过 MCP 客户端发现可用工具，执行调用并接收结果。
- Hermes Agent 在五层防御中的第四层（MCP 凭证过滤）会检查请求中是否包含 API Key 等敏感信息，并在必要时替换。

## 与近似概念的边界

- **Function Calling**：OpenAI 的 Function Calling 是厂商特定的工具调用格式；MCP 是开放标准，可跨平台使用。
- **OpenClaw 插件系统**：OpenClaw 使用自己的插件机制，不与 MCP 兼容。

## 关联概念

- [[程序化知识]]
- [[执行循环]]

## 关联实体

- [[hermes-agent]]
