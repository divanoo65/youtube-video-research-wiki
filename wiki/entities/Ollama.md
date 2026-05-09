---
title: Ollama
type: entity
tags: [ollama, ai, local-model, deployment]
summary: 一个本地大模型运行和管理工具，集成了 Hermes Agent 并支持一键部署云端免费模型。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Ollama

## 基本定位

Ollama 是一个开源的本地大模型运行框架，支持一键下载和管理各种开源模型，并提供 API 接口。在 Hermes Agent 生态中，Ollama 作为模型容器，允许用户通过简单命令选择并连接云端免费模型（如 Minimax-M2.7），实现零硬件资源消耗的 Agent 部署。

## 核心特征/能力

1. **一键安装与运行**: 用户只需下载 Ollama 客户端，执行内建 Hermes 集成命令即可完成模型连接，无需手动配置环境。
2. **云端免费模型支持**: 选择带有“Cloud”后缀的模型时，Ollama 会自动通过浏览器登录流程获取免费额度，不占用本地计算资源。
3. **多模型管理**: 支持同时安装和管理多个模型，用户可根据任务需求切换不同模型。
4. **原生 Hermes Agent 集成**: 专为 Hermes Agent 设计了集成命令，简化部署流程。
5. **跨平台兼容**: 支持 Windows、macOS、Linux 主流操作系统。
6. **标准化 API**: 提供兼容 OpenAI 格式的 API，便于与其他工具（如 Open WebUI）对接。

## 应用场景

1. **Hermes Agent 后端模型供应**: 作为 Hermes Agent 的默认模型加载器，提供本地或云端模型。
2. **零硬件 AI 实验**: 没有 GPU 的用户通过 Ollama 的云端免费模型尝试运行 Hermes Agent。
3. **快速原型开发**: 开发者利用 Ollama 快速搭建 LLM 服务，与各种前端工具组合。

## 关系网络

- [[Hermes-Agent]] — **紧密集成**: Ollama 是 Hermes Agent 首选模型运行时，提供一键部署路径。
- [[Open-WebUI]] — **间接关联**: Open WebUI 可以通过配置连接 Ollama 的 API 端口，但本视频中主要通过 Hermes Agent 暴露的 API 连接。

## 关键事件/里程碑

- **Hermes Agent 集成发布**: Ollama 增加了对 Hermes Agent 的专用命令，大幅降低用户上手难度。

## 出现的视频来源

- [[Hermes-Agent-高级玩法与部署优化简报]]
