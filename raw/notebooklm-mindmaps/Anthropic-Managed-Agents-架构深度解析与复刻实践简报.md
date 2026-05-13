---
title: "Anthropic Managed Agents 架构深度解析与复刻实践简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Anthropic-Managed-Agents-架构深度解析与复刻实践简报.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((多Agent协作架构（蜂群架构）))
  核心理念：解耦
    解耦脑（模型）与手（沙盒）
    宠物 vs 牛马理论
    无状态执行环境
    解决模型进化与代码过时矛盾
  四层解耦结构
    Agent （静态模板）
      定义工具与模型
      系统提示词
    Session （动态实例）
      对话线程
      独立运行环境
    Coordinator （协调编排）
      任务拆分与派发
      管理Agent花名册
    Session Store （云端记忆）
      上下文解耦
      状态回滚与克隆
  技术实现与工具
    Anthropic Managed Agents
    Docker/Worker节点
    毫秒级启动沙盒 （Cube Sandbox）
    任务图 （Task Graph） 编排
  应用优势
    Token Efficiency （Token效率）
    大规模并发协作
    异构模型组合
    自动化复杂流程 （编码/Review/测试）
  行业趋势
    Agent操作系统化
    从个人工具转向企业基础设施
    计算资源计价变革
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
