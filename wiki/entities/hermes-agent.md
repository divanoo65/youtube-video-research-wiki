---
title: Hermes Agent
type: entity
tags: [agent, ai-agent, hermes, 赫美斯]
summary: Hermes Agent（赫美斯）是一个高度稳定、支持主副模型配置的 AI Agent 框架，通过 Ollama 和 Open WebUI 提供极简部署和优化交互体验。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Hermes Agent

## 基本定位
Hermes Agent（中文名：赫美斯，字母 H 发音）是一个高度稳定的 AI Agent 框架，由社区开发并托管于 GitHub。其核心优势在于稳定性远超同类项目（如 OpenCloud），且通过 Ollama 原生集成和 Open WebUI 支持，提供了极简的部署和优化交互体验。

## 核心特征/能力

1. **高稳定性**: 版本更新中较少引入 Bug，稳定性远超 OpenCloud 等同类项目。
2. **Ollama 原生集成**: Ollama 已原生内置 Hermes Agent，提供一键傻瓜式部署体验。
3. **云端免费模型支持**: 通过 Ollama 可使用 Minimax M2.7 等云端免费模型，无需占用本地硬件资源。
4. **Open WebUI 原生支持**: 原生支持 Open WebUI，提供会话管理、Markdown 解析、代码流式输出等高级功能。
5. **主副模型配置**: 支持主模型和副模型分离，由主模型处理复杂任务，副模型处理辅助任务，大幅降低 Token 消耗。
6. **API 服务**: 支持通过配置文件启用 API 服务，提供 OpenAI 兼容接口。
7. **移动端适配**: 通过 Open WebUI 支持手机浏览器访问，适配良好。

## 应用场景

1. **本地 AI Agent 部署**: 通过 Ollama 一键部署 Hermes Agent，适合个人开发者快速搭建 AI Agent 环境。
2. **低成本 Token 优化**: 通过主副模型配置，使用 Gemini 2.0 Flash 等廉价模型处理辅助任务，大幅降低 Token 消耗。
3. **远程办公**: 配合内网穿透技术，通过手机浏览器远程访问家中的 Agent 实例。

## 关系网络

- [[ollama]] — 依赖关系：Ollama 原生集成 Hermes Agent，提供部署和模型支持。
- [[open-webui]] — 依赖关系：Open WebUI 提供 Hermes Agent 的交互界面优化。
- [[opencloud]] — 竞争关系：同类项目，但稳定性较差。
- [[gemini-2.0-flash]] — 推荐配置：作为副模型使用，兼顾性能与成本效益。

## 关键事件/里程碑

- **GitHub Star 增长**: 其 GitHub 仓库的 Star 增长速度已超越同类主流项目。
- **官方中文名确立**: 官方明确其中文名称为“赫美斯”，且字母“H”发音。

## 出现的视频来源

- [[hermes-agent-高级玩法与优化指南-深度简报]]