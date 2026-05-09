---
title: Token 优化
type: concept
tags: [token, 成本控制, hermes-agent]
summary: Token 优化是通过主副模型配置、辅助任务分配等技术手段，降低 AI Agent 运行过程中 Token 消耗的策略集合。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Token 优化

## 定义
Token 优化是一系列降低 AI Agent 运行过程中 Token 消耗的策略集合。在 [[hermes-agent]] 中，核心优化策略是 [[主副模型配置]]，通过将任务细分，由昂贵的主模型处理复杂逻辑，由廉价的副模型处理简单任务，从而大幅降低 Token 消耗。

## 在本库的具体例子

- 在 [[hermes-agent-高级玩法与优化指南-深度简报]] 中，视频详细介绍了 Token 优化的核心思路和具体配置方法。
- 推荐方案：使用 Google [[gemini-2.0-flash]] 作为副模型，处理审批、压缩、MCP 调用等 [[辅助任务]]，能大幅延长相同 Token 配额的使用时长。
- 具体配置：进入配置文件，定位到辅助任务（Auxiliary Tasks）部分，将相关任务的模型 ID 修改为 `gemini-2.0-flash`。

## 技术实现细节

1. **主副模型分离**: 主模型处理复杂任务，副模型处理辅助任务。
2. **辅助任务细分**: 包括审批、压缩、记忆刷新、MCP 调用、会话搜索、技能检索、网页/视觉相关任务。
3. **推荐副模型**: Google Gemini 2.0 Flash 被推荐为处理辅助任务的副模型。

## 与近似概念的边界

- **模型蒸馏**: 模型蒸馏是通过训练小模型模仿大模型的行为，而 Token 优化是运行时动态分配任务。
- **缓存机制**: 缓存机制通过存储重复计算结果减少 Token 消耗，而 Token 优化通过任务分配降低消耗。

## 关联概念

- [[主副模型配置]] — Token 优化的核心策略。
- [[辅助任务]] — Token 优化中由副模型处理的具体任务类型。

## 关联实体

- [[hermes-agent]] — 实现 Token 优化的 AI Agent 框架。
- [[gemini-2.0-flash]] — 推荐的 Token 优化副模型。