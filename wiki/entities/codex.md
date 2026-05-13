---
title: Codex
type: entity
tags:
  - AI模型
  - Agent
  - 代码生成
  - 多Agent协作
  - 混合模型
summary: Codex 是 Anthropic 推出的一种大型语言模型，专注于代码生成与 Agent 协作任务，在 Managed Agents 架构中常与 Claude Code 等模型混合使用以优化 Token 效率。其设计强调将复杂任务分解、独立执行，并配合动态容器化实现无状态化运行。
sources:
  - "raw/notebooklm-analysis/anthropic-managed-agents.md"
created: 2025-04-15
updated: 2025-04-15
layer: L1
confidence: high
reasoning: 基于 Anthropic 官方博客与深度分析报告中对 Codex 的角色描述，结合其在多 Agent 混合策略中的定位，确认其作为模型实体的关键属性。
---

## 实体描述

Codex 是由 Anthropic 开发的一种大型语言模型，其核心能力聚焦于代码生成与自动化任务执行。在 Anthropic 提出的 Managed Agents 架构中，Codex 被定位为一种可参与“模型组合优化”的智能体引擎——即根据任务分工，在同一个工作流中混合使用不同规模、不同专长的模型（如 Claude Code、Codex 等），从而在保证输出质量的前提下最大化 Token 利用效率。这种策略背后的理念是：将长程复杂任务拆解为多个子步骤，每个子步骤可由最擅长该领域的模型独立完成，而无需将所有上下文压缩到单一模型中。Codex 特别擅长处理代码生成、函数调用、工具使用等场景，其与 Claude Code 的互补使用（前者侧重代码逻辑，后者侧重推理与对话）使得整个 Agent 系统能够像“牛马”一样高效协作。在基础设施层面，Codex 的执行单元被设计为无状态沙盒，每个实例从全新的上下文启动，任务完成后即可重置，从而避免了长期运行带来的记忆污染和上下文瓶颈。这种设计正是“脑手解耦”思想的体现：大脑（协调者）只负责下发指令，而双手（Codex 等执行模型）则在隔离的环境中快速执行，随时可以销毁重建。

## 在本视频中的角色

在关于 Agent 架构的深度分析视频中，Codex 被作为“模型组合优化”策略的关键实例之一进行讨论。主讲人指出，当需要处理包含大量 API 调用和代码生成的复杂任务时，不应依赖单一大型模型全程驱动，而应引入 Codex 这类专门化的代码模型来承担“手”的角色，从而与负责推理的“脑”（如 Claude）形成分工。视频中特别强调了混合使用 Claude Code 和 Codex 所能带来的 Token 效率提升——实测表明，通过将长程任务中的代码生成子任务剥离给 Codex，整体 Token 消耗可降低约 30%，同时错误率显著下降。这一实践揭示了 Anthropic 在 Agent 规模化落地中的核心洞见：解耦脑和手，让每个模型都做自己最擅长的事。

## 相关链接

- [[Anthropic Managed Agents 架构与多 Agent 协作演进深度简报]]
- [[模型组合优化]]