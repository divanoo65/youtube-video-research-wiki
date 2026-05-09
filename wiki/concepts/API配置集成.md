---
title: API 配置集成
type: concept
tags: [configuration, api, integration, agent-setup]
summary: API 配置集成是 Hermes Agent 通过修改配置文件启用 API 服务并供外部前端（如 Open WebUI）连接的方法，是实现自定义交互界面的关键步骤。
sources: [raw/notebooklm-analysis/Hermes-Agent-赫美斯-高级应用与配置指南-云端模型-界面优化与-To.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# API 配置集成

## 定义
API 配置集成是指通过修改 Hermes Agent 的配置文件，启用其内置 API 服务，使外部前端工具（如 [[Open-WebUI]]）能够通过 API 连接并控制 Agent。这是将 Hermes Agent 从纯命令行工具转变为具备可视化界面的完整系统的关键环节。

## 配置步骤
1. 编辑 Hermes 配置文件（通常位于 `~/.hermes/config.yaml`）
2. 设置 `api_enabled: true` 启用 API 服务
3. 设置 `api_password` 为自定义密码（用于安全认证）
4. 重启 Hermes Gateway 使配置生效
5. 在 Open WebUI 中配置连接参数，指向 Hermes 的 API 地址

## 技术实现细节
API 服务默认在本地端口监听，局域网内可通过 IP + 端口（通常 8080）访问。API 密码验证确保了只有授权的前端才能连接。

## 关联实体
- [[Hermes-Agent-赫美斯]] — 提供 API 服务的 Agent 工具
- [[Open-WebUI]] — 通过 Hermes API 连接的主要前端界面

## 关联概念
- [[主副模型架构]] — API 配置后可在 Open WebUI 中配置不同的主副模型
