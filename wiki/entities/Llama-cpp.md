---
title: Llama-cpp
type: entity
tags: [inference-engine, open-source, local-ai, gguf]
summary: 高稳定性的本地大模型推理引擎，被推荐为 Hermes + Qwen 本地部署的首选方案。
sources:
  - wiki/sources/Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报.md
  - wiki/sources/Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Llama-cpp 是一个高稳定性的本地大模型推理引擎，支持 LLM 量化运行与 API 服务提供。在本地 AI Agent 部署中，它取代了 VLLM 和 DeepSpeed，成为首选推理引擎。

## 核心特征

- **高稳定性**：相比 VLLM 和 DeepSpeed，在显存受限环境下不易"爆显存"
- **模型量化**：支持各种规模的 GGUF 格式模型量化运行
- **API 服务**：提供兼容 OpenAI 的 API 接口（localhost:8080/v1）
- **CUDA 加速**：支持 NVIDIA GPU 硬件直通加速

## 关系网络

- 常用组合：[[Hermes Agent]]、[[Qwen]]（本地部署铁三角）
- 对比引擎：VLLM、DeepSpeed（稳定性劣势）
- 相关概念：[[本地AI部署]]
- 视频来源：[[Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报]]、[[Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报]]
