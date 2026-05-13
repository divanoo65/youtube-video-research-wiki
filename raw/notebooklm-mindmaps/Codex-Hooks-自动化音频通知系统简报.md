---
title: "Codex Hooks 自动化音频通知系统简报 脑图"
type: mindmap
tags: [mindmap]
source: raw/notebooklm-mindmaps/Codex-Hooks-自动化音频通知系统简报.json
---

## 图谱（Obsidian 预览中打开）

```mermaid
mindmap
root((Codex Hooks 入门教程))
  核心功能
    音频通知
    任务自动化
    解决漫长等待
  生命周期 （Hooks）
    session_start （新窗口）
    user_prompt_submit （提交提示词）
    permission_request （需要授权）
    stop （任务结束）
  准备工作
    获取脚本内容
    下载 MP3 音频文件
    查阅官方文档
  文件结构
    .codex 文件夹
      audio 目录 （存放音频）
      scripts 目录 （存放脚本）
      hooks.json （配置钩子）
      confirm 文件
  实施步骤
    新建目录与文件
    配置 hooks.json 命令
    编写/导入运行脚本 （Mac/Win/Linux）
    赋予脚本运行权限
    IDE 中人工确认/信任 Hooks
  进阶与总结
    作用域
      项目级 （项目根目录）
      全局级 （用户根目录）
    拓展应用
      系统通知
      日志检查
      Git 自动提交
```

## 与 Wiki 的链接

<!-- Stage C 完成后自动补充 wikilinks -->
