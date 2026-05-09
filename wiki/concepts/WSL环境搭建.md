---
title: WSL 环境搭建
type: concept
tags: [wsl, ubuntu, environment-setup, windows, linux]
summary: 在 Windows 上通过 WSL（Windows Subsystem for Linux）搭建 Ubuntu 环境以运行本地 AI Agent
sources:
  - raw/notebooklm-analysis/零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# WSL 环境搭建

## 定义

WSL（Windows Subsystem for Linux）环境搭建是指在 Windows 系统上通过启用 Linux 子系统并安装 Ubuntu 24.04，再配置 NVIDIA 显卡驱动直通和 CUDA 工具包，从而获得 Linux 原生性能的本地 AI 运行环境。该方案解决了 Hermes Agent 不支持原生 Windows 的问题，实现了 Windows 日常使用与 Linux 高性能推理的无缝切换。

## 在本库的具体例子

在 [[零成本本地-AI-Agent-部署方案-Hermes-与-Qwen-3-6-综合]] 中，完整的 WSL 环境搭建分为四个阶段：
1. **基础环境**：在管理员 PowerShell 中安装 WSL，部署 Ubuntu 24.04 并设置用户凭据
2. **驱动直通**：确保 NVIDIA 显卡驱动正确直通至 WSL 环境，必要时更新至最新版本
3. **依赖安装**：安装 Python、pip 及 CUDA 工具包（约 2G）
4. **启动脚本**：创建 Linux 启动脚本，实现开机自动加载模型与 Agent 服务

## 技术实现细节

- Hermes Agent 目前不支持原生 Windows 系统，必须安装 WSL2 环境
- NVIDIA 驱动直通需要 Windows 版 NVIDIA 驱动支持 WSL（最新 Game Ready 或 Studio 驱动均可）
- CUDA 工具包在 WSL 中安装后可直接访问物理 GPU 资源
- WSL 中的 Ubuntu 环境可以配置随 Windows 开机自动启动

## 与近似概念的边界

- **WSL ≠ 虚拟机**：WSL 比虚拟机更轻量，与 Windows 共享文件系统和网络，但提供完整的 Linux 内核兼容性。
- **WSL ≠ Docker**：WSL 是操作系统层面的 Linux 兼容层，Docker 是容器化平台，两者可以结合使用（Docker Desktop for Windows 底层即使用 WSL）。

## 关联概念

- [[本地AI推理部署]] — WSL 是本地部署的基础运行环境
- [[本地模型选择策略]] — 在 WSL 环境中根据显存选择模型
- [[Telegram远程Agent控制]] — 在 WSL 中运行 Agent 并通过 Telegram 控制

## 关联实体

- [[hermes-agent]] — 需要在 WSL 环境中运行的 Agent 框架
- [[qwen-3-6]] — 在 WSL 环境中部署的模型
