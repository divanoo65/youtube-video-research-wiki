---
title: 任务图（Task Graph）
type: concept
tags: [orchestration, task-decomposition, multi-agent, graph]
summary: 一种用有向无环图表示多Agent协作任务关系的编排模型，节点代表子任务，边代表依赖关系，辅助Coordinator进行任务调度。
sources: [raw/notebooklm-analysis/Anthropic-Managed-Agents-架构深度解析与多Agent协作.md]
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: medium
reasoning: 报告提到“通过主控服务器调度几十个Agent容器进行异步协作”，脑图中有“预定义任务图”节点，可归纳出此概念。
run_id: T-4kgkYAGPuD0
---

# 任务图（Task Graph）

## 定义
任务图（Task Graph）是一种用于描述多 Agent 协作任务分解与执行顺序的图模型。通常采用有向无环图（DAG），其中每个节点代表一个可独立执行的子任务（可由一个 Agent 完成），边表示子任务之间的依赖关系。Coordinator 根据任务图将各子任务分配给空闲的 Agent 执行，并在依赖满足后触发下游任务。

## 在本库的具体例子
- 在 [[Anthropic公司]] 的 Managed Agents 复刻方案中，“预定义任务图”是核心组件之一，与“Docker 容器化 Worker”和“大小模型组合”并列。
- 脑图节点“复刻与实践应用 → 预定义任务图”明确出现。
- 举例：软件开发场景中，任务图可定义为：`设计 → 编码 → 测试 → 审查 → 集成`，每个阶段由一个子 Agent 串行或并行执行。

## 技术实现细节
- **图引擎**：通常采用 DAG Runner（如 Airflow、Prefect 的底层）来解析图并安排工人。
- **动态扩展**：在 Agent 失败的节点上，Coordinator 可按照任务图逻辑重新调度到另一个干净的沙盒中执行。
- **状态追踪**：每个节点有运行状态（pending/running/success/failed），Coordinator 根据状态决定下一步动作。

## 与近似概念的边界
- **工作流（Workflow）**：工作流一般是线性的步骤序列，任务图允许并行和分支，更灵活。
- **CoT（思维链）**：CoT 是模型内部的推理步骤，任务图是系统层面由 Coordinator 编排的外部步骤。

## 关联概念
- [[编排者（Coordinator）]] — 任务图的调度执行者。
- [[四层解耦架构]] — 任务图属于控制平面，位于 Agent 层之上。
- [[Token-Efficiency-组合]] — 在任务图中，不同节点可以分配不同大小的模型。

## 关联实体
- [[Anthropic公司]] — 在设计文档中描述了该模型。
