---
title: "WSL (Windows Subsystem for Linux)"
type: entity
tags: [windows, linux, virtualization, development-environment]
summary: "Windows 的 Linux 子系统，在 Hermes + Qwen3.6 本地部署方案中作为运行底层 Ubuntu 24.04 的基础环境。"
sources:
  - raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
section: entities
---

# WSL (Windows Subsystem for Linux)

## 基本定位
Windows 内置的 Linux 子系统功能层。在 Hermes + Qwen3.6 本地部署方案中，WSL 是整个系统的底层基础——在 Windows 中通过 WSL 安装 Ubuntu 24.04，后续所有 CUDA 安装、Llama-cpp 编译、模型下载和 Hermes Agent 运行均在 WSL 环境内完成。

## 核心特征/能力

1. **系统基础层**: 在 Hermes 本地部署五阶段架构中位于最底层
2. **Windows 集成**: 通过管理员 PowerShell 一键安装，与 Windows 文件系统互通
3. **Ubuntu 24.04**: 推荐的 WSL 发行版，用于承载完整的 AI 开发环境

## 关系网络
- [[hermes-agent]] — 在其上运行的应用层
- [[qwen3-6]] — 在其上运行的模型
- [[llama-cpp]] — 在其上编译的推理引擎

## 出现的视频来源
- [[Hermes 与 Qwen3.6 本地 AI Agent 部署与应用简报]]
