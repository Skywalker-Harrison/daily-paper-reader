---
title: "C-3PO: Compact Plug-and-Play Proxy Optimization to Achieve Human-like Retrieval-Augmented Generation"
title_zh: C-3PO：紧凑即插即用代理优化实现类人检索增强生成
authors: "Guoxin Chen, Minpeng Liao, Peiying Yu, Dingmin Wang, Zile Qiao, Chao Yang, Xin Zhao, Kai Fan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hlpwAmQ4wr"
tags: ["query:fie-rag"]
score: 6.0
evidence: RAG优化框架，多智能体通信，有潜力改进少样本RAG
tldr: C-3PO通过三个轻量级智能体协同优化检索器和LLM之间的通信，模拟人类搜索行为。该框架无需修改原组件即可提升RAG性能，适用于需要精准检索和推理的语言任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 1168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 880, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlpwamq4wr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1784, \"height\": 965, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 933, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1577, \"height\": 894, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1577, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1047, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 618, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlpwamq4wr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 633, \"height\": 145, \"label\": \"Table\"}]"
motivation: RAG系统中检索器和LLM独立开发，存在对齐问题，现有方法修改组件或引入中间模块效果有限。
method: 提出C-3PO代理框架，通过三个专业智能体（查询提议、文档审查、答案整合）协作优化RAG流程。
result: 在多个QA数据集上，C-3PO优于现有RAG对齐方法，性能提升显著。
conclusion: 轻量级代理优化可有效解决RAG系统对齐问题，提升生成质量。
---

## Abstract
Retrieval-augmented generation (RAG) systems face a fundamental challenge in aligning independently developed retrievers and large language models (LLMs). Existing approaches typically involve modifying either component or introducing simple intermediate modules, resulting in practical limitations and sub-optimal performance. Inspired by human search behavior—typically involving a back-and-forth process of proposing search queries and reviewing documents, we propose C-3PO, a proxy-centric framework that facilitates communication between retrievers and LLMs through a lightweight multi-agent system. Our framework implements three specialized agents that collaboratively optimize the entire RAG pipeline without altering the retriever and LLMs. These agents work together to assess the need for retrieval, generate effective queries, and select information suitable for the LLMs. To enable effective multi-agent coordination, we develop a tree-structured rollout approach for reward credit assignment in reinforcement learning. Extensive experiments in both in-domain and out-of-distribution scenarios demonstrate that C-3PO significantly enhances RAG performance while maintaining plug-and-play flexibility and superior generalization capabilities.

---

## 论文详细总结（自动生成）

好的，这是对论文《C-3PO: Compact Plug-and-Play Proxy Optimization to Achieve Human-like Retrieval-Augmented Generation》的详细中文总结。

---

### 论文核心问题与整体含义

#### 研究动机与背景
- **核心问题**：检索增强生成（RAG）系统面临一个根本性挑战——即独立开发的检索器（Retriever）和大型语言模型（LLM）之间存在“对齐”问题。这种不匹配会导致检索器提供的信息不符合LLM的需求，或者LLM无法有效利用检索到的信息。
- **现有方法的局限性**：
    - **微调检索器或LLM**：成本高、操作复杂，可能会破坏原有能力，且不适用于商业搜索引擎。
    - **引入简单中间模块**：通常只优化单一任务（如查询重写或文档重排序），忽略了RAG流水线中各环节的协同作用，导致次优性能。

### 论文提出的方法论

#### 核心思想：代理为中心的对齐框架
C-3PO的核心思想是**在不修改检索器和LLM的前提下**，通过一个**轻量级的代理系统**来弥合二者之间的鸿沟。该框架模拟人类的搜索行为（迭代地提出查询、审查文档），将复杂的RAG协调任务委托给一个专门的、紧凑的代理模型，而将最终回答生成等核心任务留给LLM。

#### 关键技术细节

1.  **轻量级多代理系统**：在一个单一代理模型中实现了三个专业智能体角色：
    -   **推理路由器（Reasoning Router）**：决策是否需要检索。如果需要，进一步判断问题的复杂度（简单/复杂），并选择合适的策略（直接回答/单次检索/多步推理）。
    -   **信息过滤器（Information Filter）**：对检索到的文档进行分析和筛选，只保留与问题相关、对LLM友好的信息。
    -   **决策制定者（Decision Maker）**：在多步推理策略中，根据当前的推理状态（已积累的文档和LLM生成的路标）决定下一步操作（继续检索还是交给LLM生成最终答案）。

2.  **多代理协同策略**：
    -   **直接回答策略**：当推理路由器判断无需检索时，直接让LLM回答。
    -   **单次检索策略**：对于简单问题，生成一次查询，检索、过滤后交给LLM。
    -   **多步推理策略**：对于复杂问题，先由LLM生成一个高层的“路标”（Roadmap），然后由决策制定者和信息过滤器循环执行“检索-过滤”步骤，直到信息充足，最后将所有信息交给LLM生成最终答案。

3.  **树结构展开的强化学习训练**：
    -   **问题**：如何为执行不同任务（如生成查询、过滤文档）的代理分配奖励？系统级的最终答案奖励无法直接指导每个代理的局部行为。
    -   **树结构展开**：在训练时，不执行单个轨迹（从开始到结束一条线），而是构建一棵决策树。在**确定性展开阶段**，强行让推理路由器探索所有可能的策略（不检索、单次检索、多步推理）。在**随机展开阶段**，对后续的每个步骤，随机采样多个候选动作。
    -   **蒙特卡洛信用分配**：对于树中的每个节点（代表一个代理的某个动作），其奖励不再是一个单一的全局奖励，而是**从该节点出发，所有可能完整轨迹的平均期望奖励**。这解决了多智能体强化学习中的信用分配难题，为每个代理提供了更准确的局部反馈。
    -   **训练方法**：将每个树中的节点按代理分组，使用近端策略优化（PPO）算法进行端到端训练。

### 实验设计

#### 数据集
-   **领域内（In-domain）**：
    -   单跳（Simple）：Natural Questions (NQ), PopQA, TriviaQA (TQA)
    -   多跳（Multi-hop）：2WikiMultiHopQA (2Wiki), HotpotQA (HQA), Musique
-   **领域外/泛化（Out-of-Distribution, OOD）**：
    -   上下文无关数据集：FreshQA (FQA), MultiHop-RAG (M-RAG)
    -   边界数据集：Humanity's Last Exam (HLE)

#### Benchmark与对比方法
-   **基础方法**：**Direct**（无检索）、**Standard RAG**（标准RAG）。
-   **检索器微调**：**REPLUG**。
-   **LLM微调**：**Self-RAG**、**InstructRAG**、**Auto-RAG**。
-   **中间模块方法**：**Reranker**（重排序）、**QueryRewrite**（查询重写）、**SKR-KNN**、**SlimPLM**。

#### 评估指标
    -   主要使用 **准确率（Accuracy）**，在HoL等复杂任务上使用LLM作为评判官进行语义等价判断。

### 资源与算力
-   **硬件与模型**：
    - **LLM服务端**：固定使用 **Qwen2-72B-Instruct**，在OOD测试中也使用了Qwen2-7B, Llama3.3-70B, GPT-4o-mini。
    - **代理模型**：训练了轻量级的 **Qwen2-0.5B** 和 **Qwen2-1.5B**。
    - **检索器**：使用基于Contriever-msmarco的密集检索器，知识库为2018年维基百科。
-   **文中未明确说明**：论文未明确提供训练这些0.5B/1.5B代理模型所用的GPU型号、数量和具体训练时长。仅说明在监督微调阶段使用了`Llama-Factory`框架，RL阶段使用了`OpenRLHF`框架和`VLLM`推理引擎。

### 实验数量与充分性

-   **大量充分实验**：论文进行了**非常全面且客观**的实验来证明其方法的有效性。
    1.  **领域内主实验**：在6个数据集上与11种基线方法进行了比较。
    2.  **领域外泛化实验**：在2个OOD数据集上，更换检索器（Google搜索）和LLM（共4种），进行了8组对比实验。
    3.  **消融实验**：
        - 训练范式消融：对比了无树结构展开、无RL（仅监督微调）变体。
        - 协作策略消融：强制使用单一策略（不检索、单次检索、多步推理）进行对比。
    4.  **效率与性能分析**：绘制了不同方法在性能与推理时间上的散点图。
    5.  **高难任务验证**：在挑战性极高的HLE基准上进行了评估。
    6.  **训练动态分析**：展示了RL训练过程中准确率的变化曲线。
-   **公平性**：实验设计公平，对比了SOTA方法，并考虑了不同的检索器和LLM设置。总结的说，该论文的实验覆盖了性能、泛化能力、消融、效率等多个维度，充分并有说服力地支撑了其核心论点。

### 论文的主要结论与发现

-   **性能卓越**：C-3PO在域内和域外（OOD）场景下均显著优于所有基线方法。在2Wiki等复杂多跳任务上提升尤为明显（最高+15.5%）。
-   **即插即用与泛化能力强**：代理模型在不修改底层RAG组件的情况下，能够适应不同的检索器（如维基百科检索器、Google搜索）和不同的LLM（如Qwen、Llama、GPT-4o-mini），展现出了强大的泛化能力和即插即用的灵活性。
-   **树结构展开训练有效**：消融实验表明，论文提出的树结构展开和蒙特卡洛信用分配机制是性能提升的关键，它解决了多智能体环境中的奖励分配难题，避免了单一轨迹训练的退化。
-   **性能-效率平衡好**：C-3PO（使用0.5B/1.5B代理）以适度的推理时间开销（4.8s/问题）换取了显著的性能提升，优于许多更慢的方法。

### 优点

1.  **方法创新**：提出“代理为中心”的对齐框架，思路新颖。通过树结构展开实现基于期望的蒙特卡洛信用分配，巧妙解决了多智能体RL中长链条的奖励稀疏和信用分配难题。
2.  **实用性强**：无需修改检索器或LLM，真正实现了“即插即用”，降低了对计算资源的依赖，便于部署。0.5B/1.5B的代理模型非常轻量，适合边缘设备。
3.  **实验严谨深入**：实验规模宏大，不仅覆盖了多种域内任务，更在多种域外（OOD）组合（不同数据集、不同检索器、不同LLM）下进行了严格验证，充分展示了其泛化能力。消融实验设计清晰，有效分离了各模块的贡献。

### 不足与局限

1.  **应用限制**：论文实验均基于维基百科（2018年）和Google搜索等通用知识库。在特定领域（如医疗、法律、金融）的专业知识库上的表现和泛化能力有待验证。该方法是否能有效处理高度专业化、有噪声或冲突的文档尚不清楚。
2.  **固有的检索依赖风险**：虽然C-3PO优化了检索流程，但其最终性能仍然受限于检索到的信息质量。如果检索器本身存在偏见或无法返回关键信息，C-3PO也无法弥补这一点。这在高风险应用中会带来传播错误信息的风险。
3.  **推理开销分析**：虽然比许多方法快，但相比最简单的Standard RAG方法，C-3PO的推理时间更长（4.8s vs 3.6s）。对于对延迟极度敏感的应用场景，这个额外的开销可能仍然是一个考虑因素。
4.  **未明确说明的问题**：论文未提供训练代理模型所需的确切GPU资源。此外，RL训练步数（约300步）相对较少，其最终性能是否能通过更长训练进一步提升，尚有待观察。

（完）
