---
title: Hermes Agent
created: 2026-05-08
updated: 2026-05-08
type: entity
tags: [ai-agents, product, intelligence]
sources: [raw/notebooklm-analysis/S6XCelOhZ6w_report.md]
confidence: high
---

# Hermes Agent

## 概述

Hermes Agent 是一个 AI 智能体平台，支持自然语言指令解析和 [[Skill]] 调度能力。核心特点是能够与多个外部工具集成，包括 [[Google NotebookLM]]、知识库管理等系统。

## 核心功能

- **技能加载**：通过 Skill 插件系统扩展功能
- **意图解析**：理解用户自然语言并将其转化为可执行任务
- **子进程调度**：管理多个执行任务并整合结果
- **记忆管理**：维护智能体的长期记忆和知识状态

## 关键特性

### 集成能力
- 与 [[Google NotebookLM]] 无缝集成实现[[知识库管理]]
- 支持 [[notebookrm-py]] 库进行自动化操作
- 通过 [[自动化工作流]] 实现任务的链式执行

### 扩展性
- Skill 插件化架构支持功能扩展
- 支持多 Agent 协同工作
- 支持定时任务和[[自动化工作流]]

## 应用场景

在 [[Hermes-NotebookLM集成]] 中的角色：
- 解析用户的知识库操作指令
- 调用 NotebookLM 进行内容处理
- 生成多模态输出（视频、幻灯片、播客）
- 实现[[知识飞轮效应]]

## 相关技术栈

- [[notebookrm-py]] - Python SDK
- [[Google NotebookLM]] - 云端知识处理
- Cookie 持久化认证机制
