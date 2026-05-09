---
title: Hermes Agent
type: entity
tags: [ai-agent, nous-research, open-source, agent-framework]
summary: Nous Research 开发的下一代自托管 AI Agent，以执行循环驱动架构、分层记忆体系和自动程序性知识生成为核心特征。
sources:
  - wiki/sources/Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报.md
  - wiki/sources/Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报.md
  - wiki/sources/Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Hermes Agent 是 Nous Research 开发的新一代自托管 AI Agent，代表了从"指令执行"向"自我进化"的范式转变。其核心创新在于以 AI Agent 自身的执行循环为编排引擎，通过闭环反馈持续优化决策逻辑，并自动将执行经验转化为可复用的技能。

## 核心特征

- **执行循环驱动架构**：颠覆传统网关核心论，将 AI Agent 执行循环作为同步编排引擎
- **四层分层记忆体系**：核心持久记忆（~1300 tokens）+ 会话历史记忆（SQLite FTS5）+ Honcho 扩展 + 程序性记忆
- **程序性知识生成**：自动将执行轨迹转化为可调用的 Skill（技能），实现"记住方法"而非"记住事实"
- **五层纵深防御模型**：基础层、隔离层、过滤层、扫描层、网络层
- **全局身份锚定**：SOUL.md 位于全局目录，核心身份不随环境切换改变
- **模型无关性**：支持通过 `hermes model` 命令快速切换多种模型提供商
- **OpenClaw 迁移工具**：内置自动检测和转换工具
- **Cron 计划任务系统**：每 60 秒检查一次，可自动生成日报并推送

## 关系网络

- 开发方：[[Nous Research]]
- 主要对比：[[OpenClaw]]（中心化网关模式）
- 争议关联：[[EvoMap]]（被指抄袭）
- 常用组合：[[Qwen]]（本地部署伙伴）、[[Llama-cpp]]（推理引擎）
- 相关概念：[[执行循环驱动架构]]、[[分层记忆体系]]、[[程序性记忆]]、[[五层纵深防御模型]]
- 视频来源：[[Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报]]
