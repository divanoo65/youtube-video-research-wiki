---
title: Token Efficiency 组合
type: concept
tags: [token-efficiency, model-selection, cost, performanc]
summary: 在蜂群架构中按任务难度混合使用不同大小模型（如Claude Code、Codex或小型模型）的策略，以在保证结果质量的同时降低总Token消耗。
sources: [raw/notebooklm-analysis/Anthropic-Managed-Agents-架构深度解析与多Agent协作.md]
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: medium
reasoning: 报告提到“利用大小模型组合提升Token效率”，结合蜂群场景归纳得出。
run_id: T-4kgkYAGPuD0
---

# Token Efficiency 组合

## 定义
Token Efficiency 组合（Token Efficiency 策略）是蜂群架构中一种资源优化方法。核心思想是根据每个子任务的复杂度和重要性，为不同的 Agent 分配不同规模和能力的语言模型。简单任务（如格式检查）使用小型模型以节省 Token，复杂任务（如代码重构）使用大型模型（如 [[Claude-Code]]]）。通过在整体任务图中合理搭配，达到最佳的 Token 效率，即在保持最终输出质量的前提下最小化总 Token 消耗。

## 在本库的具体例子
- 在 [[Anthropic公司]] 描述的蜂群复刻方案中，“大小模型组合 (Token Efficiency)”是核心推荐策略之一，与“Docker 容器化 Worker”和“预定义任务图”并列。
- 描述场景：一个具有 20 个子 Agent 的蜂群中，可能有 5 个子 Agent 使用 Claude Code（大型），10 个子 Agent 使用 Codex（小型），5 个子 Agent 使用更小的专用模型。
- 报告原文：“这种组合能实现最佳的 Token Efficiency，在保证结果质量的同时降低成本。”

## 技术实现细节
- **任务分类器**：Coordinator 组件中嵌入一个负责分类任务难度的前置模块（可能是一个小型模型或规则引擎），决定应该将任务分配给哪种规模的 Agent。
- **模型切换路由**：Coordinator 根据分类结果，将任务派发给不同模型终端，这些终端可以是同一 API 的不同模型端点。
- **成本监控**：在任务执行过程中收集 Token 消耗数据，优化后续的模型分配策略。

## 与近似概念的边界
- **模型蒸馏**：模型蒸馏是训练一个小模型来模拟大模型，Token Efficiency 组合是运行时选择不同模型，不涉及训练。
- **MoE（混合专家）**：MoE 在模型内部混合专家，Token Efficiency 组合在系统层面混合外部模型。

## 关联概念
- [[任务图（Task-Graph）]] — 任务图节点是分配模型的基本单位。
- [[编排者（Coordinator）]] — Coordinator 负责根据 Token Efficiency 策略选择模型。

## 关联实体
- [[Claude-Code]]] — 可作为大型模型候选。
- [[Anthropic公司]] — 在架构中提倡该策略。
