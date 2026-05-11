---
title: Session Store
type: concept
tags: [session-store, managed-agents, context-management, cloud-storage, agent-architecture]
summary: 云端上下文存储实现无状态Agent
sources:
  - 6733c4ed-cdb0-420d-9a4a-a920fd1e7f03
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

## 定义

**Session Store** 是 [[Managed Agents]] 架构中的核心基础设施组件，负责将 Agent 的运行时上下文（Context）从本地内存迁移至云端存储（如 Redis 缓存）。通过这一设计，Agent 的执行状态与计算环境彻底解耦，实现了 Agent 的完全无状态化——Agent 不再依赖本地持久化来维持记忆，而是随时可以从 Session Store 中恢复、分支或回滚其上下文状态。

## 核心功能

Session Store 在架构中承担以下关键职责：

### 1. 上下文云端化
传统 Agent 的上下文（对话历史、文件引用、工具调用结果）通常存储在本地进程内存中，一旦进程崩溃或环境被销毁，所有上下文随之丢失。Session Store 将上下文序列化后存储到云端，使得 Agent 可以在任意沙盒环境中重建其完整状态。

### 2. 记忆树操作
Session Store 支持将 Session 视为“记忆树”，提供以下高级操作：
- **Fork（分支）**：从当前上下文状态创建新的分支，用于并行探索不同解决方案。
- **回滚（Rollback）**：将 Agent 恢复到之前某个已知的“聪明状态”，避免因错误决策导致的上下文污染。
- **克隆（Clone）**：复制一个完整的上下文状态，用于多 Agent 并发执行相同任务。
- **恢复（Restore）**：在 Agent 沙盒被销毁后，从 Session Store 中恢复其上下文，实现无缝重启。

### 3. 编排者视角的状态管理
[[编排者（Coordinator）]] 通过 Session Store 可以实时监控所有下属 Agent 的上下文状态。当某个 Agent 在长程任务中“变笨”（因上下文压缩导致性能下降）时，编排者可以主动将其回滚到更早的、表现更好的状态，或者将另一个 Agent 的上下文分支过来继续执行。

## 技术实现细节

根据对 Anthropic SDK 及相关实践的逆向分析，Session Store 的实现通常基于以下技术栈：

- **存储后端**：Redis 或类似的高性能键值存储系统，支持毫秒级的读写延迟。
- **序列化格式**：将 Agent 的上下文（包括消息列表、工具调用记录、文件句柄等）序列化为 JSON 或 Protocol Buffers 格式。
- **版本控制**：每次上下文变更都会生成一个新的版本号，支持时间点恢复。
- **TTL 管理**：为每个 Session 设置生存时间（TTL），避免存储空间无限增长。

## 架构意义

Session Store 的出现标志着 Agent 架构从“宠物模式”向“牛马模式”的彻底转变：

1. **故障隔离**：单个 Agent 沙盒的崩溃不会导致上下文丢失，Session Store 中保存的状态可以在新沙盒中立即恢复。
2. **横向扩展**：由于上下文存储在云端，同一个 Agent 模板可以同时在数百个沙盒中运行，每个沙盒只需从 Session Store 加载自己的上下文。
3. **状态审计**：所有上下文变更都被记录在 Session Store 中，为后续的审计和调试提供了完整的历史轨迹。

## 与相关概念的关系

- [[Session 与 Agent 的实体分离]]：Session Store 是 Session 实体的持久化层，使得 Session 可以独立于 Agent 模板存在。
- [[脑手解耦]]：Session Store 是“脑”（模型决策）与“手”（代码执行）解耦的关键使能技术——大脑的上下文存储在云端，双手（沙盒）可以随时更换。
- [[沙盒环境]]：Session Store 与沙盒环境配合使用，沙盒负责执行代码，Session Store 负责保存状态，两者共同构成无状态 Agent 的基础设施。

## 实践启示

对于构建大规模 Agent 系统的开发者而言，Session Store 意味着：

- **不再需要编写复杂的本地状态管理代码**：所有上下文管理逻辑由 Session Store 统一处理。
- **Agent 可以“死而复生”**：即使沙盒被销毁，Agent 的上下文依然存在，可以随时在新沙盒中恢复执行。
- **编排者拥有“上帝视角”**：通过 Session Store，编排者可以查看、分支、回滚任意 Agent 的状态，实现精细化的任务调度。