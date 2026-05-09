---
title: Ollama云端模型部署
type: concept
tags: [ollama, deployment, cloud-models, zero-resource]
summary: 通过Ollama连接云端免费模型，实现零本地资源占用的Hermes Agent部署方法。
sources: [raw/notebooklm-analysis/Hermes-Agent-高级玩法与部署优化简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-3DlXq9nsQOE
---

# Ollama云端模型部署

## 定义

Ollama云端模型部署是指利用Ollama框架的“Cloud”模型功能，将Hermes Agent后端模型切换为云端免费托管的大模型（如Minimax-M2.7），从而完全免除本地GPU或CPU计算资源需求，只需网络连接即可运行Agent。

## 技术实现细节

1. 用户安装Ollama客户端后，选择带有“Cloud”后缀的模型（例如 `minimax-m2.7-cloud`）。
2. 第一次运行时会自动弹出浏览器，要求用户登录云端服务商的账号并授权设备。
3. 授权成功后，Ollama会将云端模型的API密钥本地缓存，后续调用直接通过HTTPS请求传输，无需消耗本地算力。
4. Hermes Agent的Gateway在启动时检测到Ollama提供的模型URL，自动建立连接。

## 在本库的具体例子

- 在 [[Hermes-Agent-高级玩法与部署优化简报]] 中，详细描述了下载Ollama → 运行集成命令 → 选择 `MXM 2.7` Cloud模型 → 登录账号 → 刷新Gateway的完整流程。部署命令类似 `ollama run hermes-agent --model minimax-m2.7-cloud`。

## 与近似概念的边界

- **本地Ollama模型部署**：指下载模型权重到本地硬盘并运行，会占用本地内存和显存；而云端部署完全不占本地资源。
- **直接调用云端API**：指不使用Ollama，而是直接在Hermes Agent配置中填写OpenAI兼容的API地址和密钥；Ollama云端模型部署的优势在于Ollama统一管理了认证和模型切换。

## 关联概念

- [[主副模型策略]] — 在云端部署中同样适用，主模型和副模型均可通过Ollama选择不同模型。
- [[Token成本优化]] — 云端免费模型可节省Token成本，但副模型策略进一步降低开销。

## 关联实体

- [[Ollama]]
- [[Hermes-Agent]]
