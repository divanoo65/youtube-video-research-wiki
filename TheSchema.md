---
created: 2026-05-08
updated: 2026-05-08
type: guide
tags: [schema, wiki, knowledge-management, youtube-research]
---

## 0. 目标与边界

> 核心目标：将 YouTube 视频内容转化为可复利、可追溯、可审计的知识层。

- 目标：维护 `wiki/` 目录，将视频洞察沉淀为结构化知识图谱。
- 边界：
  - `raw/` 是唯一事实来源，**只读不改**。
  - 仅在 `wiki/`、`index.md`、`log.md` 内进行知识层维护。

---

## 1. 三层模型（强约束）

### L1 Fact Layer（事实层）
- 仅允许写入可由 `raw/notebooklm-analysis/` 或 `raw/notebooklm-mindmaps/` 直接支持的事实。
- 每条关键事实必须可追溯到对应的视频来源页。
- 禁止把推测写成事实。

### L2 Inference Layer（推断层）
- 允许基于多个 L1 事实做归纳/推断（跨视频综合）。
- 必须显式标注：`confidence: high|medium|low` + `reasoning: 推理依据`

### L3 Question Layer（问题层）
- 记录未决问题、假设、证据缺口。
- 指导下一轮视频采集方向，不作为既定事实。

---

## 2. 目录结构约定

| 目录 | 用途 |
|------|------|
| `raw/youtube-links/` | 输入的 YouTube 链接文件 |
| `raw/notebooklm-analysis/` | NotebookLM 生成的研究报告（只读） |
| `raw/notebooklm-mindmaps/` | NotebookLM 生成的思维导图 JSON（只读） |
| `wiki/sources/` | 每个视频的来源摘要页 |
| `wiki/entities/` | 人物、组织、产品、模型等实体页 |
| `wiki/concepts/` | 技术方法、理论、框架等概念页 |
| `wiki/comparisons/` | 对比分析页（多视频/多实体对比） |
| `wiki/overview/` | 主题总览与综合分析页 |
| `wiki/queries/` | 重要问答沉淀 |

---

## 3. 页面格式（frontmatter）

所有 wiki 页面必须包含：

```yaml
---
title: 页面标题
type: source|entity|concept|comparison|overview|query
tags: [tag1, tag2]
summary: 一句话核心内容（必填）
sources: [raw/notebooklm-analysis/xxx_report.md]
created: YYYY-MM-DD
updated: YYYY-MM-DD
layer: L1|L2|L3
confidence: high|medium|low
reasoning: 推理依据（L2/L3 必填）
---
```

**强约束**：`type/tags/summary/sources/updated/layer` 必填；L2/L3 时 `confidence+reasoning` 必填。

---

## 4. 页面类型规范

### 4.1 Source Summary（视频来源摘要页）
路径：`wiki/sources/{video-id}-{slug}.md`
必含：
- 视频信息（标题、URL、发布者、日期）
- 执行摘要（3-5句）
- 核心要点（5-10条 bullet）
- 关键引言（原文+背景分析）
- 关联实体链接 `[[entity-name]]`
- 关联概念链接 `[[concept-name]]`

### 4.2 Entity Page（实体页）
路径：`wiki/entities/{slug}.md`
覆盖：人物、组织、产品、AI模型、工具、框架
必含：
- 基本信息与定位
- 核心能力/特征
- 关键事件或里程碑
- 与其他实体的关系 `[[other-entity]]`
- 出现的视频来源 `[[source-page]]`

### 4.3 Concept Page（概念页）
路径：`wiki/concepts/{slug}.md`
覆盖：技术方法、理论框架、设计模式、行业趋势
必含：
- 定义与核心含义
- 应用场景与步骤
- 在本库视频中的具体例子
- 关联概念 `[[related-concept]]`
- 关联实体 `[[related-entity]]`

### 4.4 Comparison Page（对比页）
路径：`wiki/comparisons/{slug}.md`
必含：对象简介、相同点、不同点、结论与适用条件

---

## 5. 增量构建工作流（Webhook 触发）

### 触发条件
- `raw/notebooklm-analysis/` 或 `raw/notebooklm-mindmaps/` 有新文件

### 执行步骤
1. 读取本文件（TheSchema.md）、`index.md`、`log.md` 最近记录。
2. 用 `git diff before..sha` 找到新增/变更的 `raw/**/*.md` 文件。
3. 若无变化：`skipped:no_raw_changes`，停止。
4. 对每个新的分析报告：
   a. 创建 `wiki/sources/{video-id}-{slug}.md`（L1，从报告提炼）
   b. 创建/更新 `wiki/entities/` 相关实体页（L1/L2）
   c. 创建/更新 `wiki/concepts/` 相关概念页（L1/L2）
   d. 如有跨视频对比价值，创建 `wiki/comparisons/`
5. 更新 `index.md`（按 type 分类，字母序，带 summary）
6. 追加 `log.md`（run_id、日期、新增文件列表）
7. git add + commit + push
8. 发送 Telegram 摘要

---

## 6. 质量门禁（必过）

1. **可追溯性**：每个 wiki 页面的 `sources` 必须指向存在的 `raw/` 文件。
2. **层级一致性**：L1 事实直接来自原文；L2 推断标注 confidence+reasoning。
3. **内链健康**：每个页面至少 2 个 `[[wikilink]]` 出链；禁止孤立页。
4. **Frontmatter 完整**：缺字段的页面必须在 log 中记录。
5. **内容密度**：source 页 ≥ 300 字，entity/concept 页 ≥ 200 字。
6. **日志完整**：每次执行写 `logs/webhook-runs/{run_id}.md`。

---

## 7. 命名规范

- source 页：`{video-id}-{短标题-slug}.md`（如 `NbldZVdusKo-claude-code-demo.md`）
- entity 页：`{实体名-slug}.md`（如 `claude-sonnet.md`、`openai.md`）
- concept 页：`{概念-slug}.md`（如 `prompt-engineering.md`、`rag.md`）
- 内链：`[[page-slug]]` 或 `[[page-slug|显示文字]]`
- 所有内容使用中文，frontmatter 字段名用英文。
