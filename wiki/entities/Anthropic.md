---
title: Anthropic
type: entity
tags: [company, ai-research, llm]
summary: 美国人工智能公司，以 AI 安全研究闻名，提出 Context Reflected 和独立评估者模式等 Harness 实践。
sources: [raw/notebooklm-analysis/Harness-Engineering-深度简报-构建稳定-可落地的-AI-Ag.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Anthropic

**基本定位**
Anthropic 是一家专注于 AI 安全和对齐研究的美国公司，由前 OpenAI 成员创立，推出了 Claude 系列大语言模型。在 Harness Engineering 体系中，其提出的 Context Reflected（上下文重映）和独立评估者模式是重要的系统设计实践。

**核心特征/能力**
1. **Context Reflected（上下文重映）**：当上下文过长导致模型丢失细节或急于收尾时，启动一个干净的“新 Agent”进行任务交接，类似程序开发中的“重启进程”以解决内存泄漏。
2. **独立评估者模式**：将 Agent 任务拆分为 Planner（规划者）、Generator（执行者）和 Evaluator（评估者）三个角色，评估者必须在真实环境中操作（如实际运行页面），而非仅审查代码，从而形成“生产与验收分离”的机制。
3. **角色拆分治理**：通过明确的角色分工降低单一 Agent 的认知负荷，提高任务执行的可靠性。
4. **注重环境隔离**：强调评估者与执行者运行在独立的环境中，避免评估结果被生成过程污染。
5. **安全性优先的系统设计**：将安全约束嵌入评估环节，确保 Agent 行为符合预期边界。

**应用场景**
- **长链路任务**：需要多步骤推理和执行的场景（如代码编写、数据分析），采用 Context Reflect 防止上下文退化。
- **质量敏感型任务**：需要高准确度的输出（如医疗建议、金融报告），通过独立评估者模式进行双重验证。
- **复杂编排 Agent**：涉及多个工具调用的任务，由 Planner 规划、Generator 执行、Evaluator 验收，形成闭环。

**关系网络**
- [[OpenAI]]：竞争关系，同为领先的 AI 研究机构，但在安全策略和技术路线上有所不同。
- [[Agent]]：Anthropic 的实践是针对 Agent 系统的 Harness 设计，属于 Agent 系统的一个实现方案。
- [[上下文重映]]：Anthropic 提出的关键技术概念。
- [[独立评估者模式]]：Anthropic 推崇的评估范式。

**关键事件/里程碑**
- 2021 年：Anthropic 由 Dario Amodei、Daniela Amodei 等人创立。
- 2023 年：推出 Claude 2 模型，强化安全对齐。
- 2024-2025 年：在 Agent 系统领域推广 Harness Engineering 思想，提出上述模式。

**出现的视频来源**
- [[Harness-Engineering-深度简报-构建稳定-可落地的-AI-Agent系统]]