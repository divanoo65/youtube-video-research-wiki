---
title: "Telegram Bot"
type: entity
tags: [telegram, bot, messaging, remote-access, notification]
summary: "Telegram 平台的 Bot API，在 Hermes Agent 方案中作为手机远程调用本地模型的交互通道，支持 24 小时消息转发与指令执行。"
sources:
  - raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
section: entities
---

# Telegram Bot

## 基本定位
Telegram 平台的自动化 Bot 接口。在 Hermes Agent 方案中，Telegram Bot 是实现手机远程调用的关键通道——用户通过 Bot 发送指令，经由 Telegram 服务器转发到本地 Hermes Agent 执行并返回结果，支持 24 小时全天候远程交互。

## 核心特征/能力

1. **远程交互通道**: 支持手机随时发送指令调用本地模型，实现"不在电脑前也能用"
2. **安全绑定**: 需绑定特定 Telegram ID，防止他人未授权调用本地算力
3. **双向通信**: 用户发送指令，Agent 返回执行结果，支持文件、代码等多格式内容
4. **24 小时在线**: 配合 Hermes 开机自启脚本，实现全时段可用

## 关系网络
- [[hermes-agent]] — 集成的 Agent 框架，提供 Bot 功能
- [[qwen3-6]] — 通过 Bot 调用的底层模型

## 出现的视频来源
- [[Hermes 与 Qwen3.6 本地 AI Agent 部署与应用简报]]
