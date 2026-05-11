---
title: "多Agent协作架构：Anthropic Managed Agents 深度解析简报 脑图"
type: mindmap
source: raw/notebooklm-mindmaps/多Agent协作架构-Anthropic-Managed-Agents-深度解析.json
---

```mindmap
root((｛'name': '多Agent协作架构（Managed Agents）', 'children': 【｛'name':))
  ｛'name': '核心设计理念', 'children': 【｛'name': '解耦脑（大脑）与手（沙盒）'｝, ｛
    ｛'name': '解耦脑（大脑）与手（沙盒）'｝
    ｛'name': '宠物与牛马理论：无状态独立沙盒'｝
    ｛'name': '摆脱过时的修补代码（Harness）'｝
    ｛'name': '云端Agent操作系统'｝
  ｛'name': '四层架构模型', 'children': 【｛'name': '第一层：静态编排器 （Coordin
    ｛'name': '第一层：静态编排器 （Coordinator）', 'children': 【｛'name': '拆
      ｛'name': '拆解任务'｝
      ｛'name': '派活与协调'｝
    ｛'name': '第二层：Agent 实体', 'children': 【｛'name': '静态定义：工具、模型、提
      ｛'name': '静态定义：工具、模型、提示词'｝
    ｛'name': '第三层：Session 会话', 'children': 【｛'name': '动态状态：对话、记忆
      ｛'name': '动态状态：对话、记忆、文件'｝
      ｛'name': '支持克隆、分支与回滚'｝
    ｛'name': '第四层：Session Store 云端存储', 'children': 【｛'name': 'Co
      ｛'name': 'Context 缓存 （Redis）'｝
      ｛'name': '实现 Agent 彻底无状态化'｝
  ｛'name': '实践应用与优势', 'children': 【｛'name': '长程任务处理'｝, ｛'name'
    ｛'name': '长程任务处理'｝
    ｛'name': '大小模型组合优化 （Token Efficiency）'｝
    ｛'name': '动态容器创建与销毁 （Docker/Cube Sandbox）'｝
    ｛'name': '并发协作：搜索、写作、汇报分工'｝
  ｛'name': '行业趋势', 'children': 【｛'name': '企业基础设施化'｝, ｛'name': 
    ｛'name': '企业基础设施化'｝
    ｛'name': '毫秒级启动沙盒'｝
    ｛'name': '新职业：FDE'｝
    ｛'name': 'AGI 落地维度的竞争'｝
```
