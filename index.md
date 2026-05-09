# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-09 | Total pages: 20

## Sources
- [[Harness-Engineering-深度简报-构建稳定-可落地的-AI-Agent系统|Harness Engineering 深度简报：构建稳定、可落地的 AI Agent 系统]] — 深入剖析 Harness Engineering 概念，提出 Agent = Model + Harness 的核心公式，并给出六层成熟架构及行业最佳实践。
- [[Hermes-Agent-高级玩法与部署优化简报]] — 本视频介绍了Hermes Agent的稳定性优势、通过Ollama集成云端免费模型实现零资源部署、使用Open WebUI优化交互体验，以及通过主副模型策略降低Token消耗成本。

## Entities
- [[Anthropic]] — 美国人工智能公司，以 AI 安全研究闻名，提出 Context Reflected 和独立评估者模式等 Harness 实践。
- [[OpenAI]] — 全球领先的人工智能研究机构，提出环境设计理念、目录化 Skills 管理和自动化治理系统等 Harness 实践。
- [[Gemini]] — Google开发的大语言模型系列，本视频中推荐使用Gemini 1.5 Flash作为Hermes Agent的副模型。
- [[Hermes-Agent]] — 一个注重稳定性的AI Agent框架，支持主副模型分离、集成Ollama云端模型和Open WebUI，中文名“赫美斯”。
- [[Ollama]] — 一个本地大模型运行和管理工具，集成了Hermes Agent并支持一键部署云端免费模型。
- [[Open-WebUI]] — 一个开源的类ChatGPT交互界面，可连接Hermes Agent等后端，提供Markdown、代码执行等高级功能。
- [[OpenCloud]] — 一个与Hermes Agent竞争的AI Agent框架，但以更新频繁、稳定性差著称。

## Concepts
- [[约束工程]] — 通过构建模型外部的约束运行系统（Harness），确保 AI Agent 稳定、可纠偏、可落地的工程方法论。
- [[提示工程]] — 通过精心设计输入指令（Prompt）来引导 AI 模型产生期望输出的方法论，属于 AI 工程化第一阶段。
- [[上下文工程]] — 通过在正确时机向模型送入正确且适量的信息，解决模型“信息不足”或“信息过载”问题的工程方法。
- [[信息边界层]] — Harness 架构的第一层，负责定义 Agent 的角色、目标、任务范围，并裁剪和组织外部信息，避免上下文污染。
- [[执行编排层]] — Harness 架构的第三层，将原子能力（搜索、总结、写代码等）按逻辑链路串联成闭环流程，包括目标理解、任务串联、输出检查与修正重试。
- [[Ollama云端模型部署]] — 通过Ollama连接云端免费模型，实现零本地资源占用的Hermes Agent部署方法。
- [[Open-WebUI集成配置]] — 在Hermes Agent中启用API服务并设置密码，然后对接Open WebUI，获得类ChatGPT的交互体验。
- [[Token成本优化]] — 通过主副模型分离和辅助任务分类，将高频简单任务的Token消耗转移给廉价模型，实现Agent运行总成本的大幅下降。
- [[主副模型策略]] — 将复杂推理任务交给高端主模型，简单辅助任务交给廉价副模型，以显著降低Token消耗。
- [[辅助任务分类]] — Hermes Agent将代理运行过程中的非核心操作划分为六大辅助任务，可独立配置模型以降低成本。

## Comparisons
- [[Hermes-Agent-vs-OpenCloud]] — 从稳定性、更新策略、社区认可度等维度对比两个AI Agent框架。

## Overview

## Queries
