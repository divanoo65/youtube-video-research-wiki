---
title: Token 节省方案
type: concept
tags: [cost-optimization, token-management, agent-configuration]
summary: Token 节省方案是 Hermes Agent 综合运用主副模型架构、上下文压缩、记忆管理等机制，将简单任务分流至低成本模型以降低 API 调用费用的整体策略。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 视频详细介绍了通过主副模型架构节省 Token 的具体方法，属于跨视频可见模式。
---

# Token 节省方案

## 定义
Token 节省方案是 AI Agent 通过架构设计和配置优化，在保证核心任务质量的前提下，最小化 API Token 消耗的一系列策略组合。

## 核心策略
1. **主副模型架构**：复杂任务使用高性能模型，辅助任务统一使用低成本模型（如 [[Gemini-1.5-Flash]]）
2. **上下文压缩**：将长对话历史压缩后存储，减少每次 API 调用的输入 Token
3. **辅助任务分流**：任务批准、会话搜索、MCP 调用等辅助操作全部由副模型处理
4. **本地模型替代**：通过 [[Ollama]] 集成本地或云端免费模型，进一步降低或消除 API 费用

## 技术实现细节
在 [[Hermes-Agent-赫美斯]] 中，Token 节省方案通过配置文件实现。用户只需修改 `auxiliary_tasks` 字段，将所有辅助任务指向同一低成本模型即可。此配置已在社区测试中验证可应对所有辅助功能场景。

## 关联概念
- [[主副模型架构]] — Token 节省方案的核心机制
- [[上下文压缩]] — 减少输入 Token 的关键技术
- [[辅助任务]] — 副模型承担的工作分类

## 关联实体
- [[Hermes-Agent-赫美斯]] — 实现 Token 节省方案的 Agent 工具
- [[Gemini-1.5-Flash]] — 推荐的默认副模型
- [[Ollama]] — 提供免费模型的选项
