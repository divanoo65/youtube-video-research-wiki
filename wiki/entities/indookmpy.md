---
title: indookmpy
type: entity
tags:
  - MCP
  - 工具
  - 开源项目
summary: 一个开源的 MCP 插件，旨在实现 Claude Code 与 NotebookLM 之间的程序化交互与自动化操作。
sources:
  - "raw/notebooklm-analysis/Claude-Code-与-NotebookLM-高效集成方案简报.md"
created: 2024-05-22
updated: 2024-05-22
layer: L1
confidence: high
reasoning: 该实体是实现 Claude Code 与 NotebookLM 集成的核心技术组件，在提供的报告中被明确定义为连接两者的桥梁。
---

# indookmpy

### 实体描述
indookmpy 是一个开源的 MCP（Model Context Protocol）插件，专门为连接 [[Claude Code]] 与 [[NotebookLM]] 而设计。在现代 AI 辅助研究工作流中，该插件充当了关键的中间件角色，它通过 MCP 标准协议，将 Claude Code 的命令行操作能力与 Google 的 NotebookLM 知识库管理功能打通。用户无需进行复杂的底层开发，即可通过简单的指令将该插件全局安装至本地环境。一旦配置完成，indookmpy 能够处理身份验证流程（如通过 `nog` 命令调用 Google 认证），从而允许 Claude Code 直接读取、分析或操作 NotebookLM 中的数据。这一工具极大地降低了跨平台自动化研究的门槛，使得用户能够构建更加高效、自动化的知识管理与分析系统。

### 在本视频中的角色
在本方案中，indookmpy 是实现“Claude Code 与 NotebookLM 高效集成”的核心技术组件。它不仅是安装流程中的关键插件，还承担了身份验证（通过 Google 认证）的桥梁作用，确保 Claude Code 能够安全地访问用户的 NotebookLM 资源，从而实现对研究资料的程序化调用与处理。

### 相关链接
- [[Claude Code 与 NotebookLM 高效集成方案简报]]
- [[NotebookLM]]