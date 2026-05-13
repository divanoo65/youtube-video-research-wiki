---
title: Docker
type: entity
tags:
  - 容器化
  - AI Agent
  - 基础设施
  - 无状态化
  - 沙盒
summary: Docker 是一种轻量级容器化技术，在 AI Agent 架构中用于部署 Worker 节点，提供环境隔离、快速创建与销毁能力，支持无状态化执行。
sources:
  - "raw/notebooklm-analysis/anthropic-managed-agents-brief.md"
created: 2025-03-29
updated: 2025-03-29
layer: L1
confidence: high
reasoning: 根据报告原文对 Docker 在 Agent 基础设施中的详细描述，包括容器化 Worker 节点、毫秒级启动需求等，本实体定义准确且与上下文高度一致。
---

## 实体描述

Docker 是一种基于操作系统级虚拟化的容器技术，通过将应用及其依赖打包在轻量级、可移植的容器中，实现环境的一致性和隔离性。在 AI Agent 系统的工程实践中，Docker 被用作 Worker 节点的运行载体——每个 Agent 实例被塞入独立的 Docker 容器中，形成“无状态沙盒”。这种设计使得 Agent 执行环境完全与宿主机隔离，避免了因本地依赖积累、文件残留、进程冲突等导致的“越跑越慢”或“莫名报错”等问题。开发者可以随时销毁一个容器并重新创建，从而保证每次执行都是从干净状态开始，这与 [[无状态化]] 原则高度契合。同时，Docker 的轻量特性允许在单台物理机上密集部署大量 Worker，配合任务图驱动等调度机制，支撑起复杂的多 Agent 协作场景。然而，传统 Docker 容器在启动速度上存在瓶颈（通常需要数百毫秒到数秒），这促使行业探索更快的沙盒技术，如 [[Cube Sandbox]] 等毫秒级启动方案，以应对极大规模动态创建与销毁的需求。总体而言，Docker 在当前 Agent 基础设施中扮演着“可编程的运行时底座”角色，是实现 [[脑手分离]] 架构中“手部无状态执行”的关键技术组件。

## 在本视频中的角色

在本视频（Anthropic Managed Agents 架构深度解析与实践简报）中，Docker 作为容器化基础设施的核心组件，被用于部署 Agent Worker 节点。具体角色是：每个 Docker 容器承载一个独立的 Agent Harness 实例，容器随时可销毁、创建，并支持通过初始化参数指定模型、技能、工作目录以及 SSH Key 等配置。通过 Docker 的隔离能力，视频演示了如何解决 Agent 长期运行后的环境污染问题，并展示了基于 Docker 的 Worker 集群如何配合主控服务器执行预定义的任务图，实现编码、审查、测试等环节的异步交互。同时，视频也指出了 Docker 启动速度的局限性，并引入 [[Cube Sandbox]] 作为未来优化方向。

## 相关页面

- [[无状态化]]
- [[Cube Sandbox]]
- [[脑手分离]]
- [[托管代理架构]]