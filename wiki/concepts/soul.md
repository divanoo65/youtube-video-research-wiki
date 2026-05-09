---
title: SOUL.md
type: concept
tags: [hermes-agent, identity, configuration]
summary: Hermes Agent 和 OpenClaw 中定义智能体身份和个性的配置文件。
sources: [raw/notebooklm-analysis/Hermes-Agent-与-OpenClaw-深度对比简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# SOUL.md

## 定义

SOUL.md 是智能体系统中用于定义 AI 身份、个性和行为偏好的配置文件。在 OpenClaw 中，SOUL.md 绑定特定工作区，切换工作区即切换身份；在 Hermes Agent 中，SOUL.md 属于全局属性，保持跨环境的个性一致。

## 在本库的具体例子

在 [[Hermes-Agent-与-OpenClaw-深度对比简报]] 中，SOUL.md 的绑定方式差异被列为两款产品的架构差异之一。

## 技术实现细节

SOUL.md 通常以 Markdown 格式编写，包含角色描述、语气偏好、知识领域等元信息。系统在启动时读取该文件，将其注入到系统提示中，从而影响模型的行为。

## 与近似概念的边界

- **系统提示**：系统提示是通用的指令，SOUL.md 是专门的身份定义文件。
- **用户画像**：用户画像描述用户，SOUL.md 描述 AI 自身。

## 关联概念

- [[中心化网关]]
- [[执行循环驱动]]

## 关联实体

- [[hermes-agent]]
- [[openclaw]]
