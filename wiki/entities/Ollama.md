---
title: Ollama
type: entity
tags: [open-source, model-runner, local-ai]
summary: Ollama 是一款免费开源的 AI 大模型运行平台，支持本地和云端运行各种开源模型，提供一键部署和集成命令，与 Hermes Agent 深度集成。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Ollama

## 基本定位
Ollama 是一个开源的本地/云端大模型运行时平台，允许用户在本地部署并运行各种开源 AI 模型（如 Llama、Mistral、Mixral 等），同时提供云端免费模型调用服务。它为 AI Agent 工具如 Hermes 提供了便捷的模型后端。

## 核心特征/能力
1. **本地模型支持**：用户可以下载并运行多个开源模型，完全离线、数据私密。
2. **云端免费模型**：Ollama 提供的云端模型（如 Mixral 2.7B）无需本地 GPU 资源，可通过命令行快速调用，适合低配设备。
3. **一键部署**：从官网下载对应系统版本后，只需运行一条集成命令即可完成配置，具备傻瓜式操作特性。
4. **命令行接口**：提供简洁的 CLI 接口，可通过终端轻松启动、管理模型。
5. **广泛模型库**：支持 Hundreds 个开源模型，包括 Llama、Mistral、Code Llama 等，可自由切换。

## 应用场景
1. **与 Hermes Agent 集成**：作为 Hermes 的模型后端，提供本地或云端模型，让 Agent 具备自然语言理解与生成能力。
2. **个人研发测试**：开发者可快速下载模型进行本地测试，无需申请云 API。
3. **低成本部署**：利用云端免费模型额度，实现零成本运行 AI Agent。

## 关系网络
- [[Hermes-Agent-赫美斯]] — Hermes 深度集成 Ollama 以调用模型，是核心依赖关系。
- [[Open-WebUI]] — 可作为 Ollama 模型调用的前端界面，但 Hermes 场景下通过 Open WebUI 与 Agent 交互。
- [[Gemini-1.5-Flash]] — 与 Ollama 云端模型类似，也是低成本模型选项，但属于不同提供商（Google vs Ollama 平台）。

## 关键事件/里程碑
- 推出云端免费模型功能，降低使用门槛。
- 与 Hermes Agent 达成集成，成为其推荐的模型运行平台。

## 出现的视频来源
- [[Hermes-Agent高级配置指南]]
