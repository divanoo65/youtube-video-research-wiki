---
title: Hermes Agent 与 OpenClaw 深度对比简报
type: source
tags: [hermes-agent, openclaw, agent-framework, comparison]
summary: 深度对比 Nous Research 的 Hermes Agent 与 OpenClaw 两大个人自托管 AI Agent 框架，分析其架构逻辑、记忆体系、技能生成方式与安全性差异
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
  - raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
video_url: https://www.youtube.com/watch?v=NbldZVdusKo
mindmap: raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json
---

# Hermes Agent 与 OpenClaw 深度对比简报

**视频链接：** [https://www.youtube.com/watch?v=NbldZVdusKo](https://www.youtube.com/watch?v=NbldZVdusKo)

**脑图文件：** `raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json`

## 执行摘要

个人自托管 Agent 技术正从"工具属性"向"自我进化属性"转型。OpenClaw 凭借清晰的 Gateway 架构和强大的本地执行能力定义了行业标准，而 Nous Research 推出的 Hermes Agent 正凭借独特的"自我提升"能力和"分层记忆体系"快速崛起。两者的核心差异在于设计哲学：OpenClaw 侧重通过中心化网关实现稳定性与可控性；Hermes Agent 则将执行循环定义为编排引擎，强调从经验中自动生成程序化知识，实现从"记住事实"到"记住方法"的跨越。

## 核心要点

1. **架构差异**：OpenClaw 以 Gateway 网关为绝对控制中枢；Hermes Agent 以执行循环为同步编排引擎。
2. **技能生成方式**：OpenClaw 依赖人类编写模块化工具；Hermes Agent 自动生成程序化知识（Skill）。
3. **分层记忆体系**：Hermes 构建了四层记忆（核心持久记忆、会话历史、扩展用户画像、程序性记忆），比传统 Markdown 记忆载体更高效。
4. **内置自动化**：Hermes 内置 Cron 计划任务系统，每 60 秒检查一次条件，支持自然语言指定任务。
5. **五层纵深防御**：Hermes 设计包括用户授权、危险命令审批、容器隔离、MCP 凭证过滤及上下文扫描的安全体系。
6. **部署灵活性**：Hermes 支持 VPS、Docker、SSH、无服务器架构，实现模型无关性（OpenAI、OpenRouter、国产模型均可）。
7. **身份锚定**：Hermes 的身份是全局性的（SOUL.md），不绑定具体目录；OpenClaw 的身份绑定工作区。
8. **迁移支持**：Hermes 提供针对 OpenClaw 用户的自动迁移工具，但底层存储逻辑仍存在差异。
9. **争议事件**：Hermes Agent 卷入了与中国开源项目 EvoMap 的抄袭争议。

## 关键引言

> **"它让智能体从传统的'记住事实'，升级为了'记住方法'。这也是智能体从被动执行到主动成长的关键跨越。"**
> — 解释 Hermes Agent 自动生成技能（程序化知识）的核心价值。

> **"这种设计把智能体的计算核心与用户交互界面彻底解耦，复杂计算可以放在远端高性能设备上完成。"**
> — 论述 Hermes Agent 的解耦架构设计。

## 关联实体

- [[hermes-agent]] — Nous Research 推出的智能体框架
- [[openclaw]] — 对比的另一个智能体框架
- [[nous-research]] — Hermes Agent 开发方

## 关联概念

- [[执行循环驱动架构]] — Hermes 的核心架构设计哲学
- [[分层记忆体系]] — Hermes 的四层记忆系统
- [[程序化知识生成]] — 技能自动生成机制
- [[纵深防御模型]] — 五层安全防护体系
- [[Gateway网关架构]] — OpenClaw 的中心化控制模式

## 脑图核心节点

- 研发背景与理念：Nous Research 团队、开源优先、DisTrO 分布式训练
- 核心架构差异：OpenClaw（中心化控制）vs Hermes Agent（执行循环驱动）
- 能力特性对比：知识与技能生成、分层记忆体系、自动化与安全
- 部署与兼容性：跨平台、模型无关性、多消息平台集成
- 争议与风波：涉嫌抄袭 EvoMap 架构争议
