---
title: Gateway 网关架构
type: concept
tags: [architecture, gateway, agent-framework, centralization]
summary: OpenClaw 以 Gateway 网关为控制中枢的集中式 Agent 架构，提供高稳定性与高可审计性
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 基于 Hermes vs OpenClaw 对比报告的架构描述
---

# Gateway 网关架构

## 定义

Gateway 网关架构是 OpenClaw 采用的中心化 Agent 控制模式。以一个后台守护进程（Gateway）为绝对控制中枢，负责会话管理、请求路由、工具调用调度及全局状态维护。这种设计的优势在于高稳定性、高可审计性和极强的可控性。

## 在本库的具体例子

在 [[Hermes-Agent-与-OpenClaw-深度对比简报]] 中，OpenClaw 的 Gateway 架构与 Hermes Agent 的执行循环驱动架构形成了核心对比。所有请求通过 Gateway 统一分发，工具调用经过集中调度，操作记录完整可追溯。

## 技术实现细节

- Gateway 守护进程在后台持续运行，管理所有 Agent 会话
- 身份（Identity）绑定到工作区，切换工作区即切换完整的身份与行为配置
- 技能以 Markdown 文件形式存储在工作区中，由人工编写
- 所有操作日志记录在 Gateway 中，支持审计回溯

## 与近似概念的边界

- **Gateway 架构 ≠ 执行循环驱动架构**：Gateway 是外部集中控制，执行循环是 Agent 内置的自编排。前者更适合对审计要求高的场景，后者更适合需要自我进化的场景。
- **Gateway 架构 ≠ 微服务架构**：Gateway 架构仍然是一个单体守护进程，只是通过网关统一了访问入口。

## 关联概念

- [[执行循环驱动架构]] — 对立的架构设计范式
- [[程序化知识生成]] — Gateway 架构不支持自动生成，需要人工编写技能

## 关联实体

- [[openclaw]] — 采用此架构的核心产品
- [[hermes-agent]] — 采用执行循环驱动架构，是对立的范式
