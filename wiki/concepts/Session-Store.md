---
title: Session Store
type: concept
tags: [memory, persistence, decoupling, agent, clou]
summary: 将Agent的记忆从本地文件或进程内存储迁移到云端（如Redis）的存储机制，使Agent可以实现跨设备、跨环境的无状态恢复。
sources: [raw/notebooklm-analysis/Anthropic-Managed-Agents-架构深度解析与多Agent协作.md]
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: high
reasoning: 报告明确描述Session Store是第四层，且提到2024年4月19日合并事件。
run_id: T-4kgkYAGPuD0
---

# Session Store

## 定义
Session Store 是 Anthropic 四层解耦架构的第四层，负责将 Agent 的动态记忆（对话历史、挂载的知识文件、临时状态）从本地进程内存储迁移到外部的云存储系统（如 Redis 缓存）。通过 Session Store，Agent 不再依赖特定机器的本地文件系统，可以在任何机器上重建相同的会话上下文，实现真正的**无状态化**。

## 在本库的具体例子
- 在 [[Anthropic公司]] 的 SDK 中，`Memory Stores` 模块就是 Session Store 的实现，它支持挂载到 Session 上。
- 报告指出 **2024年4月19日** Session Store 代码被正式合并，使得记忆从本地搬到云端缓存（Redis），这是 Agent 无状态化的里程碑事件。
- 脑图节点“第四层：Session Store 云端存储”包含子节点“Context 外部化”、“Redis 缓存恢复”、“Agent 彻底无状态化”。

## 技术实现细节
- **序列化格式**：Session 内容通常序列化为 JSON 或 Protocol Buffers，存入 Redis 的 String 或 Hash 结构中。
- **缓存恢复**：当 Agent 在另一台机器上被重建时，Coordinator 从 Session Store 加载指定 Session ID 对应的内存快照，注入新创建的 Agent 实例。
- **TTL 管理**：为防止存储无限膨胀，Session Store 通常会设置过期时间（如 24 小时），或由 Coordinator 主动释放。

## 与近似概念的边界
- **本地文件存储**：传统 Agent 将记忆保存在本地磁盘文件（如 JSON），跨设备无法恢复。Session Store 将记忆中心化到云端。
- **数据库持久化**：数据库通常用于结构化数据，Session Store 更侧重于对话上下文的序列化恢复，且强调低延迟缓存。

## 关联概念
- [[四层解耦架构]] — Session Store 是其中一层。
- [[脑手分离模式]] — 需要 Session Store 外化记忆才能实现大脑与执行环境的完全分离。
- [[宠物与牛马理论]] — Session Store 是牛马模式中可恢复记忆的关键组件。

## 关联实体
- [[Redis]] — 官方推荐的 Session Store 后端。
- [[Anthropic公司]] — 设计并实现该机制的公司。
