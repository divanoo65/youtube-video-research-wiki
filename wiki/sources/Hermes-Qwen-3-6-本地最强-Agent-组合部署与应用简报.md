     1|---
     2|title: Hermes + Qwen 3.6 本地最强 Agent 组合部署与应用简报
     3|type: source
     4|tags: [hermes-agent, qwen, local-deployment, agent, llm]
     5|summary: 本视频详细介绍了基于 Hermes Agent 与 Qwen 3.6 大语言模型的本地化 AI 部署方案，实现零成本、隐私安全的 24 小时在线 AI 助手。
     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|created: 2026-05-09
     8|updated: 2026-05-09
     9|layer: L1
    10|video_url: https://youtu.be/Kh8tGD5liwo?si=5iFozTq5MXJrT2Qh
    11|mindmap: raw/notebooklm-mindmaps/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.json
    12|---
    13|
    14|## 执行摘要
    15|
    16|基于 Hermes Agent 与 Qwen 3.6 的本地部署方案实现了零月费、完全隐私安全的 AI 助手。通过 WSL 环境集成 Llama-cpp 和 Qwen 系列模型，配合 Hermes Agent 的自动化能力，构建了 24 小时在线的 AI 服务。该方案支持手机远程控制，适用于代码编写、自动化任务等场景。部署流程包括环境准备、模型部署、Agent 安装和远程访问配置。
    17|
    18|## 核心要点
    19|
    20|1. **后端选择**：Llama-cpp 作为推理后端，相比 VLLM 或 DeepSpeed 更稳定，可有效防止爆显存，适应不同硬件配置。
    21|2. **模型选择**：推荐 Qwen 3.6 27B（需 24G 显存）或 Qwen 3.5 0.8B-9B（小显存），可关闭"深度思考模式"提升响应速度。
    22|3. **环境构建**：基于 Windows 子系统 WSL (Ubuntu 24.04)，需安装最新 NVIDIA 驱动和 CUDA 工具包。
    23|4. **Agent 安装**：执行一键安装脚本，配置自定义模式、Base URL 和 API Key（随机填写）。
    24|5. **远程访问**：通过 Telegram Bot（BotFather 创建）实现手机远程控制，需获取 TOKEN 并绑定 Telegram ID。
    25|6. **系统优化**：配置开机自启动脚本，确保断电重启后自动恢复服务；支持主题设置和性能调优。
    26|7. **性能表现**：27B 模型在录屏状态下约 40 Tokens/s，优化后可达 50-60 Tokens/s。
    27|8. **应用场景**：编写 Web 应用（如 PHP+数据库的中转站）、定时任务执行、日常对话等。
    28|9. **数据隐私**：所有数据本地处理，不联网，确保完全隐私安全。
    29|
    30|## 关键引言
    31|
    32|> "零月费，数据隐私安全完全掌握在自己手里。" — 强调本地部署相对于云端模型的核心优势。
    33|> "它就是你 24 小时在线的 AI 助手，百分百本地部署，完全免费开源。" — 描述方案的自动化和长期可用性。
    34|> "本地模型已经足够使用了。" — 指出本地模型性能已达到日常使用的临界点。
    35|> "这才是很多人真正需要的 AI Agent，完全可控，本地离线使用，再也不用去购买 Token。" — 总结通过 Telegram 远程调用的最终形态。
    36|
    37|## 脑图核心节点
    38|
    39|从脑图数据提取的一级节点：
    40|- 方案优势（零成本、隐私安全、本地部署、24小时在线）
    41|- 环境准备（WSL Ubuntu 24.04、NVIDIA驱动更新、Python与Pip、CUDA工具包）
    42|- 模型部署 (Llama-cpp)（选择模型、模型编译与路径设置、启动服务8080端口、模式调整关闭深度思考）
    43|- Hermes Agent安装（一键安装脚本、配置过程：自定义模式、Base URL、API KEY）
    44|- 远程访问 (Telegram接入)（BotFather创建机器人、获取并配置TOKEN、绑定Telegram ID）
    45|- 系统优化（开机自启动脚本、Linux子系统自动运行、主题设置）
    46|- 应用场景（代码编写、自动化任务、定时任务执行、手机远程对话）
    47|
    48|## 关联实体
    49|
    50|    51|- [[qwen-3-6]]
    52|- [[llama-cpp]]
    53|- [[wsl]]
    54|- [[telegram-bot]]
    55|
    56|## 关联概念
    57|
    58|- [[deep-think-mode]]
    59|- [[model-compilation-optimization]]
    60|- [[remote-telegram-control]]
    61|- [[auto-start]]
    62|    63|