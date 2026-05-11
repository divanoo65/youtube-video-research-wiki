---
title: Redis
type: entity
tags: [cache, database, session-store, memory]
summary: 开源内存数据库，在 Managed Agents 架构中被用作 Session Store 的后端缓存，实现 Agent 记忆的云端持久化与快速恢复。
sources: [raw/notebooklm-analysis/Anthropic-Managed-Agents-架构深度解析与多Agent协作.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T-4kgkYAGPuD0
---

# Redis

## 基本定位
Redis 是一种高性能的键值存储系统，通常用作缓存和消息代理。在 Anthropic Managed Agents 架构的第四层（Session Store）中，Redis 被选为记忆的外部缓存，使得 Agent 在任何机器上都能恢复上下文，实现真正的无状态化。

## 核心特征/能力
1. **内存级速度**：读写延迟通常在微秒级，满足 Agent 高频上下文加载/保存需求。
2. **持久化支持**：即使重启也不会丢失数据，通过 RDB/AOF 机制保证记忆存储可靠性。
3. **数据结构丰富**：支持字符串、哈希、列表、集合等，可以灵活表示 Agent 记忆树。
4. **发布/订阅**：可用于 Coordinator 向各 Agent 广播消息，实现实时状态同步。
5. **分布式扩展**：通过集群模式支持大规模 Agent 会话存储。

## 应用场景
- **Session Store 后端**：在 Managed Agents 中，所有 Agent 的上下文都序列化存入 Redis，支持跨设备恢复。
- **Agent 状态共享**：多个 Agent 需要共享某些数据时（如全局计数器、知识库），Redis 作为中心缓存。
- **高可用编排**：利用 Redis 主从复制保障 Agent 记忆不丢失。

## 关系网络
- [[Session-Store]] — Redis 是实现该概念的关键组件。
- [[Anthropic公司]] — 选择 Redis 作为官方推荐的后端之一。
- [[编排者（Coordinator）]] — Coordinator 通过 Redis 获取各 Agent 的最新会话快照。

## 关键事件/里程碑
- **广受采用**：在 AI Agent 架构中作为缓存解决方案已经成为事实标准。

## 出现的视频来源
- [[Anthropic-Managed-Agents-架构深度解析与多Agent协作]]
