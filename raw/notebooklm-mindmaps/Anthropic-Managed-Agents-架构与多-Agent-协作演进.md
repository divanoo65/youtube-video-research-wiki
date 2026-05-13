---
title: "Anthropic Managed Agents 架构与多 Agent 协作演进深度简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Anthropic-Managed-Agents-架构与多-Agent-协作演进.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((多Agent协作架构（Managed Agents）))
  核心理念：解耦
    解耦大脑与双手
    大脑：大模型规划决策
    双手：独立代码沙盒环境
    宠物 vs 牛马：从持久绑定转向随用随弃
  四层解耦架构
    Agent层
      静态模板
      定义工具、模型、提示词
    Session层
      动态运行实体
      解耦对话、线程与记忆
      支持克隆、回滚与Fork
    Memory Store层
      记忆挂载至Session
      Agent本身无状态
    Session Store层
      云端记忆（如Redis缓存）
      实现Agent随时销毁与重建
  关键角色：协调者 （Coordinator）
    职责：拆解任务与派活
    能力：管理最多20个Agent
    价值：解决长程任务上下文不足
  技术实现与实践
    基础设施
      Docker容器：Worker节点
      Cube Sandbox：毫秒级启动沙盒
      MCP服务器：工具连接
    业务编排
      预定义任务图
      大小模型组合使用
      提高Token Efficiency
  未来趋势
    Agent操作系统化
    从个人工具转向企业基础设施
    计算资源分配与计价变革
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
