---
title: Hermes Agent (赫美斯)
type: entity
tags: [agent, AI, hermes, ollama, openwebui, 主副模型, 对话压缩]
summary: Hermes Agent 是一款开源的 AI Agent 框架，以高稳定性和易用性著称，支持通过 Ollama 集成云端免费模型，并可通过 Open WebUI 美化界面，配合主副模型策略有效节省 Token。
sources: ["raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-云端模型-美化界面与-Token.md"]
created: 2026-05-12
updated: 2026-05-12
layer: L1
confidence: high
reasoning: 实体信息直接来源于官方教程视频及分析报告，内容明确且可交叉验证。
---

## 实体描述

Hermes Agent（官方中文名：赫美斯）是一款基于大语言模型的自主智能体框架，专为构建可交互、可扩展的 AI Agent 而设计。其核心特点在于极高的系统稳定性——在开发者社区中，Hermes Agent 的 GitHub Star 增速已超越同类工具 OpenCloud，且版本迭代过程中极少出现 Bug 或崩溃，这使得它成为开发者和高级用户的首选工具。Hermes Agent 支持多种后端模型部署方式，尤其与 Ollama 深度集成，允许用户快速调用免费云端模型（如 Gemini 1.5 Flash）来降低使用门槛。为了提升用户体验，它还可以与 Open WebUI 配合，获得美观的聊天界面与丰富的功能面板。针对大语言模型应用中最令人头疼的 Token 消耗问题，Hermes Agent 提供了创新的“主副模型策略”：主模型负责核心推理与复杂任务，副模型（通常为轻量模型）负责简单对话或压缩历史记录，从而大幅降低 Token 使用量。此外，Hermes Agent 还内置了对话压缩机制，进一步优化长对话场景下的资源利用。这些特性使 Hermes Agent 成为当前 AI Agent 领域最具实用价值的框架之一。

## 在本视频中的角色

本视频（《Hermes Agent 高级玩法与优化指南：云端模型、美化界面与 Token 节省策略》）以 Hermes Agent 为核心教学对象，全面演示了如何通过 Ollama 部署免费云端模型、如何集成 Open WebUI 改善界面，以及如何配置主副模型与对话压缩来节省 Token。视频由“AI超元域”出品，面向已有基础的用户，纵向延伸了 Hermes Agent 的高级玩法。Hermes Agent 既是教程的主题，也是所有操作与配置的承载平台。

## 关联页面

- [[ollama|Ollama]]： Hermes Agent 的核心后端集成工具，用于部署和调用本地/云端模型。
- [[open-webui|Open WebUI]]： 为 Hermes Agent 提供美观交互界面的前端工具，支持功能扩展与自定义。
- [[primary-secondary-model-strategy|主副模型策略]]： Hermes Agent 特有的 Token 节省方案，通过分工协作降低推理成本。
- [[dialogue-compression|对话压缩]]： 与主副模型配合使用的长对话记忆优化技术。