---
title: API Enabled
type: concept
tags: [api, hermes-agent, 配置]
summary: API Enabled 是 Hermes Agent 配置文件中启用 API 服务的关键设置，需设置 api_enabled: true 和 api_password 以支持 Open WebUI 等外部工具连接。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# API Enabled

## 定义
API Enabled 是 [[hermes-agent]] 配置文件中的一个关键设置，用于启用 Agent 的 API 服务。通过设置 `api_enabled: true` 并配置自定义密码 `api_password`，外部工具（如 [[open-webui]]）可以通过 OpenAI 兼容接口连接到 Hermes Agent。

## 在本库的具体例子

- 在 [[hermes-agent-高级玩法与优化指南-深度简报]] 中，视频详细介绍了如何配置 API Enabled 以支持 Open WebUI 连接。
- 具体配置步骤：使用 `antigravity` 或 `Codex` 等工具修改 `agent` 配置文件，添加 `api_enabled: true` 并设置自定义密码 `api_password`，重启 Gateway。
- 连接配置：在 Open WebUI 的管理员设置中添加连接，URL 指向本地 8642 端口，并包含 `/v1` 后缀以确保兼容 OpenAI 接口。

## 技术实现细节

1. **配置项**: 在配置文件中添加 `api_enabled: true` 和 `api_password: <your-password>`。
2. **端口**: API 服务默认运行在本地 8642 端口。
3. **接口兼容**: 提供 OpenAI 兼容接口，URL 需包含 `/v1` 后缀。

## 与近似概念的边界

- **API 密钥**: API 密钥是用于身份验证的令牌，而 API Enabled 是启用 API 服务的开关。
- **Web 界面**: Web 界面（如 Open WebUI）是 API 的客户端，而 API Enabled 是服务端的配置。

## 关联概念

- [[一键部署]] — API Enabled 是一键部署 Hermes Agent 后的关键配置步骤。
- [[主副模型配置]] — API Enabled 与主副模型配置同属 Hermes Agent 的高级配置。

## 关联实体

- [[hermes-agent]] — 需要配置 API Enabled 的 AI Agent 框架。
- [[open-webui]] — 通过 API Enabled 连接的外部工具。