---
title: "EAReranker: Efficient Embedding Adequacy Assessment for Retrieval Augmented Generation"
title_zh: EAReranker：面向检索增强生成的嵌入充分性高效评估
authors: "Dongyang Zeng, Yaping Liu, Wei Zhang, Shuo Zhang, Xinwang Liu, Binxing Fang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mzxGGzeLCL"
tags: ["query:fie-rag"]
score: 4.0
evidence: RAG嵌入充分性评估
tldr: 传统RAG重排序方法存在计算开销大、依赖明文、仅评估相关性而非文档价值等问题。本文提出EAReranker，一种基于嵌入的文档充分性评估框架。它无需访问原始文本内容，通过综合指标量化文档对生成任务的效用，同时降低计算负担。实验表明，EAReranker在多种RAG场景下能有效提升生成质量，为RAG系统中的文档过滤提供了轻量级且有效的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzxggzelcl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzxggzelcl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1310, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzxggzelcl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 314, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1406, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 710, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzxggzelcl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 709, \"height\": 359, \"label\": \"Table\"}]"
motivation: 传统重排序方法计算开销大且仅评估相关性，忽略文档对生成的效用。
method: 提出基于嵌入的文档充分性评估框架EAReranker，无需原始文本。
result: EAReranker在多种RAG场景下降低计算开销并提升生成质量。
conclusion: 嵌入级效用评估是RAG文档过滤的有效且高效策略。
---

## Abstract
With the increasing adoption of Retrieval-Augmented Generation (RAG) systems for knowledge-intensive tasks, ensuring the adequacy of retrieved documents has become critically important for generation quality. Traditional reranking approaches face three significant challenges: substantial computational overhead that scales with document length, dependency on plain text that limits application in sensitive scenarios, and insufficient assessment of document value beyond simple relevance metrics.  We propose EAReranker, an efficient embedding-based adequacy assessment framework that evaluates document utility for RAG systems without requiring access to original text content. The framework quantifies document adequacy through a comprehensive scoring methodology considering verifiability, coverage, completeness and structural aspects, providing interpretable adequacy classifications for downstream applications. EAReranker employs a Decoder-Only Transformer architecture that introduces embedding dimension expansion method and bin-aware weighted loss, designed specifically to predict adequacy directly from embedding vectors. Our comprehensive evaluation across four public benchmarks demonstrates that EAReranker achieves competitive performance with state-of-the-art plaintext rerankers while maintaining constant memory usage ($\sim$550MB) regardless of input length and processing 2-3x faster than traditional approaches. The semantic bin adequacy prediction accuracy of 92.85\% LACC@10 and 86.12\% LACC@25 demonstrates its capability to effectively filter out inadequate documents that could potentially mislead or adversely impact RAG system performance, thereby ensuring only high-utility information serves as generation context. These results establish EAReranker as an efficient and practical solution for enhancing RAG system performance through improved context selection while addressing the computational and privacy challenges of existing methods.

---

## 论文详细总结（自动生成）

# EAReranker: 面向检索增强生成的嵌入充分性高效评估 —— 详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统检索增强生成（RAG）系统中的重排序方法存在三重关键缺陷：
  1. **计算开销随文档长度线性增长**，在资源受限环境下难以部署。
  2. **必须直接访问原始文本**，在涉及知识产权或数据治理的敏感场景中受限。
  3. **仅评估“相关性”而忽视“充分性”**，即文档对于生成任务的实际效用（如内容的可验证性、覆盖度、完整性、结构适用性），导致低价值噪声降低生成质量。
- **整体含义**：本文提出**EAReranker**，一种仅基于嵌入向量进行文档充分性评估的轻量级框架，无需读取原始文本，在保持与最优明文重排序器相当性能的同时，显著降低计算资源消耗，并实现可解释的效用分类，为RAG系统的上下文选择提供高效且隐私友好的解决方案。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将重排序任务重新定义为：学习一个仅基于查询嵌入 \(e_q\) 和文档嵌入 \(e_d\)（由预训练嵌入模型生成）的模型 \(M\)，直接预测文档的“充分性”分数 \(s' \in [0,1]\)，替代传统的语义相关性评估。
- 充分性通过**四个维度**量化：可验证性、需求覆盖度、证据完整性、结构适用性。
- 将充分性分数离散化为**6个语义分箱**（见表1）：精确充分 [0.90,1.00]、高充分 [0.75,0.90)、中充分 [0.50,0.75)、边缘相关 [0.25,0.50)、弱相关 [0.10,0.25)、不相关 [0.00,0.10)。

### 关键技术细节
1. **多模型语义分箱评分（算法1）**：
   - 使用7个不同架构的LLM（GPT-4o、DeepSeek-V3、ChatGLM、Gemini 1.5、Qwen2.5、Llama 3.3、Claude 3）对查询-文档对独立打分。
   - 采用层次化一致性校验：先取前4个模型分数，若最大偏差≤0.2则取均值；否则逐步引入更多模型，检查所有4-组合，找到内部一致（偏差≤0.2）的子集并取均值；否则取全部均值。
2. **分箱内分数校准**：
   - 利用多个重排序模型（gte-reranker-base、bge-reranker-v2-m3等）的归一化得分作为辅助排序信号，对LLM评分在分箱内进行连续化调整，增强区分度。
3. **EAReranker模型架构（图3）**：
   - **嵌入维度扩展**：将查询和文档的固定维度嵌入分别通过N个不共享的线性投影层（\(L_{q,i}, L_{d,i}\)）扩展为N个特征向量，形成序列 \([e_{CLS}, e'_{q,1},..., e'_{q,N}, e_{SEP}, e'_{d,1},..., e'_{d,N}]\)。
   - **Decoder-Only Transformer**：L层堆叠解码器（含多头自注意力和前馈网络），以[CLS]令牌输出经3层MLP头部预测充分性分数。
   - **分箱感知加权损失**：\(L_{BW MSE} = \frac{1}{N}\sum w_i \cdot (s_{true,i} - s_{pred,i})^2\)，权重根据预测分数偏离分箱边界的程度动态分配，强化边界区域的学习。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - 训练数据：100万查询-文档对，整合自bge-m3-data及其他多个公开集合（FEVER、NFCorpus、CQADupStack、FiQA、TriviaQA、Climate-FEVER、SciFact、TREC-COVID、QuizWorks等），涵盖事实核查、专业检索等多样领域。80%训练，20%测试。
  - 评估基准：4个公开标准 **FEVER**、**NFCorpus**、**DuRetrieval**、**T2Ranking**。
- **评估指标**：
  - 排名质量：NDCG@10、MRR。
  - 充分性分类：ACC25（绝对误差≤0.25的比例）、LACC@25（阈值0.25下的二分类准确率）、LACC@10（阈值0.10下的二分类准确率）。
- **对比方法**：
  - 传统词法：BM25。
  - 嵌入相似度：余弦相似度（使用gte-base、bge-m3、jina-v3、KaLM四种嵌入模型）。
  - 明文重排序器：gte-multilingual-reranker-base、bge-reranker-v2-m3、jina-reranker-v2-base-multilingual、lb-reranker-v1.0。
- **EAReranker变体**：分别基于四种嵌入模型（gte-base、bge-m3、jina-v3、KaLM）构建对应版本。
- **消融实验**：完整模型 vs. 移除维度扩展 / 移除分箱感知损失 / 移除分数校准。

## 4. 资源与算力

- 论文未明确指定使用的GPU型号与数量。仅提及训练采用AdamW优化器，batch size 256，学习率1e-5，训练50个epoch并早停。推理时，EAReranker的VRAM占用恒定约550MB，处理时间0.11-0.13秒（见表6），显著低于明文重排序器。附录B.1提到实验在配备GPU（可能为NVIDIA A100或类似）的服务器上进行，但未给出确切型号、数量或总训练时长。**需要指出：文中未详细说明算力资源配置，仅能推断为单GPU或有限数量的GPU集群。**

## 5. 实验数量与充分性

- **实验组数**：
  - 主排名实验：4个基准 × 4种EAReranker变体 + 11个基线（BM25、4种余弦、4种明文重排序器），共约20余个配置。
  - 充分性分类实验：1个数据集（测试集）上4种嵌入变体的ACC25、LACC@25、LACC@10。
  - 消融实验：3组（维度扩展、损失函数、分数校准）。
  - 计算效率对比：4种明文重排序器 vs. 4种EAReranker变体，报告VRAM和时间范围。
- **充分性分析**：
  - **客观公平**：对比了从传统词法、嵌入相似度到最新明文重排序器的全面基线；使用了多个公开基准；报告了标准差（附录B.6表10，5次不同随机种子的结果），显示模型稳定性。
  - **覆盖范围**：排名性能、充分性分类、计算效率、消融分析均有覆盖，但未在更广泛的下游生成任务（如问答、摘要）上验证生成质量的提升，仅通过充分性指标间接证明。
  - **潜在不足**：未进行跨嵌入模型维度的系统分析（如对比高维4096维嵌入）；训练数据规模及标注方法依赖多LLM，可能存在偏差漂移。

## 6. 论文的主要结论与发现

1. **排名性能竞争力**：EAReranker在4个基准上的NDCG@10和MRR仅比最优明文重排序器低0.54%–1.30%，验证了嵌入级充分性评估的可行性。
2. **计算效率优势显著**：EAReranker的VRAM恒定约550MB，不随输入长度增长（明文重排序器最高达8441MB）；推理速度0.11-0.13s，比明文模型快2-3倍。
3. **充分性分类准确率高**：基于bge-m3嵌入的版本达到ACC25 84.28%、LACC@10 92.85%、LACC@25 86.12%，有效区分高价值与低价值文档，可用于RAG自动过滤。
4. **组件有效性**：消融实验证明嵌入维度扩展、分箱感知损失、分数校准均显著提升性能（ACC25分别下降3.70%、2.67%、1.33%）。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次提出纯嵌入空间的充分性评估，摆脱明文依赖，兼顾隐私与效率。
- **系统化充分性定义**：将文档效用量化为四个可操作维度及六个语义等级，提供可解释的过滤阈值。
- **鲁棒标注流程**：多LLM交叉验证结合分箱内校准，减少了单一模型偏差，提升了标签质量。
- **实验严谨性**：报告了多次运行的标准差（附录B.6），增强了结论的可信度；消融实验验证了每项创新的贡献。
- **全面效率对比**：详细测量了不同输入长度下VRAM和推理时间，直观展示了EAReranker的恒定资源消耗优势。

## 8. 不足与局限

- **LLM标注偏差风险**：尽管采用多模型交叉验证，但LLM评价本身可能存在系统性偏好，尤其在边界样本上，且未使用人工标注验证。
- **经验性分箱设计**：语义分箱的边界和维度权重基于经验启发，缺乏严格理论推导或自适应优化。
- **评估范围有限**：仅验证了排名和充分性分类，未直接测试对生成质量（如事实准确性、连贯性）的影响；未在高维嵌入（如4096维）或长序列场景下评估。
- **资源信息不完整**：未明确训练算力配置（GPU型号、数量、总时长），影响可复现性评估。
- **缺乏领域泛化测试**：基准数据集均偏向事实类检索，未验证在创造性写作、多模态等复杂任务中的充分性定义有效性。

（完）
