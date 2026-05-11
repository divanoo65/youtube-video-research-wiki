---
title: Anthropic公司
type: entity
tags: [ai-company, safety-research, claude, harness-engineering]
summary: 人工智能安全研究公司，提出了上下文反射(Context Reflection)和角色分离机制(Planner/Generator/Evaluator)等Harness Engineering实践。
sources: [raw/notebooklm-analysis/Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T-4kgkYAGPuD0
---

# Anthropic公司

## 基本定位
Anthropic 是一家专注于 AI 安全与可靠性的美国公司，以 Claude 系列模型闻名。在 Harness Engineering 领域，Anthropic 探索了解决 Agent 上下文局限和执行稳定性问题的工程方法。

## 核心特征/能力
1. **上下文反射（Context Reflection）**：检测到上下文接近极限时，不直接压缩，而是启动一个全新的 Agent 进程承接当前状态，类似操作系统的进程重启，避免模型因“焦虑”而仓促收尾。
2. **角色分离机制**：将 Agent 系统划分为三个独立角色：Planner（规划）、Generator（执行）、Evaluator（评估）。Evaluator 必须拥有独立环境，能真实操作界面和检查交互结果，而非仅审查代码。
3. **Planner（规划者）**：负责拆解任务、制定策略、分配子目标，输出高层计划。
4. **Generator（执行者）**：按照计划生成具体输出，如代码、文本或 API 调用。
5. **Evaluator（评估者）**：验证 Generator 的输出是否符合预期，具有独立性，可实际操作执行。

## 应用场景
- **复杂长链路任务**：当任务需要多步操作且上下文可能耗尽时，利用上下文反射机制无缝交接 Agent 实例。
- **高可靠性代码生成**：通过 Planner/Generator/Evaluator 分离，确保生成代码经过独立测试和验证。
- **安全敏感应用**：强制评估环节独立，防止模型自我欺骗。

## 关系网络
- [[OpenAI公司]] — 两者共同探索 Agent 工程化，但 Anthropic 更强调角色分离和上下文处理；OpenAI 侧重指令组织和治理规则化。
- [[Scale-AI公司]] — 同为行业实践贡献者，Scale AI 在数据与评估维度提供支撑，Anthropic 在架构设计上领先。
- [[Harness-Engineering]] — Anthropic 的实践是 Harness Engineering 六层架构中“评估观测层”和“约束恢复层”的典型案例。

## 关键事件/里程碑
- 2023年：发布 Claude 2，包含长上下文能力。
- 2024年：在内部工程分享中详细披露上下文反射和角色分离机制。

## 出现的视频来源
- [[Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转]]
