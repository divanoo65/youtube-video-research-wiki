---
title: Anthropic
type: entity
tags: [ai-company, safety, agent-engineering]
summary: 专注于AI安全的研究公司，在Agent工程化中提出Context Refresh和角色分离机制等实践。
sources: [raw/notebooklm-analysis/Harness-Engineering-AI-应用落地从-概率生成-走向-稳定交.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
confidence: high
reasoning: 基于视频中对Anthropic实践的描述
run_id: T-3DlXq9nsQOE
---

# Anthropic

## 基本定位
Anthropic 是一家人工智能安全公司，由前 OpenAI 员工创立，以 Claude 系列模型闻名。在本报告中，Anthropic 因其在 Agent 工程化中的两项关键实践——**Context Refresh** 和 **角色分离机制**——被作为 Harness Engineering 的典型案例引用。

## 核心特征/能力

1. **Context Refresh（上下文重启）**：当上下文过长导致模型丢失细节或产生收尾焦虑时，Anthropic 不采用压缩方式，而是更换一个干净的 Agent 实例来承接状态，类似操作系统的进程重启。
2. **角色分离机制（Planner/Generator/Evaluator）**：将复杂任务拆分为三个独立角色——Planner（规划者）、Generator（执行者）和 Evaluator（评估者），其中 Evaluator 拥有独立运行环境进行真实操作验证，确保生产与验收逻辑分离。
3. **执行与验收环境隔离**：Evaluator 的验证并非模型自评，而是基于真实环境反馈（如代码执行结果、UI 截图对比），降低模型自评偏差。
4. **长任务稳定性治理**：通过角色分离和上下文重启，Anthropic 能在多个步骤的 Agent 任务中保持高成功率，避免上下文污染导致的连锁失败。
5. **对安全性的持续关注**：作为安全优先的公司，其 Harness 实践天然带有约束和校验机制，防止 Agent 越过操作红线。

## 应用场景

- **复杂多步骤任务**：例如自动生成并测试代码、多轮数据治理流程，Planner 规划子任务，Generator 执行，Evaluator 验证结果，每一步均有独立验证。
- **需要长上下文的对话系统**：当对话超过模型有效窗口时，采用 Context Refresh 而非简单截断，确保信息不丢失。
- **关键业务决策辅助**：需要人工审核的环节，Evaluator 的输出可以作为审计日志。

## 关系网络

- [[OpenAI]]：同行业竞争者，在 Agent 工程化路径上各有侧重（Anthropic 侧重角色分离与上下文重启，OpenAI 侧重环境设计与自动治理）。
- [[马具工程]]：Anthropic 的实践是马具工程在顶级公司的具体体现。
- [[上下文刷新]]：由 Anthropic 提出并实践。
- [[角色分离机制]]：由 Anthropic 系统化应用。

## 关键事件/里程碑

- 2021年：Anthropic 成立。
- 2023年：发布 Claude 系列模型，开始探索 Agent 工程化。
- 2024-2025年：在内部和客户项目中推广 Context Refresh 和角色分离机制，成为 Harness Engineering 代表性案例。

## 出现的视频来源
- [[Harness-Engineering-从概率生成走向稳定交付]]