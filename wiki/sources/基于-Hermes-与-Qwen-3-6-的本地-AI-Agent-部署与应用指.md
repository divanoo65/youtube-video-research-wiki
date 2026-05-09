---
title: 基于 Hermes 与 Qwen 3.6 的本地 AI Agent 部署与应用指南
type: source
tags: [hermes-agent, qwen-3-6, 本地部署, wsl2, llama-cpp]
summary: 详细分析通过整合 Hermes Agent 与 Qwen 3.6 构建零成本、高隐私、高性能本地 AI 智能体环境的完整方案。
sources:
  - raw/notebooklm-analysis/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.md
  - raw/notebooklm-mindmaps/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.json
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地-AI-Agent-部署与应用分析简报.md
  - raw/notebooklm-mindmaps/Hermes-Qwen-3-6-本地-AI-Agent-部署与应用分析简报.json
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
video_url: https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh
mindmap: raw/notebooklm-mindmaps/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.json
---

# 基于 Hermes 与 Qwen 3.6 的本地 AI Agent 部署与应用指南

**视频链接：** <https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh>

**脑图文件：** `raw/notebooklm-mindmaps/基于-Hermes-与-Qwen-3-6-的本地-AI-Agent-部署与应用指.json`

## 执行摘要

本报告详细分析由"零度解说"提出的本地 AI 解决方案，该方案通过整合 [[hermes-agent]] 与 [[qwen-3-6]]（通义千问）大模型，构建零成本、高隐私、高性能的本地 AI 智能体环境。该架构解决商业 AI 服务的三大痛点——**Token 费用消耗、数据隐私、地理/网络访问限制**。通过在 Windows 环境下利用 WSL2 和 [[llama-cpp]] 框架，可达到每秒约 40-60 Token 的推理速度，并通过 Telegram 实现远程调用与定时任务执行。

## 核心要点

1. **技术栈选型：** 以 [[hermes-agent]] 作为 Agent 框架负责任务调度与多平台对接，以 [[qwen-3-6]]（27B 为优选）作为底层推理引擎。
2. **本地化部署路径：** 利用 Windows WSL2 (Ubuntu 24.04) 确保 Linux 原生性能，推荐 [[llama-cpp]] 方案而非 VLLM 以避免显存溢出。
3. **推理效率：** 27B 模型在本地可达 ~39.51 Token/s，优化后可达 50-60 Token/s，关闭"深度思考模式"后响应更快。
4. **本地 API 桥接：** 通过 [[llama-cpp]] 开启兼容 OpenAI 标准的 API 服务（默认端口 8080），[[hermes-agent]] 无缝接入本地模型。
5. **远程控制：** 通过 Telegram Bot（BotFather）集成，实现手机端远程调用家中计算资源。
6. **显存要求：** 27B 模型约需 17G 显存，较小模型（0.8B-9B）可适配更低显存。
7. **驱动与 CUDA 环境：** 必须安装 CUDA 工具包（约 2G）并配置环境变量，否则模型回退至 CPU 推理。
8. **开源模型可用性：** 非超大规模工程的编程任务或日常逻辑处理，开源模型已能提供媲美闭源商业模型的产出质量。
9. **[[Token自由]]：** 通过一次性的硬件投入换取长期的零边际成本使用，同时规避云端服务的隐私风险。

## 关键引言

> "关键是完全免费，真的可以做到 TOKEN 自由，零月费，数据隐私安全完全掌握在自己手里。"
> *上下文：说明本地部署的核心动机——一次性的硬件投入换取长期零边际成本使用，同时规避云端服务的隐私风险。*

> "关闭深度思考模式以后，更适合对接 Hermes Agent，速度会更快。"
> *上下文：配置 Agent 时，响应速度往往比冗长的思考过程更重要。*

> "其实普通人很多的任务，都不需要用收费模型，本地模型已经足够使用了。"
> *上下文：对本地模型能力的客观评价——非超大规模工程的编程或日常逻辑处理，开源模型已能媲美商业模型。*

## 部署步骤

### 第一阶段：基础设施
1. NVIDIA 显卡驱动更新至最新（WSL2 识别 GPU 算力的前提）
2. 安装 WSL2 Ubuntu 24.04，执行 `sudo apt update`
3. 安装 CUDA 工具包，正确配置环境变量

### 第二阶段：模型与服务部署
1. 国内用户建议使用 ModelScope（魔搭社区）镜像下载模型
2. 启动模型时根据 Agent 需求选择是否禁用 `thinking mode`
3. 编写启动脚本并加入自动运行流程，实现开机即用

### 第三阶段：Agent 智能化
1. 对接 Telegram（通过 BotFather 获取 Token）
2. 配置 Hermes 为"个人使用"模式，绑定唯一 Telegram ID
3. 部署定时任务在后台持续处理数据或监控信息

## 脑图核心节点

- **基于 Hermes 与 Qwen 3.6 的本地 AI Agent**（根节点）
  - **技术栈选型：** Qwen 3.6（中文理解、代码编写、逻辑推理）、Hermes Agent（任务调度、多平台对接、记忆管理）
  - **本地化部署工程实践：** 环境隔离（WSL2 Ubuntu 24.04）、推理加速（Llama-cpp）、本地 API 桥接（端口 8080）
  - **性能表现：** 推理效率（40 Token/s）、远程控制（Telegram Bot）
  - **关键数据：** Qwen 3.6 27B 优选、Llama-cpp 架构、~39.51 Token/s、17G 显存要求、Telegram 远程平台

## 关联实体

- [[hermes-agent]] — 方案核心的 Agent 框架
- [[qwen-3-6]] — 底层推理引擎（通义千问）
- [[llama-cpp]] — 推理加速框架

## 关联概念

- [[Token自由]] — 本地部署的核心动机
- [[执行循环驱动架构]] — Hermes Agent 的底层架构
