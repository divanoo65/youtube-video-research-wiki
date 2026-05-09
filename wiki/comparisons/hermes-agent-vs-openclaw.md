---
title: Hermes Agent vs OpenClaw
type: comparison
tags: [ai-agent, comparison, architecture]
summary: 从架构哲学、知识生成、记忆体系、安全模型和适用场景深度对比两款自托管智能体框架。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 对比维度表格

| 维度 | Hermes Agent | OpenClaw |
| :--- | :--- | :--- |
| **控制中枢** | 执行循环（Execution Loop）同步编排 | Gateway 网关中心化设计 |
| **技能生成** | 自动生成（程序化知识），基于执行经验 | 人工编写（插件/工作流指令） |
| **记忆体系** | 四层分层记忆（核心持久+会话+用户画像+程序性） | Markdown 文件存储 |
| **安全模型** | 五层纵深防御（授权、审批、容器隔离、MCP过滤、扫描） | 依赖用户运维配置 |
| **定时任务** | 内置 Cron，支持自然语言设定 | 无内置，需外部工具 |
| **跨平台** | 不支持原生 Windows（需 WSL2） | 支持多种环境（本地、VPS、Docker） |
| **模型兼容** | 模型无关（支持 OpenAI、Nous Portal 等） | 模型无关 |
| **自我进化** | 支持（自动生成技能、优化记忆） | 不支持 |
| **抄袭争议** | 涉嫌抄袭 EvoMap | 无 |
| **迁移路径** | 提供从 OpenClaw 一键迁移工具 | 无 |

## 核心差异分析

Hermes Agent 的最大创新在于**从被动执行向主动进化的范式转换**。它通过执行循环将 AI 的每次使用都变成一次学习机会，而 OpenClaw 更强调稳定性和可预测性。在知识生成方面，Hermes 的自动技能生成大幅降低了人工维护成本，但牺牲了一定的精确控制。安全方面，Hermes 的纵深防御使其适合暴露在公网环境，而 OpenClaw 更依赖用户的物理隔离。

## 适用场景结论

- **选择 Hermes Agent**：当需要长期自主运行的智能体、支持跨平台交互（Telegram/Discord）、允许系统自我进化时。特别适合个人每日简报机器人、GitHub 分诊、研究数据生成等场景。
- **选择 OpenClaw**：当流程必须高度可控、行为可预测、架构透明且用户喜欢直接编辑 Markdown 文件时。适合企业级固定流程、教学演示、保密环境。

> 注意：Hermes Agent 的抄袭争议可能影响其长期可信度，部署前请评估风险。

## 关联实体

- [[hermes-agent]]
- [[openclaw]]
