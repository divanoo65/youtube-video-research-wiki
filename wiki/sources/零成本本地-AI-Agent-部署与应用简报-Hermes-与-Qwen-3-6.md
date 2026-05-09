---
title: 零成本本地 AI Agent 部署与应用简报：Hermes 与 Qwen 3.6 组合深度解析
type: source
tags: [hermes-agent, qwen3.6, local-ai, deployment]
summary: 详细阐述基于 Qwen 3.6 与 Hermes Agent 的零成本本地 AI 解决方案，通过 WSL2、Llama-cpp 实现完全免费、无限 Token 的 AI 使用体验，并支持 Telegram 远程调用。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
video_url: https://youtu.be/Kh8tGD5liwo
mindmap: raw/notebooklm-mindmaps/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.json
---

## 执行摘要

本报告提供基于 Qwen 3.6 与 Hermes Agent 的本地 AI 解决方案，完全免费、无限 Token，保护数据隐私。通过 WSL2 + Llama-cpp 后端在 Windows 上部署 Qwen 3.6 27B 模型，结合 Hermes Agent 框架和 Telegram 机器人，实现手机端远程调用本地算力。测试显示 24G 显存下生成速度约 40-60 Token/s，足以应对日常编程和办公需求。

## 核心要点

1.  **零成本**：完全免费，免除 API 调用费用，实现 Token 自由。
2.  **隐私安全**：所有数据在本地处理，不上传云端。
3.  **技术架构**：Windows + WSL2 (Ubuntu 24.04) + Llama-cpp + Qwen 3.6 + Hermes Agent。
4.  **模型选择**：主力 Qwen 3.6 27B (GGUF)，显存不足时可降级 Qwen 3.5 小参数模型。
5.  **推理速度**：27B 模型在 24G 显存下约 40 Token/s，优化后可达 50-60 Token/s。
6.  **模式切换**：默认开启深度思考模式，对接 Agent 时应关闭以提升速度。
7.  **远程调用**：通过 Telegram 绑定 Hermes Agent，手机端可远程执行代码、自动化任务。
8.  **持久运行**：编写启动脚本实现开机自启，成为 24 小时在线助理。
9.  **部署流程**：WSL 安装 → 显卡驱动更新 → CUDA 工具包 → 编译 Llama-cpp → 下载模型 → 启动服务 → 配置 Hermes。
10. **硬件适配**：显存低于 12G 建议使用 4B/9B 模型，避免爆显存。

## 关键引言

> “关键是完全免费，真的可以做到 TOKEN 自由。”
> *— 强调本地部署的核心优势。*

> “虽然收费模型原则上更强，但普通人很多的任务都不需要用收费模型，本地模型已经足够使用了。”
> *— 对本地模型实用性的客观定位。*

> “关闭深度思考模式以后，更适合对接 Hermes Agent，速度会更快。”
> *— 技术优化建议。*

> “这才是很多人真正需要的 AI Agent，完全可控，本地离线使用。”
> *— 强调数据隐私安全与掌控权。*

## 脑图核心节点

- 本地最强AI Agent组合 (Hermes + Qwen)
  - 核心架构
    - 模型层：Qwen3.6 (27B)
    - Agent层：Hermes Agent
    - 运行环境：WSL2 (Ubuntu 24.04)
    - 后端框架：Llama-cpp
  - 主要优势
    - 完全免费
    - 无限Token
    - 隐私安全
    - 24小时在线助手
    - 支持远程对话 (Telegram)
  - 部署步骤
    - 环境准备
    - 模型部署
    - Agent配置
    - 自动化设置
  - 功能应用
    - 代码编写
    - 自动化任务
    - 逻辑推理
    - 中文理解
    - 定时任务执行

## 关联实体

- [[hermes-agent]]
- [[qwen-3-6]]
- [[llama-cpp]]
- [[telegram]]

## 关联概念

- [[深度思考模式]]
- [[推理引擎]]
- [[gguf格式]]
- [[wsl2]]
