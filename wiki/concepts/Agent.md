---
title: Agent
type: concept
tags: [agent, ai-engineering, system-design]
summary: 能够在环境中自主感知、决策并执行任务的 AI 系统实体，核心公式为 Agent = Model + Harness，是 AI 工程化的最终落地形态。
sources: [raw/notebooklm-analysis/Harness-Engineering-深度简报-构建稳定-可落地的-AI-Ag.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Agent

**定义**
Agent（智能体）是 AI 系统中能够自主感知环境、做出决策并执行任务的实体。在 Harness Engineering 框架下，Agent 的核心公式为 `Agent = Model + Harness`，即由模型提供智能推理能力，由 Harness（约束运行系统）确保执行过程的稳定性、可纠偏性和可落地性。

**在本库的具体例子**
- 在 [[Harness-Engineering-深度简报-构建稳定-可落地的-AI-Agent系统]] 中，Agent 被描述为需要带上「Checklist」的执行者：不仅要理解任务（Prompt），获取信息（Context），还需要持续的观测、纠偏和验收机制（Harness）。
- [[Hermes-Agent-高级玩法与部署优化简报]] 中的 [[Hermes-Agent]] 是 Agent 框架的具体实现，通过主副模型分离、Ollama 云端集成等策略优化 Agent 的部署成本和运行稳定性。

**技术实现细节**
1. **Harness 六层架构**：一个成熟的 Agent 系统包含信息边界层、工具系统层、执行编排层、记忆与状态层、评估与观测层、约束与恢复层，共同构成 Agent 的运行轨道。
2. **主副模型分离**：如 [[Hermes-Agent]] 的实现，主模型负责复杂推理，副模型负责批准、压缩、MCP 调用等辅助任务，大幅降低 Token 消耗。
3. **多 Agent 协作**：如 Anthropic 的 [[独立评估者模式]]，将 Agent 拆分为 Planner、Generator、Evaluator 三个角色，实现生产与验收分离。

**与近似概念的边界**
- **对比 [[约束工程]]**：Agent 是系统的最终实体，约束工程是构建 Agent 的外部运行系统的工程方法论。Agent 使用约束工程来确保稳定执行。
- **区别于大语言模型（LLM）**：LLM 只是 Agent 的「大脑」组件，Agent 还包括工具调用、状态管理、执行编排等模型外部的系统能力。模型提供推理，Agent 提供完整的任务执行能力。

**关联概念**
- [[约束工程]]
- [[上下文工程]]
- [[提示工程]]
- [[独立评估者模式]]
- [[主副模型策略]]

**关联实体**
- [[Anthropic]]
- [[OpenAI]]
- [[Hermes-Agent]]
