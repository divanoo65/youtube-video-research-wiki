     1|---
     2|title: "Hermes Agent"
     3|type: entity
     4|tags: [agent-framework, open-source, nous-research, ai-agent, self-evolving]
     5|summary: "由 Nous Research 开发的开源自托管 AI Agent，采用执行循环中心化架构，实现技能自动生成和自我进化。"
     6|sources:
     7|  - raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-部署与应用简报.md
     8|  - raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md
     9|created: 2026-05-09
    10|updated: 2026-05-09
    11|layer: L1
    12|section: entities
    13|---
    14|
    15|# Hermes Agent
    16|
    17|## 基本定位
    18|由 Nous Research 开发的首个自进化 AI Agent 框架，核心创新在于将 Agent 自身的执行循环定义为同步编排引擎，实现从"执行指令"到"自我进化"的范式转移。
    19|
    20|## 核心特征/能力
    21|
    22|1. **执行循环中心化架构**: 彻底颠覆网关核心逻辑，将 Agent 执行循环作为同步编排引擎，网关、定时任务、工具运行时、通信协议（ACP）等模块均围绕此循环集成
    23|2. **程序化知识生成**: Skill 机制支持根据执行经验自动生成新技能，存储在 `~/.hermes/skills/`，实现"记住方法"而非"记住事实"
    24|3. **四层记忆体系**: 核心持久记忆（MEMORY.md~1300 tokens）、会话历史记忆（SQLite+FTS5）、扩展记忆层（Honcho）、程序性记忆（自动生成技能）
    25|4. **Cron 计划任务**: 内置自然语言可配的定时任务系统，每 60 秒检查条件，隔离会话运行
    26|5. **五层纵深防御**: 用户授权→危险命令审批→容器隔离→MCP 凭证过滤→上下文扫描+SSRF/注入防护
    27|6. **模型无关性**: 通过 `hermes model` 命令可快速切换 OpenAI、OpenRouter、Kim、MiniMax 或自定义模型
    28|7. **计算与交互解耦**: 支持本地、VPS、Docker、无服务器架构运行，同时通过 Telegram、Discord 或命令行交互
    29|8. **Telegram Bot 集成**: 支持 24 小时手机远程交互与指令转发
    30|9. **OpenClaw 迁移路径**: 自动检测并导入 `~/.openclaw` 目录内容，无缝迁移
    31|
    32|## 关系网络
    33|- [[qwen3-6]] — 推荐搭配使用的底层大语言模型
    34|- [[llama-cpp]] — 推荐的本地推理引擎组合
    35|- [[openclaw]] — 直接竞争对手，架构理念对比对象
    36|- [[telegram-bot]] — 远程交互通道
    37|- [[执行循环驱动架构]] — 核心设计模式
    38|
    39|## 出现的视频来源
    40|- [[Hermes 与 Qwen3.6 本地 AI Agent 部署与应用简报]]
    41|- [[Hermes Agent 与 OpenClaw 深度对比简报]]
    42|