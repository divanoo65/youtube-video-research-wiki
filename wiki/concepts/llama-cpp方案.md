---
title: Llama-cpp 方案
type: concept
tags: [inference, optimization, local-ai]
summary: 使用 Llama-cpp 作为推理引擎的本地模型部署方案，防止显存溢出。
sources: [raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Llama-cpp 方案

## 定义

Llama-cpp 方案指使用 Llama-cpp 推理引擎来部署大语言模型的方法，通过量化编译和内存优化，在低显存设备上运行大规模参数模型（如 Qwen3.6 27B），生成速度约 40-60 Token/s，有效防止显存溢出（爆显存）。

## 在本库的具体例子

在 [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报]] 中，推荐使用 Llama-cpp 方案而非 VLLM 或 DeepSpeed，因为后者对显存要求极高，容易爆显存。

## 技术实现细节

Llama-cpp 使用 GGUF 格式的量化模型，通过 CPU+GPU 混合推理和内存映射技术，将模型权重部分加载到显存，部分保留在系统内存，从而在有限显存下运行大模型。编译时需针对特定 GPU 架构优化。

## 与近似概念的边界

- **VLLM**：VLLM 需要更多显存，适合服务器部署；Llama-cpp 适合消费级 GPU。
- **DeepSpeed**：DeepSpeed 是分布式训练框架，Llama-cpp 是推理引擎。

## 关联概念

- [[wsl部署]]
- [[深度思考模式]]

## 关联实体

- [[llama-cpp]]
- [[qwen3-6]]
