---
title: Claude
type: entity
tags:
  - AI模型
  - 多Agent
  - 任务拆分
  - 会话与代理分离
  - 脑手解耦
summary: Claude 是 Anthropic 开发的大语言模型，在 Anthropic Managed Agents 架构中扮演协调者与执行核心的角色，通过任务拆分、模型组合优化和会话/代理分离实现高效的 Agent 协作与长程任务管理。
sources:
  - "raw/notebooklm-analysis/anthropic-managed-agents-deep-dive.md"
created: 2025-04-08
updated: 2025-04-08
layer: L1
confidence: high
reasoning: 基于 Anthropic 官方博客及深度分析报告，Claude 作为多 Agent 系统的核心模型，其架构设计与“脑手解耦”理念被多次提及，信息可靠且具有高置信度。

---

## 实体描述

Claude 是 Anthropic 推出的大语言模型系列，在 Agent 架构设计中扮演核心角色。Anthropic 在其官方博客及 SDK 设计中明确将 Claude 定位为“大脑”——负责任务理解、决策、指令生成的中央调度节点，而执行层则交由独立的、无状态的子 Agent 或沙盒环境完成。这种设计源自对传统单 Agent 长程任务中上下文压缩导致记忆丢失的反思：单一 Agent 在不断增长的上下文窗口中会逐渐丢失早期信息，而通过将任务拆分并派发给多个独立的 Claude 实例（或不同规模的模型），每个子 Agent 从全新的上下文开始工作，从而有效解决认知瓶颈。

Claude 的另一个关键特性是**模型组合优化（Token Efficiency）**。根据任务分工，协调者可以混合使用大模型（如 Claude 4）与小模型（如 Claude Code、Codex 等），在保证推理质量的同时最大化 Token 利用率。这种“把 Agent 当牛马去用”的理念，体现在底层执行单元被设计为完全无状态的独立沙盒（如 Cube Sandbox），支持毫秒级创建与销毁，确保基础设施的健壮性与可扩展性。

在 Anthropic 的 SDK 中，Claude 被进一步抽象为“Agent”实体，与“Session”严格分离：Agent 负责“我是谁”（身份、能力、工具绑定），Session 负责“我在干什么”（运行时状态、对话历史）。这种分离使得同一个 Claude Agent 可以同时服务于多个会话，且记忆存储由外部系统独立管理，实现了状态管理的彻底解耦。

## 在本视频中的角色

本实体出现在《Anthropic Managed Agents 架构与多 Agent 协作演进深度简报》中，作为 Anthropic 多 Agent 系统的核心模型。在该简报中，Claude 既是协调者模式的默认大脑，也是底层执行 Agent 的主力模型。其“脑手解耦”设计被用来解释为何本地运行的多 Agent（如“小龙虾”项目）容易失败——缺乏对执行单元的彻底隔离和随时重置的能力。Claude 扮演了从决策到执行的全链路枢纽，并与 [[OpenAI]] 和 [[Palantir]] 等厂商的 Agent 方案形成对比，凸显了 Anthropic 在将 Agent 从个人工具升级为企业基础设施方面的领先思路。

## 相关链接

- [[Anthropic Managed Agents 架构与多 Agent 协作演进深度简报]]
- [[脑手解耦]]