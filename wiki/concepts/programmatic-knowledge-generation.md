---
created: 2026-05-09
updated: 2026-05-09
title: 程序化知识生成
type: concept
tags: [ai-agent, skill-generation, automation]
sources: [raw/notebooklm-analysis/NbldZVdusKo_b2e25f66-64ec-4549-87e3-c43184c449dc_20260509T010844Z_report.md]
summary: Hermes Agent 能根据执行经验自动生成新技能并存储，实现跨会话持续学习，让能力随使用时间的增加而产生量变到质变的飞跃。
layer: L2
confidence: high
reasoning: 基于视频中对 Hermes Agent 技能机制的描述
---

# 程序化知识生成

## 定义与核心含义
程序化知识生成指的是智能体能够根据执行经验自动生成新的技能或工作流，而不仅仅是存储事实知识。Hermes Agent 通过内置的 `skill_manage` 工具，将完整的工作流抽象为“程序化知识”，存储在 `~/.hermes/skills/` 中，实现跨会话的持续学习。

## 应用场景与步骤
- **技能创建**：智能体在执行任务过程中发现可重复的模式，自动生成对应的技能文件（SKILL.md）。
- **技能存储**：生成的技能被存储在 `~/.hermes/skills/` 目录下，支持后续直接调用。
- **技能复用**：在后续任务中，智能体可以加载并执行之前生成的技能，无需重新编写。
- **持续学习**：随着使用时间的增加，智能体积累更多技能，能力从量变到质变飞跃。

## 在本库视频中的具体例子
视频中提到：\"Hermes Agent 的技能观：将完整的工作流抽象为‘程序化知识’。智能体能根据执行经验自动生成新技能并存储在 `~/.hermes/skills/` 中。通过内置的 `skill_manage` 工具，它能实现跨会话的持续学习，让能力随使用时间的增加而产生量变到质变的飞跃。*

## 关联概念
[[分层记忆体系]] [[自动化能力]] [[身份定义]] [[Agent 执行循环]]

## 关联实体
[[Hermes Agent]] [[OpenClaw]]

---
*本页面内容基于 YouTube 视频 https://www.youtube.com/watch?v=NbldZVdusKo 的 NotebookLM 分析报告生成。*
