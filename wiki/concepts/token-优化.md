---
title: token-优化
type: concept
tags: [token, optimization]
summary: Token 优化是通过主副模型配置、辅助任务分配等技术手段，降低 AI Agent 运行过程中 Token 消耗的策略集合。
sources: [wiki/sources/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Token 优化

## 定义

Token 优化是通过主副模型配置、辅助任务分配等技术手段，降低 AI Agent 运行过程中 Token 消耗的策略集合。

## 在本库的具体例子

在 [[hermes-agent]] 中，程序化知识存储在 ~/.hermes/skills/ 目录下，通过 skill_manage 工具管理，通过主副模型配置降低 Token 消耗。

## 技术实现细节

1. **主副模型分离**：将任务细分，由昂贵的主模型处理复杂逻辑，由廉价的副模型处理简单任务。
2. **辅助任务分配**：将审批、压缩、MCP 调用、会话搜索、技能检索、网页/视觉相关任务等分配给副模型。

## 与近似概念的边界

- **Token 消耗**：Token 优化是降低 Token 消耗的方法，而 Token 消耗是 AI Agent 运行过程中的自然现象。
- **成本控制**：Token 优化是成本控制的一种手段，但成本控制还包括其他方面，如硬件资源的使用。

## 关联概念

[[主副模型配置]] [[云端免费模型]]

## 关联实体

[[hermes-agent]]