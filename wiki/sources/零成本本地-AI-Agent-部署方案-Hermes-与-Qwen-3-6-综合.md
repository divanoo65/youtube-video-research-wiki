---
title: 零成本本地 AI Agent 部署方案：Hermes 与 Qwen 3.6 综合简报
type: source
tags: [hermes-agent, qwen, local-deployment, llm, llama-cpp]
summary: 通过结合 Qwen 3.6 模型与 Hermes Agent，在无需任何月费或 Token 费用的前提下构建 24 小时在线、完全受控且高度隐私安全的本地 AI 助手
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.md
  - raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
video_url: https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh
mindmap: raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.json
---

# 零成本本地 AI Agent 部署方案：Hermes 与 Qwen 3.6 综合简报

**视频链接：** [https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh](https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh)

**脑图文件：** `raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.json`

## 执行摘要

当前 AI 领域正朝着本地化、私有化和代理化方向快速演进。通过结合最新开源的 Qwen 3.6 模型与 Hermes Agent，用户可以在无需支付任何月费或 Token 费用的前提下，构建一个 24 小时在线、完全受控且高度隐私安全的本地 AI 助手。该系统在代码编写、中文理解和逻辑推理方面表现卓越，支持通过 Telegram 进行远程调度，实现了"Token 自由"与移动端 AI 控制的结合。

## 核心要点

1. **完全免费开源**：零月费、零 Token 成本，使用本地模型替代云端 API，长期使用成本优势巨大。
2. **数据隐私安全**：所有数据完全掌握在自己手里，适合处理敏感数据或私密任务。
3. **技术栈选择**：选用 Llama-cpp 作为推理后端，优先确保兼容性和防 OOM，而非极限性能。
4. **Qwen 模型灵活性**：提供 0.8B 到 27B 多种参数规模，适配不同显存，人人可参与本地部署。
5. **Hermes Agent 集成**：通过 V1 接口对接本地模型，API Key 可自定义，极大提升灵活性。
6. **Telegram 远程控制**：通过集成 Telegram Bot，实现手机随时随地给本地模型下达指令。
7. **运行效能**：未优化环境下生成复杂程序可达 39.51 Token/秒，优化后预期 50-60 Token/秒。
8. **自动化设置**：支持开机自动启动、定时任务执行，实现 24/7 在线服务。

## 关键引言

> **"真的可以做到 TOKEN 自由。"**
> — 强调本地部署在长期使用成本上的巨大优势。

> **"数据隐私安全，完全掌握在自己手里。"**
> — 明确了该方案对于处理敏感数据或私密任务的核心价值。

> **"普通人很多的任务，都不需要用收费模型，本地模型已经足够使用了。"**
> — 指出本地开源模型在日常办公、简单编程等场景下的实用性已达临界点。

## 关联实体

- [[hermes-agent]] — 部署中使用的 Agent 框架
- [[qwen-3-6]] — 部署中使用的本地模型

## 关联概念

- [[本地AI推理部署]] — 基于 Llama-cpp 的本地推理方案
- [[Telegram远程Agent控制]] — 通过 Telegram 远程操控本地 Agent
- [[本地模型选择策略]] — 根据显存规模选择模型参数
- [[WSL环境搭建]] — WSL+Ubuntu 部署环境的搭建流程

## 脑图核心节点

- 核心特性：完全免费开源、零月费零Token成本、数据隐私本地安全、24小时在线助手
- 环境准备：WSL + Ubuntu 24.04、NVIDIA 驱动直通、CUDA 工具包
- 模型部署：Llama-cpp 方案、Qwen 3.6/3.5 模型选择、关闭深度思考模式
- Agent 部署：Hermes Agent 安装、Base URL 配置、Telegram 集成
- 自动化与优化：开机自启动、定时任务、手机远程对话
