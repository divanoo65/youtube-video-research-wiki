---
title: Hermes Agent 与 OpenClaw 深度对比简报
type: source
tags: [hermes-agent, openclaw, nous-research, 对比, agent框架]
summary: 深入分析自托管智能体领域两款核心产品——OpenClaw 与 Hermes Agent 的架构差异、设计哲学及关键技术特性。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
  - raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
video_url: https://www.youtube.com/watch?v=NbldZVdusKo
mindmap: raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json
---

# Hermes Agent 与 OpenClaw 深度对比简报

**视频链接：** <https://www.youtube.com/watch?v=NbldZVdusKo>

**脑图文件：** `raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报.json`

## 执行摘要

本报告深入分析自托管智能体领域的两款核心产品——**OpenClaw** 与 **Hermes Agent**（由 [[nous-research]] 开发）。OpenClaw 作为赛道开拓者，通过清晰的架构和稳定的本地执行能力定义了个人智能体的基础。新近崛起的 Hermes Agent 则代表了设计范式的转移——从"指令执行者"演变为具备"自我进化"能力的数字基础设施。其核心优势在于去中心化的执行架构、[[程序化知识生成]]机制以及严密的[[五层纵深防御]]安全模型。尽管近期面临涉及中国团队 [[evomap]] 的架构抄袭争议，但其在自我提升和长效记忆管理方面的技术尝试为下一代本地智能体提供了重要参考。

## 核心要点

1. **控制中枢差异：** OpenClaw 使用中心化的 Gateway（网关）作为后台守护进程负责路由和状态维护；Hermes Agent 采用[[执行循环驱动架构|执行循环]]（Execution Loop），将网关、调度、工具、环境全部集成于闭环，天然支持自我进化。
2. **身份锚定机制：** OpenClaw 的身份与"工作区"绑定，切换即切换身份配置；Hermes Agent 的身份通过 `SOUL.md` 全局化，跨设备保持一致。
3. **自动技能生成：** Hermes 能将完成的工作流抽象为可复用的"程序化流程"，通过内置 `skill_manage` 工具自主完成技能的创建、优化与调用，遵循 `agentskills.io` 标准。
4. **[[分层记忆体系]]：** Hermes 构建了四层存储结构——核心持久层（MEMORY.md/USER.md）、会话历史层（SQLite FTS5）、扩展记忆层（Honcho）、程序性记忆层（自动技能流）。
5. **[[五层纵深防御]]：** 用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文文件扫描，外加 SSRF 防护、网站黑名单等额外保护。
6. **Cron 计划任务：** Hermes 内置完整定时系统，支持自然语言设定任务，每 60 秒检查一次，在隔离会话中运行。
7. **模型无关性：** Hermes 支持主流模型（OpenAI、GLM、MiniMax 等）及自定义端点，通过 `hermes model` 秒级切换。
8. **多端交互：** 支持 CLI、Telegram、Discord、Slack 及语音交互。
9. **迁移路径：** Hermes 提供从 OpenClaw 的无缝迁移功能，自动检测 `~/.openclaw` 目录并导入记忆、同步技能。

## 关键引言

> "Nous Research 的目标是让 AI 能力不被少数几家封闭平台垄断，而是实现去中心化的技术普惠。"
> *背景：Nous Research 起源于去中心化技术社群，决定了 Hermes Agent 的高可控性与开源特性。*

> "Hermes Agent 让智能体从传统的'记住事实'，升级为了'记住方法'。"
> *背景：描述 Hermes 的[[程序化知识生成]]机制——智能体从执行经验中学习并固化操作流程。*

> "它是从底层重新定义了本地智能体应该如何运行、如何学习、如何成长。"
> *背景：强调 Hermes 不是增加功能插件，而是通过执行循环改变了 Agent 的生长逻辑。*

## 行业争议：EvoMap 抄袭风波

Hermes Agent 被指控涉嫌"借鉴"中国团队 [[evomap]] 的开源项目架构设计。[[nous-research]] 两度否认抄袭，称代码无雷同。尽管代码层面可能存在差异，但架构思路的重合给项目声誉带来了负面影响。

## 应用场景建议

- **个人每日简报：** 利用 Cron 系统定时检索信息、生成日报并推送至 Telegram/Discord。
- **DevOps 辅助：** 作为 SSH/Shell 助手，执行远程服务器检查、代码审查及 GitHub Issue 自动分拣。
- **企业知识管理：** 对接内部 API 与数据库，抓取财务或客户数据并自动总结入库。
- **科研与模型微调：** 利用操作轨迹记录能力，批量生成高质量智能体运行数据用于模型训练。

## 脑图核心节点

- **Hermes Agent 与 OpenClaw 深度对比**（根节点）
  - **控制中枢对比：** Gateway（OpenClaw）vs 执行循环（Hermes）
  - **身份锚定：** 工作区绑定 vs 全局 SOUL.md
  - **Hermes 关键技术：** 自我提升、程序化知识、分层记忆、五层防御
  - **自动化与兼容性：** Cron 计划、模型无关性、多端交互
  - **迁移路径：** 自动检测并导入 ~/.openclaw

## 关联实体

- [[hermes-agent]] — Nous Research 开发的 Agent 框架
- [[openclaw]] — 自托管智能体赛道开拓者
- [[nous-research]] — Hermes Agent 开发者
- [[evomap]] — 涉及架构抄袭风波的团队

## 关联概念

- [[执行循环驱动架构]] — Hermes 的核心架构模式
- [[程序化知识生成]] — 自动技能生成机制
- [[分层记忆体系]] — 四层存储架构
- [[五层纵深防御]] — 安全模型
