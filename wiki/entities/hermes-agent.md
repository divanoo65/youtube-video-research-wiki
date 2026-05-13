---
title: Hermes Agent
type: entity
tags:
  - AI Agent
  - Hermes Agent
  - 赫美斯
  - Ollama
  - 本地部署
  - 智能体
summary: Hermes Agent（赫美斯）是一个高稳定性、低成本、支持本地部署和云端模型集成的 AI 智能体系统，通过主副模型架构和 Token 节约策略实现高效运行。
sources:
  - "raw/notebooklm-analysis/Hermes-Agent-高级玩法与配置深度简报.md"
created: 2026-05-13
updated: 2026-05-13
layer: L1
confidence: high
reasoning: 信息来源于官方视频深度解析报告，且 Hermes Agent 在开发者社区增长迅速，稳定性高于同类项目，数据可靠。
---

**Hermes Agent**（官方中文名：赫美斯）是一个以稳定性、低成本和高扩展性著称的 AI 智能体系统。相比同类项目如 **Opencloud**，Hermes Agent 在版本迭代过程中极少引入破坏性 bug，核心功能始终稳定运行，因此迅速赢得了开发者的信任，其 GitHub Star 增长速度已超越 Opencloud。该系统支持通过 **Ollama** 原生集成，用户可一键部署并使用免费云端模型（如 **Gemini 1.5 Flash**、**Minimax M2.7** 等），极大降低了入门门槛。Hermes Agent 的另一大特色是“主副模型架构”，即主模型负责核心推理与决策，副模型（通常为更轻量的模型）承担辅助任务（如信息检索、格式化输出），从而精细化控制 Token 消耗，实现成本与效率的平衡。此外，Hermes Agent 可与 **Open WebUI** 深度集成，提供美观、交互友好的 Web 界面，使得非技术用户也能轻松管理智能体对话、配置参数和监控 Token 使用情况。系统不仅支持完全本地部署保障数据隐私，还具备强大的扩展能力，允许用户通过插件机制接入自定义工具和知识库，适用于个人助理、自动化工作流、内容生成等多种场景。

在本视频（[YouTube 链接](https://www.youtube.com/watch?v=rBUfD_wvbhw&t=133s)）中，Hermes Agent 被设定为演示的主角，视频详细展示了如何使用 Ollama 快速部署该智能体、如何切换不同的云端模型以降低成本，以及如何通过主副模型配置来优化 Token 消耗。视频还强调了 Hermes Agent 相对于 Opencloud 的稳定性优势，并演示了与 Open WebUI 的集成效果，使观众能够直观地看到从命令行部署到可视化界面的完整流程。

相关页面：
- [[Ollama]]
- [[Open WebUI]]