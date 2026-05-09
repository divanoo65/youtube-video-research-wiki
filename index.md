# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-09 | Total pages: 9

## Sources
- [[sources/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报|Hermes + Qwen 3.6 本地最强 Agent 组合部署与应用简报]] — 本视频详细介绍了基于 Hermes Agent 与 Qwen 3.6 大语言模型的本地化 AI 部署方案，实现零成本、隐私安全的 24 小时在线 AI 助手。

## Entities
- [[entities/llama-cpp|llama-cpp]] — Llama-cpp 是一个基于 C++ 的高性能大语言模型推理引擎，以稳定性著称，支持 GPU 加速和多种模型格式，是本地 AI 部署的核心组件。
- [[entities/qwen-3-6|qwen-3-6]] — Qwen 3.6 是阿里巴巴推出的 Qwen 系列大语言模型之一，在中文理解、逻辑推理和代码编写方面表现卓越，提供从 0.8B 到 27B 多种尺寸。
- [[entities/telegram-bot|telegram-bot]] — Telegram Bot 是 Telegram 平台上的自动聊天机器人，用于远程控制本地 Hermes Agent，实现手机端与本地 AI 交互。
- [[entities/wsl|wsl]] — Windows Subsystem for Linux (WSL) 是 Windows 上的 Linux 运行环境，本方案使用 WSL (Ubuntu 24.04) 作为 AI 服务的部署基础。

## Concepts
- [[concepts/auto-start|auto-start]] — 开机自启动指配置系统在启动时自动运行 AI 服务（如 Llama-cpp 和 Hermes Agent），确保 24 小时在线的可用性。
- [[concepts/deep-think-mode|deep-think-mode]] — 深度思考模式是大语言模型的一种推理模式，允许模型进行更深入的计算以获得更准确的答案，但会增加延迟；可在快速任务中关闭以提升速度。
- [[concepts/model-compilation-optimization|model-compilation-optimization]] — 模型编译优化指通过重新编译 Llama-cpp 或其他推理引擎，使其针对当前硬件配置进行优化，从而提升推理性能。
- [[concepts/remote-telegram-control|remote-telegram-control]] — 远程 Telegram 控制指通过 Telegram Bot 的 API 接口，实现对本地部署的 AI Agent 的远程消息交互和任务管理。

## Comparisons

## Overview

## Queries
