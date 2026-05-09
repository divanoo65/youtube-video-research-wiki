---
title: Hermes Agent
type: entity
tags: [ai-agent, nous-research, open-source, self-evolution]
summary: Nous Research 开发的自我进化智能体框架，以执行循环为核心，自动生成程序化知识，具备四层分层记忆和五层安全防御。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛.md
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

Hermes Agent 由 Nous Research 开发，是个人自托管智能体框架，以“执行循环”（Execution Loop）为控制中枢，强调自我评估、自我修正和自我提升。核心价值在于从“被动执行工具”进化为“主动自进化系统”。

## 核心特征/能力

1. **执行循环架构**：网关、定时任务、工具运行时均围绕 AI 智能体自身的执行循环集成，每次执行都能优化后续决策。
2. **自动程序化知识**：基于执行经验自动生成可复用技能，存储在 `~/.hermes/skills/`，无需人工编写。
3. **四层分层记忆体系**：核心持久记忆（`MEMORY.md`/`USER.md`，约 1300 Tokens）、会话历史（SQLite FTS5 全文索引）、扩展记忆（Honcho 长期画像）、程序性记忆。
4. **五层纵深防御**：用户授权、危险命令审批、容器隔离、MCP 凭证过滤、上下文扫描，辅以 SSRF 防护。
5. **内置 Cron**：支持自然语言设定定时任务，每 60 秒检查一次，在隔离会话中执行。
6. **MCP 协议深度集成**：支持 Model Context Protocol，可连接各类外部工具。
7. **多平台交互**：支持 Telegram、Discord、CLI 等渠道。
8. **模型无关性**：支持 OpenAI、Nous Portal 等模型，可通过自定义 Base URL 对接本地模型。

## 应用场景

- **个人每日简报机器人**：利用 Cron 系统定时检索信息、生成日报并推送到 Telegram。
- **GitHub 分诊助手**：结合 MCP 协议自动聚类 Issue、草拟 Bug 描述。
- **研究数据生成**：记录完整操作轨迹和决策序列，为模型微调提供高质量人造轨迹数据。

## 关系网络

- [[nous-research]] — 开发者（依赖关系）
- [[openclaw]] — 竞争/替代关系（被直接对比）
- [[qwen-3-6]] — 常用后端模型（协同关系）
- [[llama-cpp]] — 常用推理引擎（集成关系）
- [[evomap]] — 涉嫌抄袭争议（伦理关系）

## 关键事件/里程碑

- 2026年：Hermes Agent 发布，迅速成为本地智能体领域的热门框架。
- 卷入疑似抄袭中国团队 EvoMap 的架构风波。
- 提供从 OpenClaw 的一键迁移工具。

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛起]]
- [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]]
