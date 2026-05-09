# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-09 | Total pages: 37

## Sources
- [[GPT-5-5-Instant-深度分析简报-核心特性与实测表现|GPT-5.5 Instant 深度分析简报：核心特性与实测表现]] — OpenAI 发布 GPT-5.5 Instant，免费开放所有用户，重点降低幻觉率、提升对话自然度，并引入长期记忆功能。
- [[Hermes-Agent-与-OpenClaw-深度对比简报|Hermes Agent 与 OpenClaw 深度对比简报]] — 深入对比个人自托管智能体 Hermes Agent 与 OpenClaw，分析中心化控制 vs 循环驱动架构、程序化知识生成、分层记忆体系等核心差异。
- [[Hermes-Qwen3-6-本地-AI-Agent-组合部署与应用简报|Hermes + Qwen3.6 本地 AI Agent 组合部署与应用简报]] — 基于 Hermes Agent 与 Qwen3.6 构建零成本本地 AI 智能体，通过 WSL 实现完全本地部署，集成 Telegram 实现远程调用。

## Entities
- [[gpt-5-5-instant|GPT-5.5 Instant]] — OpenAI 发布的最新默认模型，免费开放所有用户，重点降低幻觉率并引入长期记忆功能。
- [[hermes-agent|Hermes Agent]] — Nous Research 开发的开源自托管智能体，以执行循环驱动架构和程序化知识生成能力著称。
- [[openclaw|OpenClaw]] — 早期自托管智能体代表，采用中心化 Gateway 架构，以稳定性和可审计性著称。
- [[qwen3-6|Qwen3.6]] — 通义千问最新开源模型，27B 参数，在中文理解、逻辑推理和代码编写方面表现卓越。
- [[qwen3-5|Qwen3.5]] — 通义千问系列的开源模型，提供 0.8B 到 9B 多种参数版本，适配中低端硬件。
- [[llama-cpp|Llama-cpp]] — 轻量级推理引擎，通过优化编译在低显存设备上运行大模型，防止显存溢出。
- [[nous-research|Nous Research]] — 开源 AI 研究团队，开发了 Hermes Agent 等创新项目，致力于推动本地智能体自我进化。
- [[telegram-bot|Telegram Bot]] — 通过 Telegram Bot 实现远程调用本地 AI Agent 的通信桥梁。
- [[evomap|EvoMap]] — 中国开源项目，Hermes Agent 被指涉嫌抄袭其架构设计。
- [[openai|OpenAI]] — 人工智能研究公司，开发了 GPT 系列模型，包括 GPT-5.5 Instant。

## Concepts
- [[幻觉率下降]] — 模型减少错误信息生成的能力，GPT-5.5 Instant 的核心改进方向。
- [[对话自然化]] — 模型减少机械式回应和奉承话术，使对话更接近人类自然交流。
- [[长期记忆]] — 模型跨会话记住用户信息和历史对话的能力，GPT-5.5 Instant 的 Memory Sources 功能。
- [[多模态理解]] — 模型处理图像、文件、图表等多种输入形式的能力。
- [[chat-latest-api策略|chat-latest API 策略]] — OpenAI 推出的动态 API 调用方式，自动指向最新模型版本。
- [[中心化网关]] — OpenClaw 采用的中心化控制架构，通过 Gateway 守护进程统一管理所有模块。
- [[执行循环驱动]] — Hermes Agent 的核心架构，将 AI 自身的执行循环作为同步编排引擎。
- [[程序化知识生成]] — Hermes Agent 自动将执行经验转化为可复用技能文件的机制。
- [[分层记忆体系]] — Hermes Agent 的四层记忆架构，从核心持久记忆到程序性记忆。
- [[五层防御安全模型]] — Hermes Agent 采用的纵深安全防御体系，包含用户授权、危险命令审批等五层。
- [[cron计划任务|Cron 计划任务]] — Hermes Agent 内置的定时任务系统，支持自然语言设定。
- [[模型无关性]] — Hermes Agent 支持切换不同后端模型而不修改核心代码的特性。
- [[wsl部署|WSL 部署]] — 在 Windows 上通过 WSL 运行 Linux 子系统来部署本地 AI Agent 的方法。
- [[llama-cpp方案|Llama-cpp 方案]] — 使用 Llama-cpp 作为推理引擎的本地模型部署方案，防止显存溢出。
- [[深度思考模式]] — Qwen 模型的可选推理模式，提升准确率但降低响应速度，对接 Agent 时建议关闭。
- [[远程调用]] — 通过 Telegram Bot 在手机端远程控制本地 AI Agent 执行任务。
- [[零月费模式]] — 通过开源模型和本地部署实现无需订阅费用的 AI 使用方式。
- [[数据主权]] — 用户数据完全保留在本地设备，不经过云端服务器的控制权。
- [[结构化输出]] — 模型以结论先行、结构清晰的方式生成内容，减少废话。
- [[高风险领域处理]] — 模型在医疗、金融等高风险领域保持谨慎，不直接下诊断结论。
- [[soul.md|SOUL.md]] — Hermes Agent 和 OpenClaw 中定义智能体身份和个性的配置文件。
- [[mcp协议|MCP 协议]] — Model Context Protocol，Hermes Agent 用于与外部工具和服务通信的协议。

## Comparisons
- [[hermes-agent-vs-openclaw|Hermes Agent vs OpenClaw]] — 对比 Hermes Agent 和 OpenClaw 在架构、记忆、自动化、安全等方面的差异。

## Overview
- [[本地AI-Agent部署与对比|本地 AI Agent 部署与对比]] — 综合对比 Hermes Agent 与 OpenClaw 的架构差异，并总结基于 Hermes + Qwen 的本地部署方案。

## Queries
