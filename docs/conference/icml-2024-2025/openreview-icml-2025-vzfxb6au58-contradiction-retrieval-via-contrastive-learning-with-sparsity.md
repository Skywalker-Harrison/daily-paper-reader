---
title: Contradiction Retrieval via Contrastive Learning with Sparsity
title_zh: 基于对比学习和稀疏性的矛盾检索
authors: "Haike Xu, Zongyu Lin, Kai-Wei Chang, Yizhou Sun, Piotr Indyk"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VzFXb6Au58"
tags: ["query:fie-rag"]
score: 4.0
evidence: 使用句子嵌入进行矛盾检测，用于事实性判断
tldr: 本文提出SparseCL方法，通过对比学习和稀疏性训练句子嵌入，用于检索与查询矛盾的文档。该方法能够捕捉句子间细微的否定关系，对事实核查和事实性检测任务具有潜在价值。实验表明，SparseCL在矛盾检索基准上优于现有方法，为后续结合检索增强的推理系统提供了基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vzfxb6au58/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1207, \"height\": 909, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vzfxb6au58/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 832, \"height\": 1247, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1307, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 880, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1328, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 830, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 760, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 987, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1466, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1508, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 863, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 724, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1775, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 634, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1802, \"height\": 2183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1802, \"height\": 2041, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1804, \"height\": 1587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1800, \"height\": 2084, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1801, \"height\": 2083, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1801, \"height\": 1999, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1796, \"height\": 1625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1792, \"height\": 2336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1798, \"height\": 1997, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1801, \"height\": 1275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1802, \"height\": 1860, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1794, \"height\": 2270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vzfxb6au58/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1795, \"height\": 457, \"label\": \"Table\"}]"
motivation: 现有矛盾检索方法无法有效捕捉句子间的细微否定差异。
method: 使用对比学习训练句子嵌入，并引入稀疏性函数结合余弦相似度进行检索。
result: 在矛盾检索任务上超越传统相似度搜索和交叉编码器方法。
conclusion: 所提方法能有效识别矛盾文档，可辅助事实性检测。
---

## Abstract
Contradiction retrieval refers to identifying and extracting documents that explicitly disagree with or refute the content of a query, which is important to many downstream applications like fact checking and data cleaning. To retrieve contradiction argument to the query from large document corpora, existing methods such as similarity search and cross-encoder models exhibit different limitations.
To address these challenges, we introduce a novel approach: SparseCL that leverages specially trained sentence embeddings designed to preserve subtle, contradictory nuances between sentences. Our method utilizes a combined metric of cosine similarity and a sparsity function to efficiently identify and retrieve documents that contradict a given query. This approach dramatically enhances the speed of contradiction detection by reducing the need for exhaustive document comparisons to simple vector calculations. 
We conduct contradiction retrieval experiments on Arguana, MSMARCO, and HotpotQA, where our method produces an average improvement of $11.0\%$ across different models. We also validate our method on downstream tasks like natural language inference and cleaning corrupted corpora.
This paper outlines a promising direction for non-similarity-based information retrieval which is currently underexplored.

---

## 论文详细总结（自动生成）

# 论文总结：Contradiction Retrieval via Contrastive Learning with Sparsity (SparseCL)

## 1. 核心问题与整体含义（研究动机和背景）

- **问题定义**：矛盾检索（Contradiction Retrieval）是指从大规模文档语料库中，找出与给定查询文本明确对立或驳斥的文档。这是非相似性检索（non-similarity-based retrieval）的典型例子，用于事实核查、数据清洗、反论点检测等下游任务。
- **现有方法的局限性**：
  - **基于相似度搜索（bi-encoder + cosine similarity）**：将矛盾认定为一个“相似”关系，但余弦相似度具有传递性（若 A 相似于 B，B 相似于 C，则 A 相似于 C），无法刻画“A 反对 C、B 反对 C、但 A 与 B 不反对”的非传递性矛盾结构。此外，语料中若存在大量与查询相似的改写句（paraphrase），相似度方法会误将相似句排在矛盾句之前。
  - **交叉编码器（cross-encoder）**：能准确判断矛盾关系，但必须逐对计算，计算开销极大（论文实验显示至少比向量计算慢 200 倍），无法直接用于大规模检索。
- **本文目标**：设计一种仅依赖句子嵌入（sentence embedding）的高效矛盾检索方法，同时克服相似度检索的“传递性缺陷”和交叉编码器的低效问题。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 2.1 核心思想
- 利用“差分向量的稀疏性”来捕捉矛盾。直觉上，矛盾的两段文本在大多数语义维度上相似（如话题、风格），只在少数关键维度上产生对立（如事实性或立场的相反）。因此，其嵌入差分向量应当是“稀疏的”（大部分维度接近零，少数维度值较大）。
- 结合余弦相似度（捕捉内容相关性）和稀疏性度量（捕捉对立性），作为最终评分函数。

### 2.2 关键技术细节

#### 稀疏性度量：Hoyer 稀疏度
- 定义：对于两个嵌入向量 \( h_1, h_2 \)，其差分向量 \( d = h_1 - h_2 \)，Hoyer 稀疏度为：
  \[
  \text{Hoyer}(h_1, h_2) = \frac{ \sqrt{d} - \|d\|_1 / \|d\|_2 }{ \sqrt{d} - 1 }
  \]
  其中 \( d \) 是嵌入维度。该值在 0~1 之间，越大表示向量越稀疏。
- 选择理由：Hoyer 稀疏度不满足传递性，能区分“A 反对 C、B 反对 C、但 A 与 B 不反对”的三角关系（附录 B 提供了正式证明）。

#### 训练方法：SparseCL
- **对比学习框架**：使用 NLI 风格的训练数据，但正负样本选择与标准相似度学习相反：
  - 正例：矛盾对（与查询对立的文档）
  - 硬负例：相似对（与查询相似但不矛盾的文档，如 paraphrase）
  - 软负例：批次内的其他随机文档。
- **损失函数**：基于 Hoyer 稀疏度的对比损失（Temperature-scaled InfoNCE）：
  \[
  l_i = - \log \frac{ e^{\text{Hoyer}(h_i, h_i^+)/\tau} }{ \sum_j ( e^{\text{Hoyer}(h_i, h_j^+)/\tau} + e^{\text{Hoyer}(h_i, h_j^-)/\tau}) }
  \]
  目标是让矛盾对的 Hoyer 稀疏度尽量高，相似对的 Hoyer 稀疏度尽量低。
- **最终评分函数**：
  \[
  F(q, p) = \cos( E(q), E(p) ) + \alpha \cdot \text{Hoyer}( E_s(q), E_s(p) )
  \]
  - \( E \)：标准句子嵌入模型（可预训练或微调后的模型，提供余弦相似度）
  - \( E_s \)：通过 SparseCL 微调得到的稀疏感知嵌入模型
  - \( \alpha \)：在验证集上调优的超参数，平衡相似度与稀疏性的权重。

#### 检索流程
- 先用 FAISS 基于余弦相似度快速召回 Top-K 候选（K 通常设为 1000），再用评分函数 \( F \) 对这些候选重排序，取 Top-10 作为最终结果。理论近似等价于在全集上搜索最大值。

## 3. 实验设计

### 3.1 数据集与场景
| 数据集 | 类型 | 规模（测试集约） |
|--------|------|------------------|
| **Arguana** | 真实辩论论点-反论点对，共 6753 对，来自 1069 场辩论，15 个主题。标准划分（60% 训练、20% 验证、20% 测试），保证同一辩论数据不跨集。 | 1401 条查询 |
| **MSMARCO**（改写版） | 使用 GPT-4 为原始 MSMARCO QA 数据集中的每个答案文档生成 3 个改写句和 3 个矛盾句，替换原文档构成新语料。查询为改写句，标准答案为矛盾句。 | 约 44101 条查询（测试集） |
| **HotpotQA**（改写版） | 同上，基于 HotpotQA 生成。 | 约 81673 条查询（测试集） |

### 3.2 基线方法
- **Zero-shot (Cosine)**：直接使用预训练嵌入模型计算余弦相似度，不做任何微调。
- **CL (Cosine)**：标准对比学习（矛盾作为正例，相似句作为负例），使用余弦相似度评分。
- **Prompt + CL (Cosine)**：在查询前添加提示词 “Not true: ” 后进行对比学习。
- 另外在消融实验中比较了：直接使用 GPT-4 生成矛盾句测试、直接使用 Hoyer 稀疏度评分（不结合余弦）等方法。

### 3.3 对比的模型
- **bge-base-en-v1.5**（109M 参数）
- **UAE-Large-V1**（335M 参数）
- **GTE-large-en-v1.5**（434M 参数）

### 3.4 评估指标
- 主指标：NDCG@10（归一化折损累计增益，Top-10 结果）。
- 零样本泛化测试中也使用 NDCG@10。
- 数据清洗实验中额外报告了 Recall@10（衡量污染比例）。

### 3.5 下游任务
- **检索语料库清洁**：在原始语料中注入 GPT-4 生成的矛盾句（污染），利用 SparseCL 检测并移除 Top-3 矛盾文档，评估检索准确率恢复情况。
- **自然语言推理（NLI）**：在 SNLI 和 MNLI 数据集上，计算矛盾对、蕴含对、随机对的平均余弦相似度/Hoyer 稀疏度，观察是否能区分矛盾。

## 4. 资源与算力
- 论文明确说明：“Most of our experiments are not so computationally extensive, which can be run by one single A6000 GPU. We run our major experiments on A6000 and A100 GPUs.”
- 训练参数（附录表 10）：
  - 批次大小：64
  - 温度：0.01~0.02（模型不同略有差异）
  - 学习率：1e-5 或 2e-5
  - 训练轮数（CL）：1 epoch；SparseCL：3 epochs
  - 最大序列长度：Arguana 512；HotpotQA/MSMARCO 256
- 未给出具体训练时长，但强调“单卡 A6000 即可运行”，说明算力需求较低。

## 5. 实验数量与充分性
- **主要实验结果**：在 3 个数据集上，对 3 种不同模型（GTE、UAE、BGE）分别测试了 6 种方法组合（Zero-shot Cosine、CL Cosine、Prompt+CL Cosine、Zero-shot Cosine+SparseCL Hoyer、CL Cosine+SparseCL Hoyer、以及 Prompt+CL Cosine+SparseCL 等），共约 54 组数据（表 1）。结果稳定显示 SparseCL 方法一致提升。
- **零样本泛化测试**（表 2）：交叉训练（热）与测试（冷）不同数据集，验证了泛化能力。
- **消融研究**：
  - 在 Arguana 中增加改写句数量（从 1 到 3 个），观察相似度方法和 SparseCL 方法的鲁棒性（表 6）。
  - 比较三种不同稀疏度函数（l2/l1, κ4, Hoyer），Hoyer 最佳（表 4）。
  - 比较五种检索策略（Prompt, Gen, SparseCL 等），说明各部分贡献（表 7）。
- **下游应用实验**：语料清洁（表 3）、NLI 区分度（表 5）。
- **效率对比**：附录表 11 给出交叉编码器 vs 向量计算的时间对比。
- **评估客观性**：采用标准评价指标，使用验证集调参（α），测试集报告最终结果。在 Arguana 上与 (Shi et al., 2023) 的 Recall@1 结果进行了对比（附录 C），表明 SparseCL 显著超越前人。
- **充分性评述**：实验覆盖了真实任务（反论点检测）、合成矛盾检测、零样本泛化、下游应用、消融分析，设计较为全面。但缺乏在更大规模语料（如 BEIR 全集）上的测试；生成的矛盾数据使用 GPT-4 可能存在领域偏差；未与直接使用交叉编码器做 rerank 的基线（如 bi-encoder + cross-encoder rerank）对比，这是常见的高性能路线。

## 6. 主要结论与发现
- SparseCL（余弦相似度 + Hoyer 稀疏度）在所有数据集和模型上一致优于纯余弦相似度方法（Zero-shot 或 CL），平均提升约 11%。
- 在含有大量相似改写句的语料中（如 MSMARCO/HotpotQA 合成数据），SparseCL 将 NDCG@10 从 60% 左右提升到 90% 以上，极大缓解了相似度方法的混淆问题。
- **稀疏度与相似度互补**：余弦相似度保证检索内容相关，Hoyer 稀疏度捕捉对立信号，二者结合有效。
- **零样本泛化能力**：在一个数据集上训练的稀疏感知嵌入可迁移到另一个数据集，仅轻微下降。
- **下游应用有效**：语料清洁可恢复约 60% 的污染损失；NLI 中 SparseCL 能自动给矛盾对比蕴含对/随机对更高的 Hoyer 值，具有区分力。
- 效率媲美 bi-encoder，远超 cross-encoder。

## 7. 优点
- **方法新颖**：首次提出专门用于非相似性检索（矛盾检索）的句子嵌入训练方法，利用差分向量稀疏性的数学性质。
- **理论严谨**：提供了传递性/非传递性的形式化分析（附录 B），解释为什么 Hoyer 稀疏度优于余弦相似度。
- **效率高**：只需向量计算，无需逐对交叉编码器推理，适合大规模检索。
- **实验设计全面**：涵盖真实数据、合成数据、零样本泛化、消融、下游应用，结论可靠。
- **与现有架构兼容**：可用任意预训练嵌入模型作为基础，SparseCL 作为微调过程即可。
- **代码（推测）开源**：文中未明确链接，但强调了 FAISS 等工具的使用，可复现性较好。

## 8. 不足与局限
- **评价局限性**：仅使用 NDCG@10 作为主指标，未见 P@K、MRR、Recall 等指标，可能不够全面。
- **基准对比不全**：未与当前更有效的检索方法比较，例如：
  - 无对比 bi-encoder + cross-encoder rerank 基线（尽管计算慢，但在公平性上应讨论 trade-off）。
  - 未对比 TART (Asai et al., 2023) 等任务感知检索方法。
  - 未在大规模多样性基准（如 BEIR）上测试，仅在矛盾检索特定场景上验证。
- **合成数据依赖**：MSMARCO 和 HotpotQA 的“矛盾”由 GPT-4 生成，可能引入模型特定模式（如简单反义词替换），而非真实自然矛盾。论文表 7 的消融显示 “Prompt + CL” 对这类合成数据效果好，但对 Arguana 真实数据效果差，说明存在数据领域偏差。
- **超参数 α 需验证集调优**：实际部署时，若缺乏验证集或矛盾定义变化，α 的选取可能不稳定。零样本实验显示 α 跨数据集具有一定稳定性，但并非完全鲁棒。
- **仅处理文本层次矛盾**：未考虑多跳推理、常识知识或外部知识库的矛盾，应用范围受限。
- **理论解释的局限性**：“稀疏性”直觉虽然合理，但缺乏对嵌入空间几何的深入分析（如证明矛盾对应差分向量的稀疏性在训练后确实成立）。
- **计算开销**：虽然比 cross-encoder 快，但需对每个查询计算与全部候选（或 FAISS 召回后的 Top-K）的余弦相似度和 Hoyer 稀疏度，在极大规模语料下可能仍需近似检索优化。

（完）
