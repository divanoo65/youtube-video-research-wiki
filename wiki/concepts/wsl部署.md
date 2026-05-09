---
title: WSL 部署
type: concept
tags: [windows, linux, deployment, local-ai]
summary: 在 Windows 上通过 WSL 运行 Linux 子系统来部署本地 AI Agent 的方法。
sources: [raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# WSL 部署

## 定义

WSL（Windows Subsystem for Linux）部署指在 Windows 操作系统上安装 Linux 子系统（如 Ubuntu 24.04），并在其中配置 CUDA 工具包、Llama-cpp 和 Hermes Agent，从而实现完全本地的 AI 智能体运行环境。这是 Windows 用户实现零成本本地部署的关键路径。

## 在本库的具体例子

在 [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报]] 中，部署流程的第一步就是安装 WSL (Ubuntu 24.04) 并更新 N 卡驱动，后续所有操作均在 WSL 内完成。

## 技术实现细节

WSL 2 提供完整的 Linux 内核，支持 GPU 直通（需安装 Nvidia 驱动和 CUDA Toolkit）。用户通过 `wsl --install` 命令安装，然后在 Linux 环境中安装 Python、pip、CUDA 等依赖，最后部署模型和 Agent。

## 与近似概念的边界

- **虚拟机**：虚拟机需要分配独立内存和磁盘，WSL 与 Windows 共享资源，启动更快。
- **Docker**：Docker 是容器化方案，WSL 是子系统，两者可结合使用。

## 关联概念

- [[llama-cpp方案]]
- [[深度思考模式]]

## 关联实体

- [[llama-cpp]]
- [[hermes-agent]]
