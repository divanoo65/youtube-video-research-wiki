---
title: "Memory Sources"
type: concept
tags: [memory, personalization, long-term-context, gpt, chatgpt]
summary: "GPT-5.5 引入的跨会话记忆功能，使模型能参考过去的聊天记录和相关数据，向具备长期陪伴能力的个人 AI 助理方向演进。"
sources:
  - raw/notebooklm-analysis/GPT-5-5-Instant-深度分析简报-特性-实测与应用洞察.md
created: 2026-05-09
updated: 2026-05-09
layer: L2
confidence: medium
reasoning: "源视频中描述了 Memory Sources 功能的引入，但具体实现细节和技术方案有限，部分描述为推断"
section: concepts
---

# Memory Sources

## 定义
GPT-5.5 引入的跨会话记忆功能，使模型能更好地参考过去的聊天记录和关联数据，根据用户的历史偏好和地理位置提供更精准的建议。这是 AI 从单纯的问答工具向长期陪伴能力的个人助理演进的关键一步。

## 本库的具体例子

- GPT-5.5 Instant 引入了类似 Memory Sources 的功能
- 上下文关联：模型能更好地参考过去的聊天记录和相关关联数据
- 高度定制化建议：根据用户的历史偏好和地理位置（如特定的城市背景）提供更精准的建议
- 对比方向：与 Hermes Agent 的分层记忆体系不同，GPT-5.5 的记忆功能更侧重个性化和持续陪伴，而非技术栈层面的知识沉淀

## 关联概念
- [[分层记忆体系]] — Hermes Agent 中类似的记忆持久化方案，实现路径不同
- [[对话去机械化]] — Memory Sources 与自然对话结合，进一步提升体验

## 关联实体
- [[gpt-5-5-instant]] — 此概念的实现载体
- [[chatgpt]] — 搭载此能力的平台
