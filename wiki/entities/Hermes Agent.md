---
title: "Hermes Agent"
type: entity
tags: [ai-agent, framework, open-source, nous-research, agent-orchestration]
summary: "由 Nous Research 开发的开源 AI Agent 框架，采用执行循环架构，支持自我进化、程序化知识生成和四层记忆体系。"
sources:
  - raw/notebooklm-analysis/NbldZVdusKo-Hermes-Agent-与-OpenClaw-下一代自我进化智能体深度剖析简报.md
  - raw/notebooklm-analysis/NbldZVdusKo-智能体架构变革-Hermes-Agent-与-OpenClaw-深度对比及技术解析简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-Hermes-Qwen3-6-本地最强-Agent-组合部署简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-本地-AI-Agent-部署简报-Hermes-与-Qwen-3-6-组合方案.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 综合 Kh8tGD5liwo 和 NbldZVdusKo 两个视频的分析得出 Hermes Agent 的完整特征描述
---

## 基本定位

**Hermes Agent** 是一个由 **Nous Research** 开发的开源 AI Agent 框架，其核心设计哲学是从「被动执行工具」转向「自我进化基础设施」。不同于传统的 Agent 框架，Hermes 通过 Agent 执行循环（Execution Loop）实现能力复利增长，每次执行都能反向优化决策逻辑。

## 核心特征

- **执行循环架构**：以 AI Agent 自身的执行循环作为系统同步编排引擎，取代传统的中心化网关模式。
- **程序化知识生成**：能根据执行经验自动创建、优化技能（Skills），遵循 agentskills.io 开放标准。
- **四层结构化记忆**：核心持久记忆（~1300 tokens）+ SQLite 会话历史（FTS5 全文索引）+ Honcho 长期画像 + 程序性技能记忆。
- **模型无关性**：支持 OpenAI、OpenRouter、Kimi、MiniMax、GLM 及自定义本地模型端点，通过 `hermes model` 命令快速切换。
- **多平台接入**：支持 Telegram、Discord、Slack、WhatsApp、Signal 及 CLI。
- **内置 Cron 系统**：自然语言设定定时任务，60 秒检查条件，隔离会话运行。
- **五层纵深防御**：用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文扫描。
- **运行轨迹记录**：完整记录操作轨迹、提示词序列和动作决策，支持模型训练数据收集。

## 技术细节

- 部署依赖：Git + Python，Windows 需 WSL2
- 配置方式：通过 config.yaml 管理模型提供商、工具集、插件
- 技能管理：`skill_manage` 工具自主完成创建、优化与管理
- 记忆检索：session_search 基于 FTS5 实现跨会话精准检索
- 生态扩展：支持 Skills Hub 安装扩展

## 关系网络

- [[Nous Research]]：Hermes Agent 的创始研发团队
- [[OpenClaw]]：同赛道的传统自托管智能体，与 Hermes 形成架构对比
- [[EvoMap]]：中国开源项目，Hermes Agent 被指涉嫌借鉴其架构设计
- [[Qwen 3.6]]：与 Hermes Agent 组合部署的推荐模型
- [[Agent 执行循环]]：Hermes Agent 的核心架构机制
- [[程序化知识]]：Hermes Agent 的核心能力——自动生成可复用技能
- [[分层记忆体系]]：Hermes Agent 的四层记忆架构
- [[五层纵深防御模型]]：Hermes Agent 的安全防护体系

## 出现视频来源

- [[Hermes Agent 与 OpenClaw 智能体架构深度对比]]
- [[Hermes + Qwen3.6 本地最强 Agent 组合部署]]
