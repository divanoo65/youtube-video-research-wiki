     1|     1|---
     2|     2|title: 深度思考模式
     3|     3|type: concept
     4|     4|tags: [model-inference, optimization, deep-think, agent]
     5|     5|summary: 深度思考模式是大语言模型的一种推理模式，允许模型进行更深入的计算以获得更准确的答案，但会增加延迟；可在快速任务中关闭以提升速度。
     6|     6|sources: [raw/notebooklm-analysis/Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报.md]
     7|     7|created: 2026-05-09
     8|     8|updated: 2026-05-09
     9|     9|layer: L1
    10|    10|confidence: high
    11|    11|reasoning: 从视频中直接描述的模式调整功能。
    12|    12|---
    13|    13|
    14|    14|## 定义
    15|    15|
    16|    16|深度思考模式（Deep Think Mode）是某些大语言模型（如 Qwen 3.6）提供的一种推理配置，在开启时会分配更多计算资源进行多步推理和验证，生成的答案通常更准确但速度较慢。关闭后模型直接输出结果，响应速度显著提升。
    17|    17|
    18|    18|## 在本库的具体例子
    19|    19|
    20|    20|在 [[Hermes-Qwen-3-6-本地最强-Agent-组合部署与应用简报]] 中，推荐关闭 Qwen 3.6 27B 的深度思考模式以提升 Agent 任务响应速度。具体命令实现（例如通过 Llama-cpp 启动参数 `--no-deep-think` 或模型配置文件中的 `deep_think: false`）。在 Hermes Agent 中，可通过 model 配置选项控制此模式。
    21|    21|
    22|    22|## 技术实现细节
    23|    23|
    24|    24|深度思考模式通常在模型内部通过增加 Transformer 层循环或使用 beam search 等采样策略实现。Qwen 3.6 通过 `deep_think` 参数控制，设置为 `true` 时模型会进行多次前向传播并选择最优输出；关闭后则单次生成。在 Llama-cpp 中，启动时设置 `-dt` 或使用 `--no-deep-think` 可禁用。
    25|    25|
    26|    26|## 与近似概念的边界
    27|    27|
    28|    28|与"beam search"、"temperature"等采样参数不同，深度思考是模型层面的多步推理策略，而非后处理；与"思维链"（Chain-of-Thought）提示不同，它不需要用户提供提示，而是模型内置的推理增强。关闭深度思考等同于使用模型的默认单步推理，但首字延迟显著降低。
    29|    29|
    30|    30|## 关联概念
    31|    31|
    32|    32|    33|- [[model-compilation-optimization]]（编译优化与模式调整共同提升性能）
    33|    34|
    34|    35|## 关联实体
    35|    36|
    36|    37|- [[qwen-3-6]]
    37|    38|- [[llama-cpp]] — 通过 Llama-cpp 的参数控制使用深度思考模式
    38|    39|