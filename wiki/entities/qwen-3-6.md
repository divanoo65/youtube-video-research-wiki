---
title: Qwen 3.6
type: entity
tags: [模型, 通义千问, 开源, 本地部署]
summary: 阿里巴巴通义千问系列大语言模型，27B 版本在 24G 显存环境下表现优异，可作为 Hermes Agent 的本地推理引擎。
sources:
  - raw/notebooklm-analysis/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# Qwen 3.6

## 基本定位

阿里巴巴通义千问系列大语言模型，在中文理解、代码编写及逻辑推理方面表现卓越。27B 版本在 24G 显存环境下表现优异，是构建本地 AI Agent 的推荐推理引擎。

## 核心特征

1. **多尺寸可选：** 提供 0.8B 到 27B 等多种尺寸，适配不同层级的硬件
2. **中文理解优秀：** 在中文语境下表现卓越
3. **代码编写能力：** 代码编写能力强，适合本地编程任务
4. **推理性能：** 27B 在本地可达约 40 Token/s，优化后可达 60 Token/s
5. **显存要求：** 27B 约需 17G 显存

## 与相关实体的关系

- [[hermes-agent]] — 可与 Hermes Agent 配合构建本地 AI 智能体环境
- [[llama-cpp]] — 通过 Llama-cpp 框架实现推理加速

## 出现的视频来源

- [[基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指]]
