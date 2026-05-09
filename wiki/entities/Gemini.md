---
title: Gemini
type: entity
tags: [gemini, google, ai-model, llm]
summary: Google 开发的大语言模型系列，本视频中推荐使用 Gemini 1.5 Flash 作为 Hermes Agent 的副模型。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Gemini

## 基本定位

Gemini 是 Google 推出的大语言模型系列，涵盖多个规模。在本视频中，Gemini 1.5 Flash 因其低成本和足够的能力被推荐作为 [[Hermes-Agent]] 的副模型，专门处理辅助任务（批准、压缩、MCP 调用等）。

## 核心特征/能力

1. **低成本**: Gemini 1.5 Flash 的 API 价格远低于高端模型，适合高频简单任务。
2. **高速推理**: 具有较快的生成速度，适合用于批准、压缩等实时性要求高的辅助任务。
3. **多模态支持**: 原版支持图像、音频、视频输入，但本视频中主要使用其文本能力。
4. **广泛兼容性**: 可以通过 OpenAI 兼容 API 或 Google AI API 调用。
5. **在辅助任务中表现足够**: 实测表明，Gemini 1.5 Flash 在批准、压缩、MCP 调用等任务上的表现与昂贵模型相当。

## 应用场景

1. **Hermes Agent 副模型**: 承担 Approval、Compression、Refresh Memory、MCP 调用、Web Search、Visual 等任务。
2. **低成本批量处理**: 企业用于处理大量简单查询，节省 Token 预算。

## 关系网络

- [[Hermes-Agent]] — **推荐使用**: 作为副模型与 Hermes Agent 搭配使用，降低总成本。

## 关键事件/里程碑

- **本视频中的实测推荐**: 通过实际运行证明 Gemini 1.5 Flash 足以胜任辅助任务。

## 出现的视频来源

- [[Hermes-Agent-高级玩法与部署优化简报]]
