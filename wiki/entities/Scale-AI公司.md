---
title: Scale AI公司
type: entity
tags: [ai-data, evaluation, agent-skills, progressive-exposure]
summary: 人工智能数据与评估公司，在 Agent 工程中实践了渐进式暴露（Progressive Exposure）方法，通过动态加载 SOP 和参数定义来解决注意力问题。
sources: [raw/notebooklm-analysis/Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T-4kgkYAGPuD0
---

# Scale AI公司

## 基本定位
Scale AI 是一家专注于 AI 数据标注、评测和解决方案的公司。在 Agent 工程领域，Scale AI 提出了“Agent Skills”实践，强调通过渐进式暴露信息来提升模型执行的稳定性。

## 核心特征/能力
1. **渐进式暴露（Progressive Exposure）**：初始仅给模型展示最少量的原型（最小可行界面），只有当特定 Agent Skill 被触发时，才动态加载相关的 SOP、参数定义和脚本，防止一次性信息过载导致注意力涣散。
2. **Agent Skills 框架**：将复杂任务封装为可复用的技能模块，每个技能包含清晰的目标、SOP 和参数定义，按需激活。
3. **动态信息供给**：根据 Agent 当前走到的步骤，从知识库中实时提取最相关的上下文，避免固定上下文块的浪费。
4. **评估驱动的迭代**：利用多维度评估结果反馈到技能定义和暴露策略中，持续优化。

## 应用场景
- **多步骤客服 Agent**：初始只展示用户信息和意图分类，需要查询数据库时才加载查询 SOP 和参数模板。
- **自动化数据标注 Agent**：根据标注任务类型动态加载标注指南、质量标准和异常处理规则。
- **复杂工作流集成**：在需要调用多个外部系统时，按步骤暴露 API 文档，避免模型提前“分心”。

## 关系网络
- [[Anthropic公司]] — 同为行业实践贡献者，Anthropic 关注角色分离，Scale AI 关注信息暴露时机。
- [[OpenAI公司]] — OpenAI 的索引化指令思想与渐进式暴露类似，但实现方式不同：OpenAI 使用目录式子文档，Scale AI 使用动态加载。
- [[Harness-Engineering]] — 渐进式暴露属于六层架构中“信息边界层”和“工具系统层”的实践。

## 关键事件/里程碑
- 2024年：在 Agent 工程会议中分享 Agent Skills 实践，提出渐进式暴露方法。

## 出现的视频来源
- [[Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转]]
