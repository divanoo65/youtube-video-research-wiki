---
title: OpenClaw
type: entity
tags: [ai-agent, open-source, gateway, personal-agent]
summary: 行业基准级个人智能体框架，采用中心化网关（Gateway）架构，以稳定性和工作区管理见长
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比及技术趋势简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# OpenClaw

## 基本定位

定义了过去半年个人智能体标准的行业基准框架，采用中心化网关（Gateway）架构，以高度稳定性、可审计性和确定性著称。

## 核心特征

1. **中心化网关架构**：Gateway 充当后台守护进程，统一负责会话管理、请求路由、工具调用和状态维护
2. **完善的工作区机制**：每个任务绑定具体工作区的身份配置和权限
3. **文件系统记忆**：以 Markdown 文件为核心的事实与状态管理
4. **预设技能插件包**：主要依赖预置的插件能力，不具备自主生成能力
5. **稳定与可控优先**：设计哲学偏向确定性执行，适合对稳定性要求高的场景

## 关系网络

- 与 [[hermes-agent]] 在架构哲学上形成中心化 vs. 去中心化的对比
- 使用[[中心化网关架构]]作为核心设计模式
- Hermes Agent 支持从 OpenClaw 无缝迁移

## 出现的视频来源

- [[Hermes Agent 与 OpenClaw 深度对比及技术趋势简报]]
