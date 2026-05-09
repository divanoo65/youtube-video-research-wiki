---
title: Ollama
type: entity
tags: [ollama, 模型部署, 本地AI]
summary: Ollama 是一个本地 AI 模型部署工具，已原生集成 Hermes Agent，提供一键傻瓜式部署和云端免费模型支持。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Ollama

## 基本定位
Ollama 是一个本地 AI 模型部署工具，支持一键下载和运行各种开源 AI 模型。其核心优势在于已原生集成 Hermes Agent，提供极简的部署路径，并支持通过云端免费模型（如 Minimax M2.7）降低本地硬件资源占用。

## 核心特征/能力

1. **Hermes Agent 原生集成**: Ollama 已原生内置 Hermes Agent，用户无需额外配置即可部署。
2. **一键傻瓜式配置**: 整个配置过程高度集成，支持一键式部署，降低了初学者的门槛。
3. **云端免费模型支持**: 通过 Ollama，用户可以使用云端免费模型（如 Minimax M2.7），无需占用本地硬件资源。
4. **跨平台支持**: 支持 Windows、macOS、Linux 等主流操作系统。
5. **终端命令操作**: 用户通过终端运行特定命令即可进入模型选择界面。

## 应用场景

1. **快速部署 Hermes Agent**: 用户仅需从 Ollama 官网下载对应操作系统的版本，安装后通过终端运行特定命令即可部署 Hermes Agent。
2. **使用云端免费模型**: 选择带“Cloud”标识的模型以使用免费云端算力，适合本地硬件资源有限的用户。

## 关系网络

- [[hermes-agent]] — 依赖关系：Ollama 原生集成 Hermes Agent，提供部署和模型支持。
- [[open-webui]] — 互补关系：Ollama 提供模型部署，Open WebUI 提供交互界面。
- [[minimax-m2.7]] — 支持模型：通过 Ollama 可使用的云端免费模型。

## 关键事件/里程碑

- **Hermes Agent 原生集成**: Ollama 成为首个原生集成 Hermes Agent 的模型部署工具。

## 出现的视频来源

- [[hermes-agent-高级玩法与优化指南-深度简报]]