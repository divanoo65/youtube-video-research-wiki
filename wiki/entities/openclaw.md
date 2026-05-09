---
title: OpenClaw
type: entity
tags: [ai-agent, self-hosted, open-source]
summary: 以 Gateway 网关为中心的自托管智能体框架，强调透明可控的架构设计。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# OpenClaw

## 基本定位

OpenClaw 是一款自托管 AI 智能体框架，采用 Gateway 网关作为绝对的控制中枢，以稳定性高和一切行为可审计著称。

## 核心特征

- **Gateway 中心架构**：后台守护进程负责调度工具、路由请求和维护状态
- **工作区机制**：身份（SOUL.md）绑定在特定工作区，随工作区切换而改变
- **手动技能编写**：技能主要由人类开发者编写，以插件扩展包形式存在
- **透明可控**：一切行为可审计，稳定性高
- **有存量用户基础**：已定义个人自托管智能体的初步标准

## 关系网络

- 与 [[hermes-agent]] 并列为自托管智能体赛道两大核心产品
- [[hermes-agent]] 提供一键迁移工具，可自动转换 OpenClaw 的 Markdown 记忆为 SQLite 存储

## 出现的视频

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
