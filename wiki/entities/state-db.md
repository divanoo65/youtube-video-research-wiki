---
title: state.db
type: entity
tags:
  - Hermes-Agent
  - 核心组件
  - 数据库
summary: state.db 是 Hermes Agent 系统中的核心本地数据库文件，主要用于存储 AI 的知识储备量与运行状态，是衡量系统“大脑容量”的关键指标。
sources:
  - raw/notebooklm-analysis/Hermes-Agent-网页版中控台深度分析报告.md
created: 2024-05-22
updated: 2024-05-22
layer: L1
confidence: high
reasoning: 该实体直接来源于提供的分析报告，是系统架构中的基础数据存储单元，具有明确的定义和功能。
---

# state.db

## 实体描述
state.db 是 Hermes Agent 系统架构中的核心本地数据库文件，承担着系统“大脑容量”的存储职能。在技术层面，它不仅是系统运行状态的持久化载体，更是衡量 AI 知识储备量的重要量化指标。通过监控该文件的大小，用户可以直观地评估当前 AI 系统的积累深度与数据规模。作为系统底层的核心组件，state.db 支撑了包括[[工作记忆]]和[[用户画像]]在内的多种认知功能，确保 AI 能够跨会话保持连贯性与记忆深度。

## 在本视频中的角色
在《Hermes-Agent-网页版中控台深度分析报告》所描述的系统架构中，state.db 处于“数据总览与成长监控”板块的核心位置。它是 Dashboard 界面中“大脑容量”维度的唯一衡量标准。系统通过实时追踪 state.db 的文件大小，向用户反馈 AI 的知识储备增长情况。该实体不仅是静态的数据存储，更是系统动态成长性的直观体现，与[[Hermes Agent 网页版中控台深度分析报告]]中提到的各项活跃数据指标共同构成了 AI 系统的健康度评估体系。