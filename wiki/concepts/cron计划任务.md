---
title: Cron计划任务
type: concept
tags: [automation, hermes-agent, scheduling]
summary: Hermes Agent 内置的定时任务系统，支持自然语言设定计划，每 60 秒检查一次，在隔离会话中自动执行。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛.md
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 两个视频均提及 Hermes Agent 的 Cron 功能，且行为描述一致。
---

## 定义

Cron计划任务是 Hermes Agent 内置的一套定时自动化引擎。用户可以用自然语言描述（如“每天早上8点发送天气报告”），系统自动转换为 Cron 表达式并执行，每 60 秒轮询一次。

## 在本库的具体例子

- 在 [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]] 中，用户通过 Telegram 告诉 Hermes “每天下午6点检查我的 GitHub 未读通知”，系统自动创建定时任务并按时执行。

## 技术实现细节

- 使用 Linux 系统 Cron 工具作为底层调度器，但通过 Hermes 的封装支持自然语言解析。
- 每个定时任务在一个独立的会话中运行，避免干扰主对话状态。
- 任务执行结果可配置为通过 Telegram 推送。
- 系统支持暂停、修改、删除任务，均通过自然语言接口操作。

## 与近似概念的边界

- **Linux Cron**：传统 Cron 需要手动编辑 crontab 文件，且不支持自然语言。Hermes Cron 提供更高层的抽象。
- **OpenClaw 定时**：OpenClaw 依赖外部工具如 systemd timer，无内置 Cron 集成。

## 关联概念

- [[执行循环]]
- [[五层纵深防御]]

## 关联实体

- [[hermes-agent]]
