---
title: Anaconda Prompt
type: entity
tags: ["开发工具", "命令行", "环境管理"]
summary: Anaconda Prompt 是 [[Anaconda]] 或 [[Miniconda]] 安装后提供的一个命令行界面，用于执行 [[Conda]] 命令，管理 Python 环境和安装软件包。在《本地化部署开源语音转文字工具技术简报》中，它被用于创建、激活和配置部署环境。
sources: ["raw/notebooklm-analysis/本地化部署开源语音转文字工具技术简报.md"]
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: 根据来源报告中的明确提及和描述生成。
---
Anaconda Prompt 是 [[Anaconda]] 或 [[Miniconda]] 发行版附带的一个命令行界面（CLI）工具。它提供了一个预配置的环境，用户可以在其中直接执行 [[Conda]] 命令，用于创建、激活、管理独立的 Python 虚拟环境，以及安装、更新和管理各种软件包和依赖项。与系统自带的命令提示符或终端不同，Anaconda Prompt 自动加载了 Conda 相关的环境变量，使得用户无需手动配置路径即可方便地使用 Conda 的各项功能。这对于数据科学、机器学习和软件开发等领域中需要隔离不同项目依赖的场景尤为重要。通过 Anaconda Prompt，用户可以轻松地在不同的项目环境之间切换，确保项目依赖的稳定性和一致性。

**在本视频中的角色：**
在《[[本地化部署开源语音转文字工具技术简报]]》中，Anaconda Prompt 扮演了核心的命令行操作界面角色。它是进行环境搭建的关键工具，具体用于：
1.  **创建环境：** 使用 `conda create` 命令创建名为 `cohere_asr` 的新 Python 环境，并指定 Python 版本为 3.10。
2.  **激活环境：** 通过 `conda activate cohere_asr` 命令激活新创建的环境，确保后续操作都在隔离的环境中进行。
3.  **依赖安装：** 在激活的环境中，安装必要的第三方依赖库及音频处理库，为开源语音转文字工具的部署提供运行基础。
Anaconda Prompt 的使用确保了部署过程中的环境隔离和依赖管理，是成功部署该工具不可或缺的一环。