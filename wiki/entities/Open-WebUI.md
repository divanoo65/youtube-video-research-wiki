---
title: Open WebUI
type: entity
tags: [web-ui, chat-interface, open-source]
summary: Open WebUI 是一款开源、类 ChatGPT 的 Web 聊天界面，支持 Markdown、代码运行、会话管理、流式输出等功能，被 Hermes Agent 原生支持作为交互前端。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Open WebUI

## 基本定位
Open WebUI 是一个开源的、可自托管的 Web 聊天界面，功能对标 ChatGPT，支持多种大模型后端（如 Ollama、OpenAI API）。它为 AI Agent 提供了现代化的交互体验，被 Hermes Agent 原生集成。

## 核心特征/能力
1. **类 ChatGPT 体验**：侧边栏保存历史对话，支持会话搜索，界面简洁。
2. **Markdown 完美支持**：正确渲染代码块、表格、数学公式等。
3. **代码块直接运行**：用户可在 UI 中直接运行生成的代码（如 Python 冒泡算法），实时输出结果。
4. **流式输出**：与大模型交互时逐字流式显示文本，响应感快。
5. **语音合成**：支持文本转语音功能。
6. **文件上传与引用**：支持上传文件并在对话中引用，以及引用网页和笔记。
7. **跨平台访问**：通过局域网 IP 和端口可在手机浏览器访问电脑上运行的实例。
8. **自托管控**：完全本地部署，数据隐私安全。

## 应用场景
1. **作为 Hermes Agent 的主交互界面**：替代微信等聊天工具，提供更好的聊天管理和 Markdown 体验。
2. **个人自建 AI 助手前端**：配合 Ollama 或 OpenAI API，搭建自己的 ChatGPT。
3. **团队协作平台**：支持多用户、会话分享等功能（需额外配置）。

## 关系网络
- [[Hermes-Agent-赫美斯]] — 被 Hermes 原生支持作为交互界面，Hermes 负责 Agent 执行，Open WebUI 负责展示与输入。
- [[Ollama]] — Open WebUI 也可直接连接 Ollama 作为模型后端，但在 Hermes 场景下通过 Hermes API 间接连接。

## 关键事件/里程碑
- 被 Hermes Agent 官方推荐为主要交互前端，提升 Agent 可用性。

## 出现的视频来源
- [[Hermes-Agent高级配置指南]]
