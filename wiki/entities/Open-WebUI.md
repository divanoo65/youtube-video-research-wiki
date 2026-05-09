---
title: Open WebUI
type: entity
tags: [open-webui, ui, chat, agent-interface]
summary: 一个开源的类 ChatGPT 交互界面，可连接 Hermes Agent 等后端，提供 Markdown、代码执行等高级功能。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Open WebUI

## 基本定位

Open WebUI 是一个开源的 Web 界面，旨在为 AI 模型提供类 ChatGPT 的交互体验。在 Hermes Agent 生态中，它作为官方推荐的用户界面，替代了微信等聊天工具，支持 Markdown 渲染、代码块执行、侧边栏历史记录、流式输出和手机端访问。

## 核心特征/能力

1. **Markdown 完美渲染**: 能够正确显示数学公式、表格、代码块等格式，提供专业阅读体验。
2. **代码块直接运行**: 界面内置 Python 解释器，用户可一键运行代码（如冒泡算法），查看输出结果。
3. **历史对话侧边栏**: 左侧保存所有会话记录，支持按时间、标题检索，方便回溯。
4. **流式输出**: 实时逐字显示模型回复，减少等待感。
5. **多端访问**: 支持通过本地 IP 在手机浏览器上访问，结合内网穿透可实现远程使用。
6. **文件与网页引用**: 用户可上传文件或引用网页链接作为对话上下文。
7. **API 密码保护**: 支持设置自定义密码防止未授权访问。

## 应用场景

1. **Hermes Agent 前端界面**: 替代微信聊天窗口，提供更专业、高效的 Agent 交互环境。
2. **本地 AI 对话平台**: 连接到任何兼容 OpenAI API 的后端（包括 Ollama 直接服务），作为通用 AI 聊天室。
3. **移动端远程助理**: 通过内网穿透暴露服务，在户外的手机上访问家中的 Agent。

## 关系网络

- [[Hermes-Agent]] — **界面集成**: Open WebUI 连接 Hermes Agent 暴露的 API 端口（8642），作为其默认交互界面。
- [[Ollama]] — **间接连接**: 理论上 Open WebUI 也可直接连接 Ollama 的 API，但在本视频中通过 Hermes Agent 中转。

## 关键事件/里程碑

- **本视频中详细配置教程**: 介绍了如何修改 Hermes Agent 配置文件并添加 API 连接。

## 出现的视频来源

- [[Hermes-Agent-高级玩法与部署优化简报]]
