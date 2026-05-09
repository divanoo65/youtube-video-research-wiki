---
title: "Hermes Agent 与 OpenClaw 深度对比简报"
type: source
tags: [hermes-agent, openclaw, evomap, agent-comparison, self-evolution, skills]
summary: "深度对比 OpenClaw（网关中心化）与 Hermes Agent（执行循环中心化）的架构差异，分析技能机制、分层记忆体系、自动化与安全防御的范式转移。"
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
section: sources
---

# Hermes Agent 与 OpenClaw 深度对比简报

## 视频元数据
- **标题**: Hermes Agent 与 OpenClaw 深度对比
- **发布者**: YouTube 技术频道
- **核心主题**: 自托管智能体领域两款核心产品 OpenClaw 与 Hermes Agent 的深度架构对比

## 执行摘要
本报告深入分析了自托管智能体（Agent）领域的两款核心产品 OpenClaw 与 Hermes Agent。OpenClaw 以 Gateway（网关）作为绝对控制中枢，定义了个人自托管智能体的初期标准。而由 Nous Research 开发的 Hermes Agent 则代表了下一代智能体的发展方向，其核心优势在于从"执行指令"向"自我进化"的范式转移。通过引入去中心化的执行循环、程序化知识生成（自动生成技能）以及精密的分层记忆体系，Hermes Agent 实现了能力的持续复利增长。此外，视频还讨论了近期 Hermes 团队卷入的涉嫌抄袭中国开源项目 EvoMap 的争议事件。

## 核心要点

1. **架构本质差异**: OpenClaw 采用网关中心化架构，以 Gateway 作为绝对控制中枢；Hermes Agent 采用执行循环中心化架构，将 Agent 自身的执行循环定义为同步编排引擎
2. **技能机制对比**: OpenClaw 的技能由人类开发者编写；Hermes 的技能可根据执行经验自动生成，实现"记住方法"而非"记住事实"
3. **分层记忆体系**: Hermes 构建了四层存储——核心持久记忆（MEMORY.md ~1300 tokens）、会话历史记忆（SQLite+FTS5）、扩展记忆层（Honcho）、程序性记忆（自动生成技能）
4. **自动化能力**: Hermes 内置 cron 计划任务系统，支持自然语言设定，每 60 秒检查条件，在隔离会话中运行
5. **五层纵深防御**: 用户授权→危险命令审批→容器隔离→MCP 凭证过滤→上下文扫描，另加 SSRF 和恶意注入防护
6. **计算与交互解耦**: Hermes 支持本地、VPS、Docker、无服务器架构运行，同时通过 Telegram、Discord 或命令行交互
7. **模型无关性**: 通过 `hermes model` 命令快速切换 OpenAI、OpenRouter、Kim、MiniMax 或自定义模型端点
8. **OpenClaw 迁移路径**: 自动检测 `~/.openclaw` 目录，导入核心文件，转换存储格式
9. **EvoMap 抄袭争议**: 舆论认为 Hermes 架构高度"借鉴"中国开源项目 EvoMap，团队两度否认但声誉受损

## 关键引言

> **"Hermes Agent 正在经历从设计哲学、架构逻辑到能力成长路径的一场新的变革。"**
> 描述用户从 OpenClaw 转向 Hermes 的趋势，强调智能体正从简单的助手向可自我进化的数字基础设施演进。

> **"它让智能体从传统的记住事实，升级为了记住方法。"**
> 解释 Hermes Agent 的 Skill 机制——能将复杂的多步操作抽象并固化为可复用的程序。

> **"这种设计把智能体的计算核心与用户交互界面彻底解耦。"**
> 讨论 Hermes 的可移植性——计算核心与交互界面分离，支持多种运行环境与交互方式。

## 关联实体
- [[hermes-agent]]
- [[openclaw]]
- [[evomap]]

## 关联概念
- [[执行循环驱动架构]]
- [[分层记忆体系]]
- [[五层纵深防御模型]]
