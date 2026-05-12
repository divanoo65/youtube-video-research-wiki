# YouTube Video Research Wiki
Last updated: 2026-05-12
Total pages: 26

## Sources
- [[hermes-agent-advanced-guide|Hermes Agent 高级玩法与优化指南]] — 本指南基于AI超元域视频教程，详细介绍了Hermes Agent（赫美斯）的稳定性优势、通过Ollama集成云端免费模型、使用Open WebUI美化交互界面，以及通过主副模型策略节省Token成本的方法。
- [[llm-wiki-guide|LLM-Wiki（小Wiki）：基于大模型的个人知识库构建指南]] — 安德烈·卡帕西提出的LLM-Wiki方法，将大模型从“解释器”转向“编译器”，通过三层架构和闭环工作流实现知识的复利增长，解决传统RAG的信息孤岛问题。

## Entities
- [[andrej-karpathy|Andrej Karpathy]] — 知名人工智能专家，LLM-Wiki（小Wiki）思想的首倡者，倡导将大模型从“解释器”转变为“编译器”以构建个人知识库。
- [[claude|Claude]] — Claude 是 Anthropic 开发的对话式 AI 助手，在个人知识库构建系统中作为可选的大模型后端，负责文本生成、分类与摘要等任务。
- [[dataview|Dataview]] — Dataview 是 Obsidian 的一款社区插件，允许用户通过类 SQL 查询语言（DQL）或 JavaScript 对笔记库中的元数据进行筛选、聚合和展示，是实现知识库动态查看与回填的核心工具。
- [[deepseek|DeepSeek]] — DeepSeek 是一个由深度求索公司开发的大语言模型，通过 API 接入，作为 LLM-Wiki 知识库构建流程中的可选后端引擎之一，与 Claude 并列，提供文本生成、摘要、分类等核心能力。
- [[gemini-1-5-flash|Gemini 1.5 Flash]] — Gemini 1.5 Flash 是 Google 推出的轻量级高速语言模型，在 Hermes Agent 体系中被用作副模型，专门承担批准、压缩、记忆刷新、工具调用和视觉处理等辅助任务，以节省 Token 并提升系统整体效率。
- [[graph-view|Graph View]] — Graph View 是 Obsidian 中的核心功能插件，用于将笔记间的双向链接关系可视化为节点与边的网络图，帮助用户直观理解知识结构。
- [[hermes-agent|Hermes Agent (赫美斯)]] — Hermes Agent 是一款开源的 AI Agent 框架，以高稳定性和易用性著称，支持通过 Ollama 集成云端免费模型，并可通过 Open WebUI 美化界面，配合主副模型策略有效节省 Token。
- [[obsidian-web-clipper|Obsidian Web Clipper]] — 一款用于从网页中快速抓取内容并保存到Obsidian的浏览器扩展，支持自定义规则和自动分类，是构建个人知识库的重要工具。
- [[obsidian|Obsidian]] — Obsidian 是一款基于 Markdown 的本地知识管理软件，以其强大的双向链接和图谱视图功能著称，常被用于构建个人知识库（如 LLM-Wiki）。
- [[ollama|Ollama]] — Ollama 是一个开源的本地大语言模型运行和管理工具，支持一键部署多种主流模型，并已原生集成 Hermes Agent，极大降低了用户的上手门槛，同时可通过云端模型免去本地资源消耗。
- [[open-webui|Open WebUI]] — Open WebUI是一个开源的、可自托管的Web界面，用于管理和交互各类AI模型，支持Ollama、OpenAI等后端。在本报告中，它作为Hermes Agent的美化与功能增强工具，显著提升了用户界面的美观度和操作便捷性。
- [[vs-code|VS Code]] — Microsoft 出品的轻量级代码编辑器，在 LLM-Wiki 知识库构建流程中作为核心开发环境，配合 Cloud Code 插件和 Python 解释器完成脚本编写与自动化处理。

## Concepts
- [[bi-directional-link|双向链接]] — 双向链接是一种在知识库中建立页面之间相互引用的机制，不仅允许从A页面跳转到B页面，也能从B页面看到被A引用的记录，从而形成非线性的知识网络。
- [[compiler-pattern|编译器模式]] — 编译器模式是LLM-Wiki从传统RAG解释器模式升级后的核心运行范式，将原始知识“编译”为结构化、高关联的Wiki页面，实现知识的指数级进化与复利效应。
- [[dialogue-compression|对话压缩]] — 对话压缩是一种在不丢失核心语义和任务目标的前提下，通过技术手段减少长对话历史所占用的Token数量，从而降低推理成本、提升响应速度并延长对话窗口可用性的策略。在Hermes Agent等智能体框架中，对话压缩与主副模型策略配合，成为高效管理Token消耗的关键手段。
- [[health-check|健康检查]] — 健康检查是 LLM-Wiki 中用于维护知识库有序性的定期自动化审计机制，通过脚本扫描并修复内容矛盾、过时信息、孤立页面和缺失引用等问题。
- [[ingestion|摄入]] — LLM-Wiki 工作流的第一步，负责将新素材（PDF、笔记等）放入原始文件夹，由大模型自动解析内容、撰写摘要并主动挖掘现有知识库中的关联，触发相关概念页面的更新，从而避免信息孤岛。
- [[interpreter-pattern|解释器模式]] — 在 LLM-Wiki 框架中，解释器模式指代传统 RAG 那种临时性、一次性的知识处理方式，每次查询从零开始，缺乏知识积累与复利效应。
- [[knowledge-compounding|知识复利]] — 知识复利是指在个人知识管理过程中，通过持续积累、关联和结构化知识，使知识增长呈现出类似金融复利的指数级效应。在 LLM-Wiki 框架下，每一次新知识的摄入和编译都会对已有知识库产生正向反馈，使得后续的知识处理效率和质量不断提升。
- [[llm-wiki|LLM-Wiki]] — LLM-Wiki（小Wiki）是由Andrej Karpathy提出的一种新型个人知识库构建范式，将大模型从“解释器”转变为“编译器”，通过三层架构实现零散信息向结构化、高关联知识资产的转化，并形成知识复利效应。
- [[primary-secondary-model-strategy|主副模型策略]] — 主副模型策略是一种通过将复杂逻辑与辅助任务分离，使用昂贵高性能模型（主模型）处理核心推理，而用廉价快速模型（副模型）完成批准、压缩、记忆刷新等辅助工作，从而显著降低Token消耗并提升系统效率的方案。
- [[query-and-refinement|查询与回填]] — 查询与回填是 LLM-Wiki 三大核心步骤之一，通过低延迟的 Markdown 索引实现快速定位，并将高质量对话结果自动回存至 Wiki 文件夹，实现知识资产的持续增值。
- [[schema|Schema]] — Schema 是 LLM-Wiki 三层架构中的第三层，作为一组可配置的规则，指导大模型如何解读、分类和处理内容，将通用模型调教为懂业务的知识管理员。
- [[three-layer-architecture|三层架构]] — LLM-Wiki 的三层架构将知识库划分为原始数据层、Wiki产物层和规则层，通过“只读不写”策略保证可追溯性，并利用大模型作为编译器实现知识的结构化与持续迭代。
