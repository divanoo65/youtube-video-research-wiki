---
title: Qwen 3.6
type: entity
tags: [model, alibaba, llm, open-source]
summary: 阿里通义千问系列大语言模型，与 Hermes Agent 组合可实现本地 AI 部署
sources:
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Qwen 3.6

Qwen 3.6 是阿里通义千问系列的大语言模型。在本地 AI 部署场景中，Qwen 3.6 27B 版本与 [[hermes-agent]] 组合可在 24G 显存环境下实现高效运行，提供每秒约 40 至 60 Token 的响应速度。

## 核心特征

- **本地部署友好**：27B 参数量级适合在消费级 GPU（24G 显存）上运行。
- **Llama-cpp 适配**：通过 Llama-cpp 方案实现稳定推理，放弃可能显存溢出的 VLLM 或 DeepSpeed。
- **多尺寸选择**：小显存可选择 Qwen 3.5 系列的 0.8B、2B、4B 或 9B 版本。
- **深度思考模式**：默认开启深度推理模式，可关闭以提升响应速度。
- **实用性能充足**：代码编写、中文理解、逻辑推理等日常任务表现卓越。

## 关系网络

- 可与 [[hermes-agent]] 组合搭建本地 AI Agent
- 在 [[Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报]] 中被详细介绍
