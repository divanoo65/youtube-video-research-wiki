---
title: Hermes Agent 与 OpenClaw 深度对比简报
type: source
tags: [Hermes Agent, OpenClaw, 对比, 本地Agent]
summary: 深入对比个人自托管智能体 Hermes Agent 与 OpenClaw，分析中心化控制 vs 循环驱动架构、程序化知识生成、分层记忆体系等核心差异。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
video_url: https://www.youtube.com/watch?v=NbldZVdusKo
mindmap: raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json
---

# Hermes Agent 与 OpenClaw 深度对比简报

## 执行摘要
本报告深入对比了个人自托管智能体赛道中的两款核心产品：OpenClaw 与 Hermes Agent。OpenClaw 以其清晰的架构和稳定的本地执行能力，定义了早期的自托管智能体赛道。然而，新崛起的 Hermes Agent 正在引发一场关于设计哲学、架构逻辑和能力成长路径的变革。两者的核心差异在于：OpenClaw 侧重于中心化控制与稳定性，而 Hermes Agent 则追求自我进化与知识生成。Hermes Agent 通过将执行循环定义为编排引擎，实现了从“记住事实”到“记住方法”的跨越，标志着本地智能体正从单纯的助手工具演进为具备自我提升能力的数字化基础设施。

## 核心要点
1. **架构差异**：OpenClaw 采用中心化 Gateway 守护进程作为控制中枢，统一管控会话、路由、工具调用和状态；Hermes Agent 将 AI 自身的执行循环定义为同步编排引擎，网关、调度器等均围绕其集成。
2. **身份定义差异**：OpenClaw 的 SOUL.md 绑定特定工作区，切换工作区即切换身份；Hermes Agent 的 SOUL.md 属于全局属性，不绑定目录，保持跨环境的个性一致。
3. **程序化知识生成**：Hermes Agent 可自动将执行经验转化为可复用的技能文件（存储在 ~/.hermes/skills/），实现跨会话持续学习；OpenClaw 依赖人类编写模块化插件。
4. **分层记忆体系**：Hermes 有四层记忆架构：核心持久记忆（MEMORY.md/USER.md，约1300 token）、会话历史数据库（SQLite FTS5）、扩展记忆层（Honcho，长期用户画像）、程序性记忆（自动技能）。OpenClaw 以 Markdown 文件为核心。
5. **自动化能力**：Hermes 内置 Cron 计划任务系统，支持自然语言设定定时任务，每60秒检查条件，在隔离会话中运行，结果可推送到多端。
6. **安全防御**：Hermes 采用五层纵深防御模型（用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描），辅以 SSRF 防护和网站黑名单。
7. **模型无关性**：Hermes 支持通过 `hermes model` 命令切换 OpenAI、OpenRouter 及国产大模型，无需修改核心代码。
8. **部署兼容性**：支持终端、VPS、Docker、SSH 及 Serverless 架构，提供自动检测并导入 OpenClaw 配置的迁移工具。
9. **争议事件**：Hermes Agent 被指涉嫌抄袭中国开源项目 EvoMap 的架构设计，存在“洗代码”嫌疑，团队予以否认。
10. **行业意义**：Hermes 所代表的“Agent 知识自我沉淀”方向被视为技术突破的关键点。

## 关键引言
> “Hermes Agent 试图回答的核心问题是：如果一个本地智能体不只是能执行指令，而是能在持续使用中不断自我评估、自我修正、自我提升，它会变成什么样？”
> *上下文：揭示 Nous Research 核心愿景，通过技术栈精准捕捉执行经验，将零散行为固化为稳定能力。*

> “OpenClaw 是用中心化控制器来统一指挥所有模块，而 Hermes Agent 则是由从智能体自身的执行、到学习、再到改进的闭环来驱动整个系统。”
> *上下文：总结两款产品在系统编排逻辑上的根本分歧。*

> “它让智能体从传统的‘记住事实’，升级为了‘记住方法’。”
> *上下文：强调 Hermes 将工作流抽象为“程序化知识”的技能机制。*

## 脑图核心节点
根据脑图数据，一级节点包括：
- 核心架构差异（OpenClaw:中心化Gateway, Hermes:执行循环驱动）
- 自我提升与技能机制（程序化知识生成、对比 OpenClaw）
- 分层记忆体系（四层架构）
- 兼容性与部署（环境适应性、模型与交互）
- 自动化与安全性（Cron计划任务、五层防御）
- 行业背景与争议（Nous Research、迁移工具、EvoMap风波）

## 关联实体
- [[hermes-agent]]
- [[openclaw]]
- [[nous-research]]
- [[evomap]]

## 关联概念
- [[中心化网关]]
- [[执行循环驱动]]
- [[程序化知识生成]]
- [[分层记忆体系]]
- [[五层防御安全模型]]
- [[cron计划任务]]
- [[模型无关性]]
- [[soul.md]]
- [[mcp协议]]
