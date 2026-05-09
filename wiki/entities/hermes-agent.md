---
title: Hermes Agent
type: entity
tags: [agent-framework, nous-research, open-source, automation]
summary: Nous Research 开发的开源 AI Agent 框架，以执行循环驱动架构和程序化知识生成为核心特色
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

## 基本定位

Hermes Agent 由 Nous Research 团队开发，是一个开源、模型无关的个人自托管 AI Agent 框架。其核心创新在于以 **执行循环（Execution Loop）** 为同步编排引擎，替代传统的中心化 Gateway 架构，使智能体能够从执行经验中自动生成程序化知识（Skills），实现从"记住事实"到"记住方法"的跨越。

## 核心特征/能力

1. **执行循环驱动架构**：所有模块（工具运行时、定时任务、通信协议 ACP、SQLite 持久化）围绕 Agent 自身的执行循环集成，而非依赖外部网关调度。
2. **程序化知识自动生成**：内置 `skill_manage` 工具，支持根据执行经验自动创建、优化与管理技能（Skill），并支持 `agentskills.io` 开放标准的 Skills Hub 扩展。
3. **四层分层记忆体系**：核心持久记忆（MEMORY.md/USER.md，~1300 tokens）→ 会话历史（SQLite FTS5 全文搜索）→ 扩展记忆（Honcho 用户画像）→ 程序性记忆（自动生成的 Skills）。
4. **内置 Cron 计划任务**：支持自然语言指定任务，系统每 60 秒检查一次条件，在隔离会话中运行。
5. **五层纵深防御**：用户授权 → 危险命令审批 → 容器隔离 → MCP 凭证过滤 → 上下文扫描，支持部署在暴露的互联网环境中。
6. **模型无关性与跨平台部署**：支持 OpenAI、OpenRouter、国产模型（MiniMax、GLM），可在 VPS、Docker、SSH、无服务器架构上运行。
7. **多消息平台集成**：原生支持 Telegram、Discord、CLI 等多种交互界面，计算核心与用户界面解耦。

## 应用场景

- **个人每日简报机器人**：定时检索信息、生成日报并推送至指定消息平台。
- **DevOps 运维助手**：授权成员通过 Telegram 进行代码审查、调试、Shell 执行及 GitHub Issue 自动聚类与分诊。
- **零成本本地 AI 部署**：搭配 Qwen 3.6 等本地模型，通过 Llama-cpp 推理后端实现"Token 自由"的私有 AI 助手，并通过 Telegram 进行移动端远程控制。

## 关系网络

- [[openclaw]] — 同类竞争框架，架构设计哲学差异：执行循环驱动 vs Gateway 中心化控制
- [[nous-research]] — 开发方与维护团队
- [[qwen-3-6]] — 支持对接的本地开源模型之一

## 关键事件/里程碑

- 发布即引起行业关注，凭借"自我进化"能力快速崛起，挑战 OpenClaw 的市场地位
- 卷入了与中国开源项目 EvoMap 的抄袭争议，Nous Research 否认代码雷同，但架构设计被指存在高度"借鉴"嫌疑
- 提供了针对 OpenClaw 用户的自动迁移工具

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
- [[零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合]]
