     1|---
     2|title: "Qwen3.6"
     3|type: entity
     4|tags: [llm, open-source, alibaba, qwen, local-deployment]
     5|summary: "阿里通义千问系列开源大语言模型，提供 0.8B 到 27B 多种规格，是 Hermes Agent 推荐的本地推理搭配模型。"
     6|sources:
     7|  - raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-部署与应用简报.md
     8|created: 2026-05-09
     9|updated: 2026-05-09
    10|layer: L1
    11|section: entities
    12|---
    13|
    14|# Qwen3.6
    15|
    16|## 基本定位
    17|阿里通义千问（Qwen）系列最新开源大语言模型，提供从 0.8B 到 27B 的完整规格谱系，在中文理解和逻辑推理方面已跨过实用化门槛，是 Hermes Agent 的推荐搭配底层模型。
    18|
    19|## 核心特征/能力
    20|
    21|1. **多种规格选择**: 提供 0.8B、2B、4B、9B、27B 等规格，覆盖 4G 到 24G+ 显存场景
    22|2. **推理性能**: 27B 在 24G 显存上可达 39.51 tokens/s（未优化），优化后预期 50-60 tokens/s
    23|3. **高性价比**: 在编程、自动化等非极致复杂场景下，可替代收费 API 模型
    24|4. **中文优化**: 中文理解和生成能力成熟，适合本地部署的国产模型方案
    25|
    26|## 关系网络
    27|- [[hermes-agent]] — 推荐的搭配 AI Agent 框架
    28|- [[llama-cpp]] — 推荐的本地推理引擎
    29|- [[wsl]] — 推荐的运行环境（Windows WSL2）
    30|
    31|## 出现的视频来源
    32|- [[Hermes 与 Qwen3.6 本地 AI Agent 部署与应用简报]]
    33|