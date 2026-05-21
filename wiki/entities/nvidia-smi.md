---
```markdown
---
title: nvidia-smi
type: entity
tags:
  - nvidia-smi
  - GPU
  - CUDA
  - 命令行工具
  - 系统管理
  - 驱动匹配
  - 显卡监控
summary: nvidia-smi 是 NVIDIA 显卡驱动程序套件中包含的一个命令行工具，用于监控和管理 NVIDIA GPU 设备。它能显示 GPU 的状态、温度、功耗、内存使用情况以及驱动版本和支持的 CUDA 版本，对于深度学习环境的配置和故障排查至关重要。
sources:
  - "raw/notebooklm-analysis/本地化部署开源语音转文字工具技术简报.md"
created: 2023-10-27
updated: 2023-10-27
layer: L1
confidence: high
reasoning: nvidia-smi 是 NVIDIA GPU 管理的核心工具，在技术简报中被明确提及用于检查 CUDA 版本兼容性，是环境搭建的关键步骤。
---
`nvidia-smi`（NVIDIA System Management Interface）是NVIDIA公司为其图形处理器（GPU）提供的一个强大的命令行工具。它是NVIDIA驱动程序套件的一部分，允许用户实时监控和管理其NVIDIA GPU设备。通过`nvidia-smi`，用户可以获取到关于GPU的详细信息，包括但不限于：GPU的型号、驱动版本、[[GPU 支持的最高 CUDA 版本]]、当前功耗、温度、风扇转速、显存使用量以及每个进程的GPU占用情况。这使得它成为深度学习、高性能计算以及任何需要利用NVIDIA GPU进行加速的应用场景中不可或缺的工具。尤其在配置深度学习环境时，`nvidia-smi`常被用来检查CUDA版本兼容性，以确保所安装的深度学习框架（如[[PyTorch 版本]]）能够与GPU硬件及其驱动程序兼容，从而实现[[CUDA 加速]]。它也是诊断GPU相关问题、优化系统性能的重要手段。

### 在本视频中的角色
在《本地化部署开源语音转文字工具技术简报》中，`nvidia-smi`扮演了环境搭建阶段的关键角色。报告明确指出，在进行[[驱动匹配]]时，需要“通过 `nvidia-smi` 查看 GPU 支持的最高 CUDA 版本，确保安装的 PyTorch 版本不超限。”这意味着在部署开源语音转文字工具时，为了确保深度学习模型能够正确利用GPU进行加速计算，开发者必须使用`nvidia-smi`来核实其NVIDIA显卡所支持的CUDA版本上限，进而选择兼容的[[PyTorch 版本]]。这一步骤对于避免因CUDA版本不匹配导致的环境错误或性能问题至关重要。
```