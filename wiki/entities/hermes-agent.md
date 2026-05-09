---
title: hermes-agent
type: entity
tags: [agent, ai, deployment]
summary: Hermes Agent（赫美斯）是一个高度稳定、支持主副模型配置的 AI Agent 框架，通过 Ollama 和 Open WebUI 提供极简部署和优化交互体验。
sources: [wiki/sources/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

## 基本定位

Hermes Agent（赫美斯）是一个高度稳定、支持主副模型配置的 AI Agent 框架，通过 Ollama 和 Open WebUI 提供极简部署和优化交互体验。

## 核心特征/能力

1. **稳定性强**：在版本更新过程中较少引入 Bug，避免了系统崩溃的情况。
2. **支持主副模型配置**：通过将任务细分，由昂贵的主模型处理复杂逻辑，由廉价的副模型处理简单任务，从而大幅降低 Token 消耗。
3. **Ollama 集成**：已原生内置了 Hermes Agent，为用户提供了极简的部署路径。
4. **支持 Open WebUI**：提供 Markdown 解析、代码流式输出和多端访问，显著提升交互体验。
5. **中文命名明确**：官方中文名为“赫美斯”，且字母“H”发音。

## 应用场景

1. **AI 代理部署**：适用于需要高效运行 AI 代理的场景，如自动化任务处理。
2. **远程办公**：支持通过手机浏览器访问，适合远程工作环境。
3. **代码交互**：支持 Python 代码运行，适合开发和测试环境。

## 关系网络

- [[ollama]]：Hermes Agent 通过 Ollama 实现一键部署。
- [[open-webui]]：Hermes Agent 通过 Open WebUI 提供更优的交互体验。

## 关键事件/里程碑

- 2026 年 5 月：Hermes Agent 在 GitHub 上的关注度增长迅速，Star 数量超越同类项目。

## 出现的视频来源

[[Hermes-Agent-高级玩法与优化指南-深度简报]]