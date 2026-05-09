---
title: WSL2部署
type: concept
tags: [windows, wsl2, ubuntu, deployment]
summary: 在 Windows 系统中通过 WSL2（Windows Subsystem for Linux 2）搭建 Linux 开发环境，运行 AI 模型和智能体系统的方案。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署简报-Hermes-与-Qwen3-6-的深度.md
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报-下一代自我进化智能.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

# WSL2部署

## 定义

WSL2 部署是指在 Windows 操作系统上利用 Windows Subsystem for Linux 2 创建完整的 Linux 环境（如 Ubuntu 24.04），从而在 Windows 机器上运行 AI 模型推理和智能体系统。

## 在本库的具体例子

- **Qwen3.6 + Hermes Agent 的 Windows 部署**：在 Windows 系统中安装 WSL2 + Ubuntu 24.04，配置最新 N 卡驱动和 CUDA 工具包，安装 Llama-cpp 后部署 Qwen3.6 27B 模型。
- **Hermes Agent 的系统要求**：Windows 用户必须安装 WSL2 才能运行 Hermes Agent。
- **开机自启**：通过 Linux 自启动脚本在 WSL2 环境内自动恢复 AI 服务。

## 关联概念

- [[本地部署]] — WSL2 是 Windows 本地部署的基础
- [[Llama-cpp]] — 在 WSL2 中运行的推理框架
- [[全天候AI助手]] — WSL2 部署的最终产品形态

## 关联实体

- [[hermes-agent]] — 依赖 WSL2 在 Windows 上运行
- [[qwen3.6]] — 在 WSL2 中推理的模型
