---
title: Obsidian
type: entity
tags:
  - 笔记工具
  - 知识管理
  - 双向链接
  - Markdown
summary: Obsidian 是一款基于 Markdown 的本地知识管理软件，以其强大的双向链接和图谱视图功能著称，常被用于构建个人知识库（如 LLM-Wiki）。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2025-04-06
updated: 2025-04-06
layer: L1
confidence: high
reasoning: 该实体在项目文档中被明确列为编辑器工具，用于管理生成的双向链接网络，且 Obsidian 本身是成熟的知名软件，信息可靠。
---

## 实体描述

Obsidian 是一款以本地 Markdown 文件为核心的知识管理工具，由 Erica Xu 和 Shida Li 于 2020 年创建。它通过“双向链接”（[[bi-directional-link]]）和“图谱视图”（[[graph-view]]）将分散的笔记自动连接成网络，使用户能够像在思维中漫游一样探索知识。Obsidian 支持丰富的插件系统（如 Dataview、Kanban 等），并且完全离线运行，保证了数据隐私和长期可用性。在个人知识库构建领域，Obsidian 常被用作“第二大脑”的载体，尤其适合需要深度整理、关联和检索大量信息的场景。其核心优势包括：纯文本存储（兼容任何编辑器）、社区生态活跃、以及强大的查询能力（通过 Dataview 插件）。用户可以通过简单的 Markdown 语法快速创建笔记，并利用 wikilink 进行内部引用，从而逐步编织出一个自组织的知识网络。

## 在本视频中的角色

在 LLM-Wiki 项目的工具选择中，Obsidian 被指定为“用于查看和管理生成的双向链接网络”的核心编辑器。它直接承担了知识库的可视化管理工作：项目通过大模型自动生成 Markdown 文档后，用户使用 Obsidian 打开知识库文件夹，利用其双向链接功能进行知识漫游和验证。同时，Obsidian 的 Graph View 插件可以直观展示实体间的关系强度，辅助用户发现潜在的知识缺口。可以说，Obsidian 是连接大模型处理结果与人类认知的界面层，让原本静态的文本文件具备了动态探索能力。

## 相关页面

- [[sources/llm-wiki-guide]]：该项目整体框架与 Obsidian 深度集成，Obsidian 是其中推荐的本地管理工具。
- [[bi-directional-link]]：Obsidian 的核心功能之一，也是知识库中实体间关联的基础机制。