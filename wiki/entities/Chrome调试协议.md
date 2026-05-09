---
title: Chrome 调试协议（CDP）
type: entity
tags: [protocol, chrome, automation, debugging]
summary: Chrome 浏览器暴露的调试协议，允许外部工具通过 WebSocket 连接控制浏览器的标签页、DOM、网络请求、输入模拟等底层功能，是 Codex 插件实现计算机使用的核心技术通道。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能实测与深度解析简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# Chrome DevTools Protocol (CDP)

## 基本定位

Chrome DevTools Protocol（简称 CDP）是 Google 为 Chrome 浏览器开放的调试协议，基于 WebSocket 通信。它允许第三方工具以编程方式访问浏览器内部状态，执行页面导航、DOM 查询、JavaScript 注入、鼠标/键盘事件模拟等操作。Codex Chrome 插件正是通过 CDP 连接实现计算机使用（Computer Use）。

## 核心特征/能力

1. **标签页管理**：创建新标签页、切换标签页、关闭标签页，并能在新标签页中加载任意 URL。
2. **DOM 操作**：读取渲染后的 DOM 树、查询元素属性、高亮元素、触发点击/输入事件。
3. **网络监控**：拦截网络请求、读取响应体、模拟慢速网络等。
4. **输入模拟**：模拟鼠标移动、点击、键盘输入，支持精确坐标和元素选择器。
5. **JavaScript 执行**：在页面上下文中执行任意 JavaScript 代码并获取返回结果。

## 应用场景

- **后台自动化**：Codex 插件在后台创建独立标签页，通过 CDP 执行页面操作而不干扰用户前台任务。
- **DOM 数据提取**：当服务器抓取被防火墙拦截时，通过 CDP 读取浏览器渲染后的 DOM 获取数据。
- **跨代理隔离**：每个子代理使用独立的 CDP 连接，拥有独立的标签页和上下文。

## 关系网络

- **被 [[Codex-Chrome插件]] 使用**：插件通过 CDP 连接实现底层浏览器控制。
- **作为 [[计算机使用]] 的技术基础**：CDP 提供了操控浏览器的具体手段。
- **由 Chrome 浏览器提供**：是 Chrome 内置协议，非第三方工具。

## 关键事件/里程碑

- **长期存在**：CDP 已存在多年，早期主要用于 Chrome DevTools 和 Puppeteer 等工具。
- **2026年**：被 Codex 插件首次大规模用于 AI 代理的计算机使用场景，展现其多功能性。

## 出现的视频来源

- [[sources/Codex-Chrome-插件功能实测与深度解析简报]]
