# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-11 | Total pages: 56

## Sources
- [[Harness-Engineering-深度简报-构建稳定-可落地的-AI-Agent系统|Harness Engineering 深度简报：构建稳定、可落地的 AI Agent 系统]] — 深入剖析 Harness Engineering 概念，提出 Agent = Model + Harness 的核心公式，并给出六层成熟架构及行业最佳实践。
- [[Hermes-Agent-高级玩法与部署优化简报]] — 本视频介绍了Hermes Agent的稳定性优势、通过Ollama集成云端免费模型实现零资源部署、使用Open WebUI优化交互体验，以及通过主副模型策略降低Token消耗成本。
- [[跨越视界的探索者深空影像录核心简报|跨越视界的探索者：深空影像录——核心简报]] — 本简报深入分析现代天文观测技术（尤其是JWST）如何带领人类跨越视觉极限，重构对宇宙起源的理解。
- [[Harness-Engineering-深度解析报告-核心概念与实战|Harness Engineering 深度解析：核心概念与实战]] — 深入剖析 Harness Engineering 概念，提出 Agent = Model + Harness 的核心公式，并给出 OpenAI 和 Anthropic 的实战案例及行业争议。
- [[Codex-Hooks-入门-实现任务自动化与音频通知简报|Codex Hooks 入门：实现任务自动化与音频通知简报]] — 介绍如何利用 Codex Hooks 在任务生命周期关键节点触发音频通知，解决长时间任务授权等待问题，并作为自动化工作流的入口。
- [[Anthropic-Managed-Agents-架构深度解析与复刻实践简报|Anthropic Managed Agents 架构深度解析与复刻实践简报]] — 深度解析 Anthropic 的 "Managed Agents" 架构，探讨 AI Agent 从个人工具向企业基础设施的范式转移。

## Entities
- [[Anthropic]] — 美国人工智能公司，以 AI 安全研究闻名，提出 Context Reflected 和独立评估者模式等 Harness 实践。
- [[OpenAI]] — 全球领先的人工智能研究机构，提出环境设计理念、目录化 Skills 管理和自动化治理系统等 Harness 实践。
- [[Gemini]] — Google开发的大语言模型系列，本视频中推荐使用Gemini 1.5 Flash作为Hermes Agent的副模型。
- [[Hermes-Agent]] — 一个注重稳定性的AI Agent框架，支持主副模型分离、集成Ollama云端模型和Open WebUI，中文名“赫美斯”。
- [[Ollama]] — 一个本地大模型运行和管理工具，集成了Hermes Agent并支持一键部署云端免费模型。
- [[Open-WebUI]] — 一个开源的类ChatGPT交互界面，可连接Hermes Agent等后端，提供Markdown、代码执行等高级功能。
- [[OpenCloud]] — 一个与Hermes Agent竞争的AI Agent框架，但以更新频繁、稳定性差著称。
- [[James-Webb空间望远镜|James Webb Space Telescope (詹姆斯·韦伯空间望远镜)]] — 詹姆斯·韦伯空间望远镜（JWST）是NASA/ESA/CSA合作的红外空间望远镜，工作在拉格朗日L2点，主镜6.5米，用于研究宇宙黎明、恒星形成和系外行星。
- [[哈勃空间望远镜|Hubble Space Telescope (哈勃空间望远镜)]] — 哈勃空间望远镜（HST）是NASA/ESA合作的空间望远镜，主镜2.4米，工作在可见光、紫外和部分红外波段，自1990年起极大推动了现代天文学发展。

## Concepts
- [[Agent]] — 智能体（AI Agent）是能够自主感知环境、做出决策并执行动作的 AI 系统，核心公式为 Agent = Model + Harness。
- [[Token成本优化]] — 通过主副模型分离和辅助任务分类，将高频简单任务的Token消耗转移给廉价模型，实现Agent运行总成本的大幅下降。
- [[Open-WebUI集成配置]] — 在Hermes Agent中启用API服务并设置密码，然后对接Open WebUI，获得类ChatGPT的交互体验。
- [[Ollama云端模型部署]] — 通过Ollama连接云端免费模型，实现零本地资源占用的Hermes Agent部署方法。
- [[上下文工程]] — 通过在正确时机向模型送入正确且适量的信息，解决模型"信息不足"或"信息过载"问题的工程方法。
- [[上下文重映]] — 在长时间对话中重置上下文窗口，通过结构化摘要保留关键信息以避免模型被历史淹没，Anthropic 提出的 Harness 技术。
- [[主副模型策略]] — 将复杂推理任务交给高端主模型，简单辅助任务交给廉价副模型，以显著降低Token消耗。
- [[内网穿透]] — 通过代理工具将内网服务暴露到公网，实现远程访问本地部署的 AI 服务。
- [[工具系统层]] — Harness 架构的第二层，定义 Agent 可调用的原子工具集及其调用时机，将模型能力暴露为结构化 API。
- [[思维链]] — 引导模型逐步推理的提示技术，通过在 Prompt 中展示推理步骤提升复杂问题的回答准确性。
- [[信息边界层]] — Harness 架构的第一层，负责定义 Agent 的角色、目标、任务范围，并裁剪和组织外部信息，避免上下文污染。
- [[检索增强生成]] — 在生成回答前检索外部知识库作为额外上下文，使 LLM 可以引用最新、最相关的事实性信息。
- [[独立评估者模式]] — Anthropic 提出的评估范式，将 Planner、Generator、Evaluator 角色分离，由独立评估者验证输出质量以降低幻觉风险。
- [[目录化管理]] — OpenAI 提出的上下文管理方法，将工程规范组织为索引目录结构，Agent 按需加载子文档而非一次性注入。
- [[约束、校验与恢复层]] — Harness 架构的第六层，定义 Agent 行为的硬性边界（规则约束）、输出事后校验机制以及异常恢复策略。
- [[约束工程]] — 通过构建模型外部的约束运行系统（Harness），确保 AI Agent 稳定、可纠偏、可落地的工程方法论。
- [[自动化治理]] — OpenAI 的系统化规则引擎，通过预定义规则和策略实现 Agent 行为的自动监控、纠偏和合规检查。
- [[记忆与状态层]] — Harness 架构的第四层，管理 Agent 的工作记忆、情景记忆和长期记忆，确保跨会话的上下文连续性。
- [[评估与观测层]] — Harness 架构的第五层，通过独立验证机制对 Agent 行为进行实时监控、评估和反馈，支持系统持续改进。
- [[辅助任务分类]] — Hermes Agent将代理运行过程中的非核心操作划分为六大辅助任务，可独立配置模型以降低成本。
- [[执行编排层]] — Harness 架构的第三层，将原子能力（搜索、总结、写代码等）按逻辑链路串联成闭环流程，包括目标理解、任务串联、输出检查与修正重试。
- [[提示工程]] — 通过精心设计输入指令（Prompt）来引导 AI 模型产生期望输出的方法论，属于 AI 工程化第一阶段。
- [[红外观测|红外观测（Infrared Astronomy）]] — 红外观测是探测天体在红外波段辐射的天文方法，能穿透星际尘埃观测恒星形成区和高红移早期宇宙。
- [[代表颜色技术|代表颜色技术（Representative Color）]] — 深空影像处理中将不可见红外波段映射为可见光颜色的方法，通过赋予不同滤光片特定RGB通道生成色彩准确且科学可解释的伪色图像。
- [[宇宙黎明|宇宙黎明（Cosmic Dawn）]] — 宇宙大爆炸后约1-4亿年第一批恒星和星系开始形成的时期，红外观测是其核心研究手段。
- [[多信使天文学|多信使天文学（Multi-messenger Astronomy）]] — 利用电磁辐射、引力波、中微子和宇宙射线等多种信使同时观测宇宙现象的方法。
- [[F-Harness架构]] — Anthropic 提出的多 Agent 协作架构，通过 Planner、Generator、Evaluator 角色分离提升长程任务质量。
- [[单一事实来源]] — OpenAI 提出的数据管理原则，将所有技术决策和知识文档化并集中存放在代码仓库。
- [[吸收效应]] — 随着大模型能力增强，原本需要外部 Harness 解决的问题逐渐被模型内置吸收的现象。
- [[技术债自动清理]] — OpenAI 通过后台任务定期扫描代码库和文档，自动修复重复代码和过时文档的实践。
- [[Codex-Hooks]] — OpenAI Codex CLI 提供的事件驱动机制，允许在任务生命周期节点绑定自定义脚本实现自动化。
- [[Codex-Hooks生命周期]] — Codex Hooks 定义的六个标准化任务生命周期节点，用于精准触发自动化脚本。
- [[Codex-Hooks部署范围]] — Codex Hooks 支持项目级与全局级两种配置作用域，分别适用于单一项目和用户所有项目的自动化规则。
- [[Codex-Hooks信任机制]] — Codex Hooks 的安全机制，要求用户在新配置后手动审查并授权，防止恶意脚本自动执行。
- [[多标签并行处理]] — 一种通过多标签并行处理提高任务执行效率的技术方法。
- [[无状态化]] — 一种通过消除状态依赖提高系统稳定性和可扩展性的技术方法。
- [[沙盒技术]] — 一种通过隔离执行环境确保系统安全性和稳定性的技术方法。

## Comparisons
- [[Hermes-Agent-vs-OpenCloud]] — 从稳定性、更新策略、社区认可度等维度对比两个AI Agent框架。
- [[哈勃空间望远镜-vs-詹姆斯韦伯空间望远镜|哈勃空间望远镜 vs 詹姆斯·韦伯空间望远镜]] — 从主镜口径、工作波段、工作温度、科学核心等维度对比哈勃与韦伯两台标志性空间望远镜。
- [[OpenAI-vs-Anthropic|OpenAI vs Anthropic: Harness Engineering 实践对比]] — 对比 OpenAI 和 Anthropic 在 Harness Engineering 上的不同实践路径。

## Overview
- [[Harness-Engineering-综述|Harness Engineering 综述]] — 综合现有 Harness Engineering 相关视频分析，梳理核心概念、实战案例、争议及未来趋势。

## Queries
