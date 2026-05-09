---
title: MCP 协议
type: concept
tags: [protocol, hermes-agent, integration]
summary: Model Context Protocol，Hermes Agent 用于与外部工具和服务通信的协议。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# MCP 协议

## 定义

MCP（Model Context Protocol）是 Hermes Agent 用于与外部工具和服务通信的协议，支持凭证过滤、安全调用等功能。通过 MCP，Agent 可以连接 GitHub、数据库、内部 API 等，扩展其能力边界。

## 在本库的具体例子

在 [[Hermes-Agent-与-OpenClaw-深度对比简报]] 中，MCP 凭证过滤是五层防御安全模型的一层，防止敏感凭证泄露。同时，MCP 协议被用于自动分诊 GitHub Issue 和代码审查。

## 技术实现细节

MCP 定义了一套标准化的请求-响应格式，包括工具描述、参数规范和认证方式。Agent 通过 MCP 客户端调用外部服务，服务端返回结构化结果。凭证过滤层会检查请求中是否包含敏感信息，并予以拦截。

## 与近似概念的边界

- **REST API**：REST API 是通用 HTTP 接口，MCP 是专为 AI Agent 设计的协议，包含上下文传递和安全机制。
- **函数调用**：函数调用是模型内部能力，MCP 是外部通信协议。

## 关联概念

- [[五层防御安全模型]]
- [[程序化知识生成]]

## 关联实体

- [[hermes-agent]]
