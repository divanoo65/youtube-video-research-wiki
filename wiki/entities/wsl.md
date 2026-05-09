     1|---
     2|title: WSL
     3|type: entity
     4|tags: [wsl, windows, linux-subsystem, environment, deployment]
     5|summary: Windows Subsystem for Linux (WSL) 是 Windows 上的 Linux 运行环境，本方案使用 WSL (Ubuntu 24.04) 作为 AI 服务的部署基础。
     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|created: 2026-05-09
     8|updated: 2026-05-09
     9|layer: L1
    10|---
    11|
    12|## 基本定位
    13|
    14|WSL 是微软提供的在 Windows 上运行 Linux 二进制文件的兼容层，本方案选用 Ubuntu 24.04 作为 Linux 子系统，用于运行 Llama-cpp 和 Hermes Agent。
    15|
    16|## 核心特征/能力
    17|
    18|1. **Linux 兼容性**：提供完整的 Linux 用户态环境，可运行大部分 Linux 软件，包括 Llama-cpp、CUDA 工具包等。
    19|2. **GPU 直通**：WSL 2 支持 GPU 计算（CUDA），允许 Linux 子系统直接使用宿主机的 NVIDIA 显卡进行 AI 推理。
    20|3. **资源隔离**：与 Windows 系统共享资源但独立运行，不影响宿主机日常使用。
    21|4. **自动启动**：可配置开机自动启动 WSL 并运行服务，实现 24 小时在线。
    22|5. **网络互通**：WSL 内的服务可通过 localhost 或固定 IP 被 Windows 应用访问，Hermes Agent 通过 localhost:8080 连接。
    23|6. **简单安装**：通过管理员权限 PowerShell 执行一条命令即可安装 Ubuntu 24.04。
    24|
    25|## 应用场景
    26|
    27|1. **AI 服务服务器**：在 WSL 中运行 Llama-cpp 和 Hermes Agent，为本地网络提供 AI 服务。
    28|2. **开发环境**：利用 Linux 生态的命令行工具进行模型下载、编译和调试。
    29|3. **跨平台实验**：在 Windows 机器上测试原本需要 Linux 环境的 AI 框架。
    30|
    31|## 关系网络
    32|
    33|- [[llama-cpp]]：在 WSL 环境中编译和运行 Llama-cpp。
    34|- [[qwen-3-6]]：模型文件存储在 WSL 文件系统中，通过 Llama-cpp 加载。
    35|- Hermes Agent：Hermes Agent 也运行在 WSL 中，通过 localhost 调用 Llama-cpp。
    36|- [[telegram-bot]]：Telegram Bot 通过公共网络访问 WSL 内运行的 Agent。
    37|
    38|## 关键事件/里程碑
    39|
    40|- WSL 2 发布后支持 GPU，使得 Windows 成为可行的 AI 部署平台。
    41|
    42|## 出现的视频来源
    43|
    44|- [[Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报]]
    45|