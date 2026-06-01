---
title: "DISRetrieval: Harnessing Discourse Structure for Long Document Retrieval"
title_zh: DISRetrieval：利用话语结构进行长文档检索
authors: "Huiyao Chen, YangYi, Yinghui Li, Meishan Zhang, Min Zhang"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=6h9Q6MMqen"
tags: ["query:fie-rag"]
score: 4.0
evidence: 利用话语结构进行检索
tldr: 本文针对长文档检索中普遍忽略话语结构的问题，提出了DISRetrieval框架，创新地利用修辞结构理论RST构建句子级层次化文档组织，使检索系统能够捕捉文档内部的逻辑关系和主次结构。该方法将语言学特征深度融入检索过程，可增强基于检索的生成系统如RAG对长文档的理解能力。实验表明，DISRetrieval在多个长文档理解基准上显著优于基于平面序列或简单分块的检索方法，证明了话语结构在检索中的有效性。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 735, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1371, \"height\": 1092, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 395, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 728, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6h9q6mmqen/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 901, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 968, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6h9q6mmqen/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1434, \"height\": 1419, \"label\": \"Table\"}]"
motivation: 现有长文档检索方法将文档视为平面序列或随意分块，忽略了话语结构这一重要语言学特征。
method: 基于修辞结构理论RST构建句子级层次化文档表示，设计话语感知的检索框架，实现层次化的长文档检索。
result: 在多个长文档理解基准上，DISRetrieval在检索准确率和下游任务性能上均显著优于基线方法。
conclusion: 融入话语结构能显著提升长文档检索效果，为检索增强生成系统提供更结构化的上下文支持。
---

## Abstract
Long document understanding has become increasingly crucial in natural language processing, with retrieval-based methods emerging as a promising solution to address the context length limitations of large language models (LLMs). However, existing approaches either treat documents as flat sequences or employ arbitrary chunking strategies, failing to capture the inherent discourse structure that guides human comprehension. We present DISRetrieval, a novel hierarchical retrieval framework that leverages linguistic discourse structure to enhance long document understanding. Our approach introduces three key innovations: (1) a discourse-aware document organization framework that utilizes rhetorical structure theory (RST) to create sentence-level hierarchical representations, preserving both semantic relationships and natural document flow; (2) an LLM-enhanced node representation technique that combines discourse structure with adaptive summarization to enrich tree nodes with contextual information; and (3) a hierarchical evidence retrieval mechanism that effectively selects relevant content while maintaining discourse coherence. Through comprehensive experiments on QASPER and QuALITY datasets, DISRetrieval demonstrates substantial improvements over existing methods in both token-level retrieval metrics and downstream question answering tasks. Our ablation studies confirm that incorporating discourse structure significantly enhances retrieval effectiveness across different document lengths and query types, validating the importance of linguistically-informed document representation in long-text understanding.

---

## 论文详细总结（自动生成）

# DISRetrieval 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：长文档理解面临大语言模型（LLM）上下文长度限制的挑战。检索增强生成（RAG）方法通过将文档分割成小片段并检索相关证据来缓解此问题。然而，现有方法要么将文档视为扁平序列，要么采用任意的分块策略（如基于固定长度或语义聚类），**忽视了人类理解文档时所依赖的固有话语结构（discourse structure）**，如主题句、对比、列举、总结等关系。
- **整体含义**：作者提出**DISRetrieval**，第一个利用**修辞结构理论（RST）** 来指导长文档检索的框架。通过构建句子级层次化话语树，保留语义关系和自然文档流，从而提升检索质量和下游问答性能。这项工作弥合了语言学结构与信息检索的鸿沟。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
基于RST构建文档的层次化话语树，利用LLM进行节点增强，并在检索时引入结构感知的选择机制，以保持话语连贯性。

### 技术细节

- **(1) 话语感知的树构建（Discourse-Aware Tree Construction）**  
  - **基础**：RST定义了一个层次化树，叶子节点为基本话语单元（EDU），内部节点表示话语关系（如List, Contrast, Summary）。  
  - **句子级适配**：将EDU合并为句子，训练一个**句子级话语解析器**（基于XLNet-base-cased），直接对句子序列进行RST解析。  
  - **两阶段构建**：  
    - **段落级树**：对每个段落内的句子序列 \( S_i = \{s_{i,1}, \dots, s_{i,m}\} \) 解析为本地话语树 \( T_i \)。  
    - **文档级树**：通过自底向上的LLM增强，为每个段落级树的根节点生成文本表示（若子节点文本长度之和 ≥ 阈值 τ，则调用LLM生成摘要；否则直接拼接）。然后对根表示序列再次应用句子级解析器，得到文档级话语树 \( T_{\text{doc}} \)。  
  - **树集成**：将文档级树的叶子节点替换为对应的段落级树，形成统一的集成树 \( T_D \)。

- **(2) 节点表示（Node Representation）**  
  - 对集成树的所有内部节点应用LLM增强（同上述自适应摘要策略），使每个节点获得有意义的文本语义。  
  - 使用预训练句子编码器（Sentence-BERT 或 OpenAI text-embedding-3-large）将节点文本转换为嵌入向量，构建嵌入树。

- **(3) 层次化证据检索与选择（Hierarchical Evidence Retrieval and Selection）**  
  - **多级检索**：对查询编码后，计算与树中所有节点的相似度评分。  
  - **结构感知选择**：按相似度降序遍历节点。  
    - 如果是叶子节点且未被选过，直接加入证据集。  
    - 如果是内部节点，从它的子树中选取 Top-K 个未被选过的叶子节点（避免重复）。  
  - 直到证据集大小达到预设值 \( K \)。  
  - 算法保证局部相关性和结构连贯性，同时自动消除冗余。

### 公式要点（文本说明）
- 节点文本生成：\( t_v = \begin{cases} f_{\text{LLM}}(t_l, t_r), & \text{if } |t_l|+|t_r| \ge \tau \\ t_l \oplus t_r, & \text{otherwise} \end{cases} \)
- 文档级树构建：\( T_{\text{doc}} = f_{\text{discourse}}(\{t_{\text{root}}^1, \dots, t_{\text{root}}^n\}) \)
- 证据选择算法（Algorithm 1）：遍历排序节点，叶子直接取，内部节点取子树中未选过的Top-K叶子。

## 3. 实验设计

### 数据集
- **QASPER**：研究论文问答数据集（测试集1456个问题，416篇文档，平均长度4170词）。评价指标：F1-Match（QA）、token-level F1/Recall（检索）。
- **QuALITY**：长形式阅读理解数据集（发展集2086个问题，115篇文档，平均长度5022词）。评价指标：Accuracy（QA）。

### Benchmark 与对比方法
- **Flatten-chunk**：按最大100词分块，保留句子边界。
- **Flatten-sentence**：按句子拆分，直接检索。
- **RAPTOR**：基于自底向上语义聚类构建层次树（原文方法）。
- **Bisection**：二分法递归划分句子集，使用与DISRetrieval相同的LLM增强和检索机制，以排除树构建策略的影响。
- **DISRetrieval（本方法）**。

### 实验设置
- **上下文长度**：200、300、400词。
- **嵌入模型**：Sentence-BERT (SBERT) 和 OpenAI text-embedding-3-large。
- **生成模型**：UnifiedQA-3B、GPT-4.1-mini、Deepseek-v3。
- **LLM增强模型**：Llama3.1-8B-Instruct（默认），也测试了Qwen2.5-7B、Mistral-7B、GPT-4o-mini、Deepseek-v3。
- **Top-K**：取5（消融实验从1到20测试）。
- **温度参数 τ**：QASPER设为0（直接拼接），QuALITY设为100（触发LLM摘要）。

## 4. 资源与算力

- **话语解析器训练**：1块 NVIDIA A100-40G GPU。
- **所有其他实验**：包括文档话语解析、LLM摘要、节点嵌入、检索与生成，均在 **4块 NVIDIA A800-80G GPU** 上完成。
- 未明确说明训练总时长或推理时间，但提供了计算资源配置。

## 5. 实验数量与充分性

- **主实验**：在2个数据集上，对比4种基线方法，3种上下文长度（200/300/400），2种嵌入模型，3种生成模型 → 共计 \(2 \times 4 \times 3 \times 2 \times 3 = 144\) 个结果（Table 1）。
- **检索性能对比**：Table 2展示了QASPER上的token-level F1/Recall，涵盖同样维度。
- **消融实验**：
  - 层次检索策略变体（Figure 4）：5种（leaf-only, summary-based, all filtered leaves, Top-K rank, Top-K origin）。
  - 不同LLM对节点增强的影响（Table 3）：5种LLM。
  - 话语解析器能力影响（Figure 5）：训练数据比例0%-100%。
  - Top-K值选择（Figure 7）：K=1到20。
- **统计分析**：Table 5和Figure 6分析了检索到的中间节点特征，展示跨数据集差异。
- **公平性**：固定所有方法检索的总长度（200/300/400词），确保公平比较。使用相同LLM进行摘要（RAPTOR与DISRetrieval均用Llama3.1-8B-Instruct）。
- **结论**：实验设计充分、客观，覆盖了不同组件、不同模型和超参数，验证了方法的有效性和鲁棒性。

## 6. 主要结论与发现

- **DISRetrieval在所有设置下一致优于所有基线**。例如，在400词上下文+UnifiedQA-3B下，QASPER F1-Match达40.25%（vs flatten-sentence 37.99%），QuALITY Accuracy达58.91%（vs flatten-sentence 55.27%）。
- **相比RAPTOR**，DISRetrieval提升明显（如300词+OpenAI嵌入时40.24% vs 39.96%），说明语言学的RST结构比纯语义聚类更有效。
- **Bisection消融**表明，单纯层次化组织（不含话语结构）虽有提升，但远不及完整DISRetrieval，证实话语结构的关键贡献。
- **检索性能**：Token-level F1和Recall均最佳，尤其长上下文下Recall优势显著（400词+OPENAI: 75.77% vs flatten-chunk 73.38%）。
- **层次检索策略**：保留自然文档顺序的Top-K origin优于排序后Top-K和全过滤，说明维持文档流的重要性。
- **LLM规模影响不大**：8B级模型与更大模型性能接近，验证了方法的实用性和成本效益。
- **话语解析器质量直接影响下游性能**，改善解析能力有进一步潜力。

## 7. 优点

- **语言学启发创新**：首次将RST话语结构系统性地融入长文档检索，超越了简单的分块或聚类。
- **层次化与自适应**：两阶段构建（段落+文档）兼顾局部和全局结构，自适应摘要策略平衡计算与语义。
- **结构感知检索**：提出新颖的选择算法，既利用层次信息又避免冗余，保持连贯性。
- **广泛且公平的实验**：多数据集、多模型、多上下文长度、多消融，验证充分。
- **可扩展性**：不依赖极大规模LLM，8B模型已足够，便于实际部署。

## 8. 不足与局限

- **依赖话语解析质量**：实验表明解析器性能直接影响效果，而当前句子级解析器是EDU级简单转换而来，存在改进空间。
- **计算开销**：虽采用自适应摘要减少LLM调用，但整体流程仍涉及多次LLM推理，对大规模文档可能仍较慢。阈值τ的选择也较简单。
- **评估指标局限**：当前主要使用token-level召回和下游QA准确率，缺乏对“结构连贯性保持”的直接度量。
- **数据覆盖**：仅测试了英文研究论文和叙事文本（QASPER和QuALITY），其他类型（如法律、新闻、多语言）未验证。
- **未讨论负迁移**：对于本身缺乏明显话语结构的文档（如随机列表），强迫进行RST解析是否可能有害？文中未分析。
- **潜在偏差**：LLM摘要可能引入事实性错误或信息丢失，影响下游结果。

（完）
