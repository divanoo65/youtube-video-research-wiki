---
title: Minimax
type: entity
tags:
  - AI模型
  - 多模型分流
  - 成本优化
  - API
summary: Minimax 是一款提供 API 接口的大语言模型，在 Hermes Agent 系统中作为可选的多模型服务之一，常用于辅助任务以平衡性能与成本。
sources:
  - "raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南简报.md"
created: 2025-03-30
updated: 2025-03-30
layer: L1
confidence: high
reasoning: 基于来源报告中的明确提及，Minimax 被列为可注册的 API Key 之一，用于多模型分流配置，属于事实性描述。
---

## 实体描述

Minimax 是一家提供大语言模型 API 服务的平台，其模型在自然语言理解与生成方面表现良好，尤其适合需要平衡推理质量与调用成本的场景。在 Hermes Agent 的架构中，Minimax 被列为可与 Google、OpenRouter 等并列的多模型选项之一。通过将多个 API Key（包括 Minimax）注册到 Agent 的配置文件中，用户可以灵活地将不同类型的任务分配给不同的模型，从而实现性能与成本的优化。例如，可将需要高推理能力的复杂任务交由强模型（如 GPT-4 或 Claude）处理，而将简单辅助任务（如信息提取、分类、摘要）统一设置为 Gemini 1.5 Flash 或同样轻量化的 Minimax 模型，以降低 API 调用费用。Minimax 本身支持标准 OpenAI 兼容接口，接入 Hermes Agent 的过程与配置其他服务类似，只需在 `agent` 配置文件的 API Key 列表中加入对应的密钥即可。由于其性价比和稳定性，Minimax 常被用于需要高频调用的辅助链或大规模自动化工作流中。

## 在本视频中的角色

在关于 Hermes Agent 高级玩法与优化指南的讲解视频中，Minimax 被作为一个具体示例，展示如何通过多模型分流策略来降低运营成本。视频提到在配置文件中注册多个 API Key 时，可以将 Minimax 与 Google、OpenRouter 等并列添加，并在辅助任务配置中将 `model_id` 统一设置为轻量化模型（如 Gemini 1.5 Flash 或 Minimax 自身的轻量版本），从而实现更经济的推理。此外，视频还强调了 Minimax 作为备选模型，在主要 API 出现故障或限流时可自动切换，保证服务的连续性。

## 相关链接

- [[Hermes Agent 高级玩法与优化指南简报]]
- [[Open WebUI]]
- [[Gemini 1.5 Flash]]
- [[OpenRouter]]
- [[主副模型协作]]