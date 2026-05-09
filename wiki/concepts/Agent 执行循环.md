---
title: "Agent 执行循环"
type: concept
tags: [agent-architecture, execution-loop, orchestration, self-evolution]
summary: "Hermes Agent 的核心编排机制，以 AI Agent 自身的执行→学习→改进闭环驱动整个系统，取代传统的中心化网关架构。"
sources:
  - raw/notebooklm-analysis/NbldZVdusKo-Hermes-Agent-与-OpenClaw-下一代自我进化智能体深度剖析简报.md
  - raw/notebooklm-analysis/NbldZVdusKo-智能体架构变革-Hermes-Agent-与-OpenClaw-深度对比及技术解析简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-Hermes-Qwen3-6-本地最强-Agent-组合部署简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-本地-AI-Agent-部署简报-Hermes-与-Qwen-3-6-组合方案.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 综合 NbldZVdusKo 和 Kh8tGD5liwo 两个视频的分析，Agent 执行循环是 Hermes Agent 区别于传统 Agent 框架的核心特征
---

## 定义

Agent 执行循环（Execution Loop）是 Hermes Agent 的核心编排机制。不同于传统 Agent 框架采用的中心化控制器（如 OpenClaw 的 Gateway），Hermes Agent 以智能体自身的执行→学习→改进闭环来驱动整个系统。所有模块（网关、调度器、协议等）围绕这个执行循环集成，使每次执行都能反向优化决策逻辑。

## 在本库的具体例子

- **架构对比**：OpenClaw 采用 Gateway 中心化架构统一分发与管控，而 Hermes Agent 则通过执行循环实现自我进化（参见 [[Hermes Agent 与 OpenClaw 智能体架构深度对比]]）
- **Agent 部署**：在本地部署中，执行循环确保 Agent 能持续学习和优化任务执行，即使使用 Qwen 3.6 模型也能获得良好效果（参见 [[Hermes + Qwen3.6 本地最强 Agent 组合部署]]）

## 关联概念

- [[程序化知识]]：执行循环的输出产物——自动生成可复用技能
- [[分层记忆体系]]：执行循环需要依赖四层记忆系统提供上下文

## 关联实体

- [[Hermes Agent]]：执行循环是该框架的核心设计哲学
- [[OpenClaw]]：采用与执行循环相反的中心化 Gateway 架构
