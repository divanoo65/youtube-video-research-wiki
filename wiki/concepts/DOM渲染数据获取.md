---
title: DOM渲染数据获取
type: concept
tags: [data-extraction, anti-scraping, browser-rendering]
summary: 当服务器端直接抓取被站点的防火墙或反爬机制拦截时，AI通过浏览器渲染后的DOM（文档对象模型）来获取数据的方法。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能实测与深度解析简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# DOM渲染数据获取

## 定义

DOM渲染数据获取是一种绕过站点反爬虫策略的技术手段。当传统的 HTTP 请求方式（如 fetch 或 axios）被站点防火墙阻断时，AI 代理切换到浏览器环境，通过访问已渲染页面的 DOM 树来提取数据。因为浏览器渲染后的页面已经通过 JavaScript 生成完整内容，且请求来自真实的浏览器环境，所以能避开许多反爬措施。

## 技术实现细节

Codex Chrome 插件利用 CDP 的 `Runtime.evaluate` 或 `DOM.getDocument` 方法从当前标签页的渲染 DOM 中提取结构化数据。具体步骤：
1. AI 发现直接 HTTP 请求返回 403 或被阻塞（如 Cloudflare 防护）。
2. 插件在已存在的浏览器标签页中导航到目标 URL。
3. 等待页面加载完成（包括 JavaScript 生成的动态内容）。
4. 通过 `document.documentElement.outerHTML` 或精确的 XPath 选择器获取所需节点。
5. 将数据返回给 AI 进行后续处理。

## 在本库的具体例子

在 [[sources/Codex-Chrome-插件功能实测与深度解析简报]] 的实测中，评测者尝试总结 Simon Willison 的博客文章时，直接服务器抓取被站点防护拦截。Codex 自动切换策略，从浏览器渲染后的 DOM 获取数据，成功提取文章内容。评测者评论：“它这里说直接服务器抓取站点防护页拦截，但是页面本身是可以访问的，所以 Codex 会从浏览器渲染后的 DOM 获取数据。”

## 与近似概念的边界

- **区别于普通爬虫**：普通爬虫通常仅发送 HTTP 请求解析 HTML，无法执行 JavaScript，而 DOM 渲染数据获取在真实浏览器中执行，能处理 SPA 单页应用。
- **区别于无头浏览器**：无头浏览器（如 Puppeteer）也能渲染 DOM，但 Codex 的优势在于它与用户共享同一个真实的浏览器会话，拥有已登录的 Cookie 和 Session，能访问需要认证的页面。

## 关联概念

- [[计算机使用]] — DOM渲染数据获取是 Computer Use 能力中的一种数据策略。
- [[MCP模型上下文协议]] — 当 DOM 获取也被阻止时，可结合 MCP 转向客户端访问。

## 关联实体

- [[Codex-Chrome插件|Codex Chrome]] — 实现该技术的具体产品。