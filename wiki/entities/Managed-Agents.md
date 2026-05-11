```markdown
---
title: Managed Agents
type: concept
tags: [managed-agents, anthropic, agent-architecture, 解耦, 蜂群协作]
sources:
  - video_id: 4kgkYAGPuD0
  - video_url: https://youtu.be/4kgkYAGPuD0?si=ASZKshiLU3fCatbU
  - source_id: 9bc028e2-6acb-4d01-b223-8cc7a1826da8
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Managed Agents

## 概述

**Managed Agents** 是 Anthropic 推出的托管式 Agent 架构，其核心设计理念是将大模型的规划决策能力（大脑）、执行环境（双手）与上下文状态（记忆）彻底解耦，从而将 Agent 从脆弱的“宠物”模式转变为可随时销毁与重建的“牛马”模式。该架构基于 Anthropic SDK 中的 beta 模块（如 `agents`、`environments`、`sessions`、`skills`、`memory stores`、`vaults`）抽象而来，本质上是云端 Agent 操作系统的一次重要实践。

## 从“宠物”到“牛马”的范式转变

报告明确指出传统 Agent 开发的两大问题：

- **宠物模式**：开发者需要为模型编写大量修补代码（Harness）以弥补模型记忆缺陷，但随着模型升级，这些代码迅速过时。Anthropic 工程师曾编写数千行 Harness 代码，结果模型更新后几乎全部失效——这证明了通过代码“修补”模型的思路是死路。
- **牛马模式**：大脑只负责发出指令，底层的“双手”是无状态的独立沙盒。若某个沙盒代码跑崩或配置冲突，直接销毁它，重新拉起一个干净的沙盒继续执行，确保系统持久稳定。

> “要把 Agent 当牛马去用……哪怕某个沙盒代码跑崩了，配置冲突了，没关系直接干掉，重新拉起一个干净的沙盒接着干。”

这一理念直接借鉴了分布式系统中“宠物与牛马”的比喻，是 Agent 规模化部署的基石。

## 四层解耦模型

Managed Agents 通过四个层次实现彻底的解耦，每一层解决一个关键问题：

| 层次 | 核心组件 | 功能描述 |
| :--- | :--- | :--- |
| **第一层** | **Agent 沙盒 (Sandbox)** | 将模型执行环境容器化（如 Docker 或毫秒级启动的沙盒），实现执行层的彻底独立。实践中 Docker 在大规模并发时存在启动瓶颈，报告建议关注如腾讯云开源的 **Cube Sandbox** 技术，可实现毫秒级沙盒启动。 |
| **第二层** | **Session (会话层)** | 将 Agent 定义（静态模板）与执行过程（动态 Session）分离。一个 Agent 模板可以对应多个独立 Session，每个 Session 拥有自己的执行进度和状态。 |
| **第三层** | **Session Store (上下文管理)** | 记忆不再附着在 Agent 身上，而是作为外部挂载。支持上下文的 **Fork**（分支）、回滚、克隆和状态恢复。例如，当 Agent 在执行过程中需要回溯到某个历史步骤时，可以直接从 Session Store 恢复快照，而无需重新运行整个任务。 |
| **第四层** | **Coordinator (编排器/协调者)** | 不干活的“指挥官”。负责拆解任务、派活给最多 20 个 Agent，同时管理长程任务中的上下文压缩问题。Coordinator 是 Agent 蜂群协作的调度中枢，解决了多个 Worker 之间任务图并发执行的复杂度。 |

## 编排与蜂群协作

基于四层解耦架构，Agent 之间的协作不再是简单的串行逻辑，而是复杂的异步并发任务图：

- **任务图驱动**：主控服务器（Coordinator）通过预定义规则让各个 Worker 节点（如编码 Agent、Review Agent、测试 Agent）交互。例如，编码 Agent 完成代码编写后，Coordinator 自动触发 Review Agent 进行审查，Review 通过后再触发测试 Agent 执行单元测试。
- **Token 效率优化**：根据任务性质组合使用大、小模型。搜索环节调用轻量模型（如 Claude Haiku）进行高并发搜索，汇总和报告编写则调用强模型（如 Claude Opus），在保证质量的同时大幅降低 Token 消耗。
- **动态伸缩**：计算资源随 Agent 容器的创建与销毁动态分配。这意味着未来计算计价模式可能从“按时间计费”转向“按 Agent 实例生命周期间接费用”。报告展望，用户只需通过手机或眼镜发出指令，云端会瞬间创建数十个沙盒协作完成任务，任务结束后全部销毁——形成“随用随建”的动态蜂群。

## 关键引言

> “在 Agent 领域，你为模型写的修补代码，注定会过时的。”
> 
> —— 背景：大量 Harness 代码因模型升级而失效，驱动了解耦设计。

> “底层的多大脑、多双手的复杂并发，实在太难了……直接来买我们做好的云端 Agent 服务吧。”
> 
> —— 背景：这揭示了 Anthropic 的“阳谋”：Managed Agents 的本质是云端的 Agent 操作系统。由于底层并发调度难度极大，官方倾向于将其封装为托管服务，减少开发者负担。

## 相关实体

- [[Agent 沙盒]]：第一层解耦的核心组件，负责提供无状态的执行环境。
- [[Session 会话层]]：第二层与第三层的结合，实现 Agent 模板与执行过程的分离及上下文的外部化存储。
- [[Coordinator 编排器]]：第四层指挥官，负责任务拆解、派发与上下文压缩，是蜂群协作的核心。

## 行动启示

- **技术实现**：引入高速沙盒（如 Cube Sandbox）和外部化上下文管理（如 Redis 缓存的 Session Store）是快速落地该架构的关键。
- **战略定位**：海外趋势（Palantir AIP、Anthropic Managed Agents）正在将 Agent 从“个人工具”提升至“企业基础设施”，未来的核心竞争力在于编排效率而非单纯的模型 Token 销售。
- **新职业机会**：**FDE (Forward Deployed Engineer)** 等角色将负责将此类复杂 Agent 系统落地到具体企业场景，掌握 Managed Agents 架构将成为重要技能。