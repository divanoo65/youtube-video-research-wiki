---
title: notebooklm-mcp
type: entity
tags: [开源项目, NotebookLM, Claude Code, MCP, 自动化, AI工具集成, 命令行工具]
summary: notebooklm-mcp是一个开源项目，作为[[MCP]]的特定实现，它允许[[Claude Code]]通过命令行界面直接与[[NotebookLM]]进行交互，实现自动化地创建笔记、添加来源、查询信息及生成文档等操作，从而绕过图形用户界面。
sources: ["raw/notebooklm-analysis/Claude-Code-与-NotebookLM-协同增效-构建自动化-AI-研.md"]
created: 2024-07-30
updated: 2024-07-30
layer: L1
confidence: high
reasoning: 该实体是报告中明确提及的一个开源项目，其功能和作用在“自动化机制”部分有详细描述，是实现Claude Code与NotebookLM协同增效的关键组件。
---
`notebooklm-mcp` 是一个专为实现 [[Claude Code]] 与 [[NotebookLM]] 之间深度集成而设计的开源项目。它作为 [[MCP]]（Model Context Protocol）的一个具体实现，其核心功能是允许 [[Claude Code]] 通过命令行界面（CLI），而非传统的图形用户界面（GUI），直接对 [[NotebookLM]] 执行一系列操作。这意味着用户可以通过 [[自然语言指令]]，自动化地在 NotebookLM 中创建新的笔记、添加外部来源（如视频链接）、查询现有信息以及生成各种文档（如总结分析、信息图或学习指南）。`notebooklm-mcp` 极大地简化了跨工具的工作流程，提升了 [[AI 辅助研究系统]] 的效率和自动化水平，是构建无缝 [[跨平台数据流转]] 的关键技术组件。它使得用户能够以编程方式控制 NotebookLM，从而实现更高级别的自动化和定制化，尤其在处理大量信息和进行复杂研究时，其价值尤为突出。

### 在本视频中的角色
在报告描述的 [[Claude Code 与 NotebookLM 协同增效：构建自动化 AI 研究工作流简报]] 中，`notebooklm-mcp` 扮演着核心的“连接器”和“自动化引擎”角色。它是实现 [[Claude Code]] 直接操作 [[NotebookLM]] 的技术基础。通过安装 `notebooklm-mcp`，[[Claude Code]] 获得了绕过图形界面、直接通过 [[自然语言指令]] 与 NotebookLM 交互的能力。这使得整个自动化研究工作流得以实现，包括 [[智能搜索]] 结果的自动导入、内容的生成以及用户在 Claude 中进行的修改与 NotebookLM 的 [[高效同步]]。没有 `notebooklm-mcp`，[[Claude Code]] 将无法直接控制 NotebookLM，从而无法实现报告中演示的从搜索到生成的一站式自动化流程。