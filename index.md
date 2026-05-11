# Wiki Index

> YouTube 视频研究知识图谱。所有 wiki 页面按类型分类索引。
> Last updated: 2026-05-11 | Total pages: 28

## Sources
- [[Anthropic-Managed-Agents-架构深度解析与多Agent协作|Anthropic-Managed-Agents-架构深度解析与多Agent协作]] — 深度解析 Anthropic Managed Agents 架构，阐述从单一Agent向企业级多Agent蜂群协作的转型，重点介绍脑手分离、四层解耦与编排者模式。
- [[Harness-Engineering-技术深度简报-从提示词到系统驾驭的范式转|Harness Engineering 技术深度简报：从提示词到系统驾驭的范式转移]] — 探讨 AI 工程从 Prompt Engineering、Context Engineering 到 Harness Engineering 的三阶段演进，详解 Harness 六层架构及 Anthropic、OpenAI、Scale AI 的行业实践。

## Entities
- [[Anthropic公司]] — AI 研究与部署公司，推出了 Managed Agents 架构、Claude 系列模型及多Agent协作方案。
- [[Cube-Sandbox]] — 腾讯开源的毫秒级沙盒容器技术，旨在解决传统 Docker 启动慢的问题，适配 Agent 蜂群架构下高频的容器创建与销毁需求。
- [[Claude-Code]] — Anthropic 开发的专门面向编程任务的大模型，可用于在蜂群架构中扮演特定 Agent 的大脑角色，尤其适合代码生成与审查。
- [[Redis]] — 开源内存数据库，在 Managed Agents 架构中被用作 Session Store 的后端缓存，实现 Agent 记忆的云端持久化与快速恢复。
- [[OpenAI公司|OpenAI公司]] — 领先的人工智能研究机构，在 Harness Engineering 领域提出了索引化指令（Agent.md）和自驱动治理系统等实践。
- [[Scale-AI公司|Scale AI公司]] — 人工智能数据与评估公司，在 Agent 工程中实践了渐进式暴露（Progressive Exposure）方法，通过动态加载 SOP 和参数定义来解决注意力问题。

## Concepts
- [[脑手分离模式]] — 一种将大模型决策与执行环境彻底分离的架构模式，大脑只负责发指令，无状态沙盒负责执行，以避免环境污染和代码依赖过时。
- [[宠物与牛马理论]] — 将 Agent 生命周期管理类比为宠物（绑定长久维护）与牛马（无状态、可随时销毁重建）的隐喻，强调 Agent 应设计为无状态资源以提升系统健壮性。
- [[四层解耦架构]] — Anthropic Managed Agents 的详细分层模型，包括 Agent 静态定义、Sandbox 执行环境、Session 动态会话与 Session Store 云端记忆，层层分离以实现完全无状态化。
- [[编排者（Coordinator）]] — 在多Agent系统中专门负责任务拆解与分发的组件，不直接执行任务，可以管理多达20个子Agent，每个子Agent拥有独立的配置。
- [[Session-Store]] — 将Agent的记忆从本地文件或进程内存储迁移到云端（如Redis）的存储机制，使Agent可以实现跨设备、跨环境的无状态恢复。
- [[毫秒级沙盒]] — 能够在毫秒级别创建和销毁的轻量级执行沙盒技术，用于支持Agent蜂群架构中高频的容器生命周期变更。
- [[任务图（Task-Graph）]] — 一种用有向无环图表示多Agent协作任务关系的编排模型，节点代表子任务，边代表依赖关系，辅助Coordinator进行任务调度。
- [[Token-Efficiency-组合]] — 在蜂群架构中按任务难度混合使用不同大小模型的策略，以在保证结果质量的同时降低总Token消耗。
- [[Harness-Engineering|Harness Engineering]] — 通过构建模型外部的运行系统（Harness）来监督、约束和纠偏，将 Agent 任务成功率从 70% 提升至 95% 以上的工程方法论。
- [[信息边界层]] — Harness Engineering 六层架构的第一层，负责定义角色目标、裁剪信息并结构化组织，确保模型在正确的边界内思考。
- [[工具系统层]] — Harness Engineering 六层架构的第二层，负责配置工具选择、控制调用时机以及对返回结果进行提炼反馈，使模型成为行动者。
- [[执行编排层]] — Harness Engineering 六层架构的第三层，负责将离散步骤串联为闭环逻辑链，包括目标拆解、步骤串联和自我修正。
- [[记忆与状态管理层]] — Harness Engineering 六层架构的第四层，管理当前任务状态、中间结果和长期记忆，防止 Agent 出现“失忆”现象。
- [[评估与观测层]] — Harness Engineering 六层架构的第五层，建立独立于生成过程的验证机制，包含自省能力、日志监控和独立环境验证，让系统感知“有没有做对”。
- [[约束校验与恢复层]] — Harness Engineering 六层架构的第六层，定义行为红线、执行输出前后校验，并实施重试、路径切换或状态回滚等恢复机制，决定系统能否上线。
- [[上下文反射]] — Anthropic 提出的一种解决上下文长度极限问题的方法，不是压缩上下文，而是启动全新的 Agent 进程承接当前状态，类似进程重启。
- [[角色分离机制]] — Anthropic 提出的将 Agent 系统划分为 Planner（规划者）、Generator（执行者）、Evaluator（评估者）三种独立角色的架构设计。
- [[索引化指令文件]] — OpenAI 提出的提示词组织方法，将庞大规则集改为目录式索引文件（Agent.md），详细规范作为子文档按需暴露，解决信息过载。
- [[自驱动治理系统]] — OpenAI 提出的将资深工程师的领域经验（如模块分层规则）编写为系统规则，Agent 执行时自动拦截违规并反馈修改方案的治理方法。
- [[渐进式暴露]] — Scale AI 采用的一种上下文管理策略，初始只给模型最小原型，当特定能力被触发时才动态加载相关的 SOP、参数定义和脚本，避免注意力涣散。

## Comparisons

## Overview

## Queries
