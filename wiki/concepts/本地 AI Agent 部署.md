---
title: "本地 AI Agent 部署"
type: concept
tags: [deployment, local-ai, agent, opensource]
summary: "在本地硬件上部署开源 AI 模型的完整方法论，涵盖环境搭建、模型选择、Agent 配置和远程接入，实现零成本的私有 AI 服务。"
sources:
  - raw/notebooklm-analysis/Kh8tGD5liwo-Hermes-Qwen3-6-本地最强-Agent-组合部署简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-本地-AI-Agent-部署简报-Hermes-与-Qwen-3-6-组合方案.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

## 定义

本地 AI Agent 部署是在用户自有硬件上部署开源 AI 模型并构建完整 Agent 服务的方法论。其核心价值在于零成本 Token 自由、完全的数据隐私保护和 24 小时在线运行能力。

## 在本库的具体例子

- **Hermes + Qwen3.6 组合方案**：通过 Windows 11 + WSL (Ubuntu 24.04) + Llama-cpp + Qwen 3.6 27B + Hermes Agent 的完整架构，实现消费级显卡（24GB 显存）上约 40 Tokens/s 的本地 AI 服务（参见 [[Hermes + Qwen3.6 本地最强 Agent 组合部署]]）
- 通过对接 Telegram Bot，实现手机端远程调用和定时任务自动化

## 关联概念

- [[Llama-cpp 推理框架]]：推荐使用的本地推理引擎
- [[WSL 部署]]：Windows 环境下运行 Linux AI 工具链的桥梁
- [[Agent 执行循环]]：Hermes Agent 的核心编排机制

## 关联实体

- [[Hermes Agent]]：Agent 层负责多端接入和任务编排
- [[Qwen 3.6]]：推荐的本地推理模型
