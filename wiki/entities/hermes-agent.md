---
title: "Hermes Agent"
type: entity
tags: ["AI Agent", "Hermes", "Ollama", "开源框架", "Token优化", "云端部署"]
summary: "Hermes Agent（赫美斯）是一个高稳定性的AI Agent框架，以其极简的Ollama一键部署、云端免费模型集成以及主副模型配置方案实现Token成本控制而著称，关注度增长已超越同类项目OpenCloud。"
sources: ["raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-云端模型-美化界面与省-Token.md"]
created: 2026-05-12
updated: 2026-05-12
layer: L1
confidence: high
reasoning: "信息直接来源于官方分析报告，包含具体部署、对比数据和性能细节，且该框架在GitHub社区活跃度持续上升，来源可靠、内容翔实。"

# Hermes Agent
---

## 实体描述

Hermes Agent（中文名：赫美斯）是一个专注于高稳定性与易用性的AI Agent框架，其GitHub仓库的关注度增长已超越同类项目OpenCloud，核心优势在于极为可靠的系统更新机制——避免了类似OpenCloud在迭代过程中频繁引入错误（Bug）导致崩溃的问题。该框架通过原生集成Ollama，实现了基于云端免费模型的“傻瓜化”部署流程：用户仅需简单命令即可完成环境搭建，无需繁琐的依赖配置。同时，Hermes Agent支持通过Open WebUI搭建美观的交互界面，并允许跨端（如手机、平板）远程使用，结合内网穿透技术可进一步实现移动办公。在成本控制方面，Hermes Agent引入了主副模型（Main/Sub Models）配置方案——主模型负责核心推理（可选用高性能模型如Gemini 1.5 Flash或Claude），副模型处理简单任务（如格式校验、文本分类），从而大幅降低Token消耗。此外，框架还兼容多种后端API服务（如Minimax、ChatGPT、Codex），并支持通过微信、VS Code等终端调用。整体上，Hermes Agent通过稳定性、免费算力利用和精细化Token策略，成为目前最受关注的AI Agent框架之一。

## 在本视频中的角色

本视频《Hermes Agent 高级玩法与优化指南：云端模型、美化界面与省 Token 配置方案》以Hermes Agent为核心研究对象，详细解析了其三个关键高级功能：一是与**Ollama**的深度集成，展示了如何一键部署并调用云端免费模型（如Gemini 1.5 Flash），无需本地GPU资源；二是通过**Open WebUI**美化界面并实现跨端访问，演示了容器化部署与内网穿透的步骤；三是重点剖析了主副模型配置方案，提供了具体的YAML配置样例和实际Token节省效果（如将复杂任务分配给主模型，简单任务分配给副模型，可降低总消耗30%-50%）。视频通过对比同类项目（如OpenCloud）的稳定性缺陷，凸显了Hermes Agent在工程实践中的可靠性，并给出了从个人开发到团队协作的最佳实践建议。

## 相关链接

- [[Ollama]]
- [[主副模型配置方案]]
- [[Open WebUI]]
- [[Minimax]]