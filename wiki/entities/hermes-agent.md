---
title: Hermes Agent
type: entity
tags: [agent, open-source, nous-research, automation]
summary: Nous Research 开发的开源 AI Agent 框架，强调自我进化与程序化知识生成
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比分析简报.md
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

Hermes Agent 是由 [[nous-research]] 开发的开源 AI Agent 框架，强调"自我进化"、"[[程序化知识]]生成"以及"执行循环驱动"的设计哲学。它旨在通过持续的自我评估与修正，实现从"记住事实"到"记住方法"的跨越。

## 核心特征

- **闭环执行循环驱动**：以智能体自身的执行、学习、改进闭环驱动系统，而非中心化网关管控。
- **[[分层记忆体系]]**：四层结构化持久化系统——核心持久层（MEMORY.md/USER.md）、会话历史层（SQLite/FTS5）、长期画像层（Honcho）、程序性记忆层（Skills）。
- **自动技能生成**：根据执行经验自动生成、优化并复用工作流（Skills）。
- **内置 Cron 计划任务**：支持定期报告、数据备份、状态检查等无人值守场景。
- **五层安全模型**：用户授权、环境隔离、凭证过滤、安全扫描、网络防护。
- **模型无关性**：支持 OpenAI、OpenRouter 以及国内大模型（Kimi、GLM、MiniMax 等），通过 `hermes model` 命令快速切换。
- **多平台部署**：支持 MacOS、Linux、VPS、Docker、SSH、WSL2。
- **多端交互**：支持 CLI、TUI、Telegram、Discord、WhatsApp。
- **OpenClaw 迁移工具**：内置工具可自动检测 OpenClaw 目录并导入记忆。

## 关系网络

- 由 [[nous-research]] 开发
- 与 [[openclaw]] 在架构设计上存在对比关系
- 可与 [[qwen-36]] 组合实现本地 AI 部署
- 被质疑抄袭 [[evomap]] 项目
- 在 [[Hermes-Agent-与-OpenClaw-深度对比分析简报]] 中被详细分析
- 在 [[Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报]] 中被介绍部署方案

## 脑图关系节点

Hermes Agent 的脑图关系节点包括：研发背景与理念（Nous Research 团队、去中心化与开源优先）、架构逻辑差异（闭环执行循环驱动）、核心能力对比（自动技能生成、分层记忆体系、Cron 计划任务）、部署交互安全（多平台、多端交互、五层安全模型）、应用场景与评价。
