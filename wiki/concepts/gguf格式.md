---
title: GGUF格式
type: concept
tags: [model-format, quantization, llama-cpp]
summary: 一种用于存储量化后的大语言模型权重的高效文件格式，由 Llama-cpp 社区推广，支持多种量化级别。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: medium
reasoning: 视频中提及使用 GGUF 格式的 Qwen 模型，但未深入讲解格式细节。
---

## 定义

GGUF（GPT-Generated Unified Format）是一种用于存储量化大语言模型权重的文件格式，由 Llama-cpp 项目推广。它将模型权重压缩为不同的精度级别（如 q4_0、q4_K_M、q8_0 等），以减小文件大小和显存占用。

## 在本库的具体例子

- 在 [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]] 中，从 ModelScope 下载的 Qwen 3.6 27B 就是 GGUF 格式文件，可以直接被 Llama-cpp 加载运行。

## 技术实现细节

- 文件结构包含元数据（模型配置、分词器）和权重张量。
- 量化方式包括对称量化和非对称量化，常见如 q4_K_M 在显存和推理质量间取得平衡。
- GGUF 的读取速度快，支持内存映射（mmap），无需大量修改模型结构。

## 与近似概念的边界

- **APT 格式**：Hugging Face 的原始格式（SafeTensors 或 PyTorch）通常不量化；GGUF 是专为量化推理设计的格式。
- **AWQ 格式**：AWQ 是另一种量化方案，但主要针对 vLLM 等引擎；GGUF 是 Llama-cpp 生态的标准。

## 关联概念

- [[推理引擎]]
- [[深度思考模式]]

## 关联实体

- [[llama-cpp]]
