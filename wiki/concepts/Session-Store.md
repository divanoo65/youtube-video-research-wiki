```markdown
---
title: Session Store
type: concept
tags: [session-store, cloud-context, agent-architecture, memory-management, swarms]
sources:
  - "6733c4ed-cdb0-420d-9a4a-a920fd1e7f03"
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# Session Store

**Session Store** 是 [[Managed Agents]] 四层架构中实现“上下文解耦”的关键组件。它是一个云端上下文存储层（通常基于 Redis 或类似高性能缓存系统），负责承载 Agent 执行过程中的全部动态状态——包括对话线程、记忆挂载、文件操作记录、工具调用历史等。通过将上下文从本地搬到云端，Session Store 使得 Agent 彻底无状态化：Agent 本身不再保存任何运行时记忆，所有状态均托管在 Session Store 中，实现随时销毁、重建、回滚或克隆。

## 核心功能与技术细节

根据 Anthropic SDK 及实践报告的分析，Session Store 提供了以下关键能力：

1. **记忆树操作**：每个 Session 被视为一棵“记忆树”，支持 **Fork**（从某个历史节点分支出新会话）、**Rollback**（回滚到任意历史状态）、**Clone**（完整复制当前状态用于并行任务）以及 **Restore**（恢复已销毁的 Session）。这使得编排者可以时刻掌握 Agent“最聪明”的执行状态，并在需要时精准复用。

2. **无状态化执行**：Agent 的任务在独立沙盒（如 [[Sandbox Environment]]）中启动后，所有 I/O 交互都通过 Session Store 读写。沙盒如果因环境污染或崩溃，可被直接销毁，然后从 Session Store 中重建一个干净沙盒并继续执行，无需保留任何本地上下文。报告原文强调：“每一项执行任务都在独立的沙盒中运行，如果任务出错或环境污染，系统直接销毁该沙盒并重新拉起干净的环境。”

3. **动态编排支持**：[[编排者（Coordinator）]] 可以同时管理多个 Session（一个 Agent 模板可启动多达 20 个独立 Session），每个 Session 拥有独立的上下文存储、互不干扰。编排者通过读取 Session Store 中的历史记录，统一调度下属 Agent 的分工与切换，解决单一 Agent 长程任务“越跑越笨”的痛点。

4. **与 Agent 的实体分离**：Agent 是静态模板（定义身份、工具、模型、System Prompt），Session 是动态执行实例（承载运行时上下文）。报告中的标志性语录“Session 负责我在干什么，Agent 负责我是谁”形象说明了这一解耦关系。Session Store 正是支撑 Session 独立性的基础设施。

## 架构意义

Session Store 的引入将多 Agent 协作从“单体宠物式”转向“蜂群牛马式”。它带来的直接收益包括：

- **故障隔离**：单个 Session 崩溃不影响其他 Session 或 Agent 模板。
- **弹性伸缩**：云端上下文存储使得 Agent 可以跨机器、跨区域迁移，秒级启动。
- **审计与回放**：所有上下文被持久化到云端，支持事后审计、训练数据生成、异常排查。
- **状态共享**：不同 Agent（如编码、审核、测试）可以通过 Session Store 访问同一任务的关键上下文，实现上下文级协作。

## 相关概念

- [[Sandbox Environment]]：Session Store 的配套执行环境，提供无状态、可销毁的计算沙盒。
- [[编排者（Coordinator）]]：负责拆解任务并调度多个 Session 的“不干活的指挥官”。
- [[Agent]]：与 Session 分离的静态模板，定义身份和能力。
- [[Memory Tree]]：Session Store 内部的数据结构，支持分支、回滚、克隆等操作。
- [[无状态化]]：Agent 架构从“宠物”到“牛马”转型的核心原则。

> 报告中提到，“这不就是一个 Agent 的操作系统”——Session Store 正是这套操作系统的“内存持久层”，它使得多 Agent 协作从脚本级别的玩具进化为企业级的基础设施。
```