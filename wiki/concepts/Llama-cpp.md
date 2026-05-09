---
title: Llama-cpp
type: concept
tags: [inference-framework, local-ai, llama-cpp]
summary: 基于 C/C++ 的高性能大语言模型推理框架，专为本地推理优化，支持多种量化格式和硬件加速。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Llama-cpp

## 定义

Llama-cpp 是一个基于 C/C++ 实现的高性能大语言模型推理框架，支持多种量化格式（GGUF），能够在消费级硬件上高效运行大语言模型，相比 vLLM 或 DeepSpeed 更注重稳定性和低显存占用。

## 在本库的具体例子

- **Qwen3.6 本地推理**：在 WSL2 环境下使用 Llama-cpp 运行 Qwen3.6 27B 模型，24G 显存下可达约 40 Tokens/s。
- **防爆显存方案**：视频推荐 Llama-cpp 而非 vLLM 或 DeepSpeed，核心原因是 Llama-cpp 能有效防止显存溢出，对家庭用户硬件更加友好。
- **多规格模型支持**：Qwen3.6 的 0.8B 到 27B 各版本均可在 Llama-cpp 上运行，适配不同显存配置的硬件。

## 关联概念

- [[本地部署]] — Llama-cpp 是本地推理的核心框架
- [[Token自由]] — 通过 Llama-cpp 本地推理实现零费用
- [[WSL2部署]] — Llama-cpp 在 Windows 环境下的运行基础

## 关联实体

- [[qwen3.6]] — 通过 Llama-cpp 运行的典型模型
