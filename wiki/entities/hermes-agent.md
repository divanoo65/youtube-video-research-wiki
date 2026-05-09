---
title: Hermes Agent
type: entity
tags: [ai-agent, self-hosted, open-source]
summary: Nous Research 开发的自我进化 AI 智能体框架，引入执行循环架构、程序化知识和分层记忆体系。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.md
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Hermes Agent

## 基本定位

Hermes Agent 是由 [[nous-research]] 开发的开源自托管 AI 智能体框架，以 AI Agent 的执行循环为系统核心，支持自我进化、自动技能生成和跨平台部署。

## 核心特征

- **执行循环架构**：将 AI Agent 自身的执行循环定义为系统同步编排引擎，而非传统的网关核心模式
- **程序化知识**：能根据执行经验自动将多步操作抽象为可复用技能，存储在 `~/.hermes/skills/`
- **分层记忆体系**：四层持久化存储（核心记忆 → 会话历史 → 扩展记忆 → 程序性记忆）
- **模型无关**：支持 OpenAI、OpenRouter、国内大模型及自定义端点，可快速切换
- **全局身份**：身份定义不绑定工作区或设备，全局一致
- **内置 cron**：自然语言定义的定时任务系统，每 60 秒检查一次
- **五层纵深防御**：从用户授权到容器化隔离再到 SSRF 防护
- **多平台交互**：支持 Telegram、Discord、Slack、WhatsApp 及 TUI
- **部署灵活**：本地、VPS、Docker、SSH 远程及无服务器架构均可

## 关系网络

- 由 [[nous-research]] 开发
- 与 [[openclaw]] 并列为自托管智能体赛道核心产品
- 支持集成 [[qwen3.6]] 实现完全本地化推理
- 可调用 [[openai]] API
- 曾被指控架构抄袭 [[evomap]]
- 核心设计哲学包括 [[自我进化智能体]]、[[程序化知识]]、[[分层记忆体系]]

## 出现的视频

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
- [[零成本本地-AI-Agent-部署简报]]
