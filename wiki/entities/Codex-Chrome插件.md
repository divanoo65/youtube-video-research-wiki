---
title: Codex Chrome 插件
type: entity
tags: [chrome, plugin, ai-agent, browser-automation]
summary: OpenAI 推出的 Chrome 浏览器插件，集成 GPT-5.5 模型，实现多标签并行、后台静默的计算机使用（Computer Use），支持端到端自动化办公、深度数据提取和多代理协作。
sources: [raw/notebooklm-analysis/Codex-Chrome-插件功能实测与深度解析简报.md]
created: 2026-05-09
updated: 2026-05-09
layer: L1
run_id: T-9MCjT-eUrTs
---

# Codex Chrome Plugin

## 基本定位

Codex Chrome Plugin 是由 OpenAI 开发的 Chrome 浏览器扩展，核心价值在于将 GPT-5.5 的语言能力与浏览器底层控制结合，赋予 AI 代理“计算机使用”能力——即直接操控浏览器界面完成各类复杂任务。

## 核心特征/能力

1. **多标签并行运行**：允许 AI 在独立标签页后台运行，不干扰用户当前操作；支持同时启动多个子代理在不同标签页执行独立任务。
2. **后台静默模式**：AI 操作完全在后台进行，用户可同时进行其他工作，互不冲突。
3. **GPT-5.5 模型驱动**：集成 OpenAI 最新模型，提供 Medium（中等深度思考）和 Fast（快速执行）两种模式，兼顾推理质量与速度。
4. **CDP 底层连接**：通过 Chrome DevTools Protocol 实现标签页创建、DOM 读取、鼠标/键盘事件模拟等精细控制。
5. **MCP 协议支持**：支持 Model Context Protocol，允许代理连接外部客户端（如电商 APP）以规避网页端安全策略拦截。
6. **DOM 渲染数据获取**：当服务器抓取被拦截时，自动切换为从浏览器渲染后的 DOM 提取数据，绕过反爬机制。
7. **跨应用文件操作**：能从 Gmail 读取邮件、匹配本地 PDF 文件，并自动上传到第三方系统。

## 应用场景

- **社区调研与数据整理**：自动浏览开发者论坛（如 Hacker News / Reddit），抓取一段时间内的帖子，总结主题、关键问题与用户情绪，导出结构化 Excel。
- **财务报销自动化**：从 Gmail 检索餐食邮件，匹配本地 PDF 收据，提取日期、金额、商户信息，登录企业报销系统完成分类选择和表单提交。
- **多代理协作绘画**：同时启动四个代理加入在线画图房间，根据同一提示词各自绘制不同作品，展示并行输出能力。

## 关系网络

- **依赖 [[gpt-5.5]]**：Codex 的核心推理与决策能力来自 GPT-5.5 模型。
- **使用 [[Chrome调试协议]]**：通过 CDP 与 Chrome 浏览器建立底层通信，实现鼠标、键盘、DOM 操作。
- **支持 [[模型上下文协议]]**：通过 MCP 连接专用客户端，作为替代方案绕过网站安全策略。
- **竞争关系**：与同类 AI 浏览器自动化工具（如 AutoGPT 的计算机使用模式）存在竞争，但实测速度与准确率更优。

## 关键事件/里程碑

- **2026年5月**：Codex Chrome 插件功能实测视频发布，展示端到端报销、多代理协作、深度调研等能力。
- **2026年前后**：OpenAI 基于 Deep Research 和 Computer Use 技术积累推出该插件，标志着 AI 代理进入浏览器原生时代。

## 出现的视频来源

- [[sources/Codex-Chrome-插件功能实测与深度解析简报]]
