---
title: Telegram Bot
type: entity
tags: [messaging, remote-access, automation]
summary: 通过 Telegram Bot 实现远程调用本地 AI Agent 的通信桥梁。
sources: [raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Telegram Bot

## 基本定位

Telegram Bot 是 Hermes Agent 集成的消息平台之一，用户通过 BotFather 创建 Token 并绑定个人 Telegram ID，即可在手机端发送指令，远程调用本地部署的 AI Agent 执行任务。

## 核心特征/能力

1. **远程控制**：突破物理限制，在任何地方通过手机控制本地 AI。
2. **实时推送**：Agent 执行结果可推送到 Telegram 聊天。
3. **定时任务通知**：Cron 任务结果可通过 Bot 发送。
4. **安全绑定**：通过个人 ID 限制访问，防止未授权使用。
5. **多平台支持**：同时支持 Discord、Slack 等。

## 应用场景

1. **远程编程**：在手机上发送编程需求，让本地模型生成代码。
2. **定时任务管理**：设置每日简报、数据备份等任务，通过 Bot 接收结果。
3. **日常问答**：随时随地调用本地模型进行问答。

## 关系网络

- [[hermes-agent]] — 集成关系（作为消息平台）
- [[qwen3-6]] — 间接关系（通过 Hermes 调用）

## 关键事件/里程碑

- **持续使用**：作为 Hermes Agent 的标准集成方式。

## 出现的视频来源

- [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报]]
