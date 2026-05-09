---
title: Hermes Agent
type: entity
tags: [ai-agent, nous-research, 架构]
summary: Hermes Agent 是由 Nous Research 开发的自托管智能体框架，具有执行循环驱动架构和程序化知识生成能力。
sources: [raw/notebooklm-analysis/NbldZVdusKo_d24ec914-e7e1-4097-b8ee-574598890508_20260509T010454Z_report.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本信息与定位
Hermes Agent 是由 Nous Research 开发的自托管智能体框架，旨在从被动执行工具升级为自我进化实体。

## 核心能力/特征
- 执行循环驱动架构：将智能体自身的循环定义为同步编排引擎。
- 程序化知识生成：能根据执行经验自动将复杂工作流抽象为可复用的程序流程（Skills）。
- 四层结构化记忆体系：核心持久记忆、会话历史记忆、扩展记忆层、程序性记忆。
- 五层安全防护模型：包括用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描，并具备 SSRF 防护及网站黑名单功能。
- 自动化 Cron 系统：支持自然语言设定定时任务，每 60 秒检查一次，并在隔离会话中执行。
- 模型无关性：通过 `hermes model` 命令可快速切换 OpenAI、OpenRouter、GLM 等各类模型服务。
- 专业交互环境：内置 TUI 支持多行编辑、命令补全及流式输出。

## 关键事件或里程碑
- 2024：由 Nous Research 发布初版。
- 2025：引入程序化知识生成机制。
- 2026：内置五层安全防护模型和自动化 Cron 系统。

## 与其他实体的关系
- [[OpenClaw]]：竞争对手，架构为中心化 Gateway 网关。
- [[Nous Research]]：开发公司。
- [[ACP协议]]：Hermes Agent 中的通信协议之一。
- [[EvoMap]]：涉及争议的开源项目，被指 Hermes 借鉴其架构设计。

## 出现的视频来源
- [[NbldZVdusKo-智能体架构的范式转移-Hermes-Agent-与-OpenClaw-深度技术简报]]：详细对比了 Hermes Agent 与 OpenClaw 的技术差异。

> 本页面内容基于 raw/notebooklm-analysis/NbldZVdusKo_d24ec914-e7e1-4097-b8ee-574598890508_20260509T010454Z_report.md，仅作 L1 事实层整理。