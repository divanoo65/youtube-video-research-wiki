---
title: "DOM渲染抓取"
type: concept
tags: [data-scraping, bypass, dom, chrome-extension]
summary: DOM渲染抓取是指 AI 代理通过读取浏览器渲染后的 DOM 树（即可视化页面结构）来获取数据，而非直接请求原始 HTML 接口，从而绕过服务器端防护手段。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能特性与实测深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# DOM 渲染抓取

## 定义

DOM 渲染抓取是一种**绕过站点安全策略的技术**。当传统服务器端 HTTP 请求被防火墙或反爬机制拦截时，AI 代理模拟真实用户访问网页，待浏览器完成页面渲染后，通过 Chrome DevTools Protocol 直接获取最终渲染后的 DOM 树结构，从中提取所需信息。因为该方式与正常用户浏览行为几乎一致，所以很难被简单的反爬识别。

## 在本库的具体例子

在 [[sources/Codex-Chrome-插件功能特性与实测深度简报]] 中，演示了**抓取 Simo 博客的 121 条内容** 的过程。该博客站点对直接服务器端抓取请求返回了防火墙拦截。Codex Chrome 自动切换策略，通过浏览器渲染后的 DOM 树获取数据，并不断切换页面读取更多上下文，最终成功提取了 14 篇正式文章的要点，用时约 3 分钟。

## 技术实现细节

- Codex 通过 CDP 的 `Runtime.evaluate` 或 `DOM.getDocument` 等接口获取当前页面的完整 DOM 树。
- 由于 DOM 包含由 JavaScript 动态生成的内容，这种方式能获取到原始 HTML 请求中无法得到的动态数据。
- 代理还可以模拟用户滚动、点击等交互以触发更多内容加载，再逐层获取 DOM。

## 与近似概念的边界

- **服务器端抓取（HTTP GET）**：直接请求服务器 API 或 HTML 页面，容易被防火墙基于请求头、IP 等特征阻拦。DOM 渲染抓取则完全模拟真实浏览器行为。
- **截图 OCR**：另一种绕过手段是对页面截图然后用 OCR 提取文本，但速度慢且不精确。DOM 渲染抓取直接读取结构化 DOM，准确且高效。

## 关联概念

- [[Chrome DevTools Protocol]] — DOM 渲染抓取的核心依赖，提供获取 DOM 的接口。
- [[多标签并行]] — 在多个标签页中可同时进行 DOM 渲染抓取，提升数据采集效率。

## 关联实体

- [[codex-chrome]] — 实现该功能的产品实体。
