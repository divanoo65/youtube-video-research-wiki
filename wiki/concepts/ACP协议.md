---
title: ACP协议
type: concept
tags: [通信协议, hermes-agent]
summary: ACP协议是 Hermes Agent 中用于模块间通信的Agent通信协议。
sources: [raw/notebooklm-analysis/NbldZVdusKo_d24ec914-e7e1-4097-b8ee-574598890508_20260509T010454Z_report.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

## 定义与核心含义
ACP协议（Agent Communication Protocol）是 Hermes Agent 内置的通信协议，用于在执行循环、网关、工具运行时等模块之间传递指令、数据和状态。

## 应用场景与步骤
- 在 Hermes Agent 的执行循环中，ACP协议用于触发工具调用。
- 通过 `hermes` CLI 或 TUI，用户可以看到ACP协议在工具执行过程中的调用。
- ACP协议支持标准输入/输出（stdio）以及HTTP等传输方式。

## 在本库视频中的具体例子
- 在视频《智能体架构的范式转移：Hermes Agent 与 OpenClaw 深度技术简报》中，提到 Hermes Agent 的网关、工具运行时、ACP协议等模块均围绕执行循环集成。

## 关联概念
- [[执行循环驱动架构]]：ACP协议是执行循环的一部分。
- [[Hermes Agent]]：使用ACP协议进行内部通信的智能体框架。

## 关联实体
- [[Hermes Agent]]：采用ACP协议的智能体。
- [[Nous Research]]：开发了Hermes Agent及其ACP协议的公司。

> 本页面内容基于 raw/notebooklm-analysis/NbldZVdusKo_d24ec914-e7e1-4097-b8ee-574598890508_20260509T010454Z_report.md，仅作 L1 事实层整理。