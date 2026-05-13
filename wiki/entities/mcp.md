---
title: MCP
type: entity
tags:
  - 架构组件
  - 智能体协议
  - 技术标准
summary: MCP (Model Context Protocol) 是一种用于连接智能体与外部数据源及工具的标准化协议，在 Anthropic Managed Agents 架构中作为智能体获取外部能力的关键接口。
sources:
  - "raw/notebooklm-analysis/anthropic-managed-agents-analysis.md"
created: 2024-05-22
updated: 2024-05-22
layer: L1
confidence: high
reasoning: MCP 是现代智能体架构中连接模型与外部环境的核心标准，在提供的分析报告中被明确定义为智能体模板的重要组成部分，属于基础架构层。
---

# MCP (Model Context Protocol)

MCP 是由 Anthropic 推动的一种标准化协议，旨在解决大语言模型（LLM）与外部数据源、工具及服务之间连接的碎片化问题。在复杂的智能体架构中，MCP 充当了“通用连接器”的角色，它允许智能体以统一的方式访问本地文件系统、数据库、API 接口或其他计算资源，而无需为每个工具编写特定的集成代码。通过 MCP，开发者可以将各种功能模块化，使得智能体能够像调用本地函数一样调用远程服务，极大地提升了智能体的扩展性和互操作性。

### 在本视频中的角色

在本次关于 [[Anthropic Managed Agents 架构深度解析与复刻实践简报]] 的分析中，MCP 被置于架构的第一层——[[Agent (智能体模板)]] 中。它作为智能体身份模板的核心组成部分，规定了智能体在执行任务时能够调用的工具集。

具体而言，MCP 使得 [[托管智能体]] 能够实现“脑手解耦”，即智能体的逻辑处理（大脑）与具体执行工具（手）通过 MCP 协议进行标准化对接。这种设计确保了智能体在进行任务拆解和执行时，能够动态地挂载所需的外部能力，从而支持大规模并发和无状态化的运行模式。

### 相关链接
- [[Anthropic]]
- [[智能体操作系统]]