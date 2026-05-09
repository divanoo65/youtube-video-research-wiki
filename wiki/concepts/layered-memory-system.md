---
created: 2026-05-09
updated: 2026-05-09
title: 分层记忆体系
type: concept
tags: [ai-agent, memory-system]
sources: [raw/notebooklm-analysis/NbldZVdusKo_b2e25f66-64ec-4549-87e3-c43184c449dc_20260509T010844Z_report.md]
summary: Hermes Agent 的四层持久化记忆系统，包括核心持久层、会话历史层、扩展画像层、程序性记忆层，优化 Token 效率与检索精度。
layer: L2
confidence: high
reasoning: 直接来自视频中对 Hermes Agent 记忆体系的描述
---

# 分层记忆体系

## 定义与核心含义
分层记忆体系是 Hermes Agent 用于优化 Token 效率与检索精度的四层持久化记忆系统：
1. 核心持久层 (MEMORY.md)：存储核心笔记与用户偏好，限额约 1300 Token，仅在会话启动/重建时加载。
2. 会话历史层 (state.db)：基于 SQLite 的历史记忆，支持 FTS5 全文索引，通过大模型摘要重构实现按需检索。
3. 扩展画像层 (Honcho)：用于跨会话的深层用户理解，建立长期用户画像。
4. 程序性记忆层 (Skills)：存储“学会了怎么做”的操作模式，而非单纯的事实知识，即程序化知识。

## 应用场景与步骤
- **记忆存储**：不同类型的信息被存储在对应的层中，以提高检索效率。
- **记忆检索**：根据需求从不同层调取信息，核心层和会话层提供快速访问，扩展层提供深度理解。
- **记忆更新**：随着使用，每层记忆会被更新，特别是程序性记忆层通过技能生成不断增长。

## 在本库视频中的具体例子
视频中提到：\"Hermes Agent 构建了一套精密的四层持久化记忆系统，以优化 Token 效率与检索精度：
1. 核心持久记忆： MEMORY.md 和 USER.md，限额约 1300 Token...
2. 会话历史记忆： 基于 SQLite 的 state.db...
3. 扩展记忆层 (Honcho)： 用于跨会话的深层用户理解...
4. 程序性记忆（技能）： 存储‘学会了怎么做’的操作模式...*

## 关联概念
[[程序化知识生成]] [[自动化能力]] [[身份定义]] [[Agent 执行循环]]

## 关联实体
[[Hermes Agent]] [[OpenClaw]] [[MEMORY.md]] [[Honcho]]

---
*本页面内容基于 YouTube 视频 https://www.youtube.com/watch?v=NbldZVdusKo 的 NotebookLM 分析报告生成。*
