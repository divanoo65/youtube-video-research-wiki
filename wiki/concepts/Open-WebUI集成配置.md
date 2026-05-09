---
title: Open-WebUI集成配置
type: concept
tags: [open-webui, configuration, api, agent-interface]
summary: 在Hermes Agent中启用API服务并设置密码，然后对接Open WebUI，获得类ChatGPT的交互体验。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Open-WebUI集成配置

## 定义

Open-WebUI集成配置是指在Hermes Agent的配置文件中启用REST API服务（默认端口8642），设置访问密码，然后在Open WebUI管理后台添加该API连接，从而使用Open WebUI作为Hermes Agent的前端交互界面，替代原生简陋的聊天界面或微信等第三方工具。

## 技术实现细节

1. 修改Hermes Agent的配置文件（通常位于 `~/.hermes/config.yaml` 或 `config/agent.yaml`），添加以下参数：
   - `enable_api: true`
   - `api_port: 8642`
   - `api_password: <自定义复杂密码>`
2. 保存文件后，在终端中运行命令重启Hermes Agent Gateway（例如 `hermes restart` 或 `systemctl restart hermes-gateway`）。
3. 在Open WebUI的管理界面（通常是 `http://localhost:8080/admin/connections`）中添加新的LLM连接：
   - URL: `http://<本地IP或host.docker.internal>:8642/v1`
   - API Key: 上一步设置的自定义密码
4. 保存后，Open WebUI即可开始与Hermes Agent通信，支持Markdown渲染、代码执行、流式输出等高级功能。

## 在本库的具体例子

- 在 [[Hermes-Agent-高级玩法与部署优化简报]] 中，详细演示了上述所有步骤，并展示了在Open WebUI中输入Python冒泡排序代码并成功运行的界面。同时还提到通过内网穿透工具（如frp）将8080端口暴露到公网，实现手机远程访问。

## 与近似概念的边界

- **直接使用Hermes Agent自带界面**：自带界面功能简单，不支持Markdown和代码运行；Open WebUI集成后大幅提升体验。
- **对接微信等聊天工具**：微信不支持Markdown渲染，且历史记录管理困难；Open WebUI提供侧边栏和专业管理。

## 关联概念

- [[Token成本优化]] — 通过主副模型降低成本的配置与此处API配置独立。
- [[内网穿透]] — 实现移动端远程访问的配套技术。

## 关联实体

- [[Open-WebUI]]
- [[Hermes-Agent]]
