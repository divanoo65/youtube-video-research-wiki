---
title: Codex Hooks
type: concept
tags: [codex-hooks, 自动化, OpenAI]
summary: OpenAI Codex CLI 提供的事件驱动机制，允许在任务生命周期节点绑定自定义脚本实现自动化。
sources: [raw/notebooklm-analysis/Codex-Hooks-入门-实现任务自动化与音频通知简报.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T--jcUGGN2LFA
---

# Codex Hooks

## 定义

Codex Hooks 是 OpenAI Codex CLI 内置的一种事件驱动机制，允许用户在 AI 编码任务运行的不同生命周期阶段（如提交提示词、等待授权、任务结束）绑定自定义脚本，从而实现自动化操作，如播放音频通知、写入日志、触发 Git 提交等。其核心设计理念是“在正确的时间点插入正确的自动化动作”，将人工介入从被动等待转变为主动通知。

## 在本库的具体例子

在 [[Codex-Hooks-入门-实现任务自动化与音频通知简报]] 报告中，配置了三个关键生命周期节点的音频播放脚本：
- `user_prompt_submit`：任务开始时播放“开始”音频。
- `permission_request`：需要用户授权时播放“请求授权”音频，避免用户离开时任务长时间等待。
- `stop`：任务结束时播放“完成”音频。

这些脚本通过 `.codex/hooks.json` 配置，指向 `scripts/` 目录下的平台专用脚本（如 macOS 的 `.sh` 文件），音频文件存放在 `audio/` 目录中。

## 技术实现细节

1. **配置文件**：核心配置文件为 `.codex/hooks.json`，其结构包含 `hooks` 数组，每个 hook 对象包含 `type`（生命周期类型）、`command`（要执行的命令字符串）、`timeout`（超时时间）。示例：
   ```json
   {
     "hooks": [
       {
         "type": "permission_request",
         "command": "bash scripts/play_sound.sh permission.mp3",
         "timeout": 5000
       }
     ]
   }
   ```
2. **跨平台支持**：脚本需针对不同操作系统编写，macOS 使用 `.sh` 脚本（利用 `afplay` 命令），Windows 使用 `.ps1` 脚本（利用 `[System.Media.SoundPlayer]`），Linux 使用 `aplay` 或 `paplay`。
3. **执行权限**：在 Unix 类系统中，脚本文件需具有可执行权限（`chmod +x`）。

## 与近似概念的边界

- **与通用“钩子”模式的区别**：软件工程中的钩子（如 Git Hooks、React 生命周期）通常针对版本控制或 UI 框架，而 Codex Hooks 专为 AI 编码任务的执行流程设计，具有标准化的生命周期命名和强制性的安全信任审查机制。
- **与“回调函数”的区别**：回调函数是编程语言层面的异步处理模式，Codex Hooks 是 CLI 工具层面的声明式配置模式，用户无需编写程序主逻辑，仅需配置触发条件和命令。

## 关联概念

- [[Codex-Hooks生命周期]] — 定义了六个标准触发时机。
- [[Codex-Hooks部署范围]] — 项目级与全局级配置方式。
- [[Codex-Hooks信任机制]] — 必须通过人工审查才可激活脚本。

## 关联实体

- [[OpenAI]] — Codex CLI 的开发者，负责维护 Hooks 功能。