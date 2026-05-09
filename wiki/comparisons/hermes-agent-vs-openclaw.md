---
title: "Hermes Agent vs OpenClaw"
type: comparison
tags: [hermes-agent, openclaw, agent-architecture, comparison, self-evolving]
summary: "深度对比 OpenClaw（网关中心化）与 Hermes Agent（执行循环中心化）在架构逻辑、技能机制、记忆系统和安全防御方面的范式差异。"
sources:
  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: "对比信息来自源视频中完整的架构对比分析，所有维度均有明确依据"
section: comparisons
---

# Hermes Agent vs OpenClaw

## 对比维度表格

| 维度 | OpenClaw | Hermes Agent |
|:---|:---|:---|
| **核心架构** | 网关中心化（Gateway 为绝对控制中枢） | 执行循环中心化（Agent 执行循环为同步编排引擎） |
| **设计理念** | 稳定性、可审计性、可控性 | 自我进化、自动学习、能力复利 |
| **技能生成** | 人类开发者编写 → 按工作区/插件加载 | 根据执行经验自动生成 → 动态存储在 `~/.hermes/skills/` |
| **记忆存储** | Markdown 文件（MEMORY.md） | 四层持久化：SQLite+FTS5 + 核心记忆 + 扩展记忆 + 程序性记忆 |
| **自动化** | 未提及内置 cron 系统 | 内置 cron 计划任务，自然语言设定，60 秒检查周期 |
| **安全防御** | 未提及多层次防御 | 五层纵深防御：用户授权→命令审批→容器隔离→凭证过滤→上下文扫描 |
| **模型接入** | 未说明 | 模型无关，`hermes model` 指令快速切换 |
| **迁移支持** | N/A（被迁移方） | 自动检测并导入 `~/.openclaw` 目录内容 |

## 核心差异分析

### 架构哲学的根本分歧
OpenClaw 选择**网关中心化**，强调通过统一的 Gateway 守护进程控制所有会话、请求和工具调度——这是一种"控制优先"的设计，适合需要严格审计和可控性的场景。Hermes Agent 选择**执行循环中心化**，将 Agent 本身的运行循环作为系统的核心——这是一种"成长优先"的设计，每一次执行都能反过来优化系统行为。

### 从"记住事实"到"记住方法"
这是两者最本质的能力差异。OpenClaw 的技能体系依赖人类编写指令——智能体只能执行预设好的工作流。Hermes Agent 的 Skill 机制允许智能体从执行经验中自动提炼出可复用的程序化流程——智能体不仅知道"怎么做"，还知道"怎么学会做新的事"。

### 记忆体系的代差
OpenClaw 使用简单的 Markdown 文件存储记忆，检索效率和容量都受限。Hermes Agent 构建的四层记忆体系覆盖了从高频关键信息（~1300 tokens 核心记忆）到无限扩展的全面程（SQLite+FTS5，再到 Honcho 长期画像），检索效率和处理能力有代际优势。

## 适用场景结论

- **选择 OpenClaw 的场景**: 对可控性和审计性要求极高，且团队成员有足够能力手动编写和维护技能；偏向传统运维管理风格
- **选择 Hermes Agent 的场景**: 追求自动化程度和长期效率提升，需要智能体具备自学习能力；适合技术探索型团队、个人开发者和研究型基础设施
- **综合建议**: Hermes Agent 代表了下一代 Agent 的发展方向，但从 OpenClaw 迁移已有完善的迁移路径支持，降低了切换成本

## 双向链接
- [[hermes-agent]]
- [[openclaw]]
