```markdown
---
title: Anthropic
type: entity
tags: [AI公司, Managed Agents, 多Agent协作, 企业基础设施]
sources:
  - video_id: 4kgkYAGPuD0
  - source_id: 9bc028e2-6acb-4d01-b223-8cc7a1826da8
created: 2026-05-11
updated: 2026-05-11
layer: L1
---

# Anthropic

Anthropic 是一家专注于 AI 安全与前沿模型研发的科技公司，以 [[Claude]] 系列大语言模型闻名。2025 年，Anthropic 推出了 **Managed Agents**（托管 Agent）架构，标志着其从“提供模型”向“提供 Agent 操作系统”的战略转型。该架构的核心思想是将大模型的决策能力（大脑）与执行环境（双手）及上下文状态（记忆）彻底解耦，从而支撑大规模、高并发的 Agent 蜂群协作。

## 关键架构：Managed Agents

### 从“宠物”到“牛马”的范式转换
传统 Agent 开发中，模型记忆与本地环境紧密绑定，一旦配置出错或模型升级，整个系统就变得脆弱易崩。Anthropic 借鉴分布式系统理论，提出 **“牛马模式”**：Agent 实例无状态、可随时销毁重建。具体而言，底层执行环境是独立沙盒（如 Docker 或毫秒级启动的沙盒），若代码跑崩或配置冲突，直接销毁并重新拉起干净的沙盒，确保系统稳定性和可恢复性。这一转变将 Agent 从需要精心维护的“宠物”升级为可大规模复制的“牛马”。

### 四层解耦模型
通过对 Anthropic SDK 的 beta 模块（agents, environments, sessions, skills, memory stores, vaults）分析，可以抽象出四层递进解耦架构：

1. **Agent 沙盒（Sandbox）**：将模型执行环境容器化，实现执行层彻底独立。支持 Docker 或更高速的沙盒技术（如 Cube Sandbox），实现毫秒级启动。
2. **Session（会话层）**：将 Agent 定义（静态模板）与执行过程（动态 Session）分离。同一个 Agent 模板可以对应多个独立 Session，每个 Session 拥有独立的对话上下文。
3. **Session Store（上下文管理）**：记忆不再长在 Agent 身上，而是外部挂载到 Redis 等缓存中。支持上下文的 Fork（分支）、回滚、克隆和状态恢复。这使得 Agent 彻底无状态化，便于随时销毁和快速重建。
4. **Coordinator（编排器/协调者）**：不干活的指挥官。负责拆解任务、派活给最多 20 个 Worker Agent，管理长程任务中的上下文压缩问题。通过预定义任务图驱动异步并发执行，并可根据任务性质组合使用大/小模型以优化 Token 效率。

## 行业影响

Managed Agents 的发布推动了 [[AI代理]] 从“个人工具”向“企业级基础设施”的跃迁。海外趋势（如 Palantir AIP、Anthropic）正将 Agent 提升到操作系统层面。未来，用户只需通过手机或眼镜发出指令，云端即可瞬间创建数十个沙盒协作完成任务，任务结束后全部销毁。这种“随用随建”的动态蜂群模式将彻底重塑计算资源分配规则。

Anthropic 的这一架构也催生了新的职业角色——[[FDE (Forward Deployed Engineer)]]，负责将复杂 Agent 系统落地到具体企业场景。同时，关注 [[沙盒架构]] 的开发者正积极引入高速沙盒和外部化上下文管理技术，以在本地复现 Managed Agents 的能力。

## 关键引用

> “在 Agent 领域，你为模型写的修补代码，注定会过时的。” —— Anthropic 工程师，强调了代码修补模型的死路，唯有解耦。

> “底层的多大脑、多双手的复杂并发，实在太难了……直接来买我们做好的云端 Agent 服务吧。” —— 揭示了 Managed Agents 的本质是云端的 Agent 操作系统。

> “要把 Agent 当牛马去用……哪怕某个沙盒代码跑崩了，配置冲突了，没关系直接干掉，重新拉起一个干净的沙盒接着干。” —— 对“宠物与牛马”概念的借用，强调了规模化 Agent 的稳定性原则。

## 相关页面

- [[Claude]]
- [[AI代理]]
- [[沙盒架构]]
- [[企业级基础设施]]
- [[FDE (Forward Deployed Engineer)]]
```