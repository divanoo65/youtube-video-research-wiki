---
title: 本地AI部署
type: concept
tags: [ai, deployment, local, privacy, self-hosted]
summary: 在本地硬件上部署和运行 AI 模型与 Agent 的方案，核心优势为零成本、无限 Token 和数据隐私安全。
sources:
  - wiki/sources/Hermes + Qwen 3.6 本地最强 AI Agent 组合部署与应用简报.md
  - wiki/sources/Hermes + Qwen3.6 本地 AI Agent 组合部署与应用分析简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 定义

本地AI部署是指在用户自己的硬件设备上部署和运行 AI 模型与 Agent 的方案，无需依赖云端服务。其核心价值包括零月费、无限 Token 使用、数据隐私安全完全由用户掌握，以及 24 小时在线常驻服务能力。

## 本库具体例子

- Hermes Agent + Qwen 3.6 + Llama-cpp 被分析为当前本地运行 AI 助手的最优组合方案
- 基于 Windows + WSL2 + Ubuntu 24.04 实现 24 小时在线的本地 AI Agent 架构
- 通过 Telegram Bot 实现移动端远程调用，解决本地部署的远程访问问题
- 17-24G 显存即可运行 Qwen 27B 模型，消费级硬件门槛低

## 关联概念
- [[Token自由]] — 本地部署带来的核心价值之一
- [[深度思考模式]] — 本地部署中可权衡的模型设置

## 关联实体
- [[Hermes Agent]] — 本地部署的核心 Agent 框架
- [[Qwen]] — 本地部署的核心模型
- [[Llama-cpp]] — 本地部署的核心推理引擎
