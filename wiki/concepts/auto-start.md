     1|---
     2|title: 开机自启动
     3|type: concept
     4|tags: [automation, startup, service, agent, deployment]
     5|summary: 开机自启动指配置系统在启动时自动运行 AI 服务（如 Llama-cpp 和 Hermes Agent），确保 24 小时在线的可用性。
     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|created: 2026-05-09
     8|updated: 2026-05-09
     9|layer: L1
    10|confidence: high
    11|reasoning: 视频明确提到了创建开机自启动脚本。
    12|---
    13|
    14|## 定义
    15|
    16|开机自启动（Auto-start）是指在计算机操作系统启动时自动执行特定脚本或服务，无需用户手动登录或操作。在本方案中，通过配置 WSL 的自动启动和应用级计划任务，使 Hermes Agent 和 Llama-cpp 在 Windows 开机后立即运行，实现 24 小时不间断的 AI 服务。
    17|
    18|## 在本库的具体例子
    19|
    20|在 [[Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报]] 中，建议创建 Windows 计划任务（Task Scheduler）或 WSL 的 `/etc/rc.local` 脚本，在开机时自动执行以下命令：启动 WSL、进入 Hermes Agent 目录、运行 `hermes run`。同时 Llama-cpp 也通过类似方式启动。最终用户可在外出时通过 Telegram 调用始终在线的 AI 助手。
    21|
    22|## 技术实现细节
    23|
    24|常见做法包括：
    25|- Windows 任务计划程序创建一个"触发器为开机"的任务，执行 `wsl -d Ubuntu -- bash -c "cd /path/hermes && nohup hermes run &"`，确保子系统中 Agent 持续运行。
    26|- WSL 的 `/etc/rc.local` 中添加启动命令，包括 Llama-cpp 服务启动和 Hermes Agent 的初始化。
    27|- 结合 systemd 或 tmux/screen 会话管理，实现服务崩溃后自动重启。
    28|- 日志重定向到文件，方便排查启动失败原因。
    29|
    30|## 与近似概念的边界
    31|
    32|区别于 Docker 的 restart policy（容器自动重启）或 systemd 的 unit 管理，Windows 计划任务是在操作系统层面触发 Linux 子系统的启动；而 WSL 内的服务管理则需要依赖 Linux 内的启动机制。两者层次不同但共同构成完整的开机自启动方案。
    33|
    34|## 关联概念
    35|
    36|- [[remote-telegram-control]]（自启动确保 Bot 24 小时在线）
    37|    38|
    39|## 关联实体
    40|
    41|    42|- [[wsl]]
    43|- [[llama-cpp]]
    44|