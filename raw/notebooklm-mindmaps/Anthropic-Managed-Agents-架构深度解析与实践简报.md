---
title: "Anthropic Managed Agents 架构深度解析与实践简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Anthropic-Managed-Agents-架构深度解析与实践简报.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((多Agent协作架构（蜂群架构）))
  核心理念：解耦
    解耦大脑与双手
      大脑：负责规划决策
      双手：独立无状态沙盒
    从宠物到牛马
      宠物模式：环境绑定、易崩溃
      牛马模式：随时销毁、重新拉起
  Anthropic Managed Agents 架构
    核心组件
      Coordinator：任务拆分编排者
      Agents：具备工具和MCP服务器
      Sessions：动态执行实体
      Memory Store：挂载式记忆
    四层解耦结构
      第一层：Agent（静态模板）
      第二层：Session（执行状态）
      第三层：记忆树（Fork与回滚）
      第四层：Session Store（云端无状态）
  本地复刻实践
    技术实现
      Worker节点：使用Docker封装
      任务图：定义业务流程
      毫秒级沙盒：接入Cube Sandbox
    核心优势
      长程任务：解决上下文不足
      模型组合：Token效率最大化
      高并发：异步协作完成任务
  未来趋势与反思
    计算变革
      从固定容器到动态Agent容器
      计算资源计价模式变革
    产业格局
      企业级基础设施化
      Agent操作系统化
      从卖Token转向落地AGI理解
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
