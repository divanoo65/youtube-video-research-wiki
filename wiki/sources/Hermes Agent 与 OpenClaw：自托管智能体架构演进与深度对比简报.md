---
title: Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报
type: source
tags: [hermes-agent, openclaw, agent-architecture, nous-research, evomap, local-ai]
summary: 深度解析 Hermes Agent（Nous Research）与 OpenClaw 在自托管智能体架构上的核心技术差异，包括执行循环驱动架构、分层记忆体系、程序性知识生成等范式级差异。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-自托管智能体架构演进与深度对比简.md
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw：自托管智能体架构演进与深度对比简.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 视频元数据
- **标题**: Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报
- **主题**: 自托管智能体架构深度对比——Hermes Agent 与 OpenClaw

## 执行摘要

本简报深度解析了个人自托管智能体赛道的新兴力量 **Hermes Agent**（由 Nous Research 开发）与行业标杆 **OpenClaw** 之间的核心技术差异。OpenClaw 以其清晰的架构和稳定的本地执行能力定义了该领域，而 Hermes Agent 则代表了下一代智能体的发展方向：**从单纯的指令执行向自我进化、程序化知识生成和长效成长转型**。核心优势包括以"智能体执行循环"为中心的编排引擎、精密的四层分层记忆体系，以及能够自动将执行经验转化为可复用技能的机制。

## 核心要点

1. **架构差异**：OpenClaw 采用中心化网关模式（Gateway 为绝对控制中枢），Hermes Agent 采用执行循环驱动模式（AI Agent 自身的执行循环为编排引擎）。
2. **技能生成机制**：OpenClaw 的技能由人类开发者手动编写（类似插件），Hermes Agent 的技能可根据执行经验自动生成并优化。
3. **四层分层记忆体系**：核心持久记忆（~1300 tokens）、会话历史记忆（SQLite FTS5）、可选扩展层（Honcho）、程序性记忆（自动生成技能）。
4. **身份锚定逻辑**：OpenClaw 的 SOUL.md 属于工作区文件（可切换），Hermes Agent 的 SOUL.md 为全局核心身份（保持一致）。
5. **五层纵深防御**：基础层（用户授权）、隔离层（容器化）、过滤层（MCP 凭证）、扫描层（危险命令）、网络层（SSRF 防护）。
6. **抄袭争议**：Hermes Agent 涉嫌借鉴中国开源项目 EvoMap，引发社区讨论。
7. **零成本迁移工具**：Hermes 内置 OpenClaw 迁移工具，可自动检测和转换记忆数据。

## 关键引言

> "（Nous Research 的目标是）打造一个用户完全可控的 AI，把智能普惠到每一个人，而不是让 AI 能力被少数几家封闭平台垄断。"

> "它让智能体从传统的记住事实，升级为了记住方法。"

> "Hermes Agent 卷入了涉嫌抄袭中国团队 EvoMap 开源项目的风波……有相当洗代码的嫌疑。"

## 关联实体
- [[Hermes Agent]] — Nous Research 开发的下一代智能体
- [[Nous Research]] — Hermes Agent 的开发者
- [[OpenClaw]] — 中心化网关模式的智能体平台
- [[EvoMap]] — 被指抄袭的中国开源项目

## 关联概念
- [[执行循环驱动架构]] — Hermes Agent 的核心架构模式
- [[中心化网关模式]] — OpenClaw 的核心架构模式
- [[分层记忆体系]] — Hermes Agent 的四层记忆架构
- [[程序性记忆]] — Hermes Agent 自动生成的技能系统
- [[五层纵深防御模型]] — Hermes Agent 的安全防护体系
