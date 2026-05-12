---
title: DeepSeek
type: entity
tags: [大模型, API, 知识库, LLM-Wiki]
summary: DeepSeek 是一个由深度求索公司开发的大语言模型，通过 API 接入，作为 LLM-Wiki 知识库构建流程中的可选后端引擎之一，与 Claude 并列，提供文本生成、摘要、分类等核心能力。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2026-05-12
updated: 2026-05-12
layer: L1
confidence: high
reasoning: 基于原始报告节选明确将 DeepSeek 列为大模型后端选项，且 Obsidian 知识库构建流程中需要依赖其 API 完成自动化处理。
---

## 实体描述

DeepSeek 是深度求索（DeepSeek）公司推出的一系列大语言模型，以其高性价比、长上下文窗口和强大的推理能力著称。在知识管理场景中，DeepSeek 经常被用作自动化的文本处理引擎：用户可以通过 API 调用它来对原始素材进行摘要、分类、生成结构化标签，甚至根据预设的 Schema 自动填充实体页面的 frontmatter 与正文。与 Claude 类似，DeepSeek 也支持多种编程语言和开发环境（如 VS Code、Python 解释器）的集成，便于脚本化批量处理。其 API 接口稳定、定价相对透明，使得个人知识库维护者能够以较低成本构建持续更新的双向链接网络。同时，DeepSeek 在长文档理解、多轮对话和指令遵循方面表现优异，特别适合需要处理大量 PDF、网页剪辑或笔记摘录的“摄入”环节。在 LLM-Wiki 体系的“健康检查”流程中，DeepSeek 还可用于校验 wiki 页面的一致性、检测过时的链接或补充缺失的关联概念，从而维持知识库的活力和准确度。

## 在本视频中的角色

在本视频（[[sources/llm-wiki-guide]]）中，DeepSeek 被列为两种可选的大模型后端之一，与 Claude 并列。视频的“工具选择”部分明确提及“大模型后端：Claude 或 DeepSeek（通过 API 接入）”。这意味着 DeepSeek 承担了核心的文本生成与处理任务：当用户将原始文件放入 `raw` 文件夹后，运行的大模型脚本可以调用 DeepSeek API 自动完成分类、摘要并生成 `wiki` 目录下的 Markdown 文档。此外，视频强调的“规则配置”环节中，DeepSeek 同样需要遵循 `claud.md` 契约文件（尽管名称带有“claud”，但实际为通用的规则定义），以保证输出格式与 Obsidian 所要求的双向链接、frontmatter 规范一致。因此，DeepSeek 在视频演示的工作流中既是引擎，也是关键的自动化节点。

## 相关页面

- [[claude]]：另一种可选的大模型后端，与 DeepSeek 形成互补，用户可根据成本或性能偏好进行选择。
- [[sources/llm-wiki-guide]]：本视频的完整指南，详细阐述了 DeepSeek 在知识库搭建中的具体集成步骤。