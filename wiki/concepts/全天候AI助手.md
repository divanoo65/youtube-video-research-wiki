---
title: 全天候AI助手
type: concept
tags: [ai-agent, always-on, automation]
summary: 通过本地部署 + 开机自启 + 远程控制实现 24 小时在线的个人 AI 助手系统。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 报告中提出该方案定位为"24 小时随时在线"的 AI 助手，属于本地部署方案的终极目标概念。
---

# 全天候AI助手

## 定义

全天候 AI 助手是指通过本地部署、开机自启动脚本和远程控制技术（如 Telegram 机器人），使 AI 智能体系统能够 7×24 小时持续在线运行，用户可随时随地通过手机等设备发起任务和控制。

## 在本库的具体例子

- **Qwen3.6 + Hermes Agent 系统**：配置 Linux 自启动脚本，电脑重启后 AI 服务自动恢复；通过 Telegram 机器人实现远程控制，手机端随时随地发起任务。
- **Hermes Agent 的 cron 系统**：内置自然语言定时任务系统，每 60 秒检查条件，在隔离会话中运行定期报告、数据备份等任务。

## 关联概念

- [[本地部署]] — 全天候运行的物理基础
- [[Token自由]] — 无需持续付费即可使用
- [[WSL2部署]] — Windows 环境下的全天候部署方案

## 关联实体

- [[hermes-agent]] — 实现全天候助手的 Agent 框架
- [[qwen3.6]] — 全天候运行的推理模型
