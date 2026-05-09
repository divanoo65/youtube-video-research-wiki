---
title: Hermes Agent
type: entity
tags: [hermes-agent, agent-framework, AI]
summary: 一个注重稳定性的 AI Agent 框架，支持主副模型分离、集成 Ollama 云端模型和 Open WebUI，中文名“赫美斯”。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Hermes Agent

## 基本定位

Hermes Agent 是一个以稳定性为核心卖点的 AI Agent 框架，由社区开发并维护。它通过主副模型分离架构降低运行成本，同时原生集成 [[Ollama]] 提供云端免费模型部署，并通过 [[Open-WebUI]] 提供现代化交互界面。官方中文名称定为“赫美斯”。

## 核心特征/能力

1. **极强稳定性**: 在版本更新时极少引入 bug，不会出现崩溃或功能异常，远优于 [[OpenCloud]]。
2. **主副模型分离机制**: 允许指定主模型处理复杂任务，副模型（如 [[Gemini]] 1.5 Flash）处理批准、压缩、MCP 调用等辅助任务，大幅节省 Token。
3. **零资源云端部署**: 通过 Ollama 集成云端免费模型（如 Minimax-M2.7），完全不需要本地 GPU 或高性能硬件。
4. **Open WebUI 原生支持**: 配置文件暴露 API 端口后，可直接对接 Open WebUI，获得 Markdown 解析、代码执行、流式输出、侧边栏历史记录等高级交互功能。
5. **辅助任务六大类**: 提供 Approval（批准）、Compression（压缩）、Refresh Memory（重刷记忆）、MCP 调用、Web Search（网页搜索）、Visual（视觉）的模块化处理，每组可独立配置模型。
6. **多端访问能力**: 通过内网穿透工具可实现在手机浏览器远程访问，支持公网 IP 或域名接入。
7. **GitHub 星标增速领先**: 在同类 Agent 框架中，星标增长已超过 OpenCloud，社区活跃度高。

## 应用场景

1. **个人本地 AI 助手**: 用户在自己的 Windows/Mac 机器上部署 Hermes Agent，通过 Open WebUI 进行日常问答、代码编写、文件处理等任务。
2. **低成本企业 Agent 服务**: 企业使用主副模型策略，将高频简单任务交给 Gemini 1.5 Flash 等廉价模型，仅复杂请求调用昂贵模型，控制 API 成本。
3. **移动端远程 AI 访问**: 通过内网穿透，在户外用手机访问家中运行的 Agent，实现随时随地的智能助理。

## 关系网络

- [[Ollama]] — **集成依赖**: Hermes Agent 通过 Ollama 加载云端免费模型，Ollama 作为模型运行时提供基础设施。
- [[Open-WebUI]] — **交互集成**: Hermes Agent 暴露 API 后与 Open WebUI 对接，提供用户界面。
- [[OpenCloud]] — **直接竞争**: 两者均为 Agent 框架，但 Hermes Agent 在稳定性上领先。
- [[Gemini]] — **推荐副模型**: 官方推荐使用 Gemini 1.5 Flash 作为辅助任务的低成本模型。

## 关键事件/里程碑

- **中文命名确认**: 社区获得官方确认，中文名为“赫美斯”，统一了品牌认知。
- **Ollama 集成发布**: Hermes Agent 推出 Ollama 一键部署功能，支持云端免费模型。
- **GitHub 星标超越 OpenCloud**: 标志着其在社区认可度上的提升。

## 出现的视频来源

- [[Hermes-Agent-高级玩法与部署优化简报]]
