---
title: GPT-5.5
type: entity
tags: [ai-model, openai, language-model]
summary: 报告中与Codex Chrome插件深度集成的AI模型，提供Medium思考和Fast模式，处理速度极快，是Codex实现浏览器自动化的核心引擎。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能实测与深度解析简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# GPT-5.5

## 基本定位

GPT-5.5 是 OpenAI 在 GPT-4.5 基础上进一步迭代的 AI 语言模型（注：根据实测视频的称呼），被集成于 Codex Chrome 插件中作为推理内核。它提供两种运行模式——Medium（中等思考深度）和 Fast（快速），在 Fast 模式下处理速度远超此前所有同类 AI Agent。

## 核心特征/能力

1. **极速推理**：Fast 模式下，处理大规模浏览器自动化任务（如遍历 20+ 帖子、采集 89 条推文）总耗时仅数分钟，被评测者评价为“处理速度特别快”。
2. **双模式切换**：提供 Medium 和 Fast 两种思考深度，用户可根据任务复杂度（深度逻辑分析 vs 快速批量处理）灵活选择。
3. **深度集成**：与 Codex Chrome 插件紧密绑定，通过 CDP 实现对浏览器的底层控制，完成点击、输入、数据提取等操作。
4. **提示词自动优化**：在实测中被 Codex 调用来优化自身提示词，生成的提示词极其规范，大幅提升下游任务成功率。
5. **技术传承**：基于 OpenAI 在 Deep Research 和 Computer Use 领域的技术积累，继承了 GPT 系列强大的语言理解与代码生成能力。

## 应用场景

1. **驱动 Codex 全部任务**：作为 Codex 的推理引擎，支持社区调研、报销流程、电商比价、内容发布等所有自动化场景。
2. **提示词优化**：在跨模型操作中，Codex 登录 ChatGPT Pro 页面，使用 GPT-5.5 优化复杂任务的提示词，提升执行质量。

## 关系网络

- [[Codex-Chrome插件|Codex Chrome]] — GPT-5.5 是 Codex 的核心引擎，Codex 集成该模型实现浏览器自动化。
- [[计算机使用]] — GPT-5.5 代表了 OpenAI 在 Computer Use 方向的最新产品化成果。
- Deep Research（可选概念）— 依托的技术之一。

## 关键事件/里程碑

- **2026年5月 Codex 实测**：首次在实际产品中展示 GPT-5.5 驱动的多代理并行处理能力，Fast 模式处理速度获得实测者高度认可。

## 出现的视频来源

- [[sources/Codex-Chrome-插件功能实测与深度解析简报]]