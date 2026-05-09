---
title: Hermes Agent
type: entity
tags: [agent框架, 开源, nous-research, 本地部署]
summary: 由 Nous Research 开发的具备自我进化能力的自托管 AI Agent 框架，采用执行循环驱动架构和程序化知识生成机制。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
  - raw/notebooklm-analysis/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Hermes Agent

## 基本定位

由 [[nous-research]] 开发的下一代自托管 AI Agent 框架，采用[[执行循环驱动架构]]，从"指令执行者"演变为具备"自我进化"能力的数字基础设施。

## 核心特征

1. **执行循环驱动：** 采用 Execution Loop 架构，将网关、调度、工具、环境全部集成于闭环，天然支持自我进化
2. **[[程序化知识生成]]：** 能将完成的工作流抽象为可复用的技能，通过 `skill_manage` 工具自主完成技能的创建、优化与调用
3. **[[分层记忆体系]]：** 四层存储结构——核心持久层（MEMORY.md/USER.md）、会话历史层（SQLite FTS5）、扩展记忆层（Honcho）、程序性记忆层
4. **[[五层纵深防御]]：** 用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描
5. **模型无关性：** 支持 OpenAI、GLM、MiniMax 等主流模型及自定义端点，通过 `hermes model` 秒级切换
6. **多端交互：** 支持 CLI、Telegram、Discord、Slack 及语音交互
7. **Cron 计划任务：** 内置完整定时系统，支持自然语言设定任务
8. **身份全局化：** `SOUL.md` 位于全局目录，跨设备保持核心人格一致

## 与相关实体的关系

- [[nous-research]] — 开发者
- [[openclaw]] — 同赛道竞争对手，可无缝迁移
- [[evomap]] — 涉及架构抄袭争议的中国团队
- [[qwen-3-6]] — 可作为 Hermes Agent 的底层推理引擎
- [[llama-cpp]] — 可用于本地部署 Hermes Agent 时的推理加速

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
- [[基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指]]
