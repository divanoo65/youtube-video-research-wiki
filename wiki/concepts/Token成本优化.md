---
title: Token成本优化
type: concept
tags: [cost-optimization, token, hermes-agent]
summary: 通过主副模型分离和辅助任务分类，将高频简单任务的Token消耗转移给廉价模型，实现Agent运行总成本的大幅下降。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Token成本优化

## 定义

Token成本优化是指在使用AI Agent（特别是Hermes Agent）时，通过架构设计和模型选择策略，降低单位任务的Token消耗量，从而控制API调用费用或免费额度使用速度。核心思路是将Token预算集中用于高价值推理，而将低价值辅助任务交给低成本模型处理。

## 技术实现细节

1. **模型选择**：副模型选择价格低廉但能力足够的模型，如Gemini 1.5 Flash的API价格仅为高端模型的1/10～1/20。
2. **任务拆分**：Agent将每个用户请求分解为多个子任务，辅助任务直接调用副模型。
3. **上下文压缩**：通过Compression任务压缩历史对话，减少后续请求的输入Token长度。
4. **配置化管理**：所有模型分配在配置文件中集中管理，修改一组参数即可切换，方便实验不同模型组合。

## 在本库的具体例子

- 在 [[Hermes-Agent-高级玩法与部署优化简报]] 中，创作者将六大辅助任务全部设为Gemini 1.5 Flash后，运行一周的Token消耗从原本的约500万降至不足100万，成本下降80%以上。这一数据来自视频中展示的日志截图。

## 与近似概念的边界

- **Prompt压缩**：仅减少输入Token长度，而Token成本优化还包括减少输出Token（通过使用廉价模型输出）和降低模型单价。
- **缓存复用**：通过缓存重复查询结果来节省Token，但不涉及任务拆分；成本优化更侧重架构层面的分流。

## 关联概念

- [[主副模型策略]] — 实现Token成本优化的主要手段。
- [[辅助任务分类]] — 划分可低成本处理的非核心任务。

## 关联实体

- [[Hermes-Agent]]
- [[Gemini]]
