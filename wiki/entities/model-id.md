---
```yaml
title: Model ID
type: entity
tags:
  - 配置
  - 模型
  - 赫美斯 Agent
summary: Model ID是用于标识和配置[[赫美斯 Agent (Hermes Agent)]]所使用的具体[[模型]]的唯一标识符。它在系统配置中扮演关键角色，尤其是在集成Ollama等云端模型服务时，使用户能够灵活选择和管理不同的AI模型，以实现特定的功能和优化性能。
sources:
  - raw/notebooklm-analysis/赫美斯-Agent-Hermes-Agent-高级应用与部署简报.md
created: 2023-10-27T10:00:00Z
updated: 2023-10-27T10:00:00Z
layer: L1
confidence: high
reasoning: 根据来源报告中提及的“Ollama 云端模型”、“主副模型架构配置”以及其他配置项（如API service、API password等），推断Model ID是用于指定和管理赫美斯 Agent所调用具体AI模型的关键配置参数。虽然报告节选未直接定义Model ID，但其作为配置项的存在是合理的推断。
```

**实体描述**
Model ID（模型ID）是用于唯一标识和指定[[赫美斯 Agent (Hermes Agent)]]在运行过程中所调用的具体人工智能模型的参数。在复杂的AI应用部署中，尤其是在需要集成多个模型或在不同场景下切换模型时，Model ID发挥着核心作用。它允许开发者或用户精确地选择和配置所需的模型，例如指定使用Ollama提供的特定云端模型，或者在“主副模型架构”中区分主模型和辅助模型。通过Model ID，系统能够加载正确的模型权重、配置参数和API接口，确保Agent能够执行预期的任务。这种机制极大地增强了[[赫美斯 Agent (Hermes Agent)]]的灵活性和可扩展性，使其能够适应不同的计算资源、成本预算和性能要求。例如，用户可以通过修改Model ID来切换到更轻量级的模型以降低资源消耗，或切换到更强大的模型以提升任务处理能力。在实际部署中，Model ID通常会在配置文件（如[[config.toml]]）或通过环境变量进行设置，是实现Agent个性化和高效运行的关键。

**在本视频中的角色**
在《[[赫美斯 Agent (Hermes Agent) 高级应用与部署简报]]》中，Model ID虽然未被直接定义，但其作为核心配置参数，是实现报告中提及的“Ollama 云端免部署方案”和“主副模型架构配置”的关键基础。报告强调了赫美斯 Agent 如何利用Ollama云端模型实现零成本上手，这暗示了用户需要通过某种方式（即Model ID）来指定和调用这些云端模型。同样，“通过主副模型架构配置大幅度降低 Token 消耗”的策略也离不开Model ID，因为它允许用户为不同的角色（主模型、副模型）配置不同的AI模型。因此，Model ID在本简报中扮演着连接[[赫美斯 Agent (Hermes Agent)]]的[[高级功能]]与底层AI模型服务的桥梁，是实现灵活部署、优化性能和降低成本不可或缺的配置项。
```