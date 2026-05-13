---
title: Redis
type: entity
tags: [infrastructure, database, caching, architecture]
summary: Redis 是一个高性能的开源内存数据结构存储系统，在 Managed Agents 架构中作为 Session Store 的核心组件，用于实现智能体的状态持久化与无状态化运行。
sources: ["raw/notebooklm-analysis/managed-agents-architecture.md"]
created: 2024-05-22
updated: 2024-05-22
layer: L1
confidence: high
reasoning: Redis 在架构中扮演关键的云端存储角色，是实现智能体“无状态化”设计的技术基石。
---

# Redis

## 实体描述
Redis（Remote Dictionary Server）是一个开源的、基于内存的键值对存储系统，因其极高的读写性能和丰富的数据结构支持，被广泛应用于缓存、消息队列和实时数据处理场景。在现代分布式系统架构中，Redis 常被用作高性能的数据库、缓存和消息中间件。其核心优势在于将数据存储在内存中，从而提供亚毫秒级的响应速度，并支持多种数据类型（如字符串、哈希、列表、集合等），能够灵活应对复杂的业务需求。此外，Redis 还具备持久化功能，可以将内存中的数据定期保存到磁盘，确保在系统重启或故障时数据不丢失。

## 在本视频中的角色
在 Managed Agents（托管智能体）的架构体系中，Redis 处于“第四层：Session Store（云端存储）”的关键位置。其核心作用是实现智能体的“状态持久化”。

根据架构设计理念，为了解决智能体在本地运行容易崩溃、环境难以维护的问题，系统被设计为“无状态化”。这意味着智能体的上下文记忆不再依赖于本地环境，而是通过 Redis 将这些记忆搬运到云端。通过这种方式，智能体可以实现“随销毁随重建”的灵活性，即底层的执行环境（如 [[Docker]] 容器）可以随时被销毁或替换，而智能体的核心记忆状态始终安全地保存在 Redis 中。这种设计不仅降低了运维成本，还极大地提升了系统的容错性和扩展性，使得“脑手解耦”的架构成为可能。

## 相关链接
- [[无状态化]]
- [[托管智能体]]
- [[Anthropic Managed Agents 架构深度解析与复刻实践简报]]