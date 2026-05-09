---
title: Llama-cpp
type: entity
tags: [框架, 推理, 开源, 本地部署]
summary: 用于本地 LLM 推理加速的开源框架，以更克制的显存占用防止显存溢出，适合家用级显卡。
sources:
  - raw/notebooklm-analysis/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Llama-cpp

## 基本定位

用于本地大语言模型推理加速的开源框架，相比 VLLM 在显存占用方面更为克制，有效防止显存溢出（OOM），适合大多数家用级显卡。

## 核心特征

1. **显存优化：** 显存占用比 VLLM 更克制，防止 OOM
2. **CUDA 加速：** 支持 CUDA 硬件加速
3. **OpenAI 兼容 API：** 可开启兼容 OpenAI 标准的 API 服务（默认端口 8080），供 [[hermes-agent]] 无缝接入
4. **推理性能：** 配合 [[qwen-3-6]] 27B 可达约 40-60 Token/s

## 与相关实体的关系

- [[hermes-agent]] — 作为 Hermes Agent 的本地推理后端
- [[qwen-3-6]] — 常用推理模型组合

## 出现的视频来源

- [[基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指]]
