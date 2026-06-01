---
title: Large Language Models are Demonstration Pre-Selectors for Themselves
title_zh: 大语言模型作为自身的演示预选择器
authors: "Jiarui Jin, Yuwei Wu, Haoxuan Li, Xiaoting He, Weinan Zhang, Yiming Yang, Yong Yu, Jun Wang, Mengyue Yang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=YgfpMhNYnW"
tags: ["query:fie-rag"]
score: 7.0
evidence: 用于少样本上下文学习的演示预选择
tldr: 现有少样本上下文学习方法需针对每个查询从大规模数据集中检索相似演示，计算成本高。FEEDER提出演示预选择框架，先识别一个富含信息量的核心演示子集，后续查询仅基于该子集进行选择，大幅降低冗余检索。该方法可作为RAG中检索增强生成的先验步骤，为少样本语言任务提供高效示范选择方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 670, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1786, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 823, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 771, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 757, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ygfpmhnynw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 885, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 1013, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1762, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1766, \"height\": 1921, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 1921, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1768, \"height\": 1016, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1061, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1768, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1768, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ygfpmhnynw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1768, \"height\": 608, \"label\": \"Table\"}]"
motivation: 现有少样本ICL检索方法对每个查询重复检索大规模数据，效率低下。
method: 提出FEEDER框架，通过信息量度量预选核心演示子集，再基于该子集进行查询特定选择。
result: 在多个少样本任务上，FEEDER在保持性能的同时显著降低计算开销。
conclusion: FEEDER是一种高效、可迁移的少样本ICL检索方法，可增强RAG系统的few-shot能力。
---

## Abstract
In-context learning with large language models (LLMs) delivers strong few-shot performance by choosing few-shot demonstrations from the entire training dataset. However, previous few-shot in-context learning methods, which calculate similarity scores for choosing demonstrations, incur high computational costs by repeatedly retrieving large-scale datasets for each query. This is due to their failure to recognize that not all demonstrations are equally informative, and many less informative demonstrations can be inferred from a core set of highly informative ones. To this end, we propose FEEDER (FEw yet Essential Demonstration prE-selectoR), a novel \emph{pre-selection} framework that identifies a core subset of demonstrations containing the most informative examples. This subset, referred to as the FEEDER set, consists of demonstrations that capture both the ''sufficiency'' and ''necessity'' information to infer the entire dataset. Notice that FEEDER is selected before the few-shot in-context learning, enabling more efficient few-shot demonstrations choosing in a smaller set. To identify FEEDER, we propose a novel effective tree based algorithm. Once selected, it can replace the original dataset, leading to improved efficiency and prediction accuracy in few-shot in-context learning. Additionally, FEEDER also benefit fine-tuning LLMs, we propose a bi-level optimization method enabling more efficient training without sacrificing performance when datasets become smaller. Our experiments are on 6 text classification datasets, 1 reasoning dataset, and 1 semantic-parsing dataset, across 6 LLMs (ranging from 335M to 7B parameters), demonstrate that: (i) In few-shot inference, FEEDER achieves superior (or comparable) performance while utilizing only half the input training data. (ii) In fine-tuning, FEEDER significantly boosts the performance of LLMs.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

**研究动机**：  
在上下文学习（In-Context Learning, ICL）中，大语言模型（LLM）通过在输入中提供少量示范（demonstrations）实现少样本推理。现有方法通常基于相似度、多样性等指标从整个训练数据中为每个查询独立检索示范，这导致两个问题：  
1. **计算成本高**：对每个查询重复检索大规模数据集，尤其当示范数量较多或数据集很大时开销显著。  
2. **忽略LLM特异性**：示范的有效性取决于所使用的具体LLM，不同LLM的能力和知识分布不同，通用相似度指标无法捕捉这种依赖关系。

**整体含义**：  
论文提出，并非所有训练样本都是同等有用的，许多样本的信息可被一个核心子集所覆盖。因此，引入“预选择（pre-selection）”阶段，在**演示选择之前**先识别出一个富含信息量的核心子集（称为FEEDER集），该子集在保持对特定LLM充分性与必要性的前提下，替代全训练数据，从而显著提升后续ICL或微调阶段的效率，同时保持甚至提升性能。

## 2. 方法论核心思想、关键技术细节

### 核心思想
- 定义两个关键度量：**充分性（Sufficiency）** 和**必要性（Necessity）**。  
  - 充分性：将某示范加入上下文后，是否足以使LLM正确回答另一个样本。  
  - 必要性：从已有上下文中移除某示范后，是否会导致LLM对另一个样本的回答变错。  
- 目标是找到一个子集DFEEDER ⊆ DTRAIN，使得该子集对全训练数据既充分又必要（即包含所有必要信息且无冗余）。
- 利用LLM自身的推理能力来评估示范之间的充分性与必要性，从而**让LLM成为自身的演示预选择器**。

### 关键技术细节
1. **定义**：  
   - 充分性度量（实例级）：plug((xn,yn))后，Y(xm)=1。  
   - 必要性度量（实例级）：unplug((xn,yn))后，Y(xm)=0。  
   - 集合级：将定义扩展到集合，充分集意味着plug该集后可正确回答另一集中所有样本；必要集意味着移除该集中任意元素都会导致至少一个样本回答错误。

2. **树形近似算法（Algorithm 2）**：  
   - 自底向上构建树，初始W0为每个单样本节点。  
   - 每一轮k，对Wk-1中的每对节点(Wi,Wj)，检查Wi对Wj的充分性（及其反向）。  
     - 若双向充分，保留元素较少的节点；  
     - 若单向充分，保留充分的节点；  
     - 若都不充分，合并Wi∪Wj。  
   - 重复直到根节点只有一个集合，该集合即为近似FEEDER子集。  
   - 复杂度为O(K log^2 |DTRAIN|)，默认K=1（一次检查）已足够。

3. **双层优化（Bi-level Optimization）**：  
   - 外层：在冻结LLM下优化DFEEDER选择（使子集充分且必要）。  
   - 内层：在固定DFEEDER上微调LLM。  
   - 迭代进行，同时优化子集和模型参数。

4. **精确算法（附录A4）**：  
   - 通过必要性检查迭代移除冗余样本，但计算成本高，仅用于分析。

## 3. 实验设计

### 使用的数据集与场景
- **文本分类（6个）**：SST-2, SST-5, COLA, TREC, SUBJ, FPB。  
- **推理**：GSM8K（数学推理）。  
- **语义解析**：SMCALFlow。  
- **科学问答**：GPQA（仅部分实验）。

### LLM基准
- GPT-2 (335M, 774M), GPT-neo (1.3B), Gemma-2 (2B), Llama-2 (7B), Llama-3 (8B), Qwen-2.5 (32B)。  
- 覆盖从335M到32B参数，体现方法的跨模型适用性。

### 对比方法
- **演示选择器（6种）**：Random, Similarity（余弦相似度）, Diversity（最大边际相关性）, Uncertainty, Clustering, Latent（LLM作为隐变量模型）。  
- 基线：直接在全训练数据DTRAIN上应用这些选择器；对应地，使用FEEDER预选择子集DFEEDER作为选择池。

### 实验设置
- 采用8个随机种子和5种不同的n-shot排列，报告均值和方差。  
- 在ICL和微调（双层优化）两种设置下评估。

## 4. 资源与算力

论文**未明确说明**使用的GPU具体型号、数量和训练总时长。仅在附录A8.1提到所有实验均在**NVIDIA A100s**上运行。未提供算力消耗的详细统计。

## 5. 实验数量与充分性

- **大量实验**：覆盖6个文本分类+2个复杂任务（GSM8K, SMCALFlow）+ GPQA，6种LLM，6种选择器，多种n-shot（1,2,5,10 shots）。  
- **消融实验**：  
  - 改变算法轮数R和树深度K对性能及子集大小的影响。  
  - 与随机等量降采样的对比（表A8）。  
  - 近似FEEDER与精确FEEDER（整合必要性检查）的对比（表A9）。  
  - 增量更新实验（附录A6.2）。  
  - 跨LLM迁移（小LLM预选择供大LLM使用）（表A7）。  
- **公平性**：直接对比使用相同选择器在DTRAIN和DFEEDER上的表现，并报告方差。实验设计较为严谨。

**充分性评价**：实验规模大，维度多，但未覆盖超大模型（如65B以上）及更多真实场景，部分结论仅在中等规模LLM上验证。

## 6. 主要结论与发现

1. **性能提升**：在ICL中，FEEDER作为预选择器**可减少20%以上训练数据量**，同时保持或提升准确性。与相似度选择器结合时，性能甚至能媲美更复杂的多样性/不确定性选择器在全数据上的结果。  
2. **效率优势**：预选择只需一次或少量计算，后续所有查询均基于小得多的子集进行选择，大幅降低整体计算开销。  
3. **微调加速**：在微调设置下，使用FEEDER子集训练的LLM比在全数据上训练的LLM获得更好或相当的性能，验证了高质量数据比大数据量更重要。  
4. **模型特异性**：案例分析证明，同一示范对不同LLM的充分性/必要性不同，验证了预选择应依赖具体LLM的论点。  
5. **鲁棒性**：当训练数据包含重复或噪声时，FEEDER能有效过滤冗余信息，维持模型性能。

## 7. 优点

1. **新颖的预选择范式**：首次将数据降维引入ICL演示选择流程，改变了“全数据检索”的范式，具备理论创新性和实用价值。  
2. **LLM自评估机制**：利用LLM自身推理能力评估示范间的因果关系（充分性/必要性），无需额外标注或外部模型。  
3. **双重适用性**：既可用于ICL，也可用于微调，并进一步统一为双层优化框架，实现子集和模型协同优化。  
4. **高效近似算法**：树形算法复杂度低（log^2级别），且默认K=1即可达到良好效果，实际部署可行。  
5. **广泛验证**：在多种LLM（小至335M大至32B）和任务上一致有效，具有良好的可迁移性。

## 8. 不足与局限

1. **近似算法的必要性保证缺失**：默认的近似算法只保证充分性，不保证每个样本的必要性（即可能仍有冗余）。附录中的精确算法计算成本高，实际未采用。  
2. **偏差放大风险**：预选择依赖LLM自身能力，若LLM已有偏见或错误知识，可能选出偏向性样本，从而放大偏差（论文Impact Statement已提及）。  
3. **实验覆盖的局限性**：  
   - 未在万亿参数级模型（如GPT-4, Gemini Ultra）上验证。  
   - 复杂任务（推理、语义解析）上的绝对性能仍较低，FEEDER的提升在低基础性能上有限。  
   - 任务类型偏少（未涉及生成式任务如摘要、翻译）。  
4. **时间复杂度分析不完整**：虽提及算法复杂度，但未给出实际运行时间的具体数值比较（如与全数据检索的时间节约百分比）。  
5. **增量更新验证有限**：仅提出想法，缺乏大规模动态数据上的实证结果。

（完）
