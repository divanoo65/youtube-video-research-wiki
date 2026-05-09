---
title: Hermes Agent vs OpenClaw
type: comparison
tags: [hermes-agent, openclaw, ai-agent, comparison]
summary: 对比 Hermes Agent 和 OpenClaw 在架构、记忆、自动化、安全等方面的差异。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: high
reasoning: 两个视频中均提及两者对比，且报告直接进行深度对比分析。
---

# Hermes Agent vs OpenClaw

## 对比维度表格

| 维度 | Hermes Agent | OpenClaw |
|------|--------------|----------|
| **控制中枢** | 执行循环驱动（AI 自身循环为同步引擎） | 中心化 Gateway（后台守护进程统一管控） |
| **身份定义** | SOUL.md 全局属性，跨环境一致 | SOUL.md 绑定工作区，切换即切换身份 |
| **知识生成** | 程序化知识生成，自动创建技能文件 | 人类编写模块化插件 |
| **记忆体系** | 四层分层记忆（核心持久、会话历史、用户画像、程序性） | Markdown 文件记忆，人工编辑 |
| **自动化** | 内置 Cron 计划任务，自然语言设定 | 静态调度，需手动配置 |
| **安全模型** | 五层纵深防御（用户授权、命令审批、容器隔离、MCP 过滤、文件扫描） | 基础权限控制 |
| **模型支持** | 模型无关性，支持切换多种后端 | 固定模型绑定 |
| **部署兼容** | 终端、VPS、Docker、SSH、Serverless | 主要本地部署 |
| **自我进化** | 支持，通过执行循环和技能生成 | 不支持，需人工更新 |

## 核心差异分析

1. **架构哲学**：OpenClaw 采用中心化控制，强调稳定性和可审计性；Hermes Agent 采用执行循环驱动，强调自我进化和持续学习。
2. **知识沉淀**：Hermes Agent 能自动将执行经验转化为技能，实现跨会话复用；OpenClaw 依赖人类编写插件，扩展成本高。
3. **记忆管理**：Hermes Agent 的四层记忆体系兼顾速度、容量和学习能力；OpenClaw 的 Markdown 文件记忆便于人工审查但缺乏动态优化。
4. **自动化与安全**：Hermes Agent 内置 Cron 和五层防御，适合暴露在互联网环境；OpenClaw 更适用于受控的内部网络。

## 适用场景结论

- **选择 OpenClaw**：如果对稳定性和可审计性要求极高，且团队有能力编写和维护插件，适合企业级受控环境。
- **选择 Hermes Agent**：如果需要智能体具备自我进化能力、支持多模型切换、需要远程访问和自动化调度，适合个人开发者和追求灵活性的团队。

## 关联实体

- [[hermes-agent]]
- [[openclaw]]
