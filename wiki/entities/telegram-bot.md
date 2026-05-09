     1|---
     2|title: Telegram Bot
     3|type: entity
     4|tags: [telegram, bot, remote-access, messaging]
     5|summary: Telegram Bot 是 Telegram 平台上的自动聊天机器人，用于远程控制本地 Hermes Agent，实现手机端与本地 AI 交互。
     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|created: 2026-05-09
     8|updated: 2026-05-09
     9|layer: L1
    10|---
    11|
    12|## 基本定位
    13|
    14|Telegram Bot 是通过 BotFather 创建的机器人，本方案将其作为远程调用本地 Hermes Agent 的桥梁，用户可在手机端发送消息，由本地 Agent 处理并返回结果。
    15|
    16|## 核心特征/能力
    17|
    18|1. **远程交互**：用户通过任意 Telegram 客户端（手机、桌面）发送消息，Bot 将消息转发给本地 Agent 处理。
    19|2. **BotFather 创建**：简单几步即可创建，获取 TOKEN 和 API 权限。
    20|3. **安全绑定**：通过 Telegram ID 绑定，确保只有授权用户可与 Bot 交互。
    21|4. **低延迟**：Bot 直接通过公网连接到本地 Agent 的 Telegram 接口，响应速度快。
    22|5. **集成简便**：Hermes Agent 内置 Telegram 集成功能，只需配置 TOKEN 和 ID 即可启用。
    23|6. **支持多种消息**：可发送文本、代码、图片等，Agent 能返回 Markdown 格式内容。
    24|
    25|## 应用场景
    26|
    27|1. **移动端 AI 助手**：在外出时通过手机向本地 Agent 提问，获得回答而不依赖云端。
    28|2. **定时任务管理**：通过手机远程启动或停止本地 Agent 的定时任务。
    29|3. **家庭自动化**：结合 Agent 的工具调用能力，控制智能家居设备（未来扩展）。
    30|
    31|## 关系网络
    32|
    33|- Hermes Agent：Telegram Bot 作为 Hermes Agent 的远程接口，通过配置集成。
    34|- [[qwen-3-6]]：Agent 底层使用 Qwen 3.6 模型，Telegram Bot 消息最终由该模型处理。
    35|- [[wsl]]：Agent 运行在 WSL 中，Telegram Bot 通过公网访问。
    36|
    37|## 关键事件/里程碑
    38|
    39|- BotFather 创建流程成熟，已成为 Agent 远程访问的标准方案。
    40|
    41|## 出现的视频来源
    42|
    43|- [[Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报]]
    44|