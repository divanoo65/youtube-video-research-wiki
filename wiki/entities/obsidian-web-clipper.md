---
title: Obsidian Web Clipper
type: entity
tags:
  - Obsidian
  - 浏览器插件
  - 剪藏
  - 知识管理
summary: 一款用于从网页中快速抓取内容并保存到Obsidian的浏览器扩展，支持自定义规则和自动分类，是构建个人知识库的重要工具。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2025-04-11
updated: 2025-04-11
layer: L1
confidence: high
reasoning: Obsidian Web Clipper 是Obsidian生态中用于快速采集网络素材的核心组件，与视频中介绍的基于大模型的知识库构建流程高度相关，且被明确列为工具选择之一。
---

## 实体描述

Obsidian Web Clipper 是 Obsidian 官方及社区推出的一款浏览器扩展插件，支持 Chrome、Firefox 等主流浏览器。它的核心功能是让用户能够一键将网页中的文章、片段、图片、链接等内容剪藏（Clipping）到本地的 Obsidian 知识库中，并自动生成结构化的 Markdown 文件。用户可以根据需要自定义剪藏模板，提取标题、正文、元数据（如作者、发布时间、标签等），甚至通过 CSS 选择器精准筛选内容。该插件还支持自动识别网页类型（如博客、文档、视频页面），并应用不同的处理规则。在 [[sources/llm-wiki-guide]] 视频所介绍的流程中，Obsidian Web Clipper 被定位为“浏览器端素材入口”，与通过大模型脚本处理 `raw` 文件夹的自动化流程互补。它允许用户在浏览网络时快速捕获灵感、参考文章或技术文档，无需手动复制粘贴，从而大幅提升信息摄入效率。配合 Obsidian 的双向链接和 [[dataview]] 查询插件，剪藏内容可以自动融入已有的知识网络，形成可追溯、可关联的知识节点。此外，Obsidian Web Clipper 支持将保存结果直接放入指定目录，例如视频方案中的 `raw` 文件夹，便于后续大模型进行摘要和自动生成 Wiki 页面。这一工具解决了从“信息获取”到“知识沉淀”的关键一步，是构建个人第二大脑的基础设施之一。

## 在本视频中的角色

在 [[sources/llm-wiki-guide]] 视频中，Obsidian Web Clipper 被列为工具链中的关键浏览器插件，用于网页内容的即时剪藏。视频建议用户在浏览网页时，通过该插件将素材直接保存到知识库的 `raw` 原始素材目录，作为后续大模型处理的输入。它与 [[obsidian]] 编辑器、[[vs-code]] 开发环境以及 Claude/DeepSeek API 共同构成了完整的工作流：采集→分类→生成→漫游。

## 相关页面

- [[obsidian]]
- [[llm-wiki]]