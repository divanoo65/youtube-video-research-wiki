---
title: Ollama
type: entity
tags:
  - AI
  - LLM
  - 开源模型平台
  - 本地部署
  - 云端模型
  - Hermes Agent集成
summary: Ollama 是一个轻量级的开源大模型运行平台，支持本地与云端模型调用，被 Hermes Agent 原生集成，提供低成本、零门槛的 AI 智能体部署方案。
sources:
  - "raw/notebooklm-analysis/度简报.md"
created: 2025-06-12
updated: 2025-06-12
layer: L1
confidence: high
reasoning: 基于 Hermes Agent 高级玩法与配置深度简报中的明确描述，以及 Ollama 官方公开文档，信息可靠且无矛盾。
---

## 实体描述

Ollama 是一个开源的大语言模型（LLM）管理与运行平台，旨在简化用户在不同硬件环境下部署和调用 AI 模型的过程。它支持一键下载、加载和运行包括 Llama、Mistral、Gemma 在内的主流开源模型，并提供了简洁的 REST API 接口，方便第三方应用集成。Ollama 最大的特点是“轻量”与“零配置”：用户只需从官网下载安装对应操作系统的版本，通过一条终端命令即可启动模型服务。为了进一步降低资源消耗，Ollama 还推出了云端模型方案——用户无需本地 GPU，只需通过浏览器完成设备连接，即可免费调用平台提供的云端模型（如 Minimax M2.7）。这种混合架构既保证了本地数据的隐私性，又利用云端算力实现了低成本推理。在社区生态方面，Ollama 的 GitHub 仓库关注度持续攀升，其稳定性受到开发者广泛认可，尤其是在与 Hermes Agent 等智能体框架的深度集成中表现突出。通过 Ollama，普通用户也能轻松搭建具备联网搜索、工具调用、多轮对话等复杂能力的 AI 助手，而不必关心底层模型部署的细节。

## 在本视频中的角色

在本视频（即 Hermes Agent 高级玩法与配置深度简报中提及的演示场景）中，Ollama 担任了核心模型后端的重要角色。视频演示了如何通过 Ollama 一键启动 Hermes Agent，并利用其集成的免费云端模型（如 Minimax M2.7）完成智能体的各项任务。Ollama 的存在使得 Hermes Agent 的部署流程从原先需要手动配置 GPU 环境、下载模型文件，简化为仅需浏览器登录即可调用云端推理能力，极大降低了新手用户的上手门槛。此外，视频还介绍了通过 Ollama 实现“主副模型”配置——主模型（如 [[Minimax M2.7]]）负责复杂推理，副模型（如 [[Gemini 1.5 Flash]]）处理简单重复任务，从而在保证响应质量的同时降低 Token 消耗（即 [[Token节约策略]]）。整个案例充分展现了 Ollama 作为模型抽象层在智能体生态中的桥梁作用。

## 关联页面

- [[Hermes Agent 高级玩法与配置深度简报]]：详细介绍了 Hermes Agent 的安装、配置及 Ollama 集成步骤。
- [[Minimax M2.7]]：Ollama 云端提供的免费模型之一，在视频中被用作主模型。
- [[Open WebUI]]：与 Ollama 配合使用的交互界面，视频中演示了如何通过 Open WebUI 增强 Hermes Agent 的用户体验。