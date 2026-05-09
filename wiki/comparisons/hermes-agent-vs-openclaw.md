---
title: Hermes Agent vs OpenClaw
type: comparison
tags: [ai-agent, comparison, architecture, memory, security]
summary: 从架构哲学、记忆体系、安全模型、自动化能力和部署策略五大维度对比 Hermes Agent 与 OpenClaw
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比及技术趋势简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 基于两份分析报告中直接对比 Hermes Agent 与 OpenClaw 的明确内容
---

# Hermes Agent vs OpenClaw 深度对比

## 对比维度

| 维度 | Hermes Agent | OpenClaw |
|------|-------------|----------|
| **架构哲学** | 去中心化执行循环，AI Agent 自身为编排引擎 | 中心化 Gateway 网关为绝对中枢 |
| **核心创新** | 程序化知识生成（自动生成 Skills） | 稳定的工作区机制和预设插件包 |
| **记忆体系** | 四层分层：MEMORY/USER.md + SQLite + Honcho + 技能库 | Markdown 文件 + 文件系统持久化 |
| **安全模型** | 五层纵深防御（授权+审批+隔离+过滤+扫描） | 标准权限模型 |
| **自动化能力** | 内置 Cron 系统，自然语言设定，60 秒检查 | 依赖外部编排工具 |
| **模型支持** | 极灵活：OpenAI、OpenRouter、Kimi、GLM 等 | 有限模型支持 |
| **迁移成本** | 自动检测 `~/.openclaw`，无缝转换记忆 | — |
| **平台对接** | Telegram、Discord、CLI | 终端为主 |
| **争议** | EvoMap 抄袭争议 | 早期安全争议 |

## 核心差异分析

1. **进化 vs 稳定**：Hermes Agent 设计为"自进化"系统，每次执行都能反向优化；OpenClaw 追求确定性和可审计性。

2. **技能自主性**：Hermes Agent 能自主生成和优化技能（Skills），OpenClaw 依赖人类开发者编写插件或工作流。

3. **安全性策略**：Hermes Agent 因 OpenClaw 早期安全争议而主动加固了五层防御，更适合无人值守环境。

4. **生态兼容性**：Hermes Agent 支持多平台对接和模型无关性，OpenClaw 聚焦终端体验。

## 适用场景结论

- **选择 OpenClaw**：需要高度稳定的本地助理、清晰工作区管理、对确定性有严格要求
- **选择 Hermes Agent**：追求自动化能力（每日简报、定时任务）、长期自我进化的研究助手、需要跨平台远程交互

## 双向链接

- [[hermes-agent]]
- [[openclaw]]
- [[去中心化执行循环]] — Hermes 的核心架构
- [[中心化网关架构]] — OpenClaw 的核心架构
- [[程序化知识生成]] — Hermes 的核心创新
- [[分层记忆体系]] — Hermes 的记忆方案
- [[五层纵深防御]] — Hermes 的安全方案
