---
title: Hermes Agent
type: entity
tags: [ai-agent, open-source, nous-research, skills, execution-loop]
summary: Nous Research 开发的去中心化、自进化 AI 智能体框架，核心创新为程序化知识生成与分层记忆体系
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比及技术趋势简报.md
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

## 基本定位

由 Nous Research 开发的新一代去中心化 AI 智能体框架。与 OpenClaw 的中心化网关架构不同，Hermes Agent 以 AI Agent 自身的执行循环为同步编排引擎，强调智能体的自我提升与长期成长。

## 核心特征

1. **去中心化执行循环**：颠覆网关核心论，AI Agent 执行循环定义为同步编排引擎，天然支持闭环学习
2. **程序化知识生成**：将完成的工作流抽象为"技能"，存储在 `~/.hermes/skills/` 目录下，跨会话持续学习
3. **四层分层记忆体系**：核心持久层（MEMORY/USER.md）、会话历史层（SQLite+FTS5）、扩展长期层（Honcho）、程序化记忆层（技能库）
4. **五层纵深防御**：用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描
5. **内置 Cron 系统**：自然语言设定定时任务，60 秒检查周期，隔离会话运行
6. **极端模型灵活度**：支持 OpenAI、OpenRouter、Kimi、GLM 等，切换仅需 CLI 命令
7. **多平台对接**：Telegram、Discord、CLI 等多平台支持
8. **无缝迁移**：自动检测 `~/.openclaw` 目录并转换记忆数据

## 关系网络

- 由 [[nous-research]] 开发
- 与 [[openclaw]] 形成直接竞争和对比
- 与 [[qwen-3-6]] 组合实现本地零成本 Agent 方案
- 使用 [[llama-cpp]] 作为推理引擎
- 与 [[evomap]] 存在架构抄袭争议
- 核心架构为[[去中心化执行循环]]
- 记忆系统为[[分层记忆体系]]

## 出现的视频来源

- [[Hermes Agent 与 OpenClaw 深度对比及技术趋势简报]]
- [[Hermes + Qwen-3.6 本地最强 Agent 组合部署与应用简报]]

## 脑图关系节点

在对比分析脑图中，Hermes Agent 出现于"架构逻辑差异"（执行循环驱动）、"关键能力特性"（程序化知识生成、分层记忆体系、部署兼容性）、"自动化与安全性"等一级节点下。
