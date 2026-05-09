---
title: "Chrome DevTools Protocol"
type: concept
tags: [protocol, chrome, devtools, automation]
summary: Chrome DevTools Protocol (CDP) 是 Chrome 浏览器提供的一套调试协议，允许外部工具（如 Codex Chrome）连接并操作浏览器页面，包括 DOM 操作、网络监控、模拟用户交互等。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能特性与实测深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Chrome DevTools Protocol

## 定义

Chrome DevTools Protocol（简称 CDP）是 Google Chrome 基于 WebSocket 的**调试与自动化协议**。它允许第三方工具通过发送 JSON-RPC 消息来控制浏览器标签页，包括：导航到 URL、获取 DOM 结构、模拟点击和键盘输入、监听网络事件等。Codex Chrome 插件利用 CDP 作为底层桥梁，实现对已登录浏览器环境的无缝操作。

## 在本库的具体例子

在 [[sources/Codex-Chrome-插件功能特性与实测深度简报]] 中，Codex Chrome 通过 **CDP 连接已登录的 Chrome 实例**，使得 AI 代理可以自动登录报销系统、填写表单、上传附件。当需要绕过站点防护时，通过 CDP 获取渲染后的 DOM 树（[[DOM渲染抓取]]）。此外，多标签并行的实现也依赖为每个标签页建立独立的 CDP 会话。

## 技术实现细节

- Codex Chrome 以 Chrome 扩展的形式运行，扩展可以在后台通过 `chrome.debugger` API 获取 CDP 连接。
- CDP 提供超过 70 个域名（domain），如 `Page`, `DOM`, `Input`, `Network`, `Runtime` 等，每个域名包含若干方法。
- 代理通过组合使用 `Page.navigate`、`DOM.querySelector`、`Input.dispatchMouseEvent` 等命令来模拟用户操作。

## 与近似概念的边界

- **Selenium WebDriver**：也用于浏览器自动化，但基于 WebDriver 协议（W3C 标准），主要面向测试场景，需要额外安装驱动。CDP 更底层、更快速，且直接与浏览器 DevTools 对接，被 Playwright 和 Puppeteer 广泛采用。Codex 选择 CDP 是为了更高的执行效率和更精细的浏览器控制。
- **浏览器扩展 API**：Chrome 扩展使用 `chrome.*` API 来处理标签页、存储等，但无法实现底层页面操控。CDP 提供了远超扩展 API 的细粒度控制能力。

## 关联概念

- [[DOM渲染抓取]] — 间接使用 CDP 的 `DOM.getDocument` 和 `Runtime.evaluate` 实现。
- [[多标签并行]] — 每个标签页通过独立的 CDP 连接进行控制。

## 关联实体

- [[codex-chrome]] — 产品实体，直接利用 CDP 实现所有浏览器操作。
