     1|     1|---
     2|     2|title: 远程 Telegram 控制
     3|     3|type: concept
     4|     4|tags: [telegram, remote-access, agent, chatbot]
     5|     5|summary: 远程 Telegram 控制指通过 Telegram Bot 的 API 接口，实现对本地部署的 AI Agent 的远程消息交互和任务管理。
     6|     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|     7|created: 2026-05-09
     8|     8|updated: 2026-05-09
     9|     9|layer: L1
    10|    10|confidence: high
    11|    11|reasoning: 视频详细描述了 Telegram Bot 的创建和配置流程。
    12|    12|---
    13|    13|
    14|    14|## 定义
    15|    15|
    16|    16|远程 Telegram 控制是一种利用 Telegram Bot 作为客户端与本地 AI Agent 之间的桥梁的架构。用户通过 Telegram 消息与 Bot 对话，Bot 将消息转发给本地 Agent（如 Hermes Agent），Agent 处理后返回响应。该方式实现了随时随地通过手机控制家中或办公室的本地 AI 服务。
    17|    17|
    18|    18|## 在本库的具体例子
    19|    19|
    20|    20|在 [[Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报]] 中，步骤包括：1）在 Telegram 中搜索 BotFather，使用 `/newbot` 指令创建机器人并获取 TOKEN；2）在 Hermes Agent 配置文件中设置 `telegram_token` 和 `telegram_chat_id`（自己的 Telegram ID）；3）启动 Agent 后即可在手机端发送消息，Agent 会自动回复。该功能在 Hermes Agent 中作为内置选项提供。
    21|    21|
    22|    22|## 技术实现细节
    23|    23|
    24|    24|Telegram Bot 使用长轮询或 Webhook 接收消息。Hermes Agent 通过 Telegram 库订阅更新，解析用户消息，调用底层模型（如 Qwen 3.6）生成回答，然后通过 Bot API 返回。为确保安全，Telegram ID 需要在 Agent 配置中白名单绑定。
    25|    25|
    26|    26|## 与近似概念的边界
    27|    27|
    28|    28|区别于云端 Bot（如 ChatGPT 官方 Bot），这里 Bot 只是一个通信管道，实际模型运行在本地，数据不出网；区别于 SSH 远程登录，Telegram 控制无需端口暴露，安全性更高。
    29|    29|
    30|    30|## 关联概念
    31|    31|
    32|    32|    33|- [[auto-start]]（确保 Bot 服务始终在线）
    33|    34|
    34|    35|## 关联实体
    35|    36|
    36|    37|- [[telegram-bot]]
    37|    38|- Hermes Agent
    38|    39|- [[qwen-3-6]]
    39|    40|