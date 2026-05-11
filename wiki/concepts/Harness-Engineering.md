---
title: Harness Engineering
type: concept
tags: [harness-engineering, agent-system, system-reliability]
summary: 通过构建模型外部的运行系统（Harness）来监督、约束和纠偏，将 Agent 任务成功率从 70% 提升至 95% 以上的工程方法论。
sources: [raw/notebooklm-analysis/Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T-4kgkYAGPuD0
---

# Harness Engineering

## 定义
Harness Engineering（马具工程/约制工程）是 AI 工程化的第三阶段，核心思想是：真正决定系统稳定性的往往不是模型本身，而是模型外部的运行系统（Harness）。Harness 包含信息边界、工具系统、执行编排、记忆状态、评估观测和约束恢复六层，负责为 Agent 提供稳定的“轨道”，确保模型在真实执行中持续做对。

## 在本库的具体例子
- 在 [[Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转]] 中，Harness Engineering 被明确定义为 `Agent = Model + Harness`，并详细拆解了六层架构。
- [[Anthropic公司]] 的上下文反射机制是 Harness 中“约束恢复层”的实践：当上下文接近极限时，Harness 自动启动新 Agent 进程交接状态。
- [[OpenAI公司]] 的索引化指令文件（`Agent.md`）是 Harness “信息边界层”的实现：通过目录式暴露防止信息过载。
- [[Scale-AI公司]] 的渐进式暴露属于“工具系统层”的动态信息供给策略。

## 技术实现细节
1. **六层架构**：每一层都是独立的可插拔模块，开发者可以根据任务复杂度选择启用哪些层。例如，简单问答任务只需信息边界层+工具系统层，而复杂自动化任务需要全部六层。
2. **失败处理**：Harness 将失败视为常态，内置重试、路径切换和状态回滚机制（约束恢复层），确保自愈能力。
3. **评估独立性**：评估与观测层独立于生成过程，拥有自己的验证环境和指标体系，防止模型自我欺骗。

## 与近似概念的边界
- **与 Prompt Engineering**：PE 只修改输入文本的措辞，不改变系统结构；Harness 则从系统架构层面增加监督、记忆、恢复等组件。
- **与 Context Engineering**：CE 侧重于选择和组织送入模型的上下文信息；Harness 不仅控制信息输入，还控制工具调用、执行流程、状态管理和错误恢复。
- **与 Agent 框架（如 LangChain）**：Agent 框架提供的是预构建的工具链抽象，而 Harness Engineering 是一套设计原则和架构模式，强调工程化而非库调用。

## 关联概念
- [[信息边界层]] — Harness 的第一层，负责定义角色、目标和信息范围。
- [[执行编排层]] — Harness 的第三层，负责将步骤串联为闭环逻辑。
- [[上下文反射]] — Anthropic 在约束恢复层的具体实现。
- [[渐进式暴露]] — Scale AI 在信息边界层中的动态信息策略。

## 关联实体
- [[Anthropic公司]]
- [[OpenAI公司]]
- [[Scale-AI公司]]
