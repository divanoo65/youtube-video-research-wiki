     1|---
     2|title: "Llama-cpp"
     3|type: entity
     4|tags: [inference-engine, llama-cpp, local-llm, quantization]
     5|summary: "C/C++ 实现的高效 LLM 推理引擎，支持 GGUF 量化模型，以显存稳定性著称，适合消费级显卡本地部署。"
     6|sources:
     7|  - raw/notebooklm-analysis/Hermes-Qwen3-6-本地-AI-Agent-部署与应用简报.md
     8|created: 2026-05-09
     9|updated: 2026-05-09
    10|layer: L1
    11|section: entities
    12|---
    13|
    14|# Llama-cpp
    15|
    16|## 基本定位
    17|C/C++ 实现的高性能 LLM 推理引擎，支持 GGUF 格式量化模型。在本地部署场景中选择 Llama-cpp 而非 vLLM 或 DeepSpeed，核心考量是为防止显存溢出（OOM），更适合消费级显卡的多样化硬件配置。
    18|
    19|## 核心特征/能力
    20|
    21|1. **显存稳定性**: 相比 vLLM 或 DeepSpeed，Llama-cpp 在显存调度上更为保守稳定，防止 OOM
    22|2. **硬件适配**: 适合个人电脑的多样化硬件配置，从 4G 到 24G 显存均可使用
    23|3. **开源生态**: 活跃的开源社区，持续优化性能和模型支持
    24|4. **CUDA 加速**: 支持 NVIDIA CUDA 加速，在 24G 显存上可达 40-60 tokens/s
    25|
    26|## 关系网络
    27|- [[hermes-agent]] — 推荐的推理引擎组合
    28|- [[qwen3-6]] — 推荐的加载模型
    29|- NVIDIA CUDA — 依赖的硬件加速层
    30|
    31|## 出现的视频来源
    32|- [[Hermes 与 Qwen3.6 本地 AI Agent 部署与应用简报]]
    33|