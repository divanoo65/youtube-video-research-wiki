---
title: DOM-rendered Data Extraction (DOM渲染数据获取)
type: concept
tags: [data-extraction, dom, scraper]
summary: 当服务器端数据抓取被防火墙拦截时，Codex 通过浏览器渲染后的 DOM（文档对象模型）获取数据，绕过反爬机制。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件技术简报-AI-浏览器自动化的深度评测与分析.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# DOM-rendered Data Extraction (DOM渲染数据获取)

## 定义

DOM 渲染数据获取是一种绕过网站反爬机制的技术：当直接通过 HTTP 请求获取页面 HTML 被服务器防火墙拦截时，AI 代理改为打开浏览器实际渲染该页面，然后从浏览器内存中的 DOM 树读取内容。由于浏览器是正常用户环境，防火墙无法区分是真人操作还是 AI 代理，因此数据可被获取。

## 在本库的具体例子

在 [[Codex-Chrome-插件功能实测与深度解析简报]] 中，Codex 尝试总结 Simon Willison 的一篇博客文章时，服务器抓取被拦截。插件自动切换到“从浏览器渲染后的 DOM 获取数据”模式，成功读取了正文内容并生成结构化摘要。实测者评价：“服务器抓取站点防护页拦截，但是页面本身是可以访问的，所以 Codex 会从浏览器渲染后的 DOM 获取数据。”

## 技术实现细节

1. **自动切换逻辑**：Codex 首先尝试 HTTP 请求抓取，如果返回拦截页面，则启动 CDP 打开标签页加载该链接，等待页面渲染完成，然后执行 `document.documentElement.outerHTML` 获取完整 DOM 字符串。
2. **动态内容处理**：对于 JavaScript 动态加载的内容，浏览器渲染后 DOM 包含最终结果，因此也能获取。
3. **性能代价**：浏览器渲染比直接 HTTP 请求慢，但能处理更多反爬场景。

## 与近似概念的边界

- **与传统网络爬虫区别**：传统爬虫使用 HTTP 库（如 requests）直接获取 HTML，易被反爬；DOM 渲染方式使用真实浏览器，更难被识别。
- **与 Webdriver 方式区别**：Webdriver（如 Selenium）也使用浏览器，但通常需要额外配置 headless 模式，且可通过 navigator.webdriver 被检测；Codex 通过 CDP 直接操作，更接近真实用户环境。

## 关联概念

- [[computer-use]] — DOM 渲染数据获取是 computer use 中的关键子能力。
- [[site-security-policy-block]] — 触发 DOM 渲染数据获取的原因（站点安全拦截）。

## 关联实体

- [[codex-chrome-plugin]] — 实现此功能的实体。
- [[chrome-devtools-protocol]] — 提供 DOM 读取接口的协议。
