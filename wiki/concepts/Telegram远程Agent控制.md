---
title: Telegram 远程 Agent 控制
type: concept
tags: [telegram, remote-control, agent-integration, messaging]
summary: 通过 Telegram Bot 实现对本地 AI Agent 的移动端远程控制与命令下发
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Telegram 远程 Agent 控制

## 定义

Telegram 远程 Agent 控制是指通过集成 Telegram Bot，使用户能够通过手机随时随地给家中的本地 AI Agent 下达指令的控制方式。这是 Hermes Agent 实现"24 小时在线 AI 助手"和移动端 AI 控制的关键集成方案。

## 在本库的具体例子

在 [[零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合]] 中，Telegram 集成通过以下步骤实现：
1. 通过 BotFather 创建机器人并获取 Token
2. 获取个人 Telegram ID 以确保私密使用
3. 在 Hermes Agent 配置中设置 Telegram Token 和 Chat ID
4. 集成后，用户可以在手机上发送消息命令，Agent 在本地执行并返回结果

## 技术实现细节

- Telegram Bot API 为 Hermes Agent 提供消息推送和命令接收的通信渠道
- Agent 将计算核心与用户交互界面彻底解耦——复杂计算在本地高性能设备上完成，简单指令从手机发起
- 结合 Hermes 的内置 Cron 系统，可以定时推送简报等信息

## 与近似概念的边界

- **Telegram 控制 ≠ Web 控制台**：Web 控制台通常需要通过浏览器访问本地地址，Telegram 控制突破局域网限制，实现远程操作。
- **Telegram 控制 ≠ 专用 App**：无需开发专用 App，利用已有的 Telegram 平台实现跨平台远程控制。

## 关联概念

- [[本地AI推理部署]] — 通过 Telegram 调用的本地推理能力
- [[执行循环驱动架构]] — Telegram 消息作为执行循环的输入源之一

## 关联实体

- [[hermes-agent]] — 提供 Telegram 集成能力的框架
- [[qwen-3-6]] — 被远程调用的本地模型
