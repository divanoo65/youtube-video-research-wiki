---
title: 零成本本地 AI Agent 部署简报：Hermes 与 Qwen3.6 的深度整合方案
type: source
tags: [hermes-agent, qwen3.6, 本地部署, 零成本, AI助手]
summary: 基于 Qwen3.6 开源模型与 Hermes Agent 的完全本地化、隐私安全且零成本的 24 小时在线 AI 助手部署方案。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
  - raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
video_url: https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh
mindmap: raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.json
---

# 零成本本地 AI Agent 部署简报：Hermes 与 Qwen3.6 的深度整合方案

- 视频：https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh
- 思维导图：[[零成本本地-AI-Agent-部署简报|查看脑图]]

## 执行摘要

本视频基于"零度解说"的技术方案，详细分析了如何利用开源模型 Qwen3.6 与 Hermes Agent 构建一个完全本地化、隐私安全且零成本的 24 小时在线 AI 助手系统。该组合的核心优势在于"TOKEN 自由"与"数据隐私"，用户无需支付月费即可在本地处理自动化任务、编写代码及进行复杂逻辑推理。通过 WSL2 (Ubuntu 24.04) 环境及 Llama-cpp 推理框架，该系统支持从 0.8B 到 27B 不同参数规模的模型。

## 核心要点

1. **零成本 TOKEN 自由**：完全本地部署，无需 API 调用费用，数据隐私完全掌握在自己手中。
2. **Llama-cpp 方案首选**：放弃 vLLM 或 DeepSpeed，选择更稳定、防爆显存的 Llama-cpp 推理框架。
3. **硬件适配广泛**：支持 Qwen 模型从 0.8B 到 27B 不同参数规模，适应入门级笔记本到高端工作站。
4. **27B 模型性能**：在 24G 显存环境下可达约 40 Tokens/s，实现"秒出"结果。
5. **深度思考模式**：默认开启，但对 Agent 任务建议关闭以获得更快的响应速度。
6. **Telegram 远程控制**：通过对接 Telegram 机器人实现手机随时随地发起任务。
7. **WSL2 环境**：Windows 系统通过 WSL2 (Ubuntu 24.04) 搭建完整 Linux 运行环境。
8. **开机自启**：配置文件自启动脚本，使其成为 24 小时在线的本地服务端。
9. **Hermes 集成**：设置自定义 API 指向本地 `localhost:8080/v1`，Api Key 随意填写。
10. **国内下载优化**：推荐使用 ModelScope（魔搭社区）镜像加速模型下载。

## 关联实体

- [[hermes-agent]] — Agent 框架
- [[qwen3.6]] — 核心推理模型

## 关联概念

- [[Token自由]] — 零成本运行的核心价值
- [[本地部署]] — 完全本地化的基础架构
- [[Llama-cpp]] — 推理框架选择
- [[WSL2部署]] — Windows 环境依赖
- [[全天候AI助手]] — 最终产品形态
