---
title: Influence Guided Context Selection for Effective Retrieval-Augmented Generation
title_zh: 影响力引导的上下文选择实现有效检索增强生成
authors: "Jiale Deng, Yanyan Shen, Ziyuan Pei, Youmin Chen, Linpeng Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ugaepulZyA"
tags: ["query:fie-rag"]
score: 7.0
evidence: 基于影响力的上下文选择RAG
tldr: 标准RAG中低质量上下文会降低效果，现有选择方法有限。提出将上下文选择视为推理时数据估值问题，利用影响力函数全面评估上下文质量，从而选择最有价值的上下文。实验显示优于基线RAG，但未涉及少样本或语言学特征。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1393, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1408, \"height\": 1083, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1406, \"height\": 1074, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ugaepulzya/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1414, \"height\": 1070, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ugaepulzya/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 956, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ugaepulzya/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 728, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ugaepulzya/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ugaepulzya/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ugaepulzya/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 397, \"label\": \"Table\"}]"
motivation: RAG中检索到的低质量上下文导致性能受限。
method: 将上下文选择建模为数据估值问题，使用影响力函数评估。
result: 在多个QA数据集上提升了RAG性能。
conclusion: 影响力引导的选择策略能系统提升RAG效果。
---

## Abstract
Retrieval-Augmented Generation (RAG) addresses large language model (LLM) hallucinations by grounding responses in external knowledge, but its effectiveness is compromised by poor-quality retrieved contexts containing irrelevant or noisy information. While existing approaches attempt to improve performance through context selection based on predefined context quality assessment metrics, they show limited gains over standard RAG. We attribute this limitation to their failure in holistically utilizing available information (query, context list, and generator) for comprehensive quality assessment. Inspired by recent advances in data selection, we reconceptualize context quality assessment as an inference-time data valuation problem and introduce the Contextual Influence Value (CI value). This novel metric quantifies context quality by measuring the performance degradation when removing each context from the list, effectively integrating query-aware relevance, list-aware uniqueness, and generator-aware alignment. Moreover, CI value eliminates complex selection hyperparameter tuning by simply retaining contexts with positive CI values. To address practical challenges of label dependency and computational overhead, we develop a parameterized surrogate model for CI value prediction during inference. The model employs a hierarchical architecture that captures both local query-context relevance and global inter-context interactions, trained through oracle CI value supervision and end-to-end generator feedback. Extensive experiments across 8 NLP tasks and multiple LLMs demonstrate that our context selection method significantly outperforms state-of-the-art baselines, effectively filtering poor-quality contexts while preserving critical information. Code is available at https://github.com/SJTU-DMTai/RAG-CSM.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，对《Influence Guided Context Selection for Effective Retrieval-Augmented Generation》进行结构化的中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：检索增强生成（RAG）虽能缓解大模型幻觉，但其性能常因检索到的低质量上下文（包含无关、噪声信息）而严重受损。
*   **现有方法局限**：现有的上下文选择方法通常基于预定义的质量评估指标（如查询相关性、列表独特性、生成器一致性）进行筛选，但效果有限。论文指出，其根本原因在于这些方法**未能综合利用查询、上下文列表和生成器这三个关键信息源**来进行全面的质量评估。例如，仅关注查询相关性的指标可能选择与生成器知识冲突的上下文，而仅关注生成器反馈的指标则可能忽略上下文间的互补关系。
*   **研究动机**：鉴于上述局限性，亟需一种能够**整体性地整合“查询-上下文-生成器”三者信息**，并且**免于繁琐超参数调节（如top-k取值）** 的上下文质量评估新范式。

### 2. 论文提出的方法论：核心思想、关键技术细节

*   **核心思想：重新概念化为推理时数据估值**
    *   受到数据选择中数据影响力（Data Influence）的启发，论文将上下文质量评估重新定义为“**推理时数据估值**”问题，并提出了一个全新的度量指标——**上下文影响力值（Contextual Influence Value, CI value）**。

*   **关键指标：CI值**
    *   **定义**：对于给定的查询 \( q \)、上下文 \( c_i \in C \) 和生成器 \( f \)，CI值定义为从上下文列表 \( C \) 中移除 \( c_i \) 后，生成器输出性能的下降程度。公式化为：\( \phi_i(v) = v(f(q \oplus C)) - v(f(q \oplus \{C \setminus c_i\})) \)，其中 \( v(\cdot) \) 是衡量生成质量的效用函数。
    *   **三大特性**：CI值自然满足了四项关键要求：
        1.  **查询感知**：查询无关的上下文会得到低CI值或零CI值。
        2.  **列表感知**：通过计算边际贡献，能奖励独特且必要的信息，惩罚冗余内容。
        3.  **生成器感知**：利用生成器的反馈，能有效区分提升还是削弱生成器性能的上下文。
        4.  **易于配置**：无需针对不同任务调整top-k等超参数，只需**保留所有CI值为正的上下文**，即可实现最优或接近最优的选择策略。

*   **实现挑战与解决方案：CI代理模型（CSM）**
    *   **挑战**：计算真实CI值需要访问测试标签（不可得）且需要多次运行生成器，计算开销巨大。
    *   **解决方案**：提出一个**CI代理模型（CI Surrogate Model, CSM）**，在推理时快速预测CI值。
        *   **模型架构**：采用分层结构，包含一个**局部层**（基于BERT-uncased处理查询-上下文对）、一个**全局层**（利用自注意力机制捕获上下文间的全局交互），和一个**输出层**（MLP）。
        *   **训练范式**：
            1.  **监督训练（CSM-st）**：以真实CI值作为监督，采用加权的回归损失（处理类别不平衡）和对比学习损失（增强难分样本的区分性）进行训练。训练数据中通过“数据干预”技术（替换无关上下文以增强信号）来平衡数据分布。
            2.  **端到端训练（CSM-e2e）**：直接利用生成器的输出反馈优化CSM，通过Gumbel-Softmax技巧实现可微分的“软上下文选择”。损失函数包括一个“充分性损失”（确保选中上下文足以生成正确答案）和一个“必要性损失”（确保未选中上下文不会导致错误答案生成）。

### 3. 实验设计：数据集、基准与对比方法

*   **数据集**：涵盖了**8个**知识密集型自然语言处理任务：
    *   **开放域问答**：NQ, TriviaQA, WebQA
    *   **多跳问答**：HotpotQA, 2WikiMultiHopQA
    *   **事实核查**：FEVER
    *   **多选题**：TruthfulQA
    *   **长文问答**：ASQA
*   **对比方法**：与多类基线进行了对比，包括：
    *   **基准**：Vanilla LLM（无检索）、Standard RAG（保留所有上下文）。
    *   **重排序类**：bge-reranker（查询感知）、RankGPT（列表感知）。
    *   **生成器感知类**：RECOMP-ex（生成器感知）、RECOMP-abs（压缩）。
    *   **噪声鲁棒类**：Ret-Robust（微调生成器）。
    *   **智能体类**：Self-RAG, RQ-RAG。
    *   **理论上限**：Oracle CI value（使用真实CI值）。
*   **评估指标**：针对不同任务，分别使用EM、F1、Accuracy等标准指标。
*   **骨干模型**：使用两个不同架构的大模型**Llama3-8B-instruct**和**Qwen2.5-7B-instruct**，证明了方法的通用性。

### 4. 资源与算力

*   根据论文“Implementation Details”部分，实验是在一台配备有 **Montage Jintide(R) C6226R CPU, 256GB内存，以及4张NVIDIA GeForce RTX 4090 GPU** 的服务器上完成的。
*   论文未明确报告具体的**总训练时长**或**推理时平均时长**（仅在不同上下文数量下比较了推理时延），但指出CSM由于其轻量级架构，在高并发场景下的推理时延显著低于RankGPT等方法。

### 5. 实验数量与充分性

*   **实验数量**：非常充分。
    1.  **主结果评估**：在8个数据集上对比了11种方法，并使用了2个大模型骨干，结果汇总于表1。
    2.  **CI值有效性验证**：通过逐步添加高质量/低质量上下文并观察性能曲线变化，直观验证CI值能准确反映上下文优劣（图3， 7， 8）。
    3.  **近似效果评估**：使用Spearman秩相关系数衡量CSM预测值与真实CI值的对齐程度（图4）。
    4.  **消融研究**：对两种CSM训练方法都进行了关键模块消融（表2），证明了数据干预、对比损失、充分性/必要性损失等组件的必要性。
    5.  **推理时延分析**：比较了不同上下文数量下CSM与其他选择方法的推理时间（表3）。
    6.  **案例研究**：提供了多个具体案例，直观展示CI值如何指导上下文选择（附录E）。
*   **充分性与公平性**：实验设计较为全面和公平。
    *   **任务多样性**：覆盖了多种NLP任务，考虑了不同复杂度和输出形式。
    *   **模型多样性**：使用了两类不同架构的LLM。
    *   **对标先进**：方法对比了多个领域内的标准以及最先进的基线，包括近期提出的智能体方法。
    *   **消融扎实**：对于提出的主要模块和训练技巧都进行了验证。

### 6. 论文的主要结论与发现

*   CI值是一种**有效的上下文选择指标**。选择高CI值的上下文能提升RAG性能，而选择低CI值的上下文则会损害性能。它无需调优top-k，性能始终接近最优。
*   CI值整合了查询、上下文列表和生成器三方面的信息，比单一维度的指标（如查询相关性）更具优势。
*   所提出的CI代理模型（CSM）无论是采用监督学习（CSM-st）还是端到端学习（CSM-e2e），都能以**较低的推理成本**，极高地预测出上下文质量，从而**显著超越**所有对比基线，在8个任务的多数场景中取得最佳或次佳结果。
*   CSM的两种训练范式各有优劣，但整体都优于现有方法。CSM-st在Llama3-8B上总体效果更好，而CSM-e2e在Qwen2.5-7B上表现更均衡。
*   CSM的效果优于复杂的智能体型RAG（如Self-RAG， RQ-RAG），表明过滤低质量上下文比复杂的反思与规划机制更有效。

### 7. 优点

*   **方法论创新**：首次将“推理时数据估值”与RAG上下文选择联系起来，思想独特且具有理论启发性。提出的CI值度量指标在概念上非常优雅。
*   **设计全面**：CI值的设计一体化地考虑了查询、上下文列表、生成器三个关键维度，解决了现有工作信息利用不全面的问题。同时解决了top-k调优的痛点。
*   **提出通用评估框架**：CI值的定义并不局限于特定模型或任务，具有潜在的通用性。
*   **工程实践考虑充分**：针对CI值计算的不可行性，提出了CSM这一轻量级代理模型，并通过分层架构和两种训练范式解决了效率和性能的平衡。实验包括了推理时延分析，具有实际应用价值。
*   **实验详实、分析深入**：大量实验（包括消融、可视化、案例分析）和详尽的附录材料有力支撑了结论。对不同基准模型的优缺点也进行了深入分析。

### 8. 不足与局限

*   **训练依赖**：CSM（特别是监督训练版本）的训练需要依赖使用真实CI值标注的数据，而真实CI值的计算又需要真实标签和多次LLM前向传播，这本身就是一个有挑战且有成本的过程。
*   **任务特定性**：作者自己也提到“CSM当前需要针对特定任务进行优化”，其在不同领域或分布外的泛化能力尚未得到充分验证。训练一个通用的、跨任务的CSM模型仍是一个挑战。
*   **计算资源隐含成本**：虽然CSM推理时很轻量，但为获取训练标签（Oracle CI values）本身需要大量的LLM计算，论文未对此部分训练数据构建的计算成本进行明确量化。
*   **实验范围局限**：虽然任务多样，但所有任务都基于英文维基百科知识库，未测试其他语言或知识源。另外，数据集规模也存在差异（如TruthfulQA较小），可能会影响结论的统计显著性（虽然论文在正文和附录中使用了部分样本进行分析）。
*   **未讨论少样本场景**：方法假设有足够的训练数据来构建CSM。在数据量极其匮乏的冷启动场景下，该方法的应用受限。

（完）
