---
title: open-webui
type: entity
tags: [ai, interface, web]
summary: Open WebUI 是一个为 AI Agent 提供 Web 交互界面的工具，原生支持 Hermes Agent，提供会话管理、Markdown 解析和代码流式输出等高级功能。
sources: [wiki/sources/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Open WebUI

## 基本定位

Open WebUI 是一个为 AI Agent 提供 Web 交互界面的工具，原生支持 Hermes Agent，提供会话管理、Markdown 解析和代码流式输出等高级功能。

## 核心特征/能力

1. **会话管理**：支持侧边栏保存历史记录，方便随时查阅和搜索。
2. **Markdown 格式解析**：完美支持 Markdown 格式，具备代码块流式输出及一键运行功能（如 Python 代码运行）。
3. **多端访问**：支持手机浏览器通过 IP 地址访问，且适配良好，支持文件上传、截图和网页引用。
4. **API 启用**：需在配置文件中添加 `api_enabled: true` 并设置自定义密码 `api_password`。
5. **兼容性强**：支持与 Hermes Agent 集成，提供更优的交互体验。

## 应用场景

1. **AI 代理交互**：适用于需要频繁进行代码编写和长文本交互的用户。
2. **远程办公**：支持通过手机浏览器访问，适合远程工作环境。
3. **多端协作**：支持文件上传、截图和网页引用，适合团队协作。

## 关系网络

- [[hermes-agent]]：Open WebUI 原生支持 Hermes Agent，提供更优的交互体验。
- [[api-enabled]]：Open WebUI 需要启用 API 服务才能正常工作。

## 关键事件/里程碑

- 2026 年 5 月：Open WebUI 成为 Hermes Agent 的主要交互界面工具，广泛应用于各类 AI 代理项目。

## 出现的视频来源

[[Hermes-Agent-高级玩法与优化指南-深度简报]]