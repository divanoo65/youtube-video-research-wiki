---
title: Coordinator模式
type: concept
tags: [agent架构, 多Agent协作, 编排模式, 蜂群思维, Anthropic]
summary: 不干活的指挥官角色，负责拆解任务与调度Agent
sources:
  - 6733c4ed-cdb0-420d-9a4a-a920fd1e7f03
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Coordinator模式

**Coordinator模式**（编排者模式）是Anthropic在Managed Agents架构中提出的一种核心协作模式，其本质是一个**“不干活的指挥官”**角色。该模式通过将决策层与执行层彻底解耦，解决了单一Agent在长程任务中因上下文膨胀、记忆污染而导致的性能退化问题。

## 核心机制

在Managed Agents架构中，Coordinator被定义为一种特殊的Agent角色，其职责**不包含具体执行**，而是专注于：

1. **任务拆解**：将复杂、长程的任务分解为多个可独立执行的子任务。
2. **指令派发**：根据子任务特性，将指令分发给拥有独立System Prompt和MCP（Model Context Protocol）服务器的下属Agent。
3. **结果聚合**：收集各Agent的执行结果，进行整合与冲突消解。

根据Anthropic SDK的实践，一个Coordinator名下可管理**多达20个**拥有独立上下文和工具集的Agent。这种设计使得每个执行Agent的上下文保持清晰、精简，避免了传统单一Agent在长程任务中“不断压缩记忆导致变笨”的痛点。

## 与Session的协同

Coordinator模式与[[Session管理]]机制紧密配合。Coordinator本身不存储动态数据，仅作为静态配置模板（Agent），而每个下属Agent的执行状态由独立的Session承载。这种设计实现了：

- **无状态化**：每个执行Agent的Session可随时销毁并重建，实现故障隔离。
- **上下文解耦**：通过[[Session Store]]将上下文存储在云端（如Redis），Coordinator可以随时“Fork”或“回滚”某个Agent的最优状态，用于应对特定任务。

## 典型应用场景

在[[蜂群思维]]架构中，Coordinator模式常用于以下场景：

- **编码流水线**：一个Coordinator调度“编码Agent”、“审核Agent”、“测试Agent”协作完成软件开发任务。
- **多模态处理**：Coordinator将任务拆解为“搜索”、“写作”、“图表生成”等子任务，分别派发给擅长对应领域的Agent。
- **成本优化**：通过Coordinator实现大小模型异构组合，在简单任务阶段调用低成本模型，复杂阶段调用高性能模型，实现[[Token效率]]最大化。

## 技术启示

Coordinator模式标志着Agent架构从“个人工具”向“企业基础设施”的演进。开发者应放弃编写针对特定模型的修复补丁，转而构建基于Coordinator的解耦架构，关注高性能沙盒技术与云端上下文存储方案，为大规模Agent并发做好准备。