---
title: 本地AI部署
type: concept
tags: [deployment, local, privacy, wsl, llama-cpp]
summary: 在本地硬件上部署大语言模型和 AI Agent 的技术方案，实现数据隐私和零成本运行
sources:
  - raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# 本地AI部署

本地AI部署是一种在本地硬件（而非云端）上部署大语言模型和 AI Agent 的技术方案，强调数据隐私、零成本和全天候可用性。

## 在本库的具体例子

在 [[Hermes-Qwen-3-6-本地最强-AI-Agent-部署与应用简报]] 中，本地AI部署方案包含以下阶段：
1. **环境准备**：在 Windows 上安装 WSL2 与 Ubuntu 24.04 作为底层系统
2. **硬件驱动**：更新 N 卡驱动与 CUDA 工具包，利用 GPU 硬件加速
3. **模型运行环境**：安装并编译 Llama-cpp（放弃 VLLM/DeepSpeed，采用更稳定的方案）
4. **模型获取**：使用 Llama-cpp 下载并运行 [[qwen-36]] 27B 模型（或 Qwen 3.5 系列小模型）
5. **Agent 配置**：对接 [[hermes-agent]]，通过自定义模式设置本地 URL
6. **第三方集成**：绑定 Telegram Bot 实现远程控制

## 与其他概念的对比或关系

本地AI部署与 SaaS 模式（如 ChatGPT、Claude 网页版）的对比：
- **成本**：本地部署零月费，SaaS 需订阅费用
- **隐私**：本地部署数据完全自主可控，SaaS 数据上传云端
- **性能**：本地部署受限于硬件，SaaS 享受云端算力
- **可用性**：本地部署 24 小时在线，SaaS 受网络和平台限制

## 关联概念

- [[程序化知识]]：本地部署后可通过程序化知识实现自动化复用
- [[分层记忆体系]]：本地部署中记忆体系持久化在本地方便可靠

## 关联实体

- [[hermes-agent]]：本地 AI 部署的核心智能体框架
- [[qwen-36]]：本地部署推荐的大语言模型
