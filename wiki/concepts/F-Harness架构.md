---
title: F-Harness 架构
type: concept
tags: [harness-engineering, anthropic, multi-agent, evaluation]
summary: Anthropic 提出的多 Agent 协作架构，通过 Planner、Generator、Evaluator 角色分离提升长程任务质量。
sources: [raw/notebooklm-analysis/Harness-Engineering-深度解析报告-概念-实战与-AI-开发的.md]
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: high
reasoning: 报告明确给出了架构定义、角色分工和性能对比数据。
run_id: T-3DlXq9nsQOE
---

# F-Harness 架构

## 定义
F-Harness 是 Anthropic 针对长时运行 AI Agent 提出的多 Agent 协作框架，将任务拆解为三个独立角色：Planner（规划者）、Generator（生成者）和 Evaluator（评估者），通过角色分离和协商交付标准来提升复杂代码生成的质量和可靠性。

## 技术实现细节
- **Planner**: 接收模糊需求，将其拆解为详细的功能列表，并确定实现顺序。
- **Generator**: 逐个实现功能点，在开始每个功能前与 Evaluator 确认交付标准。
- **Evaluator**: 独立的第三方 Agent，负责客观审计生成结果，避免“王婆卖瓜”式的自我评估。

## 在本库的具体例子
在 [[Harness-Engineering-深度解析报告-核心概念与实战]] 中，Anthropic 对比了 Solo 方案（单 Agent）和 F-Harness 方案的性能数据：
- Solo：耗时 20 分钟，花费 9 美元，但布局不合理、Bug 多。
- F-Harness：耗时 6 小时，花费 200 美元，效果达到可用水准。

## 与近似概念的边界
- [[独立评估者模式]]：独立评估者模式仅关注评估环节，而 F-Harness 包含完整的规划-生成-评估三阶段流水线，且强调角色间的交互（Generator 与 Evaluator 会协商标准）。
- [[约束工程]]：约束工程侧重于构建外部规则系统，而 F-Harness 侧重于多 Agent 的分工协作机制。

## 关联概念
- [[独立评估者模式]]
- [[约束工程]]
- [[执行编排层]]

## 关联实体
- [[Anthropic]]
