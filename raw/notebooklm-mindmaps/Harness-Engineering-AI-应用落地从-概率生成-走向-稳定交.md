---
title: "Harness Engineering：AI 应用落地从“概率生成”走向“稳定交付”的深度解析 脑图"
type: mindmap
source: raw/notebooklm-mindmaps/Harness-Engineering-AI-应用落地从-概率生成-走向-稳定交.json
---

```mindmap
root((｛'name': 'Harness Engineering （HE）', 'children': 【｛'name': '))
  ｛'name': 'AI 工程演进三个阶段', 'children': 【｛'name': 'Prompt Engine
    ｛'name': 'Prompt Engineering', 'children': 【｛'name': '核心：语言设
      ｛'name': '核心：语言设计'｝
      ｛'name': '解决：表达与意图理解'｝
      ｛'name': '局限：无法处理知识缺失与长链路'｝
    ｛'name': 'Context Engineering', 'children': 【｛'name': '核心：信息
      ｛'name': '核心：信息供给'｝
      ｛'name': '解决：在正确时机送入正确信息'｝
      ｛'name': '实践：RAG、动态 SOP、分层信息暴露'｝
    ｛'name': 'Harness Engineering', 'children': 【｛'name': '核心：系统
      ｛'name': '核心：系统驾驶与约束'｝
      ｛'name': '解决：持续执行的稳定性与纠偏'｝
      ｛'name': '定义：Agent = Model + Harness'｝
  ｛'name': 'HE 的六层核心结构', 'children': 【｛'name': '信息边界层', 'child
    ｛'name': '信息边界层', 'children': 【｛'name': '角色目标定义'｝, ｛'name': 
      ｛'name': '角色目标定义'｝
      ｛'name': '信息裁剪与选择'｝
      ｛'name': '结构化组织'｝
    ｛'name': '工具系统层', 'children': 【｛'name': '工具选择与挂载'｝, ｛'name':
      ｛'name': '工具选择与挂载'｝
      ｛'name': '调用时机控制'｝
      ｛'name': '结果提炼与反馈'｝
    ｛'name': '执行编排层', 'children': 【｛'name': '任务步骤串联'｝, ｛'name': 
      ｛'name': '任务步骤串联'｝
      ｛'name': '逻辑轨道（理解-补全-生成-检查）'｝
    ｛'name': '记忆与状态管理', 'children': 【｛'name': '当前任务状态'｝, ｛'name'
      ｛'name': '当前任务状态'｝
      ｛'name': '中间结果'｝
      ｛'name': '长期记忆与用户偏好'｝
    ｛'name': '评估与观测层', 'children': 【｛'name': '独立验收机制'｝, ｛'name':
      ｛'name': '独立验收机制'｝
      ｛'name': '日志与指标归因'｝
    ｛'name': '约束、校验与恢复', 'children': 【｛'name': '操作红线约束'｝, ｛'name
      ｛'name': '操作红线约束'｝
      ｛'name': '失败重试与路径回滚'｝
  ｛'name': '顶级公司实践案例', 'children': 【｛'name': 'Anthropic', 'chi
    ｛'name': 'Anthropic', 'children': 【｛'name': 'Context Reflect
      ｛'name': 'Context Reflection （重置进程恢复状态）'｝
      ｛'name': '执行与验收分离 （Planner/Generator/Evaluator）'｝
    ｛'name': 'OpenAI', 'children': 【｛'name': '环境设计而非代码编写'｝, ｛'na
      ｛'name': '环境设计而非代码编写'｝
      ｛'name': 'Index 化指令 （按需暴露子文档）'｝
      ｛'name': '自动化治理系统 （规则反馈闭环）'｝
  ｛'name': '核心价值总结', 'children': 【｛'name': '决定 AI 应用能否落地稳定交付'｝
    ｛'name': '决定 AI 应用能否落地稳定交付'｝
    ｛'name': '从「让模型更聪明」转向「让执行更稳健」'｝
    ｛'name': '对整个运行系统的工程化管理'｝
```
