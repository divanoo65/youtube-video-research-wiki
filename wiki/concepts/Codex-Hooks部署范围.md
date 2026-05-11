---
title: Codex Hooks 部署范围
type: concept
tags: [codex-hooks, 部署, 配置]
summary: Codex Hooks 支持项目级与全局级两种配置作用域，分别适用于单一项目和用户所有项目的自动化规则。
sources: [raw/notebooklm-analysis/Codex-Hooks-入门-实现任务自动化与音频通知简报.md]
created: 2026-05-11
updated: 2026-05-11
layer: L1
run_id: T--jcUGGN2LFA
---

# Codex Hooks 部署范围

## 定义

Codex Hooks 部署范围是指 Codex Hooks 配置的生效层次，分为项目级（project-level）和全局级（global/user-level）。项目级配置放在项目根目录的 `.codex` 文件夹中，仅对当前项目生效；全局级配置放在操作系统用户根目录的 `.codex` 文件夹中，对该用户下的所有 Codex 项目生效。两个作用域的 hooks 可以共存，系统会合并执行。

## 在本库的具体例子

在 [[Codex-Hooks-入门-实现任务自动化与音频通知简报]] 中，视频教程建议将通用的自动化逻辑（如音频通知、Git 自动提交）部署在全局级，这样每次启动新项目时无需重复配置。而项目特定的钩子（如针对某个项目的日志格式检查）则部署在项目级，实现精细控制。

## 技术实现细节

1. **项目级路径**：`项目根目录/.codex/`。需要在每个需要自动化的项目下手动创建。
2. **全局级路径**：
   - macOS/Linux：`~/.codex/`（用户主目录下的隐藏文件夹）
   - Windows：`%USERPROFILE%\.codex\`
3. **文件夹结构**：两个作用域的文件夹结构完全一致，包含 `audio/`、`scripts/`、`hooks.json`、`confirm` 等。
4. **优先级与合并**：当两个作用域同时存在时，系统会先加载项目级配置，再加载全局级配置，深层合并 hooks 数组。如果同一生命周期节点在两个级别都有配置，两者都会执行（顺序：项目级先执行，全局级后执行）。
5. **信任机制差异**：每个作用域的 hooks 需要分别通过 “Review Hooks” 授权，首次配置时都需要人工审查。

## 与近似概念的边界

与其他开发工具的“全局/项目”配置（如 Git 的 `~/.gitconfig` vs 项目 `.git/config`、VS Code 的 `settings.json` 全局与工作区）类似，Codex Hooks 的部署范围也遵循相同的分层管理原则。但不同之处在于：Codex Hooks 的配置影响的是 AI 助手的自动化行为，且必须经过安全信任审查后方可使用。

## 关联概念

- [[Codex-Hooks]] — 核心机制。
- [[Codex-Hooks生命周期]] — 绑定的触发节点。
- [[Codex-Hooks信任机制]] — 每个作用域需独立授权。

## 关联实体

- [[OpenAI]] — 设计并实现了此部署范围机制。