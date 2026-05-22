---
title: config.toml
type: entity
tags:
  - configuration
  - file
  - Hermes Agent
  - Open WebUI
summary: config.toml 是赫美斯 Agent 和 Open WebUI 集成中的一个关键配置文件，用于启用API服务、设置安全密码以及配置主副模型策略以优化Token消耗。
sources:
  - "raw/notebooklm-analysis/赫美斯-Agent-Hermes-Agent-高级应用与部署简报.md"
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: 从提供的源文本中直接提取，详细描述了其在赫美斯 Agent 和 Open WebUI 配置中的关键作用。
---
`config.toml` 是在 [[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]] 中被提及的一个关键配置文件。它在 [[Open WebUI]] 与 [[赫美斯 Agent]] 的集成和高级功能配置中扮演着核心角色。用户通过修改此文件，可以启用或禁用特定的服务，例如通过设置 `enable_api = true` 来开启 [[API service]]。此外，为了增强系统的安全性，用户还可以在 `config.toml` 中配置 [[API password]]。该文件不仅限于基础服务设置，它还是实现 [[赫美斯 Agent]] “主副模型”配置策略的重要途径。通过在 `config.toml` 中针对不同任务（Task）指定对应的 API Key 和模型，可以有效节约 Token 消耗，优化资源利用。例如，可以指定廉价高效的副模型（如 Gemini 2.5 Flash）处理批准、压缩、记忆刷新、MCP/Skills 调用以及视觉/网页工具等辅助性任务，而将复杂逻辑任务留给昂贵的主模型。因此，`config.toml` 是管理 [[赫美斯 Agent]] 行为、性能和安全性的一个中心枢纽，对于实现其 [[高级功能]] 至关重要。

### 在本视频中的角色
在《赫美斯-Agent-Hermes-Agent-高级应用与部署简报》中，`config.toml` 文件被明确指出是配置 [[Open WebUI]] 与 [[赫美斯 Agent]] 集成的关键步骤之一。它主要用于：
1.  **启用 API 服务**：通过修改 `enable_api = true` 来激活 API 功能，这是 [[Open WebUI]] 连接 [[赫美斯 Agent]] 的前提。
2.  **设置 API 访问密码**：增强系统安全性。
3.  **配置主副模型策略**：在文件中针对不同任务（Task）指定不同的 API Key 和模型，以实现 Token 节约战略，优化资源分配。