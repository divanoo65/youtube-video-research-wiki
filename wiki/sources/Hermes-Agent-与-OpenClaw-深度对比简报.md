---
title: Hermes Agent 与 OpenClaw 深度对比简报：下一代自我进化智能体分析
type: source
tags: [hermes-agent, openclaw, 智能体, 自我进化, 自托管]
summary: 深度对比自托管智能体赛道两大产品 Hermes Agent 与 OpenClaw，分析执行循环架构、程序化知识机制和分层记忆体系等核心理念差异。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.md
  - raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
video_url: https://www.youtube.com/watch?v=NbldZVdusKo
mindmap: raw/notebooklm-mindmaps/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.json
---

# Hermes Agent 与 OpenClaw 深度对比简报：下一代自我进化智能体分析

- 视频：https://www.youtube.com/watch?v=NbldZVdusKo
- 思维导图：[[Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能|查看脑图]]

## 执行摘要

本报告深度对比了自托管智能体赛道的两大核心产品——由 **Nous Research** 开发的 **Hermes Agent** 与 **OpenClaw**。OpenClaw 凭借清晰的架构和工作区机制定义了个人自托管智能体的初步标准。而 Hermes Agent 通过引入"自我进化"、"程序化知识生成"和"分层记忆体系"等理念，推动智能体从单纯的"工具助手"向"个人数字化基础设施"演进。Hermes Agent 的核心优势在于去中心化设计哲学和模型无关性，支持在多种计算环境下无缝部署。

## 核心要点

1. **架构差异**：OpenClaw 以 Gateway 网关为中心的控制中枢，Hermes Agent 以 AI Agent 自身执行循环为同步编排引擎。
2. **技能机制对比**：OpenClaw 技能由人类编写插件，Hermes 能自动将执行经验抽象为可复用技能存储在 `~/.hermes/skills/`。
3. **分层记忆体系**：Hermes 构建了四层持久化存储（核心记忆 → 会话历史 → 扩展记忆 → 程序性记忆）。
4. **身份锚定**：OpenClaw 的身份绑定在工作区，Hermes 身份全局性不受目录或设备切换影响。
5. **内置自动化**：Hermes 提供自然语言 cron 计划任务系统，每 60 秒检查一次条件。
6. **五层纵深防御**：危险命令审批 → 容器化隔离 → MCP 凭证过滤 → SSRF 防护 → 消息配对过滤。
7. **部署灵活性**：支持本地、VPS、Docker、SSH 远程环境及无服务器架构。
8. **模型无关**：支持 OpenAI、OpenRouter、国内大模型及自定义端点，可快速切换。
9. **开源争议**：涉及对中国开源项目 EvoMap 架构抄袭的争议，代码无直接雷同但架构高度相似。
10. **一键迁移**：为 OpenClaw 存量用户提供 Markdown 记忆到 SQLite 存储的自动转换工具。

## 关联实体

- [[hermes-agent]] — 智能体核心产品
- [[openclaw]] — 对比对象
- [[nous-research]] — Hermes Agent 开发方
- [[evomap]] — 争议相关的开源项目

## 关联概念

- [[自我进化智能体]] — Hermes 的核心设计理念
- [[程序化知识]] — 自动技能生成机制
- [[分层记忆体系]] — 四层持久化存储
- [[执行循环架构]] — 以 Agent 执行循环为中心的架构模式
