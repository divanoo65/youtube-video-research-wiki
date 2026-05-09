---
title: Gemini 2.0 Flash
type: entity
tags: [model, ai, llm, google]
summary: Google 推出的轻量级高性能模型，被 Hermes Agent 推荐作为副模型（辅助模型）以降低 Token 消耗
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Gemini 2.0 Flash

## 基本定位
Google 推出的 Gemini 2.0 Flash 模型，以低成本和较快响应速度著称。在 [[hermes-agent]] 的生态中被官方推荐作为副模型（辅助模型）使用，用于处理审批、压缩、记忆刷新等辅助任务。

## 核心特征/能力
1. **成本效益高**：相比主模型（如 deepseek-chat）显著降低 Token 消耗，适合大批量辅助任务调用
2. **响应速度快**：作为轻量模型，首字延迟和生成速度均优于大规模参数模型
3. **辅助任务优化**：在 Hermes Agent 中负责审批（Approval）、压缩（Compression）、记忆刷新等不需强推理的任务
4. **易于集成**：通过 Open WebUI 或 Hermes Agent 配置文件即可切换设置

## 应用场景
1. 作为 [[hermes-agent]] 的副模型，处理审批和记忆刷新等辅助任务（在配置文件中将特定辅助任务模型 ID 设为 `gemini-2.0-flash`）
2. 轻量级问答和文本处理，不需要深度推理的日常任务

## 关系网络
- [[hermes-agent]] — 推荐作为副模型配置
- [[open-webui]] — 可通过 Open WebUI 界面管理模型切换

## 出现的视频来源
- [[hermes-agent-高级玩法与优化指南-深度简报]]
