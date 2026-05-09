---
title: Qwen
type: entity
tags: [llm, open-source, alibaba, chinese-model]
summary: 阿里通义千问（Qwen）3.6 开源大语言模型，以本地 AI Agent 组合部署中实现零成本与无限 Token 为特色。
sources:
  - wiki/sources/Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报.md
  - wiki/sources/Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Qwen（通义千问）3.6 是阿里巴巴开发的开源大语言模型系列，提供从 0.8B 到 27B 多种参数规模。与 Hermes Agent 组合使用被视为当前本地运行 AI 助手的最优方案之一。

## 核心特征

- **多规模选择**：提供 0.8B、2B、4B、9B、27B 等多种参数版本
- **优秀性能**：27B 模型在消费级硬件上可达 40-60 tokens/s
- **中文能力强**：在中文理解、代码生成和逻辑推理方面表现突出
- **显存适配**：24G 显存可流畅运行 27B 版本

## 关系网络

- 常用组合：[[Hermes Agent]]（本地 Agent 框架）
- 推理引擎：[[Llama-cpp]]
- 相关概念：[[本地AI部署]]、[[Token自由]]
- 视频来源：[[Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报]]、[[Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报]]
