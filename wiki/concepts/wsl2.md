---
title: WSL2
type: concept
tags: [windows, linux, virtualization, deployment]
summary: Windows Subsystem for Linux 2，在 Windows 上运行完整 Linux 内核的技术，是本地部署 AI Agent 的核心环境。
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 视频中 WSL2 是整个部署流程的基础环境，操作细节详细。
---

## 定义

WSL2（Windows Subsystem for Linux 2）是 Microsoft 提供的虚拟化技术，允许在 Windows 上运行原生 Linux 内核。在 AI Agent 部署中，它使 Windows 用户能够运行 Linux 专有软件（如 Llama-cpp 和 Hermes Agent）。

## 在本库的具体例子

- 在 [[零成本本地-AI-Agent-部署与应用简报-Hermes-与-Qwen-3-6]] 中，用户在 Windows 11 上通过 `wsl --install` 安装 Ubuntu 24.04 子系统，然后在该环境中编译 Llama-cpp、下载 Qwen 模型并运行 Hermes Agent。

## 技术实现细节

- WSL2 使用 Hyper-V 虚拟机技术，提供完整的 Linux 内核，性能接近原生。
- 支持 GPU 直通（需最新 NVIDIA 驱动），使得在 WSL2 内可使用 CUDA 加速。
- 通过 `\wsl.localhost\` 路径可以访问 Linux 文件系统。
- 启动脚本可配置为 Windows 开机自动运行。

## 与近似概念的边界

- **原生 Linux**：如果用户已有 Linux 机器，可跳过 WSL2；但 WSL2 让 Windows 用户无需双系统即可使用。
- **Docker 桌面**：Docker 也可在 WSL2 上运行，但 Hermes Agent 推荐直接在 WSL2 中运行，而非 Docker 容器内。

## 关联概念

- [[推理引擎]]
- [[gguf格式]]

## 关联实体

- [[llama-cpp]]
