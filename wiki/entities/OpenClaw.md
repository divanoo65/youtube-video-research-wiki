---
title: "OpenClaw"
type: entity
tags: [ai-agent, self-hosted, framework, opensource]
summary: "自托管 AI Agent 平台，采用中心化 Gateway 网关架构，以高稳定性、可审计性和透明性著称。"
sources:
  - raw/notebooklm-analysis/NbldZVdusKo-Hermes-Agent-与-OpenClaw-下一代自我进化智能体深度剖析简报.md
  - raw/notebooklm-analysis/NbldZVdusKo-智能体架构变革-Hermes-Agent-与-OpenClaw-深度对比及技术解析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

## 基本定位

**OpenClaw** 是一款个人自托管智能体平台，长期以来凭借其清晰的中心化 Gateway 网关架构、强大的本地执行能力和完善的工作区机制，在自托管 Agent 赛道中占据主导地位。

## 核心特征

- **Gateway 中心化架构**：采用网关后台守护进程，统一负责会话管理、请求路由和工具调度。
- **高稳定性与可审计性**：所有操作记录可追踪，行为透明。
- **模块化技能机制**：技能本质上是人类开发者编写的模块化工具或工作流，类似传统软件的插件包。
- **Markdown 记忆系统**：以 Markdown 文件为核心存储记忆，动态性相对较弱。
- **设计目标**：实用、可控、透明的助手工具。

## 与 Hermes Agent 的对比

OpenClaw 在架构设计与设计哲学上与 [[Hermes Agent]] 存在根本差异。OpenClaw 追求稳定性和可控性，而 Hermes Agent 追求自我进化和能力复利。Hermes 提供了针对 OpenClaw 用户的一键迁移工具，可自动检测配置目录并转换 Markdown 记忆为 SQLite 格式。

## 关系网络

- [[Hermes Agent]]：同赛道的竞争对手，代表了不同的设计哲学
- [[Agent 执行循环]]：Hermes Agent 取代 Gateway 中心化架构的核心机制

## 出现视频来源

- [[Hermes Agent 与 OpenClaw 智能体架构深度对比]]
