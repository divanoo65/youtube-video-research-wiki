---
title: Gemini 1.5 Flash
type: entity
tags: [model, google, cost-effective]
summary: Gemini 1.5 Flash 是 Google 推出的低成本、低延迟大语言模型，具备高性能表现，被推荐作为 Hermes Agent 的副模型以节省 Token 消耗。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Gemini 1.5 Flash

## 基本定位
Gemini 1.5 Flash 由 Google 开发，是 Gemini 1.5 系列中的轻量级、低成本模型，专为高吞吐、低延迟场景设计。在本视频中，它被推荐作为 Hermes Agent 的默认副模型，处理所有辅助任务，以显著降低 Token 消耗。

## 核心特征/能力
1. **低成本**：API 定价远低于 Gemini 1.5 Pro 等高端模型，适合批量处理辅助任务。
2. **低延迟**：响应速度快，适合需要及时反馈的任务批准、上下文压缩等。
3. **高性能**：尽管成本低，但在辅助任务（批准、压缩、记忆刷新、MCP 调用、视觉、网页工具）上的表现已被验证足够。
4. **Google 生态**：通过 Google AI Studio 或 Vertex AI 提供 API，兼容 OpenAI 格式。
5. **长上下文支持**：支持 1M token 上下文窗口（需确认，但 Flash 可能有限），至少能处理常见辅助任务输入。

## 应用场景
1. **Hermes Agent 副模型**：用于统一处理所有辅助任务，包括任务批准、上下文压缩、记忆刷新、MCP 调用、会话搜索、视觉处理、网页工具使用。
2. **低成本批量推理**：适合大量简单的文本生成、分类、提取等任务，如数据清洗、简单问答。
3. **实时对话系统**：低延迟特性适合需要快速响应的聊天场景。

## 关系网络
- [[Hermes-Agent-赫美斯]] — 被配置为 Hermes 的副模型，共同构成主副模型架构。
- [[主副模型架构]] — Gemini 1.5 Flash 是该架构中副模型的典型实例。
- [[Ollama]] — 未直接相关，但都是低成本模型选项（Ollama 提供开源模型免费使用）。

## 关键事件/里程碑
- 在 Hermes 社区中被推荐为副模型的统一选择，大幅降低 Token 消耗。

## 出现的视频来源
- [[Hermes-Agent高级配置指南]]
