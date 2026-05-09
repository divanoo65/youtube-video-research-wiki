---
title: OpenClaw
type: entity
tags: [agent, open-source, self-hosted]
summary: 个人自托管智能体赛道的早期定义者，采用中心化 Gateway 网关架构
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比分析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# OpenClaw

OpenClaw 是个人自托管智能体赛道的早期定义者，以其清晰的架构和稳定的本地执行能力奠定了该领域的基础标准。它采用中心化 Gateway 网关模式，强调稳定性、可审计性与可控性。

## 核心特征

- **中心化 Gateway 网关**：以守护进程作为控制中枢，负责路由、调度与状态维护。
- **模块化工具/指令**：技能机制主要由人类开发者编写与加载。
- **工作区绑定身份**：SOUL.md 与工作区绑定，身份随环境切换。
- **本地优先**：侧重本地执行与工作区机制。
- **可审计性高**：所有行为和工具调用均可追踪审计。

## 关系网络

- 与 [[hermes-agent]] 在架构逻辑上形成对比
- 可迁移至 Hermes Agent（内置迁移工具）
- 在 [[Hermes-Agent-与-OpenClaw-深度对比分析简报]] 中被详细分析
