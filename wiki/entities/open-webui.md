---
title: Open WebUI
type: entity
tags:
  - AI工具
  - Web界面
  - 交互体验
  - 跨端使用
summary: Open WebUI 是一个友好的图形化用户界面，用于与 Ollama 等本地或云端大语言模型进行交互，支持多轮对话、Markdown 渲染、文件上传等功能，极大提升了终端模型的易用性和跨设备访问能力。
sources:
  - "raw/notebooklm-analysis/hermes-agent-advanced-guide.md"
created: 2024-01-20
updated: 2024-01-20
layer: L1
confidence: high
reasoning: 基于报告章节描述，Open WebUI 被明确提及为提升交互体验和跨端使用能力的关键工具，且与 Ollama 深度集成，是 Hermes Agent 实际部署中的可选前端组件。
---

## 实体描述

Open WebUI 是一个开源、自托管的 Web 用户界面，专为与本地或云端大语言模型（LLM）交互而设计。它通常与 Ollama 结合使用，为用户提供远超传统命令行或基础聊天工具的交互体验。Open WebUI 支持完整的 Markdown 渲染，包括代码块高亮、表格、数学公式等，解决了在微信等聊天工具中无法正确解析 Markdown 的痛点。此外，它还具备多轮对话历史管理、会话分支、模型参数快速调节、文件上传（如图像、PDF、文本）以便模型读取内容，以及用户权限控制等高级功能。同一界面可以切换不同模型，便于对比测试。通过内网穿透或公网部署，用户甚至可以在手机、平板等移动设备上通过浏览器访问同一实例，实现真正的跨端连续使用。这种设计降低了 AI 工具的使用门槛，使得非技术用户也能轻松享受大语言模型的能力。Open WebUI 的安装简便，通常通过 Docker 一键部署，或作为 Ollama 的插件集成，因此成为许多 AI 爱好者和开发者的首选前端方案。在 Hermes Agent 的部署场景中，它被推荐为替代微信等原始交互界面的首选，以获得更专业、更高效的人机协作体验。

## 在本视频中的角色

在《Hermes Agent 高级玩法与优化指南》视频中，Open WebUI 被重点介绍为 **提升交互体验与跨端使用能力** 的核心工具。视频指出，虽然 Hermes Agent 原生支持微信等聊天工具，但微信的功能限制（例如无法解析 Markdown、多轮对话管理困难）严重影响了实用效率。Open WebUI 作为替代方案，提供了全功能的 Web 界面，允许用户在同一会话中进行复杂任务编排、查看格式化输出，并通过浏览器在电脑、手机、平板上无缝切换。视频还演示了如何将 Open WebUI 与 Ollama 连接，并通过主副模型配置实现成本优化，例如主模型使用强大的云端模型如 [[Gemini 1.5 Flash]] 处理用户意图，副模型使用本地轻量模型进行格式整理，从而降低 Token 消耗。这使得 Open WebUI 不仅仅是一个 UI 外壳，更是整个 [[Hermes Agent]] 工作流中承上启下的关键环节。