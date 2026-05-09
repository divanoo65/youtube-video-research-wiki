---
title: Llama-cpp
type: entity
tags: [llm-inference, cpp, local, gpu-acceleration]
summary: 高性能 C++ 实现的 LLM 推理引擎，以稳定性和低显存占用著称，是本地 AI Agent 方案的首选推理后端
sources:
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Llama-cpp

## 基本定位

高性能 C++ 实现的大语言模型推理引擎，相比 VLLM 或 DeepSpeed 对显存兼容性更好，运行更稳定，是本地 AI Agent 方案的首选推理后端。

## 核心特征

1. **高兼容性**：对不同显卡硬件兼容性优于 VLLM 和 DeepSpeed
2. **防爆显存**：运行稳定，能有效防止显存溢出
3. **C++ 底层实现**：轻量高效，适合资源受限的本地环境
4. **GPU 加速**：支持 CUDA 硬件加速，充分发挥 N 卡性能

## 关系网络

- 与 [[qwen-3-6]] 配合使用作为推理引擎
- 与 [[hermes-agent]] 组合构建完整本地 Agent 方案
- 替代方案包括 VLLM、DeepSpeed 等

## 出现的视频来源

- [[Hermes + Qwen-3.6 本地最强 Agent 组合部署与应用简报]]
