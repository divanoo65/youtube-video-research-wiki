---
title: "WSL 部署"
type: concept
tags: [windows, linux, wsl, deployment]
summary: "Windows Subsystem for Linux (WSL) 在 Windows 系统上运行 Linux 环境的技术方案，是本地 AI 部署的重要基础设施。"
sources:
  - raw/notebooklm-analysis/Kh8tGD5liwo-Hermes-Qwen3-6-本地最强-Agent-组合部署简报.md
  - raw/notebooklm-analysis/Kh8tGD5liwo-本地-AI-Agent-部署简报-Hermes-与-Qwen-3-6-组合方案.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
---

## 定义

WSL (Windows Subsystem for Linux) 是 Windows 系统上运行原生 Linux 环境的技术方案。在本地 AI 部署场景中，通过 WSL 安装 Ubuntu 24.04，用户可以在不改变 Windows 主系统的前提下，充分利用 Linux 环境对 AI 模型和工具链的高效支持。

## 在本库的具体例子

- Hermes + Qwen3.6 部署方案的核心底层环境：Windows 11 → PowerShell 安装 WSL → Ubuntu 24.04 → Llama-cpp + CUDA（参见 [[Hermes + Qwen3.6 本地最强 Agent 组合部署]]）

## 关联概念

- [[本地 AI Agent 部署]]：WSL 是 Windows 用户本地部署的必经之路
- [[Llama-cpp 推理框架]]：在 WSL 的 Linux 环境下编译运行

## 关联实体

- [[Qwen 3.6]]：在 WSL 环境下通过 Llama-cpp 运行
- [[Hermes Agent]]：在 WSL 环境中安装和配置
