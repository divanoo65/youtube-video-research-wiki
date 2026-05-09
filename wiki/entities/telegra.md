---
title: Telegram
type: entity
tags: [platform, messaging, bot]
summary: 支持机器人的即时通讯平台，被用于远程控制本地 Hermes Agent，实现手机端调用 AI 算力。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Telegram 是一个跨平台即时通讯软件，提供丰富的 Bot API，允许开发者创建自动响应消息的机器人。在本地 AI Agent 场景中，Telegram Bot 充当用户与本地模型之间的远程接口。

## 核心特征/能力

1. **Bot API**：通过 BotFather 创建机器人，收发消息、处理命令。
2. **端到端加密**：可选加密通信，保障隐私。
3. **跨平台**：支持手机端、桌面端，方便随时随地访问。
4. **群组集成**：可将 Bot 添加到群组中实现多人协作。
5. **高可靠性**：作为成熟平台，消息投递稳定。

## 应用场景

- **远程 AI 助手**：通过 Telegram 发送指令，让本地 Hermes Agent 执行代码编写、数据查询等任务。
- **定时推送**：结合 Cron 系统，将每日简报自动推送到 Telegram 频道。

## 关系网络

- [[hermes-agent]] — 集成关系（通过 Bot API 对接）

## 关键事件/里程碑

- 2026年：在“零成本本地 AI Agent”视频中作为远程调用通道被推广。

## 出现的视频来源

- [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]]
