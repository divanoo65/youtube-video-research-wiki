---
title: "Hermes Agent 高级应用与优化简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Hermes-Agent-高级应用与优化简报.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((Hermes Agent 高级玩法))
  Ollama 云端免费模型
    特点：内置 Hermes Agent，一键部署
    优势：不占本地资源，傻瓜化配置
    模型示例：Minimax M2.7 云端版
    步骤：官网下载 -> 安装运行 -> 连接设备 -> 刷新 Gateway
  Open WebUI 交互优化
    核心功能
      原生支持：完美解析 Markdown 格式
      历史管理：左侧边栏保存对话记录
      代码增强：支持流式输出、运行 Python 代码
      多模态：上传文件、截图、网页引用
    配置步骤
      修改配置文件：启用 API 服务、设置访问密码
      部署：执行官方安装与启动命令
      Web 设置：添加连接 （URL/端口8642/密码）
    多端访问：支持手机浏览器通过 IP 地址远程连接
  Token 节省配置
    核心策略：主副模型分工 （复杂任务 vs 简单任务）
    副模型 （辅助任务） 配置
      任务类型：批准、压缩、MCP调用、Session 搜索、视觉、网页等
      推荐模型：Gemini 1.5 Flash （性价比高）
    操作：在配置文件中为不同任务指定 API Key 和模型 ID
  项目优势
    稳定性：碾压 OpenCloud，更新少 Bug
    易用性：Star 增速快，支持中文名“赫美斯”
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
