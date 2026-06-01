---
title: "From RAG to Memory: Non-Parametric Continual Learning for Large Language Models"
title_zh: 从RAG到记忆：大语言模型的非参数持续学习
authors: "Bernal Jiménez Gutiérrez, Yiheng Shu, Weijian Qi, Sizhe Zhou, Yu Su"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LWH8yn4HS2"
tags: ["query:fie-rag"]
score: 5.0
evidence: 通过记忆结构改进RAG，可应用于少样本事实性推理
tldr: 当前RAG依赖向量检索，难以模拟人类长期记忆的动态互联特性。该文提出从RAG到记忆的转换，使用知识图谱等结构增强记忆，同时保持事实记忆性能不下降。实验表明该方法在持续学习场景下优于标准RAG。该工作可为事实性推理任务提供更丰富的检索上下文。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1756, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 694, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1380, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 787, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 785, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1773, \"height\": 1128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 505, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 895, \"height\": 424, \"label\": \"Table\"}]"
motivation: RAG在持续学习中无法模拟动态互联的人脑记忆，且事实记忆任务性能下降。
method: 引入知识图谱等结构增强向量检索，设计非参数持续学习框架。
result: 在事实记忆和持续学习基准上优于标准RAG，且保持了良好的可扩展性。
conclusion: 将RAG与结构化记忆结合能有效提升模型的知识获取与组织能力。
---

## Abstract
Our ability to continuously acquire, organize, and leverage knowledge is a key feature of human intelligence that AI systems must approximate to unlock their full potential. Given the challenges in continual learning with large language models (LLMs), retrieval-augmented generation (RAG) has become the dominant way to introduce new information. However, its reliance on vector retrieval hinders its ability to mimic the dynamic and interconnected nature of human long-term memory. Recent RAG approaches augment vector
embeddings with various structures like knowledge graphs to address some of these gaps, namely sense-making and associativity. However, their performance on more basic factual memory tasks drops considerably below standard RAG. We address this unintended deterioration and propose HippoRAG 2, a framework that outperforms standard RAG comprehensively on factual, sense-making, and associative memory tasks. HippoRAG 2 builds upon the Personalized PageRank algorithm used in HippoRAG and enhances it with deeper passage integration and more effective online use of an LLM. This combination pushes this RAG system closer to the effectiveness of human long-term memory, achieving a 7% improvement in associative memory tasks over the state-of-the-art embedding model while also exhibiting superior factual knowledge and sense-making memory capabilities. This work paves the way for non-parametric continual learning for LLMs. Code and data are available at https://github.com/OSU-NLP-Group/HippoRAG.

---

## 论文详细总结（自动生成）

# 论文《From RAG to Memory: Non-Parametric Continual Learning for Large Language Models》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有检索增强生成（RAG）系统依赖简单的向量检索，无法模拟人类长期记忆的动态和互联特性，尤其在“意义建构”（sense-making，理解长段复杂文本）和“联想性”（associativity，多跳推理）方面存在明显缺陷。此外，一些增强结构（如知识图谱）的方法虽然提升了复杂任务性能，但导致基本事实记忆任务（简单QA）的性能下降。
- **整体含义**：本文旨在开发一种更接近人类长期记忆的非参数持续学习系统，在不牺牲基本事实记忆能力的前提下，全面提升RAG在事实记忆、意义建构和联想性三个维度上的表现，为大语言模型的持续学习提供新范式。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
以神经生物学为灵感，构建一个结合知识图谱（KG）与个性化PageRank（PPR）的检索框架，实现类人记忆的“稠密-稀疏编码”整合，并引入识别记忆机制进行在线过滤。

### 关键技术细节
- **离线索引**：
  1. 使用LLM（如Llama-3.3-70B-Instruct）进行开放信息抽取（OpenIE），从每段文本提取三元组（主语、谓语、宾语），构建无模式KG。
  2. 通过检索编码器（如NV-Embed-v2）检测短语节点间的同义关系，添加同义边连接相似短语。
  3. **稠密-稀疏集成**：引入“段落节点”（passage node），通过“包含”边（context edge）将段落与其短语连接，形成同时包含概念（短语）和上下文（段落）的KG。
- **在线检索**：
  1. **查询-三元组匹配**：使用嵌入模型将整个查询与KG中的三元组进行语义匹配，而非仅匹配命名实体（NER），以获取更丰富的上下文。
  2. **识别记忆过滤**：用LLM对检索到的top-k三元组进行过滤，只保留与查询相关且有助于推理的三元组。
  3. **种子节点选择与PPR**：从过滤后的三元组中提取短语节点和所有段落节点作为种子节点，并根据排名分数分配重置概率（段落节点乘以权重因子0.05）。运行PPR算法，对KG进行上下文感知的随机游走，最终根据段落节点的PageRank分数排序并返回top-k段落。
- **最终QA**：将检索到的top-5段落作为上下文，输入LLM生成答案。

## 3. 实验设计

### 数据集与场景
- **事实记忆（Simple QA）**：NaturalQuestions（NQ，1000 queries）、PopQA（1000 queries）
- **联想性/多跳QA**：MuSiQue（1000 queries）、2WikiMultihopQA（1000 queries）、HotpotQA（1000 queries）、LV-Eval（hotpotwikiqa-mixup 256k，124 queries）
- **意义建构/长篇理解**：NarrativeQA（293 queries，来自10部长篇文档）

### 对比基线
- **简单基线**：BM25、Contriever、GTR（T5-base）
- **大规模嵌入模型**：GTE-Qwen2-7B-Instruct、GritLM-7B、NV-Embed-v2（7B）
- **结构增强RAG**：RAPTOR、GraphRAG、LightRAG、HippoRAG

### 评估指标
- 检索：passage recall@5
- QA：token-level F1 score（部分报告Exact Match）

## 4. 资源与算力

- 论文明确说明：使用Llama-3.3-70B-Instruct作为LLM（用于OpenIE、NER、三元组过滤和QA阅读），部署在配备4块NVIDIA H100 GPU的机器上，采用vLLM实现张量并行。
- 对MuSiQue语料库（约11k文档）的对比实验显示：HippoRAG 2的索引时间约99.5分钟，每查询QA时间约1.2秒，QA时GPU内存约9.9GB（包含模型权重共享部分）。
- 相比之下，GraphRAG和LightRAG的索引时间和每查询时间大幅增加（数倍），而NV-Embed-v2等纯嵌入方法则更轻量。

## 5. 实验数量与充分性

### 实验数量
- **主要QA实验**：在7个数据集上对比了约11种方法（包括不同配置），报告了F1和部分EM指标。
- **检索实验**：在5个有标注段落的数据集上报告了recall@2/recall@5。
- **消融实验**：对三种链接方式（NER-to-node、Query-to-node、Query-to-triple）、是否包含段落节点、是否使用三元组过滤进行了消融。
- **超参数实验**：对段落节点权重因子（0.01~0.5）进行了验证。
- **鲁棒性实验**：
  - **语料库扩展实验**：将NQ和MuSiQue分为4段，模拟持续学习场景，测量性能变化。
  - **检索器灵活性实验**：使用不同嵌入模型（GTE-Qwen2、GritLM、NV-Embed-v2）测试。
  - **LLM鲁棒性实验**：使用Llama-3.3-70B-Instruct和GPT-4o-mini作为提取器/阅读器。
- **错误分析**：对100个召回失败的样本分析了原因。

### 充分性与公平性
- **充分**：覆盖了多种任务类型（简单、多跳、长篇）、多种基线（从简单到最先进）、多种消融配置，并进行了鲁棒性验证。
- **公平**：所有结构增强方法均使用相同的LLM和检索器进行复现，超参数基于验证集调整，显著性检验采用bootstrap方法（p<0.05）。

## 6. 论文的主要结论与发现

- **HippoRAG 2** 在所有三类任务（事实记忆、意义建构、联想性）上均全面优于标准RAG（NV-Embed-v2）及所有对比的结构增强方法。
- 在联想性任务（多跳QA）上，平均F1提升7个百分点；在简单QA上性能不降反升；在长篇理解上也有显著改善。
- 关键改进点（稠密-稀疏集成、查询-三元组匹配、识别记忆过滤）均被消融实验验证为有效。
- 系统在持续学习场景（语料库扩展）下能稳定保持优势；且对不同检索器和LLM具有鲁棒性。

## 7. 优点

- **方法创新**：首次将稠密编码（段落节点）与稀疏编码（短语节点）在KG中融合，更贴近人脑记忆机制；引入“查询-三元组”匹配和识别记忆过滤，提升了上下文对齐精度。
- **全面性**：同时评估了三个记忆维度，克服了以往方法“偏科”的问题。
- **实用性**：在保持高性能的同时，索引和查询效率可接受，且兼容开源LLM，便于部署。
- **鲁棒性验证充分**：包括不同数据集、不同检索器、不同LLM、持续学习场景等。

## 8. 不足与局限

- **实验覆盖**：仅测试了英文数据集，未涉及多语言或领域特定的持续学习场景。
- **偏差风险**：主要基于维基百科等公开语料，可能面临知识分布偏差和企业级私域数据适配问题。
- **应用限制**：
  - 索引阶段需要LLM进行OpenIE，产生较多token消耗（约9.2M输入/3.0M输出）；KG构建需消耗时间，不适合对实时性要求极高的场景。
  - 三元组过滤使用LLM的推理，可能会误删关键信息（错误分析中8%样本过滤后相关短语比例下降）。
  - 对超参数（如段落节点权重、同义阈值）敏感，需要验证集微调。
- **实验设计局限**：持续学习实验仅模拟了增量添加文档，未考虑删除/更新场景；未与参数化持续学习方法（如模型微调、知识编辑）直接对比性能与成本。
- **可复现性**：代码已开源，但论文未提供全部超参数搜索过程和具体随机种子设置。

（完）
