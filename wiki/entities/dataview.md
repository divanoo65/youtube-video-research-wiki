---
title: Dataview
type: entity
tags:
  - obsidian
  - plugin
  - query
  - knowledge-management
  - automation
summary: Dataview 是 Obsidian 的一款社区插件，允许用户通过类 SQL 查询语言（DQL）或 JavaScript 对笔记库中的元数据进行筛选、聚合和展示，是实现知识库动态查看与回填的核心工具。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2025-03-25
updated: 2025-03-25
layer: L1
confidence: high
reasoning: Dataview 是 Obsidian 生态中最具代表性的查询插件，几乎所有高阶知识库用户都会依赖它实现结构化内容管理，其重要性在 LLM-Wiki 流程中被明确列为功能插件之一。
---

## 实体描述

Dataview 是 Obsidian 笔记软件中一款非常强大的社区插件，其核心能力在于让用户能够以类似数据库查询的方式操作笔记库中的结构化信息。通过在笔记的 frontmatter（元数据区域）中定义字段（如 `tags`、`status`、`date` 等），用户可以编写 Dataview Query Language（DQL）语句，从所有笔记中筛选出符合条件的内容，并以列表、表格、日历、任务等视图动态呈现。例如，一条简单的查询可以列出所有状态为“待办”的笔记，并按创建日期排序。Dataview 还支持嵌入 JavaScript 脚本（DataviewJS），实现更复杂的逻辑处理和数据变换。该插件极大地提升了笔记库的“可编程性”，使得用户不再需要手动整理或整理目录，而是通过查询实时生成所需的视图。此外，Dataview 与 Obsidian 的 [[bi-directional-link]] 机制结合，可以构建出动态的“MOC”（内容地图）或“索引页”，为知识管理带来了类似数据库的灵活性和可扩展性。在 [[llm-wiki]] 的实践中，Dataview 被用于自动生成知识库的索引、统计实体数量、展示最新更新的页面等，是连接元数据与用户界面的关键桥梁。

## 在本视频中的角色

在本视频（即《LLM-Wiki（小Wiki）：基于大模型的个人知识库构建指南》）中，Dataview 被列为“功能插件”之一，其角色是充当知识库的**查询引擎**。视频演示了如何利用 Dataview 的查询能力，结合 frontmatter 中定义的元数据（如类型、标签、置信度等），自动生成实体列表、关系网络摘要以及维护状态报告。例如，通过一条 DQL 查询可以快速找到所有“layer: L1”的实体页面，并展示其摘要和链接。Dataview 使得知识库不再是静态的文档集合，而成为可被实时检索和动态呈现的“活”系统，显著提升了用户的知识回溯和维护效率。

## 相关链接

- [[obsidian]]
- [[query-and-refinement]]