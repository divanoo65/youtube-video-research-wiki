---
title: Llama-cpp
type: entity
tags: [open-source, inference-engine, local-ai]
summary: 轻量级推理引擎，通过优化编译在低显存设备上运行大模型，防止显存溢出。
sources: [raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Llama-cpp

## 基本定位

Llama-cpp 是一个轻量级推理引擎，专为在消费级 GPU 上运行大语言模型而优化。通过量化编译和内存管理，它能在 24G 甚至更低显存的设备上运行 27B 参数模型，生成速度约 40-60 Token/s，是本地部署方案的核心组件。

## 核心特征/能力

1. **显存优化**：通过量化技术减少模型显存占用，防止爆显存。
2. **跨平台支持**：支持 Linux、Windows（通过 WSL）、macOS。
3. **高性能推理**：在未深度优化的情况下达到 40-60 Token/s 的生成速度。
4. **模型兼容性**：支持多种开源模型格式，如 GGUF。
5. **易于集成**：提供 HTTP API 接口，可对接 Hermes Agent 等前端。

## 应用场景

1. **本地模型部署**：作为 Qwen3.6/3.5 等模型的推理引擎，实现完全本地运行。
2. **开发测试**：在开发环境中快速测试模型性能。
3. **边缘计算**：在资源受限的设备上运行 AI 模型。

## 关系网络

- [[qwen3-6]] — 依赖关系（作为推理引擎）
- [[qwen3-5]] — 依赖关系（作为推理引擎）
- [[hermes-agent]] — 兼容关系（作为后端引擎）

## 关键事件/里程碑

- **持续更新**：作为开源项目，不断优化性能和兼容性。

## 出现的视频来源

- [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报]]
