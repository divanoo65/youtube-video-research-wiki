---
title: Anthropic
type: entity
tags: [AI, 公司, Claude, 上下文工程, API缓存]
summary: Anthropic 是一家人工智能安全公司，开发了 Claude 系列模型。其 API 的缓存机制在 Claude Code 上下文工程架构中扮演关键角色，影响双轨决策与压缩策略。
sources: ["raw/notebooklm-analysis/claude-code-context-engineering-architecture-deep-analysis.md"]
created: 2025-03-28
updated: 2025-03-28
layer: L1
confidence: high
reasoning: 信息直接来源于关于 Claude Code 上下文工程架构的分析报告，描述了 Anthropic API 缓存对压缩决策的具体影响，属于高信度的一级陈述。
---

## 实体描述

Anthropic 是一家总部位于美国的 AI 安全公司，由前 OpenAI 员工 Dario Amodei 和 Daniela Amodei 于 2021 年创立。公司专注于构建可靠、可解释且符合人类价值观的 AI 系统，其核心产品为 Claude 系列大语言模型（包括 Claude 3.5 Sonnet、Claude 4 等）。Anthropic 以其在 AI 安全研究（如“宪法 AI”）和长上下文处理能力上的突破而闻名。Claude 模型支持高达 200K token 的上下文窗口，并提供了包括 Prompt 缓存在内的多项 API 优化功能，允许开发者对重复使用的系统提示或工具定义进行缓存，从而显著降低延迟和成本。这一特性使得 Anthropic 的 API 在外挂工具系统（如 Claude Code）中成为理想选择，但也因其缓存行为左右了上层压缩架构的设计。

## 在本视频中的角色

在关于 [[Claude Code 上下文工程架构深度解析简报]] 的视频分析中，Anthropic 被明确提及为核心的外部依赖与决策变量。视频详细阐述了“四层防御系统”中的[[微压缩]]策略（即第一层压缩），而该策略正是围绕 Anthropic API 缓存的有效性设计的。具体而言：

- **双轨决策机制** 以 Anthropic API 缓存是否失效为分水岭：当用户连续高频对话时，服务端缓存有效，系统（Catch Microcompact）通过 API 发送指令移除旧工具输出结果，但不触动原始 Prompt 前缀，从而保持 [[Anthropic]] API 缓存不失效，兼顾速度和成本。反之，若对话中断导致缓存过期，则切换离线路径（HB Microcomplex），在本地将冗长的工具输出替换为简短占位符。
- 系统还实现了 [[线程隔离]] 机制，基于 Query Source 的主线程隔离确保了后台子 Agent 在压缩过程中不会误删主线程的聊天历史，这一隔离的必要性同样源于对 Anthropic API 请求格式（成对消息、思考绑定）的依赖。

由此可见，Anthropic 不仅是底层模型提供商，其 API 缓存特性的存在与否直接决定了上下文压缩系统在微观层面上的响应路径与优化边界。