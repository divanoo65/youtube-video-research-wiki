---
title: agent.yaml
type: entity
tags:
  - configuration file
  - Hermes Agent
  - API
  - WebUI
  - model configuration
summary: Hermes Agent 的核心配置文件，用于启用API服务、设置密码以及精细化配置不同任务的模型，是实现高级功能和自动化的关键。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化深度简报.md
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: 在来源报告中被明确指出为 [[Hermes Agent]] 部署、API 服务启用、模型配置和自动化操作的核心配置文件，是实现高级功能和优化的关键。
---
`agent.yaml` 是 [[Hermes Agent]] 框架中的一个核心配置文件。它以 YAML 格式存储，用于定义和管理 Agent 的各项运行参数和行为。该文件在 Agent 的部署和优化中扮演着至关重要的角色。通过编辑 `agent.yaml`，用户可以启用或禁用特定的功能，例如开启 API 服务（`enable_api: true`）并设置相应的访问密码，这对于将 [[Hermes Agent]] 与外部界面（如 [[Open WebUI]]）进行联动至关重要。此外，`agent.yaml` 也用于精细化配置 Agent 在执行不同任务时所使用的模型。例如，为了平衡性能与成本，用户可以在此文件中手动指定主模型（Primary）用于处理核心逻辑和复杂推理，而将辅助任务（如批准、压缩、记忆刷新、MCP 调用、视觉、网页工具等）统一配置为使用更经济高效的模型（如 Gemini 1.5 Flash）。对于不熟悉手动编辑的用户，甚至可以通过 [[Codex]] 或 [[Claude Code]] 等工具，通过自然语言指令让 Agent 自动修改 `agent.yaml`，实现“Agent 配置 Agent”的高级自动化操作。其灵活性和可配置性是 [[Hermes Agent]] 高级玩法的基础。

### 在本视频中的角色

在《[[Hermes Agent 高级玩法与优化深度简报]]》中，`agent.yaml` 被强调为实现 [[Hermes Agent]] 高级功能和优化的核心配置文件。它在以下几个方面发挥关键作用：

1.  **API 服务启用与安全设置：** 它是启用 [[Hermes Agent]] API 服务（`enable_api: true`）并设置自定义 API 密码的唯一途径，这对于将 Agent 与 [[Open WebUI]] 等专业界面进行集成是必不可少的步骤。
2.  **模型配置与成本优化：** 报告建议通过修改 `agent.yaml` 来精细化配置不同任务（主模型、辅助任务如批准、压缩、记忆刷新等）所使用的模型，以达到性能与成本的最佳平衡。
3.  **自动化配置的基础：** 报告还指出，`agent.yaml` 是实现“Agent 配置 Agent”高级操作的载体，用户可以通过 [[Codex]] 或 [[Claude Code]] 等工具，以自然语言指令自动修改此文件，从而简化配置流程。