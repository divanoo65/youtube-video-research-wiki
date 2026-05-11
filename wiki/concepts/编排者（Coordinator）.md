---
title: 编排者（Coordinator）
type: concept
tags: [orchestration, multi-agent, task-decomposition, coordinator]
summary: 在多Agent系统中专门负责任务拆解与分发的组件，不直接执行任务，可以管理多达20个子Agent，每个子Agent拥有独立的配置。
sources: [raw/notebooklm-analysis/Anthropic-Managed-Agents-架构深度解析与多Agent协作.md]
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: high
reasoning: 报告详细描述了Coordinator的职责和规模，是Managed Agents架构的核心创新。
run_id: T-4kgkYAGPuD0
---

# 编排者（Coordinator）

## 定义
编排者（Coordinator，亦称协调者/指挥官）是 Anthropic Managed Agents 架构中引入的一种专门角色。它不直接参与执行具体任务，而是负责将复杂任务拆解为多个子任务，然后分发给不同的子 Agent，并监控子 Agent 的执行状态，必要时进行调度或回滚。一个 Coordinator 可以管理多达 20 个子 Agent，每个子 Agent 拥有独立的 Prompt、工具和 MCP 服务器。

## 在本库的具体例子
- 在 [[Anthropic公司]] 的 Managed Agents 中，Coordinator 是顶层组件。例如在软件开发场景中，Coordinator 将“实现新功能”拆解为“设计模块”、“编写代码”、“编写测试”、“代码审查”、“集成测试”五个子任务，分别派发给不同的子 Agent。
- 脑图节点“第三层：Coordinator 编排者”明确显示了其位置，子节点包括“指挥官职责”、“任务拆分与分发”、“管理 Agent 蜂群”。
- 报告强调“Coordinator 可管理 20 个子 Agent”，这是一个具体数值。

## 技术实现细节
- **任务分解规则**：Coordinator 使用预定义的任务图（Task Graph）引导分解，或动态利用大模型理解任务并生成子步骤。
- **状态管理**：Coordinator 通过 Session 层的克隆/回滚能力，可以保存子 Agent 的最佳中间状态，在子任务失败时回滚重试。
- **通信协议**：Coordinator 与子 Agent 之间通过标准化的消息格式（如 JSON-RPC）交换指令和结果，底层可能通过 Redis Pub/Sub 或 gRPC。

## 与近似概念的边界
- **传统 Agent 中的主 Agent**：很多系统中一个 Agent 同时承担规划与执行，容易因上下文过长导致遗忘。Coordinator 将规划与执行分离，本身不执行代码，专注协调。
- **工作流引擎（如 Airflow）**：工作流引擎偏固定 DAG，Coordinator 更灵活，可基于大模型动态调整任务拆分。

## 关联概念
- [[任务图（Task-Graph）]] — Coordinator 使用的任务编排模型。
- [[四层解耦架构]] — Coordinator 属于组织层/控制平面，位于三层（Session）之上。
- [[脑手分离模式]] — Coordinator 是“大脑”的协调功能延伸。

## 关联实体
- [[Anthropic公司]] — 提出该角色。
- [[Claude-Code]], [[Cube-Sandbox]] — 可作为 Coordinator 调度的一个子 Agent 模型。
