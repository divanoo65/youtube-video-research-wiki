# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-09 | Total pages: 13

## Sources
- [[sources/Hermes-Agent-高级玩法与优化指南-深度简报|Hermes Agent 高级玩法与优化指南：深度简报]] — 本视频深入介绍了 Hermes Agent 的高级玩法，包括通过 Ollama 集成云端免费模型、使用 Open WebUI 优化交互体验，以及通过主副模型配置大幅降低 Token 消耗的策略。

## Entities
- [[entities/hermes-agent|hermes-agent]] — Hermes Agent（赫美斯）是一个高度稳定、支持主副模型配置的 AI Agent 框架，通过 Ollama 和 Open WebUI 提供极简部署和优化交互体验。
- [[entities/ollama|ollama]] — Ollama 是一个本地 AI 模型部署工具，已原生集成 Hermes Agent，提供一键傻瓜式部署和云端免费模型支持。
- [[entities/open-webui|open-webui]] — Open WebUI 是一个为 AI Agent 提供 Web 交互界面的工具，原生支持 Hermes Agent，提供会话管理、Markdown 解析和代码流式输出等高级功能。
- [[entities/gemini-2.0-flash|gemini-2.0-flash]] — Gemini 2.0 Flash 是 Google 推出的轻量级高性能模型，被 Hermes Agent 推荐作为副模型（辅助模型）以降低 Token 消耗。
- [[entities/minimax-m2.7|minimax-m2.7]] — MiniMax M2.7 是 MiniMax 推出的云端免费模型，通过 Ollama 可直接调用，无需本地 GPU 资源。

## Concepts
- [[concepts/api-enabled|api-enabled]] — API Enabled 是 Hermes Agent 配置文件中启用 API 服务的关键设置，需设置 api_enabled: true 和 api_password 以支持 Open WebUI 等外部工具连接。
- [[concepts/token-优化|token-优化]] — Token 优化是通过主副模型配置、辅助任务分配等技术手段，降低 AI Agent 运行过程中 Token 消耗的策略集合。
- [[concepts/一键部署|一键部署]] — 一键部署是通过 Ollama 原生集成 Hermes Agent 实现的傻瓜式配置体验，用户只需下载安装 Ollama 并运行特定命令即可完成部署。
- [[concepts/主副模型配置|主副模型配置]] — 主副模型配置是一种通过将任务细分，由昂贵的主模型处理复杂逻辑，由廉价的副模型处理简单任务，从而大幅降低 Token 消耗的策略。
- [[concepts/云端免费模型|云端免费模型]] — 云端免费模型是通过 Ollama 使用的无需占用本地硬件资源的 AI 模型，如 Minimax M2.7，适合本地硬件资源有限的用户。

## Comparisons
- [[comparisons/hermes-agent-vs-opencloud|hermes-agent-vs-opencloud]] — Hermes Agent 在稳定性上远超 OpenCloud，后者每次更新都会引入大量 Bug，而 Hermes Agent 的 GitHub Star 增长速度也已超越 OpenCloud。

## Overview
- [[overview/hermes-agent-部署与优化|hermes-agent-部署与优化]] — 综合多个视频来源，总结 Hermes Agent 的部署方案、优化策略和最佳实践。

## Queries
