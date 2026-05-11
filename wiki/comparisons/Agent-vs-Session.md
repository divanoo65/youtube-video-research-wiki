---
title: Agent vs Session
type: concept
tags: [agent, session, architecture, managed-agents, decoupling]
summary: 静态模板与动态执行分离
sources:
  - 6733c4ed-cdb0-420d-9a4a-a920fd1e7f03
created: 2026-05-11
updated: 2026-05-11
layer: L2
confidence: high
reasoning: 基于Anthropic Managed Agents架构文档及实践报告归纳
---

# Agent vs Session：静态模板与动态执行分离

在 [[Managed Agents]] 架构中，**Agent** 与 **Session** 被定义为两个完全不同的实体，这是实现“脑手解耦”与无状态化的核心设计。简单来说：**Agent 定义“我是谁”，Session 记录“我在干什么”**。

## 核心对比

| 维度 | Agent（静态模板） | Session（动态执行） |
|------|-------------------|---------------------|
| **本质** | 配置模板 | 运行时实例 |
| **状态** | 无状态，不存储动态数据 | 有状态，承载对话线程与记忆 |
| **生命周期** | 持久存在，可复用 | 按需创建，任务结束后可销毁 |
| **核心内容** | 身份、工具列表、模型选择、System Prompt | 对话历史、文件操作、记忆挂载 |
| **可扩展性** | 一个模板可被多个Session引用 | 一个Session只对应一个Agent模板 |
| **故障隔离** | 模板错误影响所有实例 | Session崩溃不影响其他Session |

## 架构意义

### 1. 从“宠物”到“牛马”的转变
传统Agent开发将模型逻辑、上下文记忆与本地环境深度绑定，一旦环境配置出错或记忆冗余，系统便会崩溃。通过Agent与Session的分离：

- **Agent作为静态模板**：定义Agent的身份、使用的工具、模型及系统提示词。它不存储任何动态数据，仅作为配置模板存在。
- **Session作为动态执行单元**：承载对话线程、记忆挂载和文件操作。同一个Agent模板可以同时启动多个独立的Session，互不干扰。

这种设计使得Agent不再是需要精心呵护的“宠物”，而是可随时销毁并重建的“牛马”。

### 2. 无状态化与沙盒执行
每一项执行任务都在独立的沙盒（如Docker或高性能沙盒Cube Sandbox）中运行。如果任务出错或环境污染，系统直接销毁该沙盒并重新拉起干净的环境。Session作为执行载体，天然支持这种无状态化模式：

- **销毁重建**：Session崩溃时，只需基于Agent模板重新创建新Session
- **环境隔离**：每个Session拥有独立的沙盒环境，互不污染
- **快速恢复**：通过[[Session Store]]实现上下文云端化，Session可随时从云端恢复

### 3. 编排者模式下的分工
在[[Coordinator]]模式中，Agent与Session的分离使得编排者可以灵活调度：

- **一个编排者**管理多个Agent模板（最多20个）
- **每个Agent模板**可同时运行多个Session实例
- **不同Session**可执行不同任务，互不干扰

例如，一个编码Agent模板可以同时运行：
- Session A：处理项目X的代码编写
- Session B：处理项目Y的代码审查
- Session C：处理项目Z的测试用例

## 实践示例

### Agent定义（静态模板）
```yaml
agent:
  id: code-assistant-v2
  model: claude-3-opus
  tools:
    - code_interpreter
    - file_editor
    - web_search
  system_prompt: "你是一个专业的代码助手，擅长Python和JavaScript开发。"
```

### Session创建（动态执行）
```yaml
session:
  id: session-20260511-001
  agent: code-assistant-v2
  context:
    - project: "电商平台重构"
    - task: "实现用户认证模块"
    - memory: "已阅读项目文档，了解现有架构"
  sandbox: cube-sandbox-001
  status: running
```

## 关键语录

> “Session负责我在干什么，Agent负责我是谁。”

这句话形象地解释了静态配置（Agent）与动态运行状态（Session）之间的解耦关系。在[[蜂群思维]]架构中，这种分离使得系统具备极高的弹性和可扩展性。

## 技术启示

1. **模板复用**：Agent模板可版本化管理，支持灰度发布和A/B测试
2. **资源优化**：Session按需创建，避免资源浪费
3. **故障隔离**：单个Session崩溃不影响其他Session和Agent模板
4. **状态管理**：通过[[Session Store]]实现上下文云端化，支持Fork、回滚、克隆等操作

## 相关概念

- [[Managed Agents]] - 整体架构框架
- [[Coordinator]] - 编排者模式
- [[Session Store]] - 上下文云端存储
- [[脑手解耦]] - 架构设计原则