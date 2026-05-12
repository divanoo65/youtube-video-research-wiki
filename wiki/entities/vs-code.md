---
title: VS Code
type: entity
tags: ["IDE", "代码编辑器", "配置工具"]
summary: Visual Studio Code 是微软开发的轻量级代码编辑器，广泛用于编程和配置文件修改，在 Hermes Agent 项目中作为修改配置的主要工具之一。
sources: ["raw/notebooklm-analysis/hermes-agent-advanced-guide.md"]
created: 2025-03-30
updated: 2025-03-30
layer: L1
confidence: high
reasoning: VS Code 是公认的行业标准编辑器，其功能和使用方式在官方文档及社区中广泛记录，且直接出现在 Hermes Agent 配置指南的文本中，因此可信度极高。
---

## 实体描述

Visual Studio Code（简称 VS Code）是由微软开发的一款免费、开源的跨平台代码编辑器。它基于 Electron 框架构建，凭借其轻量级、高度可扩展的插件生态以及内置的 Git 支持、调试终端和智能代码补全（IntelliSense）等功能，已成为全球开发者最常用的开发环境之一。VS Code 支持几乎所有主流编程语言，用户可以通过安装扩展实现语法高亮、格式化、 linting、版本控制、远程开发等复杂任务。其界面设计简洁现代，用户可通过设置文件（`settings.json`）或图形界面进行个性化调整。在 AI Agent 开发与配置的领域，VS Code 常被用作修改 YAML、JSON 或 TOML 等配置文件的工具，因为它提供了清晰的语法高亮、错误提示和多光标编辑等高效操作，使得调整模型参数、API 端点或模型分层策略变得直观快捷。此外，VS Code 内集成的终端功能允许开发者在不离开编辑器的情况下执行命令行指令，进一步提升工作效率。

## 在本视频中的角色

在关于 Hermes Agent 高级玩法与优化指南的文档（或配套视频）中，VS Code 被明确列举为可用于修改 Agent 配置文件的工具之一。文档提到用户可以选择使用 `antigravity`、记事本、VS Code 甚至 AI 辅助工具（如 Codex 或 Claude）来进行配置调整。这表明 VS Code 在此方案中扮演了“主力的手动配置编辑器”的角色——它既比记事本更具可读性和编辑效率，又比 antigravity 更通用、更符合大多数开发者的日常工作流。特别是在需要频繁修改 API 密钥、模型名称、分层策略等关键参数时，VS Code 的多标签页、搜索替换和语法校验功能能显著降低人为出错的风险。同时，文档也暗示了可以将 VS Code 与 AI 辅助插件（如 GitHub Copilot）结合使用，实现更智能的配置建议和自动补全，从而进一步降低 Token 消耗和配置复杂度。

## 相关链接

- [[Hermes Agent]] – VS Code 是配置该智能体系统的重要工具之一。
- [[主副模型配置方案]] – 修改配置文件以启用分层模型时，VS Code 提供了便捷的编辑环境。