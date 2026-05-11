---
title: Codex Hooks 生命周期
type: concept
tags: [codex-hooks, 生命周期, 自动化]
summary: Codex Hooks 定义的六个标准化任务生命周期节点，用于精准触发自动化脚本。
sources: [raw/notebooklm-analysis/Codex-Hooks-入门-实现任务自动化与音频通知简报.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T--jcUGGN2LFA
---

# Codex Hooks 生命周期

## 定义

Codex Hooks 生命周期是 OpenAI Codex CLI 为 AI 编码任务定义的六个标准化事件节点：`session_start`、`user_prompt_submit`、`permission_request`、`tool_use_start`、`tool_use_end`、`stop`。每个节点对应任务运行中的特定时刻，用户可以通过 `hooks.json` 将自定义脚本绑定到这些节点上，实现精准的自动化触发。

## 在本库的具体例子

在 [[Codex-Hooks-入门-实现任务自动化与音频通知简报]] 中，重点使用了以下三个节点：
- **`user_prompt_submit`**：用户提交提示词后立即执行，用于播放任务开始的音频提醒。
- **`permission_request`**：当 Codex 需要用户授权（如删除文件、访问网络）时触发，播放“需要授权”音频，将用户的注意力拉回屏幕。这是解决长时间任务空闲等待的核心节点。
- **`stop`**：任务处理结束时触发，播放任务完成的音频，告知用户可检查结果。

另外三个节点 `session_start`、`tool_use_start`、`tool_use_end` 在本视频中未直接使用，但可作为扩展点。

## 技术实现细节

1. **配置方式**：在 `hooks.json` 的 `type` 字段填写生命周期名称，例如：`"type": "permission_request"`。注意名称必须完全匹配官方定义的字符串（区分大小写）。
2. **执行时机**：每个节点在任务流程中精确触发一次（`stop` 可能因异常提前触发）。`permission_request` 可能在一次任务中出现多次，每次需要授权时都会触发。
3. **节点完整列表**：
   - `session_start`：打开新 Codex 窗口时。
   - `user_prompt_submit`：用户提交提示词后。
   - `permission_request`：需要用户授权时。
   - `tool_use_start`：工具调用开始时。
   - `tool_use_end`：工具调用结束时。
   - `stop`：任务处理结束时（包括成功或异常中止）。

## 与近似概念的边界

与软件工程中常见的“生命周期钩子”（如 Vue.js 的 `mounted`、`updated`）不同，Codex Hooks 生命周期是针对 AI 编码任务的特殊流程设计的，特别是包含了 `permission_request` 这种 AI 场景特有的节点。此外，这些节点必须通过安全信任审查才能生效（见 [[Codex-Hooks信任机制]]）。

## 关联概念

- [[Codex-Hooks]] — 事件驱动机制的核心。
- [[Codex-Hooks部署范围]] — 决定了这些生命周期节点在何种范围内生效。
- [[Codex-Hooks信任机制]] — 新配置的 Hooks 需要人工授权才能激活。

## 关联实体

- [[OpenAI]] — 定义了这六个生命周期标准。