---
title: Coordinator模式
type: concept
tags: [agent-architecture, multi-agent, task-decomposition, orchestration]
sources:
  - 4kgkYAGPuD0
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Coordinator模式

**Coordinator模式**（编排者模式）是[[Managed Agents]]架构中的核心设计模式，其核心思想是引入一个“不干活的指挥官”角色，专门负责**任务拆解**与**指令指派**，而将具体的执行工作交由下属Agent完成。该模式解决了单一Agent在长程任务中因上下文膨胀、记忆污染而导致的性能退化问题。

## 核心职责

在Anthropic的Managed Agents架构中，Coordinator被设计为一个**轻量级的决策节点**，其职责严格限定为：

1. **任务拆解**：将用户输入的复杂、多步骤任务，分解为若干个逻辑独立、边界清晰的子任务。
2. **Agent调度**：根据子任务的性质（如编码、审核、测试、搜索），将其分发给拥有专门Prompt和工具集的**下属Agent**。
3. **结果聚合**：收集各下属Agent的执行结果，进行校验、合并，并最终返回给用户。

Coordinator本身**不执行任何具体的业务逻辑**（如写代码、查数据库），从而保持其上下文的极度精简和决策的高效性。

## 架构优势

### 1. 解决上下文退化
传统单一Agent在处理长程任务时，随着对话轮次增加，上下文窗口被大量中间步骤填充，导致模型“变笨”，即[[上下文退化]]问题。Coordinator模式通过将任务分发给多个独立的Agent，每个Agent只处理自己专业领域内的短程任务，其上下文始终保持清晰、聚焦。

### 2. 故障隔离
下属Agent运行在独立的[[沙盒环境]]中。如果某个Agent在执行任务时发生错误或环境被污染，Coordinator可以直接销毁该Agent的Session并重新拉起一个干净的实例，而不会影响其他Agent的正常工作。这体现了“把Agent当牛马用，而不是当宠物养”的设计哲学。

### 3. 横向扩展
一个Coordinator可以管理多达**20个**拥有独立System Prompt和MCP（Model Context Protocol）服务器的下属Agent。这意味着系统可以通过增加下属Agent的数量来线性提升处理复杂任务的能力，而Coordinator本身保持轻量。

## 技术实现

在Anthropic SDK的实现中，Coordinator模式通过以下机制落地：

- **Agent模板**：每个下属Agent被定义为静态模板，包含身份、工具集、模型配置和系统提示词。它不存储动态数据。
- **Session管理**：Coordinator为每个子任务创建一个独立的Session。Session承载对话线程、记忆挂载和文件操作。同一个Agent模板可以被Coordinator多次实例化，互不干扰。
- **任务图（Task Graph）**：实践中，Coordinator常配合预定义的任务图使用。任务图定义了子任务之间的依赖关系和执行顺序，Coordinator根据任务图进行调度，实现多节点的异步并发执行。

## 应用场景

- **复杂软件开发**：Coordinator将需求拆解为“需求分析”、“架构设计”、“编码实现”、“单元测试”、“代码审查”等子任务，分别指派给对应的专业Agent。
- **多步骤研究**：Coordinator将研究问题拆解为“文献搜索”、“数据提取”、“交叉验证”、“报告生成”等步骤，由不同Agent并行执行。
- **企业业务流程自动化**：处理涉及多个系统（CRM、ERP、邮件系统）的跨部门流程，Coordinator负责协调各Agent调用不同API。

## 相关概念

- [[Managed Agents]]：Coordinator模式是其核心组件。
- [[脑手解耦]]：Coordinator代表“脑”，下属Agent代表“手”。
- [[Session Store]]：Coordinator通过云端上下文存储，可以随时获取或回滚下属Agent的最优状态。