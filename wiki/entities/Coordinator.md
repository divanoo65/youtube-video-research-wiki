---
title: Coordinator
type: entity
tags: [agent-architecture, orchestration, managed-agents]
sources:
  - "9bc028e2-6acb-4d01-b223-8cc7a1826da8"
  - "https://youtu.be/4kgkYAGPuD0"
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Coordinator

Coordinator（编排器/协调者）是 [[Managed Agents]] 架构中的第四层核心组件，定位为“不干活的指挥官”。它的核心职责是**任务拆解与调度**：将顶层用户请求分解为可执行的子任务，然后将这些子任务分发给多个 Worker Agent，并管理整个长程协作过程中的上下文状态与通信效率。

在 Anthropic 的四层解耦模型中，Coordinator 位于最上层，直接与 [[Session]] 层和 [[Agent沙盒]] 层交互。它本身不直接执行任何具体工作（如代码编写、测试、搜索），而是专注于**任务图（Task Graph）的构建与驱动**。例如，当用户要求“开发一个带用户登录的 Web 应用”时，Coordinator 会将其拆解为：需求分析 → 前端设计 → 后端 API 开发 → 集成测试 → 部署。每个阶段可以派发给最多 20 个独立的 Worker Agent 并发执行。

### 技术细节与关键机制

1. **上下文压缩与记忆管理**  
   长程任务中，Agent 之间的对话历史会不断膨胀。Coordinator 负责在每次任务交接时对上下文进行压缩，只保留对后续任务有影响的关键信息（如决策理由、接口约定），丢弃冗余的中间输出。这解决了传统多 Agent 系统中“上下文丢失”和“记忆混淆”的痛点。报告中提到，Coordinator 可以管理“长程任务中的上下文压缩问题”，确保 Worker Agent 不会因历史过长而降低推理质量。

2. **并发调度与 Token 效率优化**  
   Coordinator 根据子任务的性质动态选择不同规模的模型。例如，对于并发搜索、数据采集等 I/O 密集任务，调度轻量级模型（如 Claude Haiku）；对于逻辑推理、代码审查、报告编写等需要强推理的任务，则调度重量级模型（如 Claude Sonnet/Opus）。这种“大小模型混编”策略显著降低了总 Token 消耗，同时不牺牲关键环节的质量。

3. **失败恢复与动态伸缩**  
   基于“牛马模式”理念，Coordinator 对 Worker Agent 采用无状态管理。一旦某个沙盒中的 Agent 因代码崩溃或配置冲突而失败，Coordinator 直接销毁该沙盒，并重新拉起一个干净的新沙盒，将已保存的上下文（来自 [[Session Store]]）注入后继续执行。这使得整个蜂群在遇到单点故障时无需人工介入即可自愈。

4. **任务图驱动**  
   主控服务器（Coordinator）通过预定义的规则或动态决策生成 DAG（有向无环图）来组织任务依赖。例如，编码节点完成后才能触发 Review 节点，Review 通过后才能触发测试节点。Coordinator 会持续监控各节点的进度，并在必要时插入“人类审批”节点。

### 实际场景示例

假设一个金融报告生成任务：用户提出“生成上季度的投行业务分析报告”。Coordinator 立即拆解为：
- 数据收集（派发 5 个小模型并发爬取不同数据库）
- 数据清洗与汇总（派发 1 个中型模型）
- 趋势分析与图表生成（派发 1 个强模型）
- 报告撰写（派发 1 个强模型）
- 合规审查（暂停，等待人类审批）

整个过程 Coordinator 维护一张全局状态表，记录每个子任务的完成状态、输出摘要、以及需要传递给下游的接口契约。当数据收集中的一个沙盒超时时，Coordinator 自动将其标记为失败并重试，同时通知下游暂缓依赖该子任务的节点。

### 与纯 Agent 自协调的区别

早期多 Agent 架构常采用 Agent 之间直接通信（如通过消息队列互相调用），这在任务规模增大后极易导致通信爆炸、上下文混乱和循环依赖。Coordinator 作为中心化的“大脑”，将所有调度逻辑收敛到单一组件中，保持了系统的可观测性和可控性。Anthropic 在其 Managed Agents SDK 中将此模式固化为 beta 模块，并隐含地建议：**“底层的多大脑、多双手的复杂并发，实在太难了……直接来买我们做好的云端 Agent 服务吧。”** 这背后折射出 Coordinator 层的高复杂度正是未来云端 Agent 操作系统的核心竞争壁垒。

### 相关实体

- [[Agent沙盒]]：Coordinator 调度的执行环境，每个沙盒是无状态的独立容器。
- [[Session]]：Separated runtime instance managed by Coordinator，一个 Agent 模板可对应多个 Session。
- [[Session Store]]：提供上下文的 Fork、回滚、克隆功能，Coordinator 依赖它实现状态恢复。

### 总结

Coordinator 是 [[Managed Agents]] 架构从“宠物模式”转向“牛马模式”的关键使能者。它通过任务拆解、并发调度、上下文压缩和失败自愈，使得企业级 Agent 蜂群能够稳定、高效地处理复杂长程任务。随着未来 Agent 使用场景从固定服务向动态蜂群演化，Coordinator 的设计将直接影响系统的可伸缩性和鲁棒性。