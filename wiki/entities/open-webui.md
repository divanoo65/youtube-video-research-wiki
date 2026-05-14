---
title: "Open WebUI"
type: entity
tags:
  - 用户界面
  - AI交互
  - Hermes Agent
  - 会话管理
summary: "Open WebUI 是一个开源的Web用户界面，为AI Agent（如Hermes Agent）提供类ChatGPT的交互体验，支持会话管理、Markdown渲染和模型切换等功能，显著提升用户操作效率与体验质量。"
sources:
  - "raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南简报.md"
created: "2025-02-01"
updated: "2025-02-01"
layer: L1
confidence: high
reasoning: "该实体从简报中提取，作为Hermes Agent增强交互的关键组件，具有明确的功能定位和文档引用，故创建为独立实体。"
---

## 实体描述

Open WebUI 是一个专为大型语言模型（LLM）和AI Agent设计的开源Web用户界面，旨在通过现代化的交互方式提升用户的操作体验。它最初作为Ollama等本地推理引擎的友好前端而开发，后逐渐扩展对多种Agent框架的原生支持，包括Hermes Agent。Open WebUI 提供类似ChatGPT的界面布局，左侧为会话历史侧边栏，支持搜索、重命名、删除历史对话；主区域采用流式输出实时显示模型回复，并完整支持Markdown渲染、代码高亮、LaTeX公式等富文本格式。此外，它还集成了多模型切换、系统提示词编辑、文件上传（用于RAG）以及API密钥管理等高级功能，使得用户无需离开浏览器即可完成从模型选择到对话管理的全部操作。与微信等聊天工具相比，Open WebUI 在会话记录的持久性、搜索的便利性、以及复杂交互（如多轮Agent调用、工具使用结果的展示）方面具有明显优势。其开源特性允许用户自行部署、定制主题和插件，从而适配不同场景下的AI工作流。

## 在本视频中的角色

（注：本报告基于简报文本生成，未提供对应视频。依据简报上下文，Open WebUI 的角色是：作为Hermes Agent的官方推荐交互界面，替代微信等聊天工具，提供专业级的会话管理、历史记录搜索和Markdown渲染功能，使得用户在执行Agent任务（如调用工具、处理长文档、进行多轮对话）时拥有更稳定、更直观的操作环境。它直接提升了Hermes Agent的可用性和用户体验，是打通用户与Agent能力之间的关键视觉层。）

## 相关页面

- [[Hermes Agent 高级玩法与优化指南简报]]
- [[主副模型协作]]