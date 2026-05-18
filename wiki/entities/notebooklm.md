---
title: NotebookLM
type: entity
tags:
  - AI工具
  - 知识管理
  - Google
summary: NotebookLM 是由 Google 开发的一款基于 RAG（检索增强生成）技术的 AI 研究与知识管理工具，旨在通过用户上传的特定资料库进行精准问答与内容生成。
sources:
  - "raw/notebooklm-analysis/Claude-Code-与-NotebookLM-高效集成方案简报.md"
created: 2026-05-18
updated: 2026-05-18
layer: L1
confidence: high
reasoning: 该实体是报告中的核心研究对象，其功能特性及集成方案在文档中有明确定义。
---

# NotebookLM

NotebookLM 是 Google 推出的创新型 AI 研究助手，其核心优势在于能够构建“私有化”的知识库。与通用的生成式 AI 不同，NotebookLM 严格限制模型仅基于用户上传的特定文档（如 PDF、网页、YouTube 视频链接等）进行分析与回答，从而极大地降低了幻觉风险，确保了输出内容的“忠实度”。该工具不仅支持多文档的交叉分析，还能自动提取关键信息并生成摘要，是进行深度学习、资料整理及学术研究的强力辅助工具。

在当前的自动化集成方案中，NotebookLM 扮演了“知识引擎”的角色。通过与 [[Claude Code]] 的集成，用户可以利用 [[MCP (Model Context Protocol)]] 协议，将原本需要手动上传和交互的 UI 流程转化为由 Claude Code 驱动的自动化指令。这种集成方式使得 NotebookLM 的资料处理能力能够无缝嵌入到更广泛的 [[自动化研究工作流]] 中，实现了从资料收集、内容解析到知识汇总的全链路自动化，显著提升了处理复杂信息源的效率。

### 在本视频中的角色
在本方案中，NotebookLM 作为核心的知识处理后端，负责接收由 Claude Code 预处理后的数据，并利用其强大的 RAG 能力对特定资料进行深度分析与总结。它不仅是信息存储的容器，更是确保 AI 输出具备高可信度和[[资料溯源]]能力的基石。