     1|---
     2|title: "OpenClaw"
     3|type: entity
     4|tags: [agent-framework, open-source, gateway-centric, self-hosted]
     5|summary: "采用网关中心化架构的自托管 AI Agent 框架，以 Gateway 作为绝对控制中枢，定义了个人自托管智能体的初期标准。"
     6|sources:
     7|  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
     8|created: 2026-05-09
     9|updated: 2026-05-09
    10|layer: L1
    11|section: entities
    12|---
    13|
    14|# OpenClaw
    15|
    16|## 基本定位
    17|以 Gateway（网关）作为绝对控制中枢的自托管 AI Agent 框架，统一负责会话管理、请求路由和工具调度，强调稳定性、可审计性与可控性。
    18|
    19|## 核心特征/能力
    20|
    21|1. **网关中心化架构**: Gateway 作为后台守护进程，是系统唯一的控制中枢
    22|2. **模块化技能体系**: 技能由人类开发者编写和管理，按工作区或插件加载
    23|3. **可审计性优先**: 强调操作记录的完整性和系统行为的可控性
    24|4. **Markdown 记忆存储**: 使用 MEMORY.md 等 Markdown 文件存储记忆，与 Hermes 的 SQLite 方案形成对比
    25|
    26|## 关系网络
    27|- [[hermes-agent]] — 直接竞争对手，被 Hermes 的执行循环架构所超越
    28|- [[evomap]] — 均为开源 Agent 领域项目，但 OpenClaw 未被卷入抄袭争议
    29|
    30|## 出现的视频来源
    31|- [[Hermes Agent 与 OpenClaw 深度对比简报]]
    32|