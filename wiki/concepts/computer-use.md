---
title: Computer Use (计算机使用)
type: concept
tags: [ai-agent, automation, browser-control]
summary: AI 代理直接操控计算机图形用户界面（GUI）执行操作的能力，而非仅通过文本或 API 交互。Codex Chrome 插件通过 CDP 与 MCP 实现了键鼠模拟、页面导航和表单填写等计算机使用场景。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件技术简报-AI-浏览器自动化的深度评测与分析.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# Computer Use (计算机使用)

## 定义

Computer Use 指 AI 代理像人类一样直接操作计算机界面的能力：移动鼠标、点击按钮、输入文本、滚动页面、复制粘贴等，而不是通过 API 调用或结构化数据交换。它要求代理理解屏幕内容（DOM 或视觉图像）、规划动作序列并执行细粒度操作。

## 在本库的具体例子

在 [[Codex-Chrome-插件功能实测与深度解析简报]] 中，Codex 插件展现了多个 computer use 实例：
- 自动登录报销系统，在表单中选择报销类别、上传附件、提交表单，完全模拟人类操作。
- 在在线画图房间中，代理控制鼠标选择画布、选择颜色、绘制图形。
- 在 ChatGPT 官网中，代理自行输入提示词并点击生成按钮，完成提示词优化。

## 技术实现细节

1. **底层控制**：Codex 通过 [[chrome-devtools-protocol]] (CDP) 获取浏览器的 DOM 树，并将元素坐标映射为鼠标点击位置；通过 Input.dispatchMouseEvent 模拟点击。
2. **视觉反馈**：代理可以读取渲染后的 DOM，也可以根据屏幕截图判断 UI 状态（未来可能结合视觉模型）。
3. **多步骤规划**：将复杂任务分解为“打开页面→定位输入框→输入文字→点击提交→等待结果”等原子动作。

## 与近似概念的边界

- **与 API 自动化区别**：API 自动化通过编程接口直接获取数据，速度快但依赖平台开放；Computer Use 模拟人类操作，可工作于任何 GUI 应用，但速度较慢且受站点安全策略限制。
- **与 RPA (机器人流程自动化) 区别**：RPA 通常使用固定脚本操作桌面软件，缺乏 AI 决策能力；Computer Use 结合 LLM 的推理能力，能应对未预定义的动态页面。

## 关联概念

- [[multi-tab-parallel-processing]] — 多个 Computer Use 代理可同时在独立标签页运行。
- [[dom-rendered-data-extraction]] — Computer Use 中从渲染 DOM 获取数据的子能力。
- [[end-to-end-automation]] — Computer Use 用于串联多个应用的闭环流程。

## 关联实体

- [[codex-chrome-plugin]] — 实现 Computer Use 的典型实体。
- [[gpt-5.5]] — 提供规划与决策的模型。
