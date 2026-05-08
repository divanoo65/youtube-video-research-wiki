---
type: roadmap
title: YouTube Wiki - DAG 迁移路线图
created: 2026-05-08
status: todo
priority: high
---

# YouTube Wiki DAG 迁移代办

> 当前状态：使用 Hermes Webhook + LLM Agent 模式
> 目标状态：迁移到 Hermes DAG Workflow Engine
> 优先级：中（在 Dify 之前）

---

## 📋 阶段 1：DAG 引擎开发（Hermes 核心升级）

> 预计工期：4-5 天
> 负责人：Architecture Team
> 依赖：无

### 1.1 DAG YAML Schema 设计
- [ ] 定义 workflow YAML 格式规范
  - triggers（何时启动）
  - stages（执行阶段）
  - dependencies（依赖关系）
  - outputs（输出配置）
  - retry policy（重试策略）
- [ ] 文档：`docs/workflow-schema.md`
- [ ] 示例：`examples/youtube-workflow.yml`

**参考格式**：
```yaml
name: youtube-analysis-pipeline
version: 1.0

trigger:
  - type: github_webhook
    repo: divanoo65/youtube-video-research-wiki
    paths: ["raw/youtube-links/", "raw/notebooklm-*/"]

stages:
  notebooklm_analyze:
    skill: notebooklm-cli
    input: "{{trigger.file}}"
    output: "raw/notebooklm-analysis/"
    next: [llm_wiki_compile]
  
  llm_wiki_compile:
    depends_on: [notebooklm_analyze]
    skill: llm-wiki
    input: "{{stages.notebooklm_analyze.output}}"
    action: incremental_build
```

### 1.2 DAG Parser 实现
- [ ] 实现 `DAGParser` 类
  - 解析 YAML 文件
  - 验证 schema 合法性
  - 构建依赖图
- [ ] 文件位置：`hermes/core/dag_engine/parser.py`
- [ ] 单元测试：`tests/test_dag_parser.py`

### 1.3 Dependency Graph Builder
- [ ] 拓扑排序算法实现
- [ ] 检测循环依赖
- [ ] 支持并行 stage 识别
- [ ] 文件位置：`hermes/core/dag_engine/graph.py`

### 1.4 DAG Executor 实现
- [ ] `DAGExecutor` 主类
  - 按依赖顺序执行 stage
  - 并行执行无依赖 stage
  - 管理中间状态
- [ ] `StageExecutor` 单 stage 执行器
  - 调用对应的 skill
  - 传递输入/输出
  - 处理错误
- [ ] 文件位置：`hermes/core/dag_engine/executor.py`

### 1.5 State Manager
- [ ] 中央状态管理（SQLite）
- [ ] 表设计：
  - `workflow_runs` - 工作流执行记录
  - `stage_runs` - 阶段执行记录
  - `stage_outputs` - 阶段输出数据
- [ ] 文件位置：`hermes/core/dag_engine/state.py`
- [ ] 迁移脚本：`migrations/create_dag_tables.sql`

### 1.6 Retry & Error Handling
- [ ] 指数退避重试逻辑
- [ ] 单 stage 失败处理
- [ ] 全局回滚策略
- [ ] 错误日志记录
- [ ] 文件位置：`hermes/core/dag_engine/retry.py`

### 1.7 Webhook Router 修改
- [ ] 检测 workflow 存在性
  - 查找 repo 中的 `.hermes/pipeline.yml`
  - 或全局 `~/.hermes/workflows/`
- [ ] 条件分发
  - 有 workflow → 调用 DAG Engine
  - 无 workflow → 走旧流程（LLM Agent）
- [ ] 文件位置：修改 `hermes/core/webhook_router.py`

### 1.8 CLI 命令扩展
- [ ] `hermes workflow run <name>` - 手动运行
- [ ] `hermes workflow list` - 列出所有
- [ ] `hermes workflow status <run_id>` - 查看状态
- [ ] `hermes workflow logs <run_id>` - 查看日志
- [ ] `hermes workflow retry <run_id> --stage <stage>` - 重试
- [ ] 文件位置：`hermes/cli/commands/workflow.py`

### 1.9 集成测试
- [ ] YouTube pipeline 完整流程测试
- [ ] 错误恢复测试
- [ ] 并行执行测试
- [ ] 文件位置：`tests/integration/test_youtube_dag.py`

---

## 📋 阶段 2：YouTube Wiki 迁移（应用层）

> 预计工期：1 天
> 依赖：阶段 1 完成
> 注意：前提是 DAG 引擎已验证

### 2.1 创建 DAG 定义文件
- [ ] 文件路径：`youtube-video-research-wiki/.hermes/pipeline.yml`
- [ ] 内容：YouTube 2-stage 工作流定义
- [ ] Git 提交：`feat: add DAG workflow definition`

### 2.2 更新 GitHub Workflow
- [ ] 简化 `.github/workflows/hermes-webhook-on-push.yml`
  - 移除复杂的路径判断逻辑
  - 保持基础的 webhook POST
  - 新增元数据字段（可选）
- [ ] Git 提交：`refactor: simplify workflow for DAG mode`

### 2.3 迁移 webhook_subscriptions.json
- [ ] 旧配置保留（为其他 wiki）
- [ ] 新增 `youtube-wiki-ops-dag` 路由指向 DAG engine
  - 或删除旧的 `youtube-wiki-ops` 路由
- [ ] Git 提交：`ops: migrate youtube-wiki to DAG mode`

### 2.4 更新文档
- [ ] 更新 `README.md`
  - 说明现在用的是 DAG 模式
  - 流程说明
- [ ] 更新 `TheSchema.md`
  - 新增 DAG workflow section
- [ ] Git 提交：`docs: update for DAG mode`

### 2.5 E2E 验证
- [ ] 推送测试 URL 到 `raw/youtube-links/`
- [ ] 验证两个 stage 自动执行
- [ ] 检查 Telegram 通知
- [ ] 验证日志记录完整
- [ ] **记录测试结果到** `RUNBOOK.md`

---

## 📋 阶段 3：推广到其他 Wiki（未来）

> 预计工期：2-3 天/wiki
> 依赖：YouTube 验证通过
> 优先级：低（视需要）

### 3.1 obsidian-blink 迁移
- [ ] 创建 DAG 配置
- [ ] 迁移 webhook 路由
- [ ] E2E 验证

### 3.2 prompt-qa 迁移
- [ ] 创建 DAG 配置
- [ ] 迁移 webhook 路由
- [ ] E2E 验证

### 3.3 新 Wiki 模板
- [ ] 为 Dify、Podcast 等创建 DAG 模板
- [ ] 文档化常见模式

---

## 🔧 技术细节

### 当前流程（YouTube - 现状）
```
raw/youtube-links/*.md pushed
  ↓
GitHub Workflow POST → Hermes webhook
  ↓
LLM Agent reads prompt
  ↓
Agent: "based on path, call notebooklm-cli"
  ↓
notebooklm-cli executed
  ↓
Results pushed → 2nd webhook triggered
  ↓
LLM Agent reads prompt again
  ↓
Agent: "based on path, call llm-wiki"
  ↓
llm-wiki executed
  ↓
Telegram notification
```

### 新流程（YouTube - DAG 模式）
```
raw/youtube-links/*.md pushed
  ↓
GitHub Workflow POST → Hermes webhook
  ↓
Webhook Router detects pipeline.yml
  ↓
DAG Engine executes:
  ├─ Stage 1: notebooklm_analyze
  │   ├─ Input: raw/youtube-links/
  │   ├─ Output: raw/notebooklm-analysis/
  │   └─ Push to GitHub
  │
  ├─ Stage 2: llm_wiki_compile (waits for stage 1)
  │   ├─ Input: raw/notebooklm-analysis/
  │   ├─ Action: incremental_build
  │   └─ Output: Telegram notification
  │
  └─ End
```

### 关键改进
- ✅ 无需 LLM 推理（确定性编排）
- ✅ 支持并行（future use case）
- ✅ 明确的依赖（易维护）
- ✅ 完整的状态追踪

---

## 📊 验收标准

### DAG 引擎完成后
- [ ] 所有单元测试通过
- [ ] 集成测试通过
- [ ] 文档完整
- [ ] CLI 命令可用

### YouTube 迁移完成后
- [ ] YouTube wiki 正常工作
- [ ] 与旧模式结果一致
- [ ] 日志记录完整
- [ ] Telegram 通知正常

### 整体验收
- [ ] 性能不下降
- [ ] 错误恢复能力更强
- [ ] 代码覆盖率 >80%
- [ ] 文档齐全

---

## 📝 后续维护

### 监控指标
- [ ] DAG 执行成功率
- [ ] 平均执行时间
- [ ] 错误类型分布
- [ ] 重试次数

### 常见问题
- [ ] FAQ 文档：`docs/workflow-faq.md`
- [ ] 故障排查：`docs/workflow-troubleshooting.md`
- [ ] 最佳实践：`docs/workflow-best-practices.md`

---

## 🎯 下一步行动

1. **立刻**：快速实现 YouTube wiki（用现有 Hermes 方案）✅
2. **阶段 1 开始**：设计 DAG YAML schema
3. **本周完成**：DAG 引擎核心开发
4. **下周验证**：YouTube 迁移到 DAG
5. **后续推广**：其他 wiki 逐步迁移

---

## 📞 相关文件

- 当前配置：`~/.hermes/webhook_subscriptions.json`
- 技能文档：`hermes-brain/brain/hermes-home/skills/research/llm-wiki/SKILL.md`
- 工作流模板：`hermes-brain/brain/hermes-home/skills/devops/llm-wiki-multiwiki-e2e-gate/templates/`

---

**上次更新**：2026-05-08
**负责人**：@copilot-cli
**状态**：Ready to Start Phase 1
