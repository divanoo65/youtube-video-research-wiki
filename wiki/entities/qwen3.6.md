---
title: Qwen3.6
type: entity
tags: [llm, open-source, alibaba, chinese-model]
summary: 阿里通义千问最新开源大模型，支持从 0.8B 到 27B 多参数规格，与 Hermes Agent 组合实现零成本本地 AI 部署。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Qwen3.6

## 基本定位

Qwen3.6 是阿里通义千问（Qwen）系列最新开源大模型，支持从 0.8B 到 27B 多种参数规格，可配合 [[hermes-agent]] 实现完全本地化的 AI 助手系统。

## 核心特征

- **多参数规格**：0.8B、2B、4B、9B、27B 等多种版本，适配不同显存配置
- **本地推理性能**：27B 版本在 24G 显存下可达约 40 Tokens/s
- **中文理解优秀**：即使小参数模型在中文理解上依然表现优异
- **深度思考模式**：默认开启，但对 Agent 任务建议关闭以提升速度
- **开源免费**：可下载本地部署，无需 API 调用费用
- **国内镜像加速**：可通过 ModelScope（魔搭社区）快速下载

## 关系网络

- 可搭配 [[hermes-agent]] 实现完整本地 AI Agent 方案
- 与 [[gpt-5.5-instant]] 同为 LLM 代表（开源 vs 闭源）
- 通过 Llama-cpp 推理框架运行

## 出现的视频

- [[零成本本地-AI-Agent-部署简报]]
