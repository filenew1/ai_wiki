# 1. Multi-Agent-GPT
   - Github (110 stars): https://github.com/YangXuanyi/Multi-Agent-GPT
   - 基本功能
     - 单轮/多轮聊天
     - 多模态信息展示与交互
     - Age
     - 工具
       - Web searching  
       - Image generation
       - Image caption
       - audio-to-text
       - text-to-audio
       - Video caption
     - RAG 
       - 私有数据库
       - 离线部署

# 2. Qwen-Agent
   - Github (1.4k stars): https://github.com/QwenLM/Qwen-Agent
   - built upon Qwen1.5, featuring Function Calling, Code Interpreter, RAG, and Chrome extension.

# 3. OpenAGI

github:https://github.com/agiresearch/OpenAGI

OpenAGI是一个前沿的开源人工通用智能（AGI）研究平台，巧妙地将专业化小模型与高级学习机制相结合，致力于执行并优化特定的高级任务，如情感分析和图像去模糊化。该平台代表了AI研究的最新进展，通过精心设计的系统架构来提升智能任务的处理质量。

主要特征:
- 专家模型集成: OpenAGI结合了针对特定任务的精细化专家模型，从而针对每个任务提供最合适的解决方案。
- 强化学习的应用: 平台采用了基于任务反馈的强化学习（RLTF）方法，此举让模型通过持续学习提高其性能。
- 动态工具选择: 根据任务需求的上下文，OpenAGI可以动态地选取最适合的工具，包括但不限于ChatGPT、LLaMa2等大型语言模型（LLM），以及其他专业模型。

运作机制:
- 在OpenAGI平台上，每项任务开始时，系统首先评估其性质和需求。
- 接着，它从汇聚的专家模型库中选取一个或多个适合解决该问题的模型。
- 任务执行过程中，强化学习机制基于任务反馈不断迭代和调整模型输出，确保输出质量逐步提升。

OpenAGI的多模型和学习方法之融合，不仅为特定AI任务提供了精准的解决方案，还在持续学习和自我改进的过程中，为实现更高阶的智能任务处理设置了新的标准。这个平台展现了开源AGI研究的动力和可能性，是探索未来人工智能潜力的有力工具。

# 4. TaskWeaver

github：https://github.com/microsoft/TaskWeaver

TaskWeaver是一个专为构建大型语言模型（LLM）驱动的自主代理而设计的先进框架，这一架构深刻理解代码的重要性，并以代码作为连接用户需求和功能实现的关键。它具备将用户的复杂请求有效转化为可执行代码的能力，并在这个过程中创新性地将用户定义的插件作为函数进行动态调用。

核心特性:
- 代码转换: 通过LLM，TaskWeaver可以将用户请求转换成高效的执行代码，把纯文字描述的功能需求实体化为程序命令。
- 丰富的数据结构: 框架支持多样化的数据结构，为不同类型的任务提供强大的数据处理能力。
- 插件系统: 用户定义的插件可以轻松集成，成为执行任务时可调用的模块，极大地提升了框架的适用性和灵活性。
- 动态插件选择: 根据任务的需求，框架能动态地选择合适的插件，确保任务执行的优化和个性化。
- LLM编码能力: 利用大型语言模型处理复杂逻辑，编写符合逻辑的严谨代码。
- 集成领域知识: TaskWeaver集成了特定领域的知识示例，这使得它能够对特专业领域进行更加细致的编程。
- 安全执行保障: 平台确保所有生成的代码都在一个安全的环境中执行，避免安全隐患。

TaskWeaver的开发哲学是代码至上。通过允许用户以最直观的方式定义功能需求，并将其转化为精确的代码，这个框架打通了用户意图与软件功能间的直接通路。

TaskWeaver对大型语言模型的编码实力和领域知识的综合应用，确保了在执行用户请求的同时，能够维持代码的结构性和安全性，从而为自主AI代理的构建提供了一个强大且可靠的解决方案。

# 5. MetaGPT

github：https://github.com/geekan/MetaGPT

MetaGPT是一个先进的开源AI代理框架，它巧妙地模拟了传统软件公司的操作架构。该框架通过将GPT代理分配到不同角色—产品经理、项目经理和工程师—推动他们协同工作，解决用户定义的编程难题。

主要特征和优势:
- 模拟专业角色: MetaGPT赋予代理特定的开发团队角色，确保每个步骤都能得到专业处理。
- 中等难度任务处理: 目前MetaGPT擅长执行中等难度的任务，比如编程经典的贪吃蛇游戏或创建基本的实用程序。
- 成本效益: 使用OpenAI的API，集成MetaGPT生成一个完整项目的费用非常合理，大约为2美元。

MetaGPT通过为GPT分配不同的职能角色，从产品经理到架构师，再到项目经理和工程师，形成一个高效协作的实体。这种多代理框架不仅重现了通常由软件公司提供的所有标准操作流程，还使这些流程可访问并容易操控。

实现流程:
- 实现用户需求: 仅需简单的需求描述输入，MetaGPT就能够自动生成用户故事、进行竞争分析、明确需求、设计数据结构和API等各个开发阶段的必需品。
- 发展潜力: 虽然目前主要集中在中等复杂度任务，但MetaGPT所展示的潜力预示着它可能会迅速发展，并最终处理更复杂的编程挑战。
- MetaGPT呈现了开源AI技术如何仿照传统软件开发流程，带来效率和成本优势，为广大开发者和企业提供了一个有前途的工具，用于在未来的软件开发中实现节约成本、提高效率的目标。

# 6. AutoGen

github: https://github.com/microsoft/autogen

创新的开源代理工具AutoGPT由托兰·布鲁斯·理查兹创建，自2023年3月发布后就广受欢迎。它被设计为一款强大的工具包，旨在帮助用户构建和运行自定义的AI代理，以适应各式各样的项目需求。

实用性与便捷性

- 多功能性: 平台允许用户仅通过输入目标或任务，便可自能力主生成缘分解为一系列子任务，具备执行如网站创建、社交媒体内容生产、电子邮件撰写至营销副本等多项任务的能力。
- 语言能力: 它甚至可以胜任翻译工作，展现AI语言模型的多语种威力。

AutoGPT并不仅仅是技术的集合，它巧妙地将AI技术融入人们的工作和项目中，提供解决方案，加速任务执行进程，极大提高效率。未来，AutoGPT旨在引领个人和企业更便捷地进入智能化时代，创新工作模式，开启智能代理和人类协作的新篇章

# 7. SuperAGI

github：https://github.com/TransformerOptimus/SuperAGI

SuperAGI，一个比AutoGPT更灵活和用户友好的开源AI代理平台，被设计成一个全能发射台，它包含了搭建、维护和运行个性化AI代理所需的全部元素。通过其独有的云环境，用户得以在云端测试和优化各式功能，增强了实用性和可访问性。

核心特征和优势:
- 易用性: SuperAGI的图形用户界面（GUI）让开发和管理代理更直观、简便。
- 技术支持: 多个人工智能模型与向量数据库的融合为数据存储和检索带来革新。
- 洞察力: 性能洞察工具提供有助于优化AI代理性能的关键数据。
- 扩展性: 通过插件市场连接至广泛的应用程序和服务，例如Google Analytics，扩充了代理的功能性。

此外，SuperAGI极大丰富了自主AI代理的运行环境。通过动作控制台，开发者可以轻松管理多个代理，输入指令和配置权限变得前所未有的简单。用户还能通过代理活动页面实时监测AI的行动，从而确保所有操作都在预期的轨迹上顺利进行。

从任务管理到数据收集，再到内容生成和代码编写，乃至更为专业化的领域分析，SuperAGI携其独特的特性和功能，展现了在挑选适合特定项目需求的解决方案时所能考虑的多元化选择。

SuperAGI不仅仅带来AI技术的革新，它为手头的项目加速，为特定的挑战找到解决的途径，最终为用户打开进入高效、智能化工作流程的大门。

# 8. Transformers 智能体 2.0

https://huggingface.co/docs/transformers/v4.41.2/pipeline_tutorial

⇒ 🎁 在现有智能体类型的基础上，我们新增了两种能够 根据历史观察解决复杂任务的智能体。

⇒ 💡 我们致力于让代码 清晰、模块化，并确保最终提示和工具等通用属性透明化。

⇒ 🤝 我们加入了 分享功能，以促进社区智能体的发展。

⇒ 💪 全新的智能体框架性能卓越，使得 Llama-3-70B-Instruct 智能体在 GAIA 排行榜上超越了基于 GPT-4 的智能体！

# 9. OpenAI Swarm

https://github.com/openai/swarm

Swarm：用于构建、协调和部署多智能体（multi-agent）系统的框架，由OpenAI Solutions团队管理。Swarm是一个符合工效（ergonomic）、轻量级的多智能体协调框架。

# 10. Agno

Github (18.9k stars): https://github.com/agno-agi/agno
- 快得离谱：创建智能体只要2微秒（0.000002秒），比LangGraph快10000倍
- 百变金刚：支持文本/图片/音频/视频全模态处理
- 自由组合：不用绑定特定AI模型，想用GPT-4还是Claude随你换
- 团队作战：能同时指挥多个智能体协作，像复仇者联盟一样分工配合

# 11. Smolagents

Github (11.6k stars): https://github.com/huggingface/smolagents

huggingface.co/docs/smolagents

huggingface出品

轻量级设计

整个核心逻辑才1000行代码，却并不影响功能的完整性。

轻松接入OpenAI、Anthropic等其他任何LLM。

配合HuggingFace Hub的工具生态，有无限扩展能力。

Code Agent机制

不同于传统的工具调用方式，它让AI直接通过代码来执行动作。

这种方式能减少30%的模型调用，性能还更好。

考虑到代码执行的安全问题，还提供了安全解释器和沙盒环境。

帮助处理琐碎但重要的底层工作

比如代码格式的统一性、解析器的配置等

可以用全套框架，也可以只取需要的部分来用

# 12. Owl

Github (9.3 stars): https://github.com/camel-ai/owl

OWL: Optimized Workforce Learning for General Multi-Agent Assistance in Real-World Task Automation

🏆 OWL achieves 58.18 average score on GAIA benchmark and ranks 🏅️ #1 among open-source frameworks! 🏆

![](.01_Github开源项目_images/owl架构图.png)

# 13. OpenAI Agent框架

发布事件：2025-03-13

- Agents Blog: https://openai.com/index/new-tools-for-building-agents
- Built-in tools: https://platform.openai.com/docs/guides/tools?api-mode=responses
- Responses API: https://platform.openai.com/docs/api-reference/responses
- Agents SDK项目：https://github.com/openai/openai-agents-python
- Computer Using Agent项目：https://github.com/openai/openai-cua-sample-app

- 内置工具（Built-in tools）：包括网页搜索、文件搜索以及电脑使用（Computer Use）
- Responses API ：新的响应API，将 Chat Completions API 的简单性与 Assistants API 的工具使用功能相结合，用于构建Agents
- Agents SDK：协调Single-Agent和Multi-Agent工作流程
- 监控工具：集成可观察性工具跟踪和检查Agent工作流程的执行情况

其中：Agents SDK是开源的，并且还开源了一个Computer Using Agent项目

# 14. Rowboat

Github (1.4k stars): https://github.com/rowboatlabs/rowboat.git

🔥 Rowboat 三大核心优势
1. 🚀 AI Copilot 自动生成工作流
• 只需输入需求（如“搭建一个外卖公司客服助手，处理订单状态和缺货问题”），Rowboat 自动生成多智能体协作逻辑，省去手动编排时间。
2. 🧩 模块化工具集成（MCP 协议）
• 支持连接 MCP 服务器，轻松导入外部工具（如天气查询、数据库操作），让智能体具备真实业务能力。
3. ⚡ 一键部署，无缝集成
• 提供 HTTP API 和 Python SDK，5 行代码即可嵌入现有系统，支持企业级高并发调用。

# 15. AutoAgent

登顶GAIA全球评测，成本直降50%碾压商业巨头

AutoAgent是将智能体开发过程从传统的编程模式转变为一种自然语言驱动的自动化过程。
- 通过模拟现代计算机操作系统的工作方式，将复杂的智能体开发任务分解为多个模块化的组件
- 通过自然语言接口实现这些组件之间的交互和协调。

https://arxiv.org/pdf/2502.05957

https://github.com/HKUDS/AutoAgent

# 16. RDAgent

https://arxiv.org/pdf/2404.11276

https://arxiv.org/pdf/2407.18690

https://github.com/microsoft/RD-Agent

https://rdagent.readthedocs.io/en/latest/introduction.html

推出RDAgent的目的在于：打造一个工业研发过程的自动化助手，专注于数据驱动场景，通过提出新想法和实施它们来简化模型和数据的开发。

RDAgent由两个关键部分组成：

- （R）esearch代表通过提出新想法积极探索，
- （D）evelopment代表实现这些想法。


在数据挖掘过程中，可以将数据驱动分解成以下动作：

- 首先，提出一个idea假设。例如，像RNN这样的模型结构可以捕获时间序列数据中的模式
- 然后，将idea变成可操作的实验。例如：挖掘金融数据包含时间序列模型
- 第三，搜索与实验相关的数据，将实验实现为代码。例如：pytorch代码
- 最后，执行代码以获得数据反馈。例如：指标、损失曲线等

通过上述步骤，数据挖掘专家能从反馈中学习，并在下一次迭代中改进

# 17. Chat2Graph

作为首个全面践行「图原生」理念的智能体系统，Chat2Graph 开源并发布了首个可用版本（v0.1.0）(链接：https://github.com/TuGraph-family/chat2graph/releases/tag/v0.1.0)

关注仓库：https://github.com/TuGraph-family/chat2graph

项目文档：https://chat2graph.vercel.app/

![](.01_Github开源项目_images/chat2graph.png)

系统的核心组件有：

- 图系统层：构建了面向图系统的统一抽象，使用图数据库服务统一管理，并支持未来更多图计算系统的扩展。
- AI 系统层：构建 AI 基础设施抽象，如智能体框架、RAG、记忆工具、模型服务工具等，提供智能体能力基建和生态扩展。
- 存储服务层：存储智能体的持久化数据，包括元数据、记忆、知识、文件等。
- 推理机：提供 LLM 服务封装、推理增强、工具调用等基础能力。
- 工作流：负责智能体内部的算子（Operator）编排与SOP抽象，定义智能体工作流程。
- 记忆系统：构建分层的知识精练体系，负责智能体系统的信息存储、检索，包括记忆管理、知识库、环境等。
- 工具库：基于图谱的方式描述工具和智能体行动的关联关系，实现工具的自动化管理和推荐。
- 智能体：智能体系统执行单元的统一抽象，使用角色定义（Profile）描述工作职责，使用工作流描述工作流程。主要包括 Leader 智能体和 Expert 智能体两大类型。
- 自动化：系统智能体化能力的抽象，「Less Structure」理念的实践手段。包括自动的任务规划、工作流生成、工具库优化、知识精练、资源调度等能力。
- 系统集成：提供 Web UI、Restful API、SDK 的集成方式，通过 YAML 一键配置智能体系统，方便开发者快速接入 Chat2Graph 的能力。

协作当前更多的还是强调多个智能体之间的互动，处理任务、资源的动态分配和调度。不论是采用「单主动-多被动」的统一 Leader 协调方式，还是多个 Expert 自由通信的自主方式。亦或采用单进程的串行处理，还是使用远程通信的并发处理。多智能体系统的协作机制都要处理以下几个关键问题：

- 任务分配：将拆分好的子任务合理地分配到对应的智能体执行。
- 执行容错：任务执行结果的评估与反思，并能通过重试自动恢复。
- 重新规划：对不合理的任务拆分的容错能力，能适时的请求重新规划流程。
- 结果交付：能通过合理的协作，对任务产出物生成、加工、优化，交付预期结果。
- 资源调度：通过调度优化资源的使用，降低时间、空间、Token 开销，提升质量。

![](.01_Github开源项目_images/写作.png)

相比 Workflow 的「静态」属性多一些，更侧重规范化流程，JobGraph 的「动态」属性则多一些，更侧重任务的灵活性以及能力扩展。尤其是类似 A2A 协议定义了智能体交互的规范，更需要良好的协作机制，通过引入更开放的生态，扩展系统边界，提升解题能力。

**记忆系统**

Chat2Graph 借鉴了 DIKW （链接：https://en.wikipedia.org/wiki/DIKW_pyramid）金字塔模型，从信息的内容角度出发将记忆划分为四层结构。

![](.01_Github开源项目_images/分层记忆.png)

分层记忆系统引入的多级信息抽象，允许我们能从更精细的粒度对知识进行管理。

- 知识精练（Knowledge Refinement）：原始知识经过逐级的处理、分析、抽象、压缩，形成更高层次的知识，扩展知识生产的能力。
- 知识下钻（Knowledge Drilling）：在使用高维知识的同时，还可以按需下钻低维知识，让推理上下文粗中有细，强化知识消费的能力。
- 知识延拓（Knowledge Expansion）：表示同层级知识关联的构建和召回，通过特定方法丰富知识上下文。典型代表是 RAG（检索增强生成）。

![](.01_Github开源项目_images/知识层级.png)

最新的 G-Memory （链接：https://arxiv.org/abs/2506.07398）的研究与我们的分层记忆系统的理念不谋而合，它设计了三层图结构来管理记忆：

- 交互图（Interaction Graph）：存储细粒度的智能体间的通信日志，提供事实依据。
- 查询图（Query Graph）：记录任务节点（含状态）以及语义相似或关联的任务关系，并与交互图链接。
- 洞见图（Insight Graph）：存储从多次成功或失败的交互中提炼出的、具有普适性的经验和教训。

我们甚至可以通过一个 YAML （链接：https://github.com/TuGraph-family/chat2graph/blob/master/app/core/sdk/chat2graph.yml）文件完整的描述多智能体系统的能力，而不需要复杂的硬编码。

![](.01_Github开源项目_images/配置文件.png)

![](.01_Github开源项目_images/架构.png)

我们认为，「推理」、「记忆」、「工具」是对 AI 工程三大基石「模型」、「数据」、「计算」的工程化表达，同时「规划 & 协作」、「知识 & 环境」、「行动 & 战略」是对「推理」、「记忆」、「工具」的进一步抽象，而它们都可以使用 Graph 统一表达，分别对应「任务图谱」、「知识图谱」、「工具图谱」，甚至在未来这三张 Graph 还可以进一步融合，这便是我们对「Graph for AI 软件工程」的整体理解。

![](.01_Github开源项目_images/智能体生成.png)

![](.01_Github开源项目_images/chat2graph架构1.png)

# 18. CWIC Flow

与传统聊天机器人解决方案不同，CWIC Flow 协调多个专业智能体——这些智能体具备工具、技能和记忆能力——为客户提供高度上下文化和可操作的洞察。这一架构上的飞跃使 Clearwater 在行业广泛采用此类范式之前就处于领先地位，展示了一个 Multi-Agent 人工智能系统。

# 参考

[1] Multi-Agent-GPT: 一款基于RAG和agent构建的多模态专家助手GPT，https://mp.weixin.qq.com/s/C3ZnnxzmGqF8lXir9B9-BQ
[2] 5个顶级开源Agent框架，你必须知道！，https://mp.weixin.qq.com/s/zf_BSlcmTgNKLbVu8Tq8Qg
[3] 授权调用: 介绍 Transformers 智能体 2.0, https://mp.weixin.qq.com/s/C2Yd3tBUTdSPEOcdhcr0TQ
[4] 18.9K 星推荐！这个 Python 库让开发 AI 智能体像搭积木一样简单, https://mp.weixin.qq.com/s/Vk238RASp9ULnDDYMerRew
[5] 3.4K Star 港大开源AutoAgent登顶GAIA全球评测，成本直降50%碾压商业巨头, https://mp.weixin.qq.com/s?__biz=MzkzNjgwNzMwNQ==&mid=2247485549&idx=1&sn=ff87c3ba29b538a37b73d3fa9848acac&scene=21#wechat_redirect
[6] 微软发布：工业级Agent落地方案RDAgent, https://mp.weixin.qq.com/s?__biz=MzkzNjgwNzMwNQ==&mid=2247484346&idx=1&sn=c55cab4835761d9f6589f2b067c0284a&scene=21#wechat_redirect
[7] 技术前沿之Graph+Agent：Chat2Graph如何重构GraphRAG范式？https://mp.weixin.qq.com/s/TKev6oPft5I1VOlXqHwONQ