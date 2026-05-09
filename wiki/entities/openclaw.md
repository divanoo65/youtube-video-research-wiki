---
title: OpenClaw
type: entity
tags: [agent-framework, open-source, personal-agent]
summary: 以 Gateway 网关为控制中枢的个人自托管 AI Agent 框架，定义了自托管智能体的行业标准
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# OpenClaw

## 基本定位

OpenClaw 是最早定义个人自托管 AI Agent 标准的框架之一，以 **Gateway 网关** 为绝对控制中枢，将 Agent 的管理与执行集中在一个后台守护进程中。其核心优势在于高稳定性、高可审计性和极强的可控性，适合对透明度和可靠性有较高要求的用户。

## 核心特征/能力

1. **Gateway 中心化架构**：网关后台守护进程负责会话管理、请求路由、工具调用调度及全局状态维护，所有操作均可追溯。
2. **Markdown 记忆载体**：以 Markdown 文件为记忆存储方式，结构清晰、易于人工编辑和审计。
3. **工作区身份绑定**：身份（Identity）与具体工作区绑定，切换工作区即切换完整的身份与行为配置。
4. **模块化技能定义**：技能本质上是模块化的工具或工作流指令，由人类开发者编写与优化。
5. **高可审计性**：由于所有请求通过 Gateway 统一分发，每个操作都有完整的审计轨迹。

## 应用场景

- **日常任务自动化**：利用清晰的 Markdown 工作区管理机制处理常规任务。
- **需要高透明度的场景**：对操作审计有严格要求的团队或个人使用。
- **稳定性优先的生产环境**：Gateway 架构确保请求调度可靠、无单点逻辑混乱。

## 关系网络

- [[hermes-agent]] — 同类竞争框架，架构设计哲学差异：Gateway 中心化控制 vs 执行循环驱动
- [[nous-research]] — 其 Hermes Agent 提供了从 OpenClaw 迁移的工具

## 关键事件/里程碑

- 开创了个人自托管智能体的标准架构（Gateway + 工作区 + Markdown 配置）
- 面临 Hermes Agent 崛起带来的行业竞争，Hermes 提供了 OpenClaw 到自身的迁移工具

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
