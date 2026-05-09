---
title: api-enabled
type: concept
tags: [api, configuration]
summary: API Enabled 是 Hermes Agent 配置文件中启用 API 服务的关键设置，需设置 api_enabled: true 和 api_password 以支持 Open WebUI 等外部工具连接。
sources: [wiki/sources/Hermes-Agent-高级玩法与优化指南-深度简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
---

# API Enabled

## 定义

API Enabled 是 Hermes Agent 配置文件中启用 API 服务的关键设置，需设置 `api_enabled: true` 和 `api_password` 以支持 Open WebUI 等外部工具连接。

## 在本库的具体例子

在 [[open-webui]] 中，需在配置文件中添加 `api_enabled: true` 并设置自定义密码 `api_password`，以便与 Open WebUI 连接。

## 技术实现细节

1. **配置文件修改**：在 Hermes Agent 的配置文件中，设置 `api_enabled: true` 以启用 API 服务。
2. **密码设置**：需设置 `api_password` 以确保 API 服务的安全性。

## 与近似概念的边界

- **API 服务**：API Enabled 是启用 API 服务的配置项，而 API 服务本身是提供接口的功能模块。
- **安全机制**：API Enabled 包含密码验证，而其他安全机制可能涉及更多层面的防护。

## 关联概念

[[token-优化]] [[主副模型配置]]

## 关联实体

[[open-webui]]