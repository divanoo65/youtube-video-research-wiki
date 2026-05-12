---
title: VS Code
type: entity
tags:
  - 编辑器
  - 开发环境
  - 工具
  - LLM-Wiki
summary: Microsoft 出品的轻量级代码编辑器，在 LLM-Wiki 知识库构建流程中作为核心开发环境，配合 Cloud Code 插件和 Python 解释器完成脚本编写与自动化处理。
sources:
  - raw/notebooklm-analysis/LLM-Wiki-小Wiki-基于大模型的个人知识库构建指南.md
created: 2026-05-12
updated: 2026-05-12
layer: L1
confidence: high
reasoning: 实体在项目工具选择中被明确列出，是开发环境的核心组件，影响自动化脚本与知识库生成效率。
---

# VS Code

VS Code（Visual Studio Code）是由微软开发的一款免费、开源的跨平台代码编辑器，基于 Electron 框架构建。它凭借丰富的扩展生态、内置 Git 集成、智能代码补全（IntelliSense）以及高度可定制的界面，成为当今最流行的代码编辑器之一。在 LLM-Wiki 知识库构建项目中，VS Code 承担着核心开发环境角色：用户通过 VS Code 编辑和维护规则文件（如 `claud.md`）、编写 Python 脚本对原始素材进行分类与摘要、管理项目目录结构，并借助 Cloud Code 插件实现与大模型 API 的高效交互。与 [[obsidian]] 专注于知识可视化和双向链接管理不同，VS Code 更侧重于自动化流程的开发与调试，是连接大模型能力与本地文件系统的关键枢纽。

## 在本视频中的角色

在「LLM-Wiki（小Wiki）：基于大模型的个人知识库构建指南」这一项目中，VS Code 被列为“开发环境”的首要工具，与 Cloud Code 插件、Python 解释器共同构成技术底座。用户需在 VS Code 中创建标准文件夹结构（如 `/raw`、`/output`、`/scripts`），并运行大模型脚本自动处理素材、生成 wiki 实体页面。VS Code 的终端集成与任务运行器使得多步骤操作（环境初始化、规则配置、素材处理）得以无缝衔接，从而降低手动操作成本，提升知识库构建的自动化程度。在实际工作流中，用户往往同时打开 VS Code 进行脚本编写与调试，以及 [[obsidian]] 进行知识漫游与可视化，二者互补。

## 关联页面

- [[sources/llm-wiki-guide]] — 本实体的主要使用场景文档，详细描述了 VS Code 在项目中的配置与操作步骤。
- [[obsidian]] — 作为知识管理前端与 VS Code 形成工具链，前者负责展示双向链接网络，后者负责后端处理。
- [[claude]] — 大模型后端之一，通过 API 接入后在 VS Code 的脚本中被调用，完成素材分类与文档生成。