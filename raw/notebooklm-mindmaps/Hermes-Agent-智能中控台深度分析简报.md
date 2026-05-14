---
title: "Hermes Agent 智能中控台深度分析简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Hermes-Agent-智能中控台深度分析简报.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((Hermes Agent AI 中控台 （Dashboard）))
  Dashboard （总览仪表盘）
    Overview: 模型、后端与运行时间
    AI 成绩单: 对话数、消息数、工具调用、Token处理
    内存状态: state.db 数据库大小与用户画像占用
    成长曲线: 每日快照对比 （Growth Delta）
    活动分析: 工具排行、每日活动量折线图
  Memory & Sessions （记忆与会话）
    工作记忆: Agent 运行时的中间记忆
    用户画像: 存储用户相关信息
    管理功能: 直接编辑、删除或新增记忆条目
    会话记录: 完整对话历史、来源区分 （Telegram/CLI）
    全文检索: 搜索标题与内文关键字
  Cost & System （成本与系统）
    费用统计: 今日消费与累计美元总额
    模型明细: 按不同模型 （如 Opus） 拆分费用
    Health 状态: API Key 状态与服务运行监控
  Skills & Automation （技能与自动化）
    技能管理: 80个技能分类与自定义技能 （Custom）
    Cron 任务: 背景自动跑任务管理 （摘要、检查、备份）
    Pattern 分析: 任务聚类与高频 Prompt 自动识别
    Project Step: 自动侦测项目源码与 Git 状态
  Advanced Features （高级功能）
    Correction: 错题本 （记录并修正 AI 的错误）
    Wchat: 浏览器内直接与 Hermes 聊天
    快捷操作: T 键切换主题、Ctrl+K 快速搜索跳转
  Installation （安装配置）
    前提: 需先安装 Hermes Agent 本体
    步骤: Git Clone 项目 -> 运行 install 指令
    自动化: 自动构建虚拟环境、安装套件、前端 Build
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
