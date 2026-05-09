---
title: Llama-cpp
type: entity
tags: [inference-engine, open-source, cpp, gguf]
summary: 基于 C++ 的高效 LLM 推理引擎，支持 CUDA 加速和 GGUF 模型格式，是本地部署 Qwen 3.6 的首选后端。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Llama-cpp 是一个轻量级、高性能的 C++实现 LLM 推理引擎，支持多种量化格式（尤其是 GGUF）。在本地部署场景中，它替代了显存要求高的 vLLM 和 DeepSpeed，成为家用显卡的首选。

## 核心特征/能力

1. **CUDA 加速**：通过重新编译支持 NVIDIA GPU 推理，充分发挥本地显卡算力。
2. **GGUF 格式支持**：原生支持 GGUF 量化模型，压缩模型体积的同时保持推理质量。
3. **低资源消耗**：相比 vLLM，显存占用更低，适合 24G 甚至 12G 显存的消费级显卡。
4. **OpenAI 兼容 API**：提供 `/v1/chat/completions` 接口，可直接对接 Hermes Agent 等框架。
5. **跨平台**：主要用于 Linux 和 WSL2，Windows 原生支持有限。

## 应用场景

- **本地模型服务**：在 WSL2 中启动 Llama-cpp 服务，提供 API 供 Hermes Agent 调用。
- **低成本推理**：在显存受限（如 12G）的环境下运行 4B/9B 模型，仍能获得可用速度。
- **离线开发测试**：无需联网即可验证模型效果，适合隐私敏感的研发场景。

## 关系网络

- [[qwen-3-6]] — 常用推理目标（集成关系）
- [[hermes-agent]] — 通过 API 对接（集成关系）
- [[gguf格式]] — 模型文件格式（依赖关系）

## 关键事件/里程碑

- 2026年：在本地 AI 部署视频中被推荐为首选推理引擎，替代 vLLM。
- 持续更新支持最新的 CUDA 和模型架构。

## 出现的视频来源

- [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]]
