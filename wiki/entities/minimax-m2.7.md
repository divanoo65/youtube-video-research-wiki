---
title: MiniMax M2.7
type: entity
tags: [model, ai, llm, cloud, free]
summary: MiniMax 推出的云端免费模型，通过 Ollama 可直接调用，无需本地 GPU 资源
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# MiniMax M2.7

## 基本定位
MiniMax 推出的云端免费模型（M2.7），在 [[ollama]] 中作为带"Cloud"标识的免费模型提供，用户无需本地 GPU 资源即可使用。

## 核心特征/能力
1. **完全免费**：作为云端免费模型，无需付费即可使用，适合预算有限的用户
2. **零本地资源占用**：不需要本地 GPU 或大量 RAM，所有计算在云端完成
3. **一键部署**：通过 [[ollama]] 内置命令即可选择并使用，无需额外配置
4. **适合轻度任务**：适合不需要高强度计算能力的日常 AI 任务

## 应用场景
1. 通过 [[ollama]] 选择 Cloud 模型直接使用，无需本地硬件投入
2. 作为 Hermes Agent 的轻量级云端后备模型

## 关系网络
- [[ollama]] — 通过 Ollama 内置命令调用
- [[hermes-agent]] — 可对接作为 Agent 的 LLM 后端

## 出现的视频来源
- [[hermes-agent-高级玩法与优化指南-深度简报]]
