---
title: Codex Hooks 信任机制
type: concept
tags: [codex-hooks, 安全, 信任]
summary: Codex Hooks 的安全机制，要求用户在新配置后手动审查并授权，防止恶意脚本自动执行。
sources: [raw/notebooklm-analysis/Codex-Hooks-入门-实现任务自动化与音频通知简报.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T--jcUGGN2LFA
---

# Codex Hooks 信任机制

## 定义

Codex Hooks 信任机制是 OpenAI Codex CLI 内置的安全防护措施。当用户首次配置 Hooks（包括新增 hooks.json 或脚本文件）后，Codex App 会拦截所有未授权的脚本执行，弹出一个 “Review Hooks” 界面，要求用户逐一审查已配置的生命周期节点和对应的命令，并手动选择 “Trust”（信任）该配置。只有经过信任的 Hooks 才会在后续任务中生效。

## 在本库的具体例子

在 [[Codex-Hooks-入门-实现任务自动化与音频通知简报]] 中，视频明确强调：完成文件结构搭建和脚本编写后，必须打开 Codex App 找到 Hooks 设置，点击 “Review Hooks”，仔细检查每条 hook 配置，确认没有恶意或危险命令后再点击 “Trust”。如果用户跳过此步骤，脚本将不会执行，自动化功能无法生效。

## 技术实现细节

1. **触发条件**：当 `.codex/` 目录中的 `hooks.json` 或任何脚本内容发生变化（新增、修改）时，系统会在下一个任务启动前弹出审查界面。
2. **审查内容**：用户可以看到每个 hook 的 `type`（生命周期节点）、`command`（即将执行的命令字符串）以及 `timeout`。用户可以逐个启用或禁用。
3. **作用域信任**：项目级和全局级需要分别独立信任。信任状态持久化，直到配置再次被修改。
4. **恢复默认**：用户可以在 App 设置中清除信任状态，重新进入审查流程。

## 与近似概念的边界

与操作系统的权限请求（如 macOS 的“允许录屏”提示或 Android 的运行时权限）类似，Codex Hooks 信任机制也是在自动化执行前获取用户明确同意。不同之处在于：OS 权限通常以粗粒度（如“所有录屏能力”）请求，而 Codex Hooks 的审查粒度是每个 hook 的具体命令，用户可以看到即将执行的确切脚本路径和参数，提供了更精细的控制。

## 关联概念

- [[Codex-Hooks]] — 受信任机制保护的自动化系统。
- [[Codex-Hooks生命周期]] — 需要信任才能触发的节点。
- [[Codex-Hooks部署范围]] — 每个作用域需分别信任。

## 关联实体

- [[OpenAI]] — 设计并实现了此安全审查机制。