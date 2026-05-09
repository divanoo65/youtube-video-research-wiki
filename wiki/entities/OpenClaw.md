---
title: OpenClaw
type: entity
tags: [ai-agent, agent-framework, open-source, gateway]
summary: 自托管智能体平台，采用中心化网关（Gateway）模式，以高可预测性、稳定性和明确的工作区划分为核心优势。
sources:
  - wiki/sources/Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 基本定位

OpenClaw 是自托管智能体领域的行业标杆，以中心化网关（Gateway）模式为核心架构。Gateway 作为稳定的后台守护进程，统一负责会话管理、请求路由、工具调用和状态维护，行为高度可预测、可审计且稳定性极强。

## 核心特征

- **中心化网关模式**：Gateway 为绝对控制中枢，架构清晰
- **高稳定性**：行为可预测、可审计
- **工作区划分**：SOUL.md 属于工作区文件，切换工作区即切换完整身份与上下文
- **手动技能编写**：技能由人类开发者编写与优化，类似插件系统

## 关系网络

- 主要对比：[[Hermes Agent]]（执行循环驱动模式）
- 相关概念：[[中心化网关模式]]
- 视频来源：[[Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报]]
