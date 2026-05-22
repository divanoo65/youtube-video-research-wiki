---
title: Docker SDK
type: entity
tags:
  - Docker
  - SDK
  - 远程管理
  - JupyterLab
  - 命令行
  - 空间资源
summary: Docker SDK 是一种允许开发者通过编程方式与 Docker 守护进程交互的工具包，在 Hugging Face Spaces 中，它与 JupyterLab 结合使用，使用户能够通过命令行远程管理和深度定制其部署的 AI 项目和空间资源。
sources:
  - "raw/notebooklm-analysis/Hugging-Face-Spaces-永久免费云服务器使用与-AI-项目部署指.md"
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: 该实体在来源报告中被明确提及，并详细说明了其在 Hugging Face Spaces 中实现远程管理和终端操作的关键作用。其功能和应用场景清晰，信息来源可靠且直接，因此置信度高。
---
Docker SDK（Software Development Kit）是一套允许开发者通过编程方式与 Docker 守护进程进行交互的工具包。它提供了各种语言的 API 客户端库，使得开发者可以构建、运行、管理 Docker 容器、镜像、网络和卷等资源。通过 Docker SDK，用户可以自动化 Docker 相关的操作，将其集成到更复杂的应用程序或工作流中，从而实现对容器化环境的精细控制和管理。这对于需要高度定制化、自动化部署或远程操作的场景尤为重要。在云计算和 AI 项目部署中，Docker SDK 常常被用于提供底层资源管理和环境配置的能力，确保应用在不同环境中一致运行。

### 在本视频中的角色
在《[[Hugging Face Spaces 永久免费云服务器使用与 AI 项目部署指南]]》视频中，Docker SDK 被介绍为一种进阶选项，专为需要对 Hugging Face Spaces 进行深度定制和远程管理的用户设计。通过选择 **Docker SDK** 并配合 **JupyterLab** 模板，用户可以为自己的空间设置访问密码（TOKEN）。部署完成后，用户便能够进入远程终端协议，直接通过命令行管理空间资源。这意味着用户可以执行更复杂的配置、安装额外的软件包、调试代码，甚至对 [[存储空间]] 等资源进行更细致的控制，从而实现更深层次的自定义操作，满足特定 AI 项目的部署需求。