---
title: Hermes Agent
type: entity
tags: [nous-research, ai-agent, open-source, local-ai]
summary: Nous Research 开发的开源自托管智能体，以执行循环驱动架构和程序化知识生成能力著称。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md, raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

## 基本定位

Hermes Agent 是由 Nous Research 开发的开源自托管智能体，核心设计理念是将 AI 自身的执行循环定义为同步编排引擎，实现自我进化与知识生成。与传统的中心化控制架构不同，Hermes Agent 通过程序化知识生成、分层记忆体系和自动化能力，使智能体从“记住事实”升级为“记住方法”，成为具备持续学习能力的数字化基础设施。

## 核心特征/能力

1. **执行循环驱动架构**：将 Agent 自身的循环作为同步编排引擎，网关、调度器等模块围绕其集成，天然支持自我进化，每一次执行都能优化决策逻辑。
2. **程序化知识生成**：自动将执行经验转化为可复用的技能文件，存储于 `~/.hermes/skills/` 目录下，通过 `skill_manage` 工具管理，实现跨会话持续学习。
3. **分层记忆体系**：包含四层记忆：核心持久记忆（MEMORY.md/USER.md，约 1300 token）、会话历史数据库（SQLite FTS5 全文索引）、长期用户画像（Honcho 扩展）、程序性记忆（自动技能）。
4. **内置 Cron 计划任务**：支持自然语言设定定时任务，系统每 60 秒检查一次条件，在隔离会话中运行，结果可推送到多端平台。
5. **五层纵深防御安全模型**：包括用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描，辅以 SSRF 防护和网站黑名单，适合暴露在互联网环境。
6. **模型无关性**：通过 `hermes model` 命令可切换 OpenAI、OpenRouter 及国产大模型，无需修改核心代码。
7. **多平台集成**：支持 Telegram、Discord、Slack 等消息平台，以及语音交互。
8. **广泛部署兼容**：支持终端、VPS、Docker、SSH 及 Serverless 架构，提供从 OpenClaw 的迁移工具。

## 应用场景

1. **个人数字助理**：作为每日简报机器人，定时检索信息、备份数据、生成日报并推送到 Telegram 或 Discord。
2. **工程运维助手**：借助 MCP 协议自动分诊 GitHub Issue，进行代码审查，或作为 CLI 编程助手辅助调试。
3. **企业知识管理**：连接内部 API 和数据库，抓取财务票据或客户数据，辅助新员工阅读材料并提供问答支持。

## 关系网络

- [[openclaw]] — 竞争关系（同赛道自托管智能体，架构理念对立）
- [[nous-research]] — 开发者关系
- [[qwen3-6]] — 兼容/依赖关系（可作为后端模型）
- [[llama-cpp]] — 兼容关系（可作为推理引擎）
- [[telegram-bot]] — 集成关系（作为消息平台）

## 关键事件/里程碑

- **2026 年**：发布并引发关注，与 OpenClaw 形成对比。
- **近期**：卷入涉嫌抄袭中国开源项目 EvoMap 的风波，团队予以否认。

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比简报]]
- [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报]]
