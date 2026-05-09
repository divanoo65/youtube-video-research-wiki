---
title: Hermes Agent vs OpenClaw：自托管智能体架构对比
type: comparison
tags: [hermes-agent, openclaw, comparison, architecture]
summary: 深度对比 Hermes Agent 与 OpenClaw 在架构模式、技能机制、记忆体系、身份锚定和安全防护等维度的差异。
sources:
  - wiki/sources/Hermes Agent 与 OpenClaw：自托管智能体架构演进与深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 分析报告明确提供了两个实体的对比维度和技术细节，基于直接比较得出结论。
---

## 对比维度

| 维度 | Hermes Agent | OpenClaw |
|:---|:---|:---|
| **架构模式** | 执行循环驱动：AI Agent 执行循环为编排引擎 | 中心化网关：Gateway 为绝对控制中枢 |
| **技能生成** | 自动生成：根据执行经验自动提取并优化 | 手动编写：由开发者编写，类似插件系统 |
| **记忆体系** | 四层分层记忆（核心持久+会话历史+Honcho+程序性） | 工作区级别记忆，切换工作区即切换上下文 |
| **身份锚定** | 全局 SOUL.md，核心身份不随环境切换 | 工作区 SOUL.md，可随工作区切换 |
| **安全防护** | 五层纵深防御（基础→隔离→过滤→扫描→网络） | 基础安全机制 |
| **成长路径** | 主动成长，跨会话持续学习 | 被动扩展，依赖外部更新 |
| **存储管理** | Skills 存储于 `~/.hermes/skills/`，支持 Skills Hub | 按工作区或共享插件加载 |

## 核心差异分析

1. **架构哲学差异**：Hermes Agent 将控制权从网关转移到 AI Agent 自身的执行循环，实现了"自我进化"；而 OpenClaw 坚持网关核心论，保证行为高度可预测和稳定。
2. **知识演进差异**：Hermes Agent 开创了"记住方法"的范式——自动将执行轨迹转化为可调用的技能，实现能力复利；OpenClaw 需要人类开发者手动编写和优化技能。
3. **身份管理差异**：Hermes Agent 的全局身份锚定更适合"个人助手"定位，OpenClaw 的工作区切换更适合多任务专业开发场景。

## 适用场景结论

- **选择 OpenClaw**：需要高度稳定性和可审计性，有明确工作区划分需求，愿意手动编写和管理工具流的专业开发者
- **选择 Hermes Agent**：需要长期智能"个人助理"，期望自动进化和持续学习，追求零成本迁移和快速上手的用户

## 关联实体
- [[Hermes Agent]]
- [[OpenClaw]]
- [[Nous Research]]
