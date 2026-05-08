# YouTube Video Research Wiki

**状态**: ✅ 生产可用  
**最后更新**: 2026-05-08T144000Z

## 概述

使用 NotebookLM 和知识图谱编译的自动化研究 wiki，用于分析 YouTube 视频内容。

### 自动化流程

- **第一步**：push YouTube 链接 → NotebookLM 分析（报告、思维导图）
- **第二步**：分析结果 → 知识图谱编译 → Wiki 更新
- **第三步**：Telegram 自动通知

### 核心特性

- ✅ Webhook 驱动自动化（GitHub → Hermes → Skills）
- ✅ Wiki 完全隔离（不影响其他 wiki）
- ✅ 两阶段处理（NotebookLM + llm-wiki）
- ✅ 可扩展架构（支持未来扩展多个内容源）

## 快速开始

👉 **[QUICK_START.md](./QUICK_START.md)** - 5 分钟快速上手指南

包含：
- 完整的自动化流程图
- 分步骤说明（如何推送 YouTube 链接）
- 验证清单（如何确认处理完成）
- 常见问题（Q&A）
- 配置项说明

## 下一步计划

⏭️ **[ROADMAP_DAG_MIGRATION.md](./ROADMAP_DAG_MIGRATION.md)** - DAG 迁移路线图

将当前的 Hermes LLM Agent 模式迁移到 DAG Workflow Engine 模式：
- 更清晰的流程定义（YAML 而非 prompt）
- 更强的可维护性
- 支持复杂的多阶段工作流（Douyin、Podcast 等）

目前状态：**Phase 1 ready**（DAG 引擎开发即将启动）

## 文件结构

```
youtube-video-research-wiki/
├── README.md                      # 本文件
├── QUICK_START.md                 # 快速启动指南
├── ROADMAP_DAG_MIGRATION.md       # DAG 迁移规划
├── TheSchema.md                   # wiki 结构定义
├── SCHEMA.md                      # 数据模型
├── .github/
│   └── workflows/
│       └── hermes-webhook-on-push.yml  # GitHub workflow 配置
├── raw/                           # 原始数据输入
│   ├── youtube-links/             # YouTube 链接
│   ├── notebooklm-analysis/       # NotebookLM 生成的分析报告
│   └── notebooklm-mindmaps/       # NotebookLM 生成的思维导图
├── wiki/                          # 最终输出（知识图谱）
│   ├── sources/                   # 信息源（YouTube 视频）
│   ├── concepts/                  # 概念（主题、原理等）
│   ├── entities/                  # 实体（人物、地点等）
│   ├── relations/                 # 关系（how/why/uses etc）
│   ├── overview/                  # 总览和索引
│   └── queries/                   # 查询和分析
└── logs/
    └── webhook-runs/              # 每次自动化运行的日志
```

## 配置项

### Webhook 配置

**文件**：`~/.hermes/webhook_subscriptions.json`

```json
{
  "youtube-wiki-ops": {
    "description": "YouTube video research wiki - 2-stage workflow",
    "secret": "youtube-wiki-secret-20260508",
    "provider": "Gptsapi-GPT-5-Mini",
    "skills": ["notebooklm-cli", "llm-wiki"]
  }
}
```

### GitHub 仓库变量

**位置**：GitHub Repo Settings → Secrets and variables

```
HERMES_WEBHOOK_URL=https://hermes.vyibc.com/webhooks/youtube-wiki-ops
HERMES_WEBHOOK_TOKEN=youtube-wiki-secret-20260508
```

### 环境变量（本地开发）

```bash
export YOUTUBE_WIKI_PATH=/home/zhouhuijuan1987/wiki/youtube-video-research-wiki
export HERMES_HOME=~/.hermes
export NOTEBOOKLM_HOME=~/.notebooklm
```

## 常见操作

### 手动推送 YouTube 链接

```bash
git clone https://github.com/divanoo65/youtube-video-research-wiki.git
cd youtube-video-research-wiki

# 创建视频文件
cat > raw/youtube-links/video-001.md << 'EOF'
---
title: "Video Title"
url: "https://www.youtube.com/watch?v=..."
date: 2026-05-08
---

简要描述
EOF

# 推送
git add .
git commit -m "Add: YouTube video"
git push origin main
```

### 查看处理状态

```bash
# GitHub Actions 日志
# https://github.com/divanoo65/youtube-video-research-wiki/actions

# 本地日志
cat /home/zhouhuijuan1987/wiki/youtube-video-research-wiki/logs/webhook-runs/*.md

# git 提交历史
cd /home/zhouhuijuan1987/wiki/youtube-video-research-wiki
git log --oneline
```

### 验证完成标志

推送后 5-10 分钟内应该看到：

1. ✅ GitHub Actions 两个连续的 workflow runs
2. ✅ 本地 git log 中有两个新 commits
   - `chore: add notebooklm analysis`
   - `chore: update llm wiki graph`
3. ✅ `wiki/sources/`, `wiki/concepts/`, `wiki/entities/` 目录有新文件
4. ✅ Telegram 收到通知消息

## 故障排查

### 没有收到 Telegram 通知

1. 检查 GitHub Actions 日志（有无错误）
2. 检查本地日志：`cat logs/webhook-runs/*.md`
3. 检查 wiki/ 是否实际更新：`git diff HEAD~1`
4. 确认 Telegram bot token 有效

### NotebookLM 处理失败

常见原因：
- YouTube URL 无效
- NotebookLM 配额用尽（每天限制）
- 网络连接问题

解决方案：
1. 检查 URL 格式
2. 等待 24 小时后重试
3. 重新推送同样的文件

### Git stash 冲突

如果处理失败且 git stash pop 冲突：

```bash
cd /home/zhouhuijuan1987/wiki/youtube-video-research-wiki
git stash list  # 查看 stash 列表
git stash show -p stash@{0}  # 查看内容
git stash drop  # 删除有问题的 stash
```

然后重新推送触发工作流。

## 技术细节

### Hermes Webhook 流程

```
GitHub Event (raw/ 变更)
    ↓
GitHub Actions Workflow
    ↓
POST to https://hermes.vyibc.com/webhooks/youtube-wiki-ops
    ↓
Hermes Webhook Router
    ↓
Lookup: youtube-wiki-ops 路由
    ↓
Execute Prompt (LLM Agent)
    ↓
Agent 调用相应 Skills:
  - notebooklm-cli (第一步)
  - llm-wiki (第二步)
    ↓
Push 到 GitHub
    ↓
GitHub 再次触发 Workflow
    ↓ (重复上述流程)
```

### Skills 说明

- **notebooklm-cli**: 调用 NotebookLM API，生成分析报告和思维导图
- **llm-wiki**: 知识图谱编译引擎，构建 wiki 页面和实体关系

### 隔离机制

- 每个 wiki 有独立的 webhook 路由（secret 隔离）
- 每个 wiki 有独立的 Hermes prompt（逻辑隔离）
- 每个 wiki 有独立的 GitHub 仓库（数据隔离）
- 修改一个 wiki 不会影响其他 wiki

## 相关文档

- 📖 [Hermes Brain - llm-wiki Skill](../../../hermes-brain/brain/hermes-home/skills/research/llm-wiki/SKILL.md)
- 📖 [Hermes Brain - Multi-Wiki Gate](../../../hermes-brain/brain/hermes-home/skills/devops/llm-wiki-multiwiki-e2e-gate/SKILL.md)
- 📖 [NotebookLM CLI](https://github.com/teng-lin/notebooklm-py)

## 贡献

- 报告 Bug：GitHub Issues
- 功能建议：GitHub Discussions
- 代码贡献：Pull Requests

## 许可

TBD

---

**最后更新**：2026-05-08T144000Z  
**维护者**：@copilot-cli  
**状态**：生产可用 ✅
