---
title: Andrej Karpathy
type: entity
tags:
  - AI
  - knowledge management
  - LLM-Wiki
  - personal knowledge base
summary: 知名人工智能专家，LLM-Wiki（小Wiki）思想的首倡者，倡导将大模型从“解释器”转变为“编译器”以构建个人知识库。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2026-05-12
updated: 2026-05-12
layer: L1
confidence: high
reasoning: 实体信息来源于公开资料及报告节选，内容准确且与LLM-Wiki主题高度相关。
---

# Andrej Karpathy

Andrej Karpathy 是人工智能领域的知名学者与工程师，曾担任 OpenAI 研究科学家和特斯拉人工智能高级总监。他因在深度学习、计算机视觉和自然语言处理方面的贡献而广受认可。近年来，他积极推广个人知识管理的新范式，提出了 **LLM-Wiki**（又称“小Wiki”）理念，旨在解决传统知识管理中信息碎片化、难以积累的问题。

Karpathy 的核心洞见在于：传统检索增强生成（RAG）将大模型当作“解释器”，每次查询都从零开始，无法实现知识的复利增长；而 LLM-Wiki 将大模型视为“编译器”，能够将原始、零散的文本“编译”为结构化、高关联的 Wiki 页面，并通过双向链接和自动更新，使知识库持续迭代进化。这一思想被广泛收录于《LLM-Wiki（小Wiki）：基于大模型的个人知识库构建指南》中，并已影响了众多知识管理实践者。

Karpathy 本人也是 Obsidian、VS Code 等工具的深度用户，他的公开分享和代码仓库为 LLM-Wiki 的实现提供了技术蓝图。他强调，构建个人知识库的关键在于“规则层”的设计——即定义清晰的 [[schema]] 和健康检查机制，确保知识资产的长期可用性和可维护性。

## 在本视频中的角色

在本视频（指《LLM-Wiki（小Wiki）：基于大模型的个人知识库构建指南》讲解视频）中，Andrej Karpathy 作为该理念的提出者，其核心思想贯穿始终。视频详细阐述了 Karpathy 提出的 [[compiler-pattern]] 与 [[interpreter-pattern]] 的对比，并以其公开分享的“LLM-Wiki”代码库为案例，演示了如何利用大模型自动将网络剪藏、笔记等原始信息转化为符合 [[three-layer-architecture]] 的 Wiki 页面。Karpathy 本人并未直接出镜，但其理论框架和 GitHub 仓库是视频研究的主要素材来源。

## 关联页面
- [[sources/llm-wiki-guide]]
- [[compiler-pattern]]
- [[interpreter-pattern]]
- RAG
- [[schema]]