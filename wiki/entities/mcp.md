---
title: MCP
type: entity
tags:
  - MCP
  - Model Context Protocol
  - Claude Code
  - NotebookLM
  - AI研究
  - 自动化
  - 协议
  - 连接器
summary: MCP（Model Context Protocol，模型上下文协议）是一个关键的连接协议，被形象地比喻为“插头”，它允许Claude Code连接并操作各类外部工具与服务。在自动化AI研究工作流中，MCP是实现Claude Code与NotebookLM等工具协同增效的核心技术，能够绕过图形用户界面，通过自然语言指令驱动自动化任务。
sources:
  - raw/notebooklm-analysis/Claude-Code-与-NotebookLM-协同增效-构建自动化-AI-研.md
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: MCP的定义、功能及其在自动化工作流中的核心作用在来源报告中被明确阐述。
---

**实体描述:**
MCP，全称为 [[模型上下文协议]]（Model Context Protocol），是一个在AI系统，特别是像Claude Code这样的命令行界面工具中，扮演着至关重要角色的连接协议。它被形象地比喻为“插头”，其核心功能是允许AI模型（如Claude Code）能够无缝地连接并操作各种外部工具与服务。这意味着通过MCP，AI不再局限于自身的处理能力，而是能够扩展其功能边界，与外部世界进行交互。例如，在报告中提及的场景中，MCP使得Claude Code能够与Google的NotebookLM进行通信，从而实现自动化地创建笔记、添加来源、查询信息等操作。这种协议是构建高度自动化、跨平台AI工作流的基础，它使得AI能够通过统一的接口，以结构化的方式理解和调用外部API或服务，极大地提升了AI系统的实用性和集成能力。通过MCP，用户可以通过自然语言指令，间接控制和协调多个独立的软件工具，实现复杂任务的自动化执行，而无需手动操作各个工具的图形用户界面。

**在本视频中的角色:**
在本报告所描述的自动化AI研究工作流中，[[MCP]] 扮演着核心的“连接器”角色。它是实现 [[Claude Code]] 与 [[NotebookLM]] 协同增效的关键技术。通过安装专用的 `[[notebooklm-mcp]]` 开源项目，MCP使得Claude Code能够绕过NotebookLM的图形用户界面（GUI），直接通过自然语言指令在NotebookLM中执行操作，例如创建笔记、添加资料来源、查询信息等。它将Claude Code的指令能力扩展到外部工具，从而构建了一个完全基于个人或特定数据源的、低成本且高效率的 [[AI 辅助研究系统]]。MCP是整个自动化机制得以运作的底层协议，确保了不同工具之间的数据流转和指令执行。