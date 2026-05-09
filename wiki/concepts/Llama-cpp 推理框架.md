---
title: "Llama-cpp 推理框架"
type: concept
tags: [inference, local-llm, cpp, gpu]
summary: "高性能本地 LLM 推理引擎，通过 C++ 实现和 CUDA 加速在消费级显卡上高效运行各种开源模型。"
sources:
  - raw/notebooklm-analysis/Kh8tGD5liwo-Hermes-Qwen3-6-本地最强-Agent-组合部署简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-本地-AI-Agent-部署简报-Hermes-与-Qwen-3-6-组合方案.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

## 定义

Llama-cpp 是一个高性能的本地 LLM 推理引擎，使用 C++ 实现并支持 NVIDIA CUDA 加速。相比 VLLM 和 DeepSpeed，它在显存管理上更为稳定，能有效防止爆显存，适合不同配置的家用电脑使用。在 24GB 显存环境下运行 Qwen 3.6 27B 模型可达约 40 Tokens/s。

## 在本库的具体例子

- 作为 Hermes + Qwen3.6 本地部署方案的核心推理层，Llama-cpp 配合 CUDA 编译后驱动 27B 模型在消费级显卡上运行（参见 [[Hermes + Qwen3.6 本地最强 Agent 组合部署]]）

## 关联概念

- [[本地 AI Agent 部署]]：Llama-cpp 是本地部署方案中的核心推理引擎
- [[WSL 部署]]：Llama-cpp 在 Windows 上的运行需要 WSL 环境

## 关联实体

- [[Qwen 3.6]]：通过 Llama-cpp 运行的主力推荐模型
- [[Hermes Agent]]：Agent 层通过 API 与 Llama-cpp 推理服务对接
