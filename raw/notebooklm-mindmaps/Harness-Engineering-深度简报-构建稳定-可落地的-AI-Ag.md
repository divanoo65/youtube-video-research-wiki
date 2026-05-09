---
title: "Harness Engineering 深度简报：构建稳定、可落地的 AI Agent 系统 脑图"
type: mindmap
source: raw/notebooklm-mindmaps/Harness-Engineering-深度简报-构建稳定-可落地的-AI-Ag.json
---

```mindmap
root((｛'name': 'Harness Engineering （HNIS）', 'children': 【｛'name':))
  ｛'name': '概念定义', 'children': 【｛'name': '核心定义', 'children': 【
    ｛'name': '核心定义', 'children': 【｛'name': 'Agent = Model + Harn
      ｛'name': 'Agent = Model + Harness'｝
    ｛'name': '本质', 'children': 【｛'name': '模型外的运行系统'｝, ｛'name': '
      ｛'name': '模型外的运行系统'｝
      ｛'name': '确保模型稳定执行任务'｝
    ｛'name': '目标', 'children': 【｛'name': '不跑偏'｝, ｛'name': '跑得稳'｝
      ｛'name': '不跑偏'｝
      ｛'name': '跑得稳'｝
      ｛'name': '可纠偏'｝
  ｛'name': 'AI工程化三阶段', 'children': 【｛'name': 'Prompt Engineeri
    ｛'name': 'Prompt Engineering', 'children': 【｛'name': '解决表达问题
      ｛'name': '解决表达问题'｝
      ｛'name': '塑造局部概率空间'｝
    ｛'name': 'Context Engineering', 'children': 【｛'name': '解决信息问
      ｛'name': '解决信息问题'｝
      ｛'name': '在正确时机提供正确信息'｝
    ｛'name': 'Harness Engineering', 'children': 【｛'name': '解决执行问
      ｛'name': '解决执行问题'｝
      ｛'name': '对整个运行系统的工程化'｝
  ｛'name': '六层成熟架构', 'children': 【｛'name': '第一层：信息边界', 'childr
    ｛'name': '第一层：信息边界', 'children': 【｛'name': '角色目标定义'｝, ｛'name
      ｛'name': '角色目标定义'｝
      ｛'name': '信息裁剪选择'｝
      ｛'name': '结构化组织'｝
    ｛'name': '第二层：工具系统', 'children': 【｛'name': '工具选择'｝, ｛'name':
      ｛'name': '工具选择'｝
      ｛'name': '触发时机'｝
      ｛'name': '结果提炼'｝
    ｛'name': '第三层：执行编排', 'children': 【｛'name': '目标理解'｝, ｛'name':
      ｛'name': '目标理解'｝
      ｛'name': '任务串联'｝
      ｛'name': '输出检查'｝
    ｛'name': '第四层：记忆与状态', 'children': 【｛'name': '当前任务状态'｝, ｛'nam
      ｛'name': '当前任务状态'｝
      ｛'name': '中间结果'｝
      ｛'name': '长期记忆'｝
    ｛'name': '第五层：评估与观测', 'children': 【｛'name': '输出验收'｝, ｛'name'
      ｛'name': '输出验收'｝
      ｛'name': '环境验证'｝
      ｛'name': '自动测试'｝
    ｛'name': '第六层：约束与恢复', 'children': 【｛'name': '操作约束'｝, ｛'name'
      ｛'name': '操作约束'｝
      ｛'name': '校验机制'｝
      ｛'name': '重试与回滚'｝
  ｛'name': '一线公司实践', 'children': 【｛'name': 'Anthropic', 'child
    ｛'name': 'Anthropic', 'children': 【｛'name': 'Context Reflect
      ｛'name': 'Context Reflect （进程重置）'｝
      ｛'name': '角色拆分 （Planner/Generator/Evaluator）'｝
    ｛'name': 'OpenAI', 'children': 【｛'name': '环境设计而非单纯写码'｝, ｛'na
      ｛'name': '环境设计而非单纯写码'｝
      ｛'name': '目录化管理 （Index-based Context）'｝
      ｛'name': '自动化治理系统'｝
```
