---
title: Cron 计划任务
type: concept
tags: [automation, hermes-agent, scheduling]
summary: Hermes Agent 内置的定时任务系统，支持自然语言设定。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Cron 计划任务

## 定义

Cron 计划任务是 Hermes Agent 内置的自动化调度系统，用户可以通过自然语言设定定时任务（如“每天早上8点发送日报”）。系统每 60 秒检查一次条件，在隔离会话中运行任务，结果可推送到 Telegram、Discord 等平台。

## 在本库的具体例子

在 [[Hermes-Agent-与-OpenClaw-深度对比简报]] 中，Cron 计划任务被列为 Hermes Agent 的自动化能力之一，与 OpenClaw 的静态调度形成对比。

## 技术实现细节

Hermes Agent 维护一个任务队列，每个任务包含触发条件（cron 表达式或自然语言解析）和执行脚本。系统后台线程每 60 秒扫描队列，匹配当前时间的任务，在隔离环境中执行并记录结果。

## 与近似概念的边界

- **系统 Cron**：系统 Cron 需要手动编辑 crontab，Hermes 支持自然语言。
- **定时触发器**：定时触发器是单一事件，Cron 计划任务支持周期性执行。

## 关联概念

- [[远程调用]]
- [[五层防御安全模型]]

## 关联实体

- [[hermes-agent]]
