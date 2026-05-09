---
title: 本地 AI 推理部署
type: concept
tags: [local-llm, llama-cpp, inference, deployment]
summary: 使用 Llama-cpp 推理后端在本地部署大语言模型，实现零 API 成本的私有化推理服务
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# 本地 AI 推理部署

## 定义

本地 AI 推理部署是指使用 Llama-cpp 等推理框架在个人电脑上运行大语言模型，无需依赖云端 API。该方案优先确保兼容性和稳定性而非极限性能，能有效防止显存溢出（OOM），适合显存容量有限的个人电脑。配合 Hermes Agent，可以在本地实现完整的 AI Agent 服务。

## 在本库的具体例子

在 [[零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合]] 中，选用 Llama-cpp 作为推理后端，而非 VLLM 或 DeepSpeed。配置方式：通过本地 `http://localhost:8080/v1` 接口与 Hermes Agent 对接，API Key 可自定义为随机字符串。实测生成复杂程序速度达 39.51 Token/秒。

## 技术实现细节

- 下载并根据本地硬件路径重新编译 Llama-cpp
- 根据显存大小选择 Qwen 3.6/3.5 模型（如 27B 版本约 17G）
- 启动模型并开启 8080 端口服务
- 可选禁用"深度思考模式"以加速 Agent 响应
- 通过启动脚本实现开机自动加载模型

## 与近似概念的边界

- **本地推理 ≠ 云端 API**：本地推理无 API 费用但受限于本地硬件，云端 API 成本高但可调用更大模型。
- **Llama-cpp ≠ VLLM/DeepSpeed**：Llama-cpp 优先兼容性（防 OOM），VLLM 和 DeepSpeed 优先性能（高吞吐量）。

## 关联概念

- [[本地模型选择策略]] — 根据硬件选择适合的模型规模
- [[WSL环境搭建]] — 本地部署的环境基础
- [[Telegram远程Agent控制]] — 实现移动端远程使用本地推理能力

## 关联实体

- [[qwen-3-6]] — 本地部署中使用的模型
- [[hermes-agent]] — 对接本地推理服务的 Agent 框架
