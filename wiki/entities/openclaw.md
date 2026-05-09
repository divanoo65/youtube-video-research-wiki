---
title: OpenClaw
type: entity
tags: [ai-agent, open-source, local, gateway]
summary: 个人自托管智能体赛道的定义者，采用 Gateway 网关中心化设计，强调稳定性、可控性和可审计性。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

OpenClaw 是早期自托管智能体框架的代表，以 Gateway 网关作为绝对控制中枢，是一个稳定的后台守护进程，负责会话管理、请求路由和工具调度。

## 核心特征/能力

1. **Gateway 中心化设计**：所有请求通过网关路由，保证透明性和可审计性。
2. **模块化技能体系**：技能由人类开发者编写为插件或工作流指令，存储在 Markdown 文件中。
3. **高度可预测**：行为完全受控，无自动演化风险，适合要求严格的环境。
4. **多环境支持**：可在本地、VPS、Docker、SSH 等多种环境中运行。
5. **交互渠道**：支持 Telegram、Discord、CLI 等。
6. **模型无关性**：同样支持多种后端模型。

## 应用场景

- **企业级自动化任务**：需要全流程可审计的场景，如金融交易自动处理。
- **个人秘密管理**：需要高度可控的本地控制台，避免外部依赖。
- **教学演示**：架构透明，适合作为学习智能体框架的入门工具。

## 关系网络

- [[hermes-agent]] — 竞争/被替代关系（直接对比对象）
- [[nous-research]] — 间接关联（Hermes 的开发者）

## 关键事件/里程碑

- 长期作为个人自托管智能体赛道标杆。
- 2026年：面临 Hermes Agent 的竞争，社区开始向其迁移。

## 出现的视频来源

- [[Hermes-Agent-与-OpenClaw-深度对比-下一代自进化智能体的崛起]]
