---
title: Open WebUI
type: entity
tags: [open-webui, web界面, 交互优化]
summary: Open WebUI 是一个为 AI Agent 提供 Web 交互界面的工具，原生支持 Hermes Agent，提供会话管理、Markdown 解析和代码流式输出等高级功能。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Open WebUI

## 基本定位
Open WebUI 是一个为 AI Agent 提供 Web 交互界面的开源工具，原生支持 Hermes Agent。其核心价值在于提供类似 ChatGPT 的交互体验，包括会话管理、Markdown 格式解析、代码块流式输出及一键运行功能，显著提升 Agent 的使用效率和用户体验。

## 核心特征/能力

1. **会话管理**: 支持侧边栏保存历史记录，方便随时查阅和搜索。
2. **Markdown 格式解析**: 完美支持 Markdown 格式，具备代码块流式输出及一键运行功能（如 Python 代码运行）。
3. **多端访问**: 支持手机浏览器通过 IP 地址访问，且适配良好，支持文件上传、截图和网页引用。
4. **API 连接**: 支持通过 OpenAI 兼容接口连接 Hermes Agent，URL 指向本地 8642 端口，并包含 `/v1` 后缀。
5. **管理员设置**: 提供管理员后台，支持添加和管理连接配置。

## 应用场景

1. **提升交互体验**: 对于需要频繁进行代码编写和长文本交互的用户，建议优先部署 Open WebUI 而非单纯依赖命令行或社交软件。
2. **远程办公**: 配合内网穿透技术，通过手机浏览器远程访问家中的 Agent 实例。

## 关系网络

- [[hermes-agent]] — 依赖关系：Open WebUI 为 Hermes Agent 提供交互界面。
- [[ollama]] — 互补关系：Ollama 提供模型部署，Open WebUI 提供交互界面。
- [[api-enabled]] — 配置依赖：需在 Hermes Agent 配置文件中启用 API 服务才能连接。

## 关键事件/里程碑

- **Hermes Agent 原生支持**: Open WebUI 成为 Hermes Agent 官方推荐的 Web 交互界面。

## 出现的视频来源

- [[hermes-agent-高级玩法与优化指南-深度简报]]