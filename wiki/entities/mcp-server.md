---
title: MCP 服务器
type: entity
tags:
  - AI
  - 设计系统
  - 协作
  - 协议
  - Open Design
summary: MCP 服务器（Model Context Protocol Server）是 [[Open Design]] 平台中的一个核心组件，它通过实现不同 AI 代理间的跨工具协作和设计文件共享，极大地提升了设计工作流的效率和灵活性。
sources:
  - raw/notebooklm-analysis/Open-Design-开源-AI-设计系统的深度解析与实操指南.md
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: 信息直接来源于提供的报告节选，明确指出了MCP服务器的功能和重要性。
---
MCP 服务器，全称为 Model Context Protocol Server，是 [[Open Design]] 这一开源 AI 设计系统中的一个关键技术支柱。它被设计用来解决在复杂 AI 驱动的设计环境中，不同人工智能代理（Agents）之间协同工作和数据共享的挑战。具体而言，MCP 服务器实现了跨工具的协作能力，允许不同的 AI 代理，例如处理 [[UI 布局]]、[[原型设计]] 或代码生成的模块，能够无缝地交换信息、共享设计文件和共同推进设计任务。这种“跨代理协作”的模式，在当前的 AI 设计工具领域被认为是具有前瞻性的创新，它打破了传统工具的孤岛效应，使得整个设计流程更加流畅和高效。通过 MCP 服务器，[[Open Design]] 不仅能够整合多种 AI 工具，还能确保它们作为一个统一的系统协同运作，从而重新定义了 AI 驱动的工业级设计工作流，为用户提供了前所未有的自由度和强大的功能。

### 在本视频中的角色
在本视频中，MCP 服务器被强调为 [[Open Design]] 实现其核心优势——“突破闭源束缚的开放架构”的关键技术之一。它具体负责实现不同 AI 代理间的跨工具协作与设计文件共享，是 Open Design 能够整合并协调多种 AI 工具，从而提供高度自由和灵活设计体验的重要支撑。报告指出，通过 MCP 服务器实现的跨代理协作，以及对本地文件系统的直接访问，Open Design 正在重新定义 AI 驱动的工业级设计工作流。