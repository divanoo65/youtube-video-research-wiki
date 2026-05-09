---
title: Hermes Agent (赫美斯)
type: entity
tags: [agent-tool, open-source, task-automation]
summary: Hermes Agent，中文名赫美斯，是一款稳定性远超同类（如OpenCloud）的开源AI Agent工具，支持Ollama云端模型集成、Open WebUI交互界面以及主副模型架构以节省Token消耗。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent (赫美斯)

## 基本定位
Hermes Agent（官方中文名：赫美斯）是一款在 GitHub 上增速极快的开源 AI Agent 工具，由社区开发维护，以高稳定性、低崩溃率著称。核心价值在于提供稳定可靠的本地/云端 Agent 运行环境，并支持灵活的模型调度和交互界面定制。

## 核心特征/能力
1. **高稳定性**：版本更新时几乎不引入 bug，不会崩溃，稳定性远超同类产品 OpenCloud（该产品更新频繁出 bug）。
2. **Ollama 深度集成**：内置对 Ollama 的支持，可直接调用本地或云端 Ollama 模型，包括云端免费模型（如 Mixral 2.7B），无需本地 GPU 资源。
3. **Open WebUI 原生支持**：提供原生 Open WebUI 集成，具备类 ChatGPT 的交互体验，支持侧边栏会话管理、Markdown 解析、代码块直接运行、流式输出、语音合成、文件上传等功能。
4. **主副模型架构**：支持配置主模型处理复杂任务，副模型处理简单辅助任务（批准、压缩、记忆刷新、MCP 调用等），实现 Token 消耗大幅节约。
5. **跨平台访问**：通过局域网 IP 和端口 8080 可在手机浏览器上访问运行在电脑上的 Agent，并保持流式输出效果。
6. **灵活的 API 配置**：支持通过 `api_enabled` 和 `api_password` 参数启用 API 服务，便于外部 UI（如 Open WebUI）连接。
7. **傻瓜式一键部署**：Ollama 集成部署仅需运行一条命令即可完成，降低使用门槛。

## 应用场景
1. **个人本地智能助手**：用户可在本地运行 Hermes，通过 Open WebUI 作为日常对话、代码生成、文档处理助手，无需依赖第三方服务。
2. **低预算云端 Agent**：利用 Ollama 云端免费模型（如 Mixral 2.7B）作为主模型或副模型，以极低成本运行 Agent 任务，适合预算有限的个人开发者。
3. **企业级任务分派**：配置主模型（如高成本高性能模型）处理核心逻辑，副模型（如 Gemini 1.5 Flash）处理大量辅助性任务，在保证质量的同时控制整体 API 支出。

## 关系网络
- [[Ollama]] — Hermes 通过集成 Ollama 实现模型调度，Ollama 提供模型运行环境。
- [[Open-WebUI]] — Hermes 原生支持 Open WebUI 作为交互界面，两者互补。
- [[Gemini-1.5-Flash]] — 被推荐作为 Hermes 的副模型，用于辅助任务，是典型的低成本模型选择。
- [[OpenCloud]] — 竞品，但稳定性较差，Helmes 作为更稳定的替代方案。

## 关键事件/里程碑
- 官方公布中文名为“赫美斯”，澄清读音争议（H 发音）。
- 新增 Ollama 云端免费模型集成功能，降低部署门槛。
- 引入主副模型架构，显著提升 Token 利用效率。
- 原生支持 Open WebUI，大幅改善用户体验。

## 出现的视频来源
- [[Hermes-Agent高级配置指南]]
