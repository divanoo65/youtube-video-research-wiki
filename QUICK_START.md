# YouTube Wiki - 快速启动指南

**状态**：✅ 已配置（Hermes LLM Agent 模式）  
**更新日期**：2026-05-08  
**下一阶段**：DAG 迁移 → 见 `ROADMAP_DAG_MIGRATION.md`

---

## 1. 自动化流程（完整展示）

```
┌─────────────────────────────────────────────────────────────────┐
│ 你推送一个 YouTube 链接到 raw/youtube-links/                      │
└──────────────┬──────────────────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────────────────┐
│ GitHub Actions 监听到 raw/ 目录变化                              │
│ 自动 POST 到 Hermes webhook：                                   │
│ https://hermes.vyibc.com/webhooks/youtube-wiki-ops              │
└──────────────┬──────────────────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────────────────┐
│ 【第一步】Hermes 接收 webhook                                    │
│ ├─ 检测变更文件：raw/youtube-links/ ✓                            │
│ ├─ 调用 NotebookLM CLI：                                        │
│ │  • 创建笔记本                                                 │
│ │  • 添加 YouTube 视频源                                         │
│ │  • 生成研究报告                                               │
│ │  • 生成思维导图                                               │
│ ├─ 保存输出到 raw/notebooklm-analysis/ 和 raw/notebooklm-mindmaps/
│ └─ 自动 commit & push                                           │
└──────────────┬──────────────────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────────────────┐
│ GitHub Actions 再次监听（检测到第一步的 push）                    │
│ 再次 POST 到 Hermes webhook                                     │
└──────────────┬──────────────────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────────────────┐
│ 【第二步】Hermes 接收第二次 webhook                              │
│ ├─ 检测变更文件：raw/notebooklm-* ✓                              │
│ ├─ 调用 llm-wiki 技能：                                         │
│ │  • 读取分析结果                                               │
│ │  • 构建知识图谱实体（sources, concepts, entities）            │
│ │  • 创建关系链接                                               │
│ │  • 更新 wiki/ 目录                                            │
│ ├─ 自动 commit & push                                           │
│ └─ 发送 Telegram 通知                                           │
└──────────────┬──────────────────────────────────────────────────┘
               │
               ↓
┌─────────────────────────────────────────────────────────────────┐
│ ✅ 完成！知识已集成到 wiki                                        │
│ 📱 你收到 Telegram 消息（包含新增实体/概念数量）                   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 2. 具体步骤

### 2.1 推送 YouTube 链接

**方式 A**：Web UI 编辑
```
1. GitHub → youtube-video-research-wiki
2. 点击 "Add file" → "Create new file"
3. 路径：raw/youtube-links/my-video-001.md
4. 内容：
   ---
   title: "Video Title From YouTube"
   url: "https://www.youtube.com/watch?v=..."
   date: 2026-05-08
   tags: [topic1, topic2]
   ---
   
   ## 简要描述
   可选的背景说明
5. 提交（Commit directly to main）
```

**方式 B**：本地 clone + push
```bash
git clone https://github.com/divanoo65/youtube-video-research-wiki.git
cd youtube-video-research-wiki

# 创建视频文件
cat > raw/youtube-links/video-001.md << 'EOF'
---
title: "AI 的未来趋势"
url: "https://www.youtube.com/watch?v=..."
date: 2026-05-08
---

这是关于 AI 最新进展的分析视频。
EOF

# 推送
git add raw/youtube-links/video-001.md
git commit -m "Add: YouTube video - AI trends"
git push origin main
```

### 2.2 查看自动化进展

**方式 A**：GitHub Actions 日志
```
1. GitHub 仓库主页
2. 点击 "Actions" 标签
3. 看到两个连续的 workflow runs
   - Run 1: "raw/youtube-links/ changed" ✓
   - Run 2: "raw/notebooklm-* changed" ✓
```

**方式 B**：本地日志
```bash
cd /home/zhouhuijuan1987/wiki/youtube-video-research-wiki
ls logs/webhook-runs/
# 看到类似：2026-05-08T143052Z-abc123.md

# 查看详情
cat logs/webhook-runs/2026-05-08T143052Z-abc123.md
```

### 2.3 Telegram 通知

收到的消息样式：
```
[YOUTUBE-WIKI-RUN]
run_id=2026-05-08T143052Z-abc123
stage=wiki_compile_completed
raw_changed_files=["raw/notebooklm-analysis/video-001.md", ...]
entities_created=5,["AI", "机器学习", ...]
concepts_created=3,["深度学习", "神经网络", ...]
relations_created=12,["AI uses 深度学习", ...]
commit=a1b2c3d4e5f6
push=success
```

---

## 3. 验证清单

推送后，按照以下顺序验证：

- [ ] **1 分钟内**：GitHub Actions workflow 1 运行（NotebookLM）
  - 位置：Actions 标签
  - 应该看到日志中 `notebooklm create` 和 `notebooklm generate` 命令

- [ ] **2-3 分钟内**：GitHub 出现第二个 commit（raw/notebooklm-*/ 文件）
  - 查看 git log：`git log --oneline`
  - 应该看到 `chore: add notebooklm analysis` 的 commit

- [ ] **随后**：GitHub Actions workflow 2 运行（llm-wiki）
  - 应该看到日志中 `llm-wiki incremental_build` 命令

- [ ] **最后**：GitHub 出现第三个 commit（wiki/ 文件）
  - 查看 git log 和 `git diff HEAD~1`
  - 应该看到 `wiki/sources/`, `wiki/concepts/`, `wiki/entities/` 更新

- [ ] **5 分钟内**：Telegram 收到通知
  - 检查 Telegram 聊天记录
  - 应该看到包含实体/概念计数的消息

---

## 4. 常见问题

### Q: 多久能看到结果？

**A**：总耗时约 5-10 分钟
- NotebookLM 处理：2-5 分钟（取决于视频长度）
- llm-wiki 编译：1-2 分钟
- 网络和 GitHub 延迟：1-2 分钟

### Q: 如果没有收到 Telegram，怎么调试？

**A**：按以下顺序检查
```bash
# 1. 检查 workflow 日志
# 在 GitHub Actions 看是否有错误

# 2. 检查本地日志
cat /home/zhouhuijuan1987/wiki/youtube-video-research-wiki/logs/webhook-runs/*.md

# 3. 检查是否有 raw 变更被检测到
cd /home/zhouhuijuan1987/wiki/youtube-video-research-wiki
git log --oneline

# 4. 检查 wiki 是否被更新
git diff HEAD~2 HEAD -- wiki/
# 如果空，说明 llm-wiki 没有生成任何页面
```

### Q: 能否手动触发？

**A**：可以，两种方式
```bash
# 方式 1：模拟 GitHub webhook
curl -X POST https://hermes.vyibc.com/webhooks/youtube-wiki-ops \
  -H "X-Hub-Signature: sha256=..." \
  -d '{"action":"push", "before":"...", "after":"..."}' \
  # 需要正确的 signature，略复杂

# 方式 2：直接推送
cd /home/zhouhuijuan1987/wiki/youtube-video-research-wiki
echo "test" >> raw/youtube-links/test.md
git add raw/youtube-links/test.md
git commit -m "test: trigger webhook"
git push origin main
```

### Q: 如何添加多个视频？

**A**：创建多个 .md 文件，每个一个视频
```bash
# 文件 1
raw/youtube-links/video-001.md → 对应一个 YouTube 视频
# 文件 2
raw/youtube-links/video-002.md → 对应另一个 YouTube 视频

# 推送时，NotebookLM 会逐个处理
```

### Q: 处理失败了怎么办？

**A**：检查日志，通常原因是：
1. **YouTube URL 无效** → 检查 URL 格式
2. **NotebookLM 配额用尽** → 等待一天后重试
3. **网络连接问题** → 重新推送同样的文件
4. **git stash 冲突** → 手动解决后重新推送

---

## 5. 配置项

当前配置存储位置：

| 项目 | 位置 | 说明 |
|------|------|------|
| Webhook 路由 | `~/.hermes/webhook_subscriptions.json` | 中央配置，含 prompt |
| GitHub Workflow | `.github/workflows/hermes-webhook-on-push.yml` | 触发条件 |
| 仓库变量 | GitHub Repo Settings → Secrets | HERMES_WEBHOOK_URL/TOKEN |
| Schema | `TheSchema.md` | wiki 结构定义 |

### 如何修改 Prompt？

编辑 `~/.hermes/webhook_subscriptions.json` 中的 `youtube-wiki-ops.prompt` 字段。

**修改会影响**：
- ✅ 仅影响 YouTube wiki（完全隔离）
- ✅ 不影响 obsidian-blink 或 prompt-qa
- ⚠️ 下次 webhook 触发时生效

---

## 6. 下一步（DAG 迁移）

当前使用 **Hermes LLM Agent 模式**（prompt-driven）

改进计划（详见 `ROADMAP_DAG_MIGRATION.md`）：
1. **DAG Engine 开发**：Hermes 支持 YAML workflow 定义（更清晰）
2. **YouTube 迁移**：从 prompt 改为 DAG YAML（维护更简单）
3. **推广**：其他 wiki 也改用 DAG

---

## 7. 参考文档

- 📚 [TheSchema.md](./TheSchema.md) - wiki 结构和文件组织规范
- 📚 [SCHEMA.md](./SCHEMA.md) - 数据模型定义
- 🗺️ [ROADMAP_DAG_MIGRATION.md](./ROADMAP_DAG_MIGRATION.md) - DAG 迁移计划
- 📖 [hermes-brain SKILL.md](../../../hermes-brain/brain/hermes-home/skills/research/llm-wiki/SKILL.md) - llm-wiki 技能文档

---

**最后更新**：2026-05-08  
**状态**：生产可用  
**支持**：@copilot-cli
