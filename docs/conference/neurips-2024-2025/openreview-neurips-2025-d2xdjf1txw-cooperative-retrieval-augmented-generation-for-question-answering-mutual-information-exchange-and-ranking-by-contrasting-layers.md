---
title: "Cooperative Retrieval-Augmented Generation for Question Answering: Mutual Information Exchange and Ranking by Contrasting Layers"
title_zh: 合作检索增强生成问答：互信息交换与对比层排序
authors: "Youmin Ko, Sung Jong Seo, Hyunjoon Kim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=D2XdJf1tXW"
tags: ["query:fie-rag"]
score: 7.0
evidence: 合作RAG问答框架利用互信息
tldr: 现有RAG在问答中仍存在错误检索和幻觉。提出CoopRAG框架，让检索器与LLM通过互信息交换协作，同时检索器内部层间协作排序，提升多跳问答的事实准确性。实验显示效果优于现有RAG，但未涉及少样本或语言学特征。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1310, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 606, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d2xdjf1txw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1430, \"height\": 580, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1330, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1456, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1457, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1457, \"height\": 1065, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1456, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1456, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1453, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1453, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1455, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1453, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1456, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1453, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1456, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1454, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1456, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d2xdjf1txw/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1453, \"height\": 301, \"label\": \"Table\"}]"
motivation: 传统RAG在问答中检索不准确且易产生幻觉。
method: 提出检索器与LLM互信息交换以及层间对比排序的合作框架。
result: 在简单和多跳问答任务上取得更优结果。
conclusion: 合作式RAG能显著提升事实准确性。
---

## Abstract
Since large language models (LLMs) have a tendency to generate factually inaccurate output, retrieval-augmented generation (RAG) has gained significant attention as a key means to mitigate this downside of harnessing only LLMs. However, existing RAG methods for simple and multi-hop question answering (QA) are still prone to incorrect retrievals and hallucinations. To address these limitations, we propose CoopRAG, a novel RAG framework for the question answering task in which a retriever and an LLM work cooperatively with each other by exchanging informative knowledge, and the earlier and later layers of the retriever model work cooperatively with each other to accurately rank the retrieved documents relevant to a given query. In this framework, we (i) unroll a question into sub-questions and a reasoning chain in which uncertain positions are masked, (ii) retrieve the documents relevant to the question augmented with the sub-questions and the reasoning chain, (iii) rerank the documents by contrasting layers of the retriever, and (iv) reconstruct the reasoning chain by filling the masked positions via the LLM. Our experiments demonstrate that CoopRAG consistently outperforms state-of-the-art QA methods on three multi-hop QA datasets as well as a simple QA dataset in terms of both the retrieval and QA performances. Our code is available.

---

## 论文详细总结（自动生成）

好的，这是基于您提供的论文内容生成的详细中文总结。

### 论文总结：合作检索增强生成（CoopRAG）

#### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：大型语言模型（LLM）存在生成事实性不准确内容（即“幻觉”）的倾向。检索增强生成（RAG）是一种有效的缓解方法，但现有RAG方法在简单问答和复杂的多跳问答（Multi-hop QA）任务中，仍然容易发生**检索错误**和**生成幻觉**。
*   **研究动机**：作者假设现有方法的局限性源于三个原因：
    1.  **问题信息不足**：原始问题太短，难以引导检索器找到相关文档，也难以激发LLM的高质量推理。
    2.  **检索器的“大众化”倾向**：密集检索器的对比学习目标（InfoNCE loss）可能导致其只匹配输入问题的表面词汇模式，而非真正蕴含答案的关键文档，从而产生“大众化”行为，忽略了关键信息。
    3.  **缺乏不确定性处理**：现有方法未能为LLM提供一个有效途径来补偿其不确定或缺失的关键知识。虽然有一些推理策略，但缺少一种有效的方式来填补LLM知识中的空白。
*   **整体含义**：为了解决这些问题，论文提出了一个名为**CoopRAG**的合作式RAG框架，旨在通过**双向协同**（检索器与LLM之间、检索器内部不同层之间）来提高检索和推理的准确性，最终提升问答的事实可靠性。

#### 2. 论文提出的方法论：核心思想、关键技术细节

CoopRAG框架的核心思想是实现“双向协同”：**LLM输出其内部知识来辅助检索器进行更精准的检索，而检索器则提供高质量文档来帮助LLM补全其不确定的知识，从而提升推理的置信度。** 框架包含以下五个关键阶段：

*   **阶段一：问题展开（Question Unrolling）**
    *   **核心思想**：LLM利用其内部知识，将原始问题分解为多个子问题和一个**带掩码的不确定性推理链**。这旨在提取出LLM确信的知识，同时显式地标记出它不确定的部分。
    *   **具体步骤**：
        1.  LLM将问题 \( Q \) 分解为一组子问题 \( S \) 和一个推理链 \( R \)。
        2.  推理链由一系列三元组（头实体，关系，尾实体）构成，模拟逐步推理过程。
        3.  对于LLM没有信心的实体，用不确定性掩码 `<UNCERTAIN>` 进行替代。最终答案的位置被标记为 `<FILL>` 占位符。
        4.  最终，将原始问题 \( Q \)、子问题 \( S \) 和推理链 \( R \) 拼接起来，形成“展开后的问题” \( U \)。这样，检索器和LLM都能利用LLM确信的内部知识。

*   **阶段二：展开增强检索（Unrolling-Augmented Retrieval, UAR）**
    *   **核心思想**：使用展开后的问题 \( U \) 进行文档检索，以获得比仅使用原始问题更丰富、更具信息量的查询。
    *   **技术细节**：使用经过微调的编码器（如MPNet）对展开后的问题和文档进行编码，通过计算它们[CLS]令牌嵌入的余弦相似度，检索出与 \( U \) 最相关的Top-n文档。

*   **阶段三：对比层排序（Ranking by Contrasting Layers, RaLa）**
    *   **核心思想**：这是论文的核心创新之一。受LLM知识存储在不同层的理论启发，通过对比编码器**早期层（关注句法/表面信息）** 和**后期层（关注抽象语义）** 的表示差异，来对检索到的文档进行重排序，从而筛选出真正与问题语义相关的文档，而非仅是表面匹配的文档。
    *   **技术细节**：
        1.  将编码器的层分为若干个桶，从每个桶中选择一个候选层。\( C \) 表示候选层集合，\( L \) 表示最后一层。
        2.  对于每个文档 \( D \)，计算其与展开后问题 \( U \) 的**差距感知得分**。关键公式为 `score(U, D)`，它通过一个 **MaxSim** 算子计算每个查询令牌与所有文档令牌的最大相似度之差。这个差值是候选层 \( l \) 与最后一层 \( L \) 的余弦相似度之差。公式如下：
            `score(U, D) = avg_i( max_j( max_{l in C} (<qi, d(L)_j> - <qi, d(l)_j>) ) )`
        3.  为了降低计算开销，实践中使用了简化的**优化版本** `score_o(U, D)`，它将上述差距计算简化为仅使用[CLS]令牌的差距权重 \( \omega_{U,D} \)，然后乘以原有MaxSim得分。公式如下：
            `score_o(U, D) = ω_{U,D} * avg_i( max_j( <qi, d(L)_j> ) )`
        4.  基于优化版得分对Top-n文档进行重排序，筛选出Top-k个最相关的文档。

*   **阶段四：推理链补全与推理（Reasoning Chain Completion and Reasoning）**
    *   **核心思想**：利用重排序后的Top-k文档，让LLM补全在“问题展开”阶段被掩码的不确定实体。
    *   **具体步骤**：
        1.  LLM根据Top-k文档中的事实证据，将推理链中的 `<UNCERTAIN>` 和 `<FILL>` 占位符填充为具体的实体。
        2.  然后，LLM根据补全后的推理链、原始问题、子问题和Top-k文档，生成最终答案。

*   **模型训练（难度感知训练）**
    *   为了训练上述编码器，论文提出了**难度感知训练**策略。在InfoNCE损失函数中，为每个样本引入一个权重 \( \alpha_{Ui} \)，该权重与问题展开后得到的**子问题数量**成正比。这确保了模型能更多地关注复杂、困难的问题，避免过拟合于简单、表面的模式。

#### 3. 实验设计：数据集、基准和对比方法

*   **数据集**：
    *   **多跳QA**：HotpotQA、MuSiQue、2WikiMultihopQA。
    *   **单跳QA（事实型）**：NaturalQuestions (NQ)。
    *   **额外评测**：SimpleQA 和 FreshQA（更接近真实场景、更新的事实型问答基准）。
*   **基准（Benchmark）**：采用Recall@2和Recall@5评估检索性能，采用Exact Match (EM)和F1-score评估问答性能。
*   **对比方法**：
    *   **简单基线**：BM25, Contriever, ColBERTv2。
    *   **大型LM**：GTE-Qwen2-7B, GritLM-7B, NV-Embed-v2。
    *   **结构化RAG**：RAPTOR, GraphRAG, HippoRAG, HippoRAG2, SiReRAG, HopRAG。
    *   **多步检索方法**：IRCoT。

#### 4. 资源与算力

*   **训练**：使用**两张NVIDIA A6000 GPU**进行训练。训练时长因数据集而异：HotpotQA约5小时，MuSiQue约2小时，2WikiMultihopQA约8小时，NaturalQuestions约2小时。
*   **推理**：使用**单张NVIDIA A6000 GPU**进行推理。
*   **核心模型**：使用MPNet作为编码器，Gemma2 (9B, 27B)、Llama3.3-70B 和 GPT-4o-mini 作为大语言模型。

#### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量、全面的实验，足以支持其核心结论。
    *   **主要结果**：在4个标准数据集上对比了多种单步检索和QA方法（表2、表3）。
    *   **额外评测**：在SimpleQA和FreshQA上进行了评测（表4）。
    *   **消融实验**：对**差距感知权重 (ω)**、**难度感知权重 (α)**（表5）、**不确定性掩码**（表7）、**不同问题展开方式**（表16）、**不同重排序策略**（表17）、**损失函数**（表20）进行了消融。
    *   **对比分析**：比较了**多步检索**（表12）和**多步QA**（表13）的性能。
    *   **效率分析**：比较了检索和推理效率（表14、表15）。
    *   **鲁棒性分析**：测试了对**候选文档规模**的扩展性（表22）和**超参数敏感性**（附图6、7）。
*   **充分性与客观性**：实验设计较充分，对比了多个SOTA基线，并提供了详细的消融和分析。实验结论客观，验证了论文提出的每个模块的有效性。整体来看，实验是公平和可信的。

#### 6. 论文的主要结论与发现

*   **CoopRAG框架性能卓越**：CoopRAG在**单跳和多跳QA**的检索和问答性能上**全面超越**了所有对比的现有方法，包括HippoRAG2、HopRAG等最新SOTA模型。
*   **小模型也能表现优异**：CoopRAG使用Gemma2-9B（一个较小的开源模型）就能超越使用Llama3.3-70B（更大的模型）的HippoRAG2，证明了其方法的有效性。
*   **各模块的有效性**：
    *   **问题展开**：有效增强了检索，尤其是对于复杂问题（子问题越多，优势越大）。
    *   **不确定性掩码**：通过避免LLM输出不自信的信息，显著提升了检索和最终答案的准确性。
    *   **对比层排序（RaLa）**：有效区分了语义相关文档和表面匹配的干扰文档，大幅提升了检索质量。
    *   **难度感知训练**：通过关注困难样本，提高了编码器的鲁棒性。
*   **高效性**：CoopRAG在保持高准确率的同时，其推理效率（LLM调用次数）与HippoRAG2相当，优于HopRAG。

#### 7. 优点

1.  **创新性方法论**：提出了一个优雅的“双向协同”RAG框架，将检索器与LLM的协作以及检索器内部层间的协作有机结合。
2.  **处理不确定性**：通过显式的“不确定性掩码”（`<UNCERTAIN>`），创新性地解决了LLM在推理过程中的不确定性传播问题，这是一个显著亮点。
3.  **新颖的对比重排序**：RaLa方法利用Transformer不同层编码信息差异进行重排序，在理论上有依据，在实践中也验证了有效性。
4.  **实验全面且深入**：除了常规基准，还进行了丰富的消融实验、多步对比、效率分析和扩展性分析，论证充分。
5.  **强实用性和效率**：使用相对较小的LLM（如Gemma2-9B）就能达到优异性能，并证明了其在计算效率上的优势，具备在资源受限场景部署的潜力。

#### 8. 不足与局限

1.  **文档长度限制**：作者指出，预训练语言模型（如MPNet）由于序列长度限制，无法编码过长的文档。
2.  **计算成本**：与ColBERT类似，CoopRAG的密集检索方法在MaxSim操作中，随着令牌数量增加，计算成本会上升。
3.  **实验覆盖范围有限**：作者承认，目前方法主要在标准问答数据集上验证，尚未在KBQA（知识库问答）、特定领域（如医疗、技术）数据集上进行充分验证。
4.  **未来方向**：作者提出将框架从段落检索扩展到知识图谱问答（KGQA）是一个有前景但尚未实现的方向。这表明当前方法还不完全适用于结构化知识源。

（完）
