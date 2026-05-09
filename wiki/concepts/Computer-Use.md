---
title: Computer Use
type: concept
tags: [ai-capability, browser-automation, agent]
summary: AI直接操作计算机界面的能力，包括控制浏览器、鼠标键盘、文件系统等，是AI从文本对话走向自主操作的重大跨越。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能实测与深度解析简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# Computer Use（计算机使用）

## 定义

Computer Use 是指 AI 代理直接操作计算机用户界面的能力，包括移动鼠标、点击按钮、填写表单、浏览网页、打开应用程序等。它不同于仅通过 API 执行的自动化，而是模拟人类用户的操作方式，能与任何现有界面交互。在 Codex Chrome 插件的语境中，Computer Use 特指 AI 通过浏览器控制 Web 应用。

## 技术实现细节

Codex 的 Computer Use 能力基于两个核心组件：一是 **GPT-5.5 模型**，负责理解当前屏幕状态并决定下一步操作；二是 **CDP（Chrome DevTools Protocol）**，执行具体的 DOM 操作和事件触发。模型会接收页面的 DOM 快照（包括元素坐标、文本、可交互性），输出要执行的动作（如“点击坐标 X,Y 的元素”、“输入文本”）。插件通过 CDP 的 `Input.dispatchMouseEvent` 和 `Input.dispatchKeyEvent` 模拟真实操作。与传统 Computer Use 方案不同，Codex 支持多个代理在多个标签页上并发操作。

## 在本库的具体例子

在 [[Codex-Chrome-插件功能实测与深度解析简报]] 中，Codex 演示了完整的 Computer Use 流程：
- 登录报销系统，点击下拉菜单选择类别，上传 PDF 附件，提交表单。
- 登录京东查询商品价格，模拟滚动和点击“加入购物车”按钮。
- 在小红书编辑器中填写标题、插入图片、点击发布。
这些操作均通过模拟人类交互完成，而非 API。

## 与近似概念的边界

- **区别于 RPA（机器人流程自动化）**：RPA 通常通过录制宏或底层 API 操作，而 Computer Use 基于视觉和语义理解动态适应界面变化。
- **区别于 API 集成**：传统 API 集成只需调用端点，Computer Use 不需要平台提供 API，可以直接操作界面。
- **区别于截图+代码生成**：部分方案仅根据截图生成操作代码，而 Computer Use 使用实时 DOM 状态获得更精确的信息。

## 关联概念

- [[多标签并行处理]] — Codex 将 Computer Use 扩展到了多标签并行场景。
- [[DOM渲染数据获取]] — 在 Computer Use 中，当直接抓取被拦截时，通过 DOM 获取数据。
- [[后台静默运行]] — 使 Computer Use 可以在后台进行，不干扰用户。

## 关联实体

- [[codex-chrome|Codex Chrome]] — 实现 Computer Use 的具体产品。
- [[gpt-5.5|GPT-5.5]] — 为 Computer Use 提供决策能力的 AI 模型。