---
title: Qwen-3.6
type: entity
tags: [llm, open-source, alibaba, local-deployment]
summary: 阿里千问系列最新开源模型，与 Hermes Agent 组合实现本地零成本 AI Agent 方案
sources:
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Qwen-3.6

## 基本定位

阿里巴巴千问（Qwen）系列最新开源大语言模型，与 Hermes Agent 组合构建本地零成本 AI Agent 方案。提供从 0.8B 到 27B 的多种规格适配不同硬件。

## 核心特征

1. **多规格可选**：0.8B、2B、4B、9B、27B 多种规模，适配不同显存容量
2. **高性能推理**：27B 模型在 24GB 显存下可达 40 tokens/s（无干扰预期 50-60 tokens/s）
3. **完全开源**：可本地私有化部署，不依赖云端 API
4. **多平台镜像**：可通过 ModelScope 国内镜像下载，避免境外源不稳定问题
5. **深度思考可关闭**：关闭深度思考模式可显著减少首字延迟，提升 Agent 响应速度

## 关系网络

- 与 [[hermes-agent]] 组合使用构建本地 Agent
- 使用 [[llama-cpp]] 作为推理引擎
- 支持通过 ModelScope 等国内镜像下载

## 出现的视频来源

- [[Hermes + Qwen-3.6 本地最强 Agent 组合部署与应用简报]]
