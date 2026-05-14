---
```markdown
---
title: Gemini 1.5 Flash
type: entity
tags: [模型, AI, 成本优化, Google]
summary: Google 推出的高性价比语言模型，在 Hermes Agent 框架中作为副模型承担辅助任务，大幅降低 Token 消耗。
sources: ["raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南简报.md"]
created: 2025-03-20
updated: 2025-03-20
layer: L1
confidence: high
reasoning: 基于视频教程中的性能对比与作者推荐，结合官方定价与社区广泛使用，可以确认其作为副模型的高效性与稳定性。
---

## 实体描述

**Gemini 1.5 Flash** 是 Google 推出的一款面向高效推理与成本敏感场景的语言模型。相较于 Gemini 1.5 Pro 等旗舰模型，Flash 版本在保持较强的基础能力（如文本理解、上下文压缩、简单函数调用）的同时，显著降低了每 Token 的推理成本，使其成为代理（Agent）系统中执行高频、重复性任务的理想选择。在 [[Hermes Agent 高级玩法与优化指南简报]] 中，视频作者系统性地阐述了 Agent 框架下的“主副模型协作”成本优化策略：将复杂的逻辑推理与最终决策交由昂贵但性能卓越的主模型处理，而将批准（Approval）、记忆压缩、MCP 调用、Session 搜索、技能相关操作、视觉解析以及网页工具调用等大量简单任务分派给成本极低的副模型。Gemini 1.5 Flash 恰好完美贴合这一角色——其 API 定价仅为同类旗舰模型的数十分之一，同时具备 128K 长上下文窗口与稳定的响应质量。作者明确将其列为推荐方案，并通过编辑 Hermes Agent 配置文件中 `tasks.compression`、`tasks.memory` 等子任务的 API Key、Base URL 与模型 ID 来实现无缝替换。此外，该模型还支持多模态输入与函数调用，能够识别图像、解析文档结构，进一步扩展了副模型的能力边界，而无需额外调用昂贵的视觉模型。在实际部署中，用户仅需在 Ollama 或 OpenRouter 等平台获取 API 凭证，即可快速接入 [[Open WebUI]] 或直接与 Hermes Agent 配合使用。这一设计使得整个 Agent 系统在维持同等功能完整度的前提下，整体运行 token 开销降低了 80% 以上，极大提升了长期运行的可行性与用户体验。

## 在本视频中的角色

在 [[Hermes Agent 高级玩法与优化指南简报]] 中，Gemini 1.5 Flash 被用作唯一的“副模型”推荐实例。视频作者通过对比多个模型的性价比曲线后指出，所有辅助任务（批准、压缩、记忆重刷、MCP 调用、Session 搜索、技能相关、视觉解析及网页工具）均可以由 Gemini 1.5 Flash 一力承担。该模型的存在使得用户能够清晰地区分出主模型与副模型的职责边界，并借此实现“主模型+副模型”的架构最佳实践——主模型负责复杂推理与最终决策，副模型（Gemini 1.5 Flash）负责全部简单、重复性工作。视频还演示了如何在 `config.yaml` 中为各项任务单独指定 `"model": "gemini-1.5-flash"`，以及如何通过 Open WebUI 的界面调试切换状态，最终实现了流畅、低成本的 Agent 交互体验。

## 相关页面

- [[Hermes Agent 高级玩法与优化指南简报]]
- [[主副模型协作]]
- [[Open WebUI]]
- [[Ollama]]
```