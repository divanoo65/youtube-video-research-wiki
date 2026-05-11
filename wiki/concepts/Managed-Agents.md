---
title: Managed-Agents
type: concept
tags: [agent-architecture, multi-agent, anthropic, swarm-architecture, decoupling]
sources:
  - 6733c4ed-cdb0-420d-9a4a-a920fd1e7f03
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Managed-Agents

**Managed-Agents**（托管Agent架构）是 Anthropic 提出的一种多 Agent 协作架构范式，核心思想是通过将“大脑”（模型决策）与“双手”（代码执行环境）彻底解耦，实现 Agent 的**无状态化**和**可规模化**。该架构被视为从“个人工具”向“企业基础设施”演进的关键技术路径。

## 核心原理

传统 Agent 开发常将模型逻辑、上下文记忆与本地环境深度绑定，导致系统在长程任务中容易因环境配置错误或记忆冗余而崩溃。Managed-Agents 通过四层解耦解决了这一问题：

1.  **脑手解耦**：模型决策（大脑）与代码执行沙盒（双手）分离。每个执行任务在独立的沙盒（如 Docker 或高性能沙盒 Cube Sandbox）中运行，出错时直接销毁并重建，确保系统稳健性。
2.  **Session 与 Agent 实体分离**：
    - **Agent**：静态模板，定义身份、工具、模型及系统提示词，不存储动态数据。
    - **Session**：动态执行单元，承载对话线程、记忆挂载和文件操作。同一 Agent 模板可同时启动多个独立 Session。
3.  **编排者（Coordinator）模式**：引入“不干活的指挥官”角色，负责拆解复杂任务并派发给下属 Agent。一个编排者可管理多达 20 个拥有独立 Prompt 和 MCP 服务器的 Agent，解决单一 Agent 在长程任务中上下文不足的问题。
4.  **上下文解耦（Session Store）**：将上下文从本地迁移至云端（如 Redis 缓存），实现 Agent 彻底无状态化。Session 可作为“记忆树”进行 Fork、回滚、克隆或恢复，编排者可随时掌握 Agent 的最优状态。

## 关键特性

- **无状态化**：Agent 被视为“牛马”而非“宠物”，可随时销毁并重建，故障隔离能力强。
- **多模型组合**：通过任务图（Task Graph）预定义规则，实现大小模型异构组合，优化 Token 效率。
- **动态资源分配**：从固定服务转向动态容器，云端计算资源根据需求瞬间创建并销毁 Agent 容器，形成“蜂群”效应。

## 实践意义

Managed-Agents 架构预示了 Agent 从“个人工具”向“企业基础设施”的演进趋势。开发者应停止编写针对特定模型的修复补丁，转而构建基于沙盒环境的解耦架构。企业应将 Agent 视为基础设施，探索部署 Managed Agents 以处理长程、复杂的业务流程。

## 相关概念

- [[Swarm-Architecture]]：多 Agent 协作的蜂群架构范式。
- [[Session-Store]]：云端上下文存储，实现 Agent 无状态化的关键技术。
- [[Coordinator-Pattern]]：编排者模式，负责任务拆解与派发。
- [[Brain-Hand-Decoupling]]：脑手解耦，模型决策与执行环境分离的核心原则。