```markdown
---
title: Session Store
type: concept
tags: [session-store, managed-agents, context-management, anthropic, knowledge-graph, architecture]
sources:
  - video_id: 4kgkYAGPuD0
    source_id: 9bc028e2-6acb-4d01-b223-8cc7a1826da8
    report: 多Agent协作架构-Anthropic-Managed-Agents-深度解析
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Session Store

**Session Store** 是 [[Managed Agents]] 四层解耦架构中的**第三层组件**（上下文管理层），核心职责是将 Agent 的运行时上下文（记忆、状态、中间结果）从 Agent 实例中彻底剥离，作为外部持久化存储挂载。这一设计使得 Agent 本身变为**无状态**的“牛马”式计算单元，而所有会话相关的上下文信息则交由 Session Store 统一管理。

## 架构定位

在 Anthropic 提供的参考实现中，Agent 的生命周期被拆解为四个独立层次：

1. **Agent 沙盒 (Sandbox)** —— 执行环境容器化（[[Docker 或毫秒级沙盒]]）。
2. **Session (会话层)** —— 将 Agent 模板与每次执行实例分离，一个模板可创建多个独立 Session。
3. **Session Store (上下文管理)** —— 将记忆外部化，支持上下文的 **Fork（分支）**、**回滚**、**克隆**和**状态恢复**。
4. **Coordinator (编排器)** —— 负责任务拆解与 Agent 分配。

Session Store 位于 Session 之下，为每个 Session 提供独立的、可持久化、可版本化的上下文容器。

## 核心能力与技术细节

- **外部挂载**：Session Store 通常基于分布式缓存（如 [[Redis]]）或对象存储实现，Agent 在启动时从 Store 加载上下文，运行结束后将增量状态写回，之后可以随时销毁 Agent 实例而不丢失进度。
- **分支与回滚**：类似软件版本控制，Session Store 支持按时间点或标签创建上下文快照。当 Agent 在复杂推理过程中发生错误时，协调器可以指示 Agent **回滚到上一个健康快照**，而非从头开始。
- **克隆与并行探索**：支持从某个 Session 状态克隆出一个完全相同的上下文副本，交给不同 Agent 同时执行不同策略，最后比较结果。这在大规模搜索或 A/B 测试场景中极为有用。
- **状态恢复**：长程任务（例如持续数小时的代码审查）可能因资源耗尽或意外中断而终止。Session Store 允许新的 Agent 实例在中断点**无缝恢复**，避免了重复计算。

## 优势与意义

该组件直接解决了传统 Agent 项目中“记忆与执行强耦合”导致的脆弱性问题。参考报告指出：

> “记忆不再长在 Agent 身上，而是作为外部挂载。支持上下文的 Fork、回滚、克隆和状态恢复。”

这使得 Agent 从需要精心维护的“宠物”模式转变为可随时销毁重建的“牛马”模式。当某个沙盒因配置冲突崩溃时，只需销毁旧沙盒，从 Session Store 中读取最新上下文到新沙盒即可继续执行。系统的整体稳定性和可恢复性大幅提升。

## 实际应用示例

假设一个多 Agent 协作代码审查任务：
- **主控 Agent**（Coordinator）将代码库分为多个模块。
- **编码 Agent** 负责修改模块 A，其上下文（当前文件、修改历史、lint 规则）全部存储在 Session Store 中。
- **测试 Agent** 在克隆的 Session 上运行单元测试，生成结果后写回 Store。
- 若测试 Agent 崩溃，Coordinator 只需启动新 Agent，从 Store 加载崩溃前的上下文继续运行，整个过程对用户无感。

## 关联概念

- [[Agent 沙盒]]：提供执行隔离环境，与 Session Store 配合实现无状态。
- [[Session (会话层)]]：对应 Session Store 中每个独立的上下文实例。
- [[Coordinator (编排器)]]：依赖 Session Store 的分支与回滚能力进行容错调度。

## 参考

- 报告《多Agent协作架构：Anthropic Managed Agents 深度解析》第三层上下文管理部分。
- Anthropic SDK beta 模块中的 `sessions` 与 `memory_stores` 设计。
```