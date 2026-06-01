---
title: "DynamicRAG: Leveraging Outputs of Large Language Model as Feedback for Dynamic Reranking in Retrieval-Augmented Generation"
title_zh: DynamicRAG：以大语言模型输出为反馈的动态重排序检索增强生成
authors: "Jiashuo Sun, Xianrui Zhong, Sizhe Zhou, Jiawei Han"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NuCtKoflsV"
tags: ["query:fie-rag"]
score: 7.0
evidence: RAG方法利用大模型输出进行动态重排序
tldr: 现有RAG系统在选取文档数量时面临信息缺失或噪声问题。DynamicRAG提出利用大语言模型自身的输出作为反馈信号，动态重排序检索到的文档，从而自动选择最优文档数量。该方法在知识密集型任务中提升了生成质量与可解释性，为少样本叙实性推理中检索阶段的优化提供了可行方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 733, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 676, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 729, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 710, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nuctkoflsv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 721, \"height\": 432, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 938, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 702, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 698, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1104, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1013, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 954, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1281, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 2175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nuctkoflsv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1454, \"height\": 1757, \"label\": \"Table\"}]"
motivation: RAG中选取最优文档数量k的问题未解决，过多或过少均影响效果。
method: 利用LLM的输出质量作为反馈，动态调整检索文档的排序和选择数量。
result: DynamicRAG在知识密集型任务上优于固定k值的RAG基线。
conclusion: 动态重排序能有效提升RAG系统在信息获取和生成质量上的鲁棒性。
---

## Abstract
Retrieval-augmented generation (RAG) systems combine large language models (LLMs) with external knowledge retrieval, making them highly effective for knowledge-intensive tasks. A crucial but often under-explored component of these systems is the reranker, which refines retrieved documents to enhance generation quality and explainability. The challenge of selecting the optimal number of documents (k) remains unsolved: too few may omit critical information, while too many introduce noise and inefficiencies. Although recent studies have explored LLM-based rerankers, they primarily leverage internal model knowledge and overlook the rich supervisory signals that LLMs can provide, such as using response quality as feedback for optimizing reranking decisions. In this paper, we propose DynamicRAG, a novel RAG framework where the reranker dynamically adjusts both the order and number of retrieved documents based on the query. We model the reranker as an agent optimized through reinforcement learning (RL), using rewards derived from LLM output quality. Across seven knowledge-intensive datasets, DynamicRAG demonstrates superior performance, achieving state-of-the-art results.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

检索增强生成（RAG）系统通过结合大语言模型（LLM）与外部知识检索，在知识密集型任务上表现出色。然而，RAG系统中的重排序器（reranker）一个关键但常被忽视的问题是：如何为每个查询动态选择最优的文档数量（k）。固定k值会导致信息缺失（k过小）或引入噪声（k过大），且现有基于LLM的重排序方法仅利用模型内部知识，忽视了LLM输出质量本身可作为反馈信号来优化重排序决策。本论文提出DynamicRAG框架，利用LLM输出作为反馈，通过强化学习动态调整检索文档的顺序和数量，以提升生成质量和系统效率。

### 方法论

**核心思想**：将重排序器建模为强化学习（RL）智能体，以LLM生成质量作为奖励信号，动态决定每个查询的文档排序和选择数量。训练分为两个阶段：行为克隆（Behavioral Cloning）和监督微调（SFT）使重排序器具备基本能力；然后通过与生成器（环境）交互，利用直接偏好优化（DPO）进一步优化。

**关键技术细节**：
- 重排序器输出一个动态子集 $\hat{D} \subset D$，包含重新排序和选择的文档，数量k根据查询动态调整。
- 行为克隆阶段：最大化专家轨迹的似然 $J_{BC}(\theta) = \mathbb{E}_{(q,D,k^*)\sim D_e}[\log \pi_\theta(k|q,D)]$。
- RL优化阶段：使用DPO，从采样轨迹中选取奖励最高（$\tau^+$）和最低（$\tau^-$）的配对，优化目标：$J_{DPO}(\theta) = \mathbb{E}_{(\tau^+,\tau^-)}[\log \sigma(\beta(\log \pi_\theta(\tau^+) - \log \pi_\theta(\tau^-)))]$。
- 奖励函数为多维组合：精确匹配（EM）、语义相似度（SS, BERTScore）、文本流畅度（TF, ROUGE）、长度惩罚（LP）、LLM评估（LLM-Eval）。最终奖励 $r = \alpha\cdot EM + \beta\cdot SS + \gamma\cdot TF + \lambda\cdot LP + \delta\cdot LLM\text{-Eval}$。

**算法流程**（文字描述）：
1. 初始化重排序器和生成器参数。
2. 行为克隆：使用专家数据集（MonoT5生成）监督训练重排序器模仿专家选择k。
3. 生成器训练：用标准RAG数据训练生成器。
4. 交互学习：重排序器多次采样不同k，生成器输出回答，计算多维奖励，选择最好和最差轨迹对，使用DPO更新重排序器。

### 实验设计

**数据集**：涵盖7个知识密集型数据集：NQ、TriviaQA（通用QA）、HotpotQA、2WikimQA（多跳推理）、ASQA、ELI5（长文本生成）、FEVER（事实验证）。

**评价指标**：NQ、HotpotQA、2WikimQA、ASQA使用EM；TriviaQA和FEVER使用准确率；ELI5使用ROUGE-L。

**对比基线**：
- 无检索：GPT-3.5-turbo、GPT-4、GPT-4o。
- 有检索：IRCoT、ReAct、FLARE、RA-DIT、Reward-RAG；基于LLaMA2-7B/13B的Vanilla-RAG、Reranker、SFT、Self-RAG、DRAGIN、Smart-RAG；基于LLaMA3-8B的Auto-RAG、ChatQA-1.5、RankRAG。

**重排序性能对比**：与BM25、Contriever、monoT5、RankLLaMA、RankRAG等比较R@5/10/20。

### 资源与算力

论文明确说明：训练在8块Nvidia A100 GPU（80GB）上进行，使用DeepSpeed Stage 3和Bfloat16精度，FlashAttention加速。行为克隆和DPO各使用1-2个epoch。总训练数据约150k条（其中20k用于冷启动重排序器，100k用于生成器SFT，30k用于DPO）。推理使用vLLM加速，配置类似。

### 实验数量与充分性

论文做了多组实验：
- 主表（Table 1）包含7个数据集、多个基线（约20种方法）、3种骨干模型（7B/13B/8B）。
- 重排序性能对比表（Table 2）包含多种重排序方法。
- 消融实验（Table 3a、3b）：分析重排序器和生成器大小、组件（有无检索、重排序、RL）的影响。
- 效率分析：从LLM调用次数和Token处理时间对比（Table 4）。
- 文档分布分析（Figure 5）。
- 附录中还包含不同检索器、Top-N文档数量、奖励函数设计、闭源模型增强、训练数据规模扩展等实验。

实验设计全面，结果客观，对比基线覆盖主流方法，消融验证各组件必要性。但各实验均未报告多次运行的标准差或置信区间，可能需谨慎看待单次结果。

### 主要结论与发现

1. DynamicRAG在7个数据集上均优于或达到同等参数规模模型的SOTA，尤其在NQ上LLaMA3-8B达到48.4 EM，超越GPT-4o（40.0）。
2. 动态调整k比固定k显著提升性能，RL优化进一步提升。
3. 参数共享的重排序器-生成器组合效果更好。
4. 训练数据量远小于RankRAG（~150k vs ~470k），但性能接近或超越，表明数据效率高。
5. 仅需2次LLM调用（一次重排序、一次生成），效率高于RankRAG（20次调用）。

### 优点

- **创新性**：将LLM输出质量作为奖励信号，通过强化学习动态优化重排序，解决了固定k的痛点。
- **有效性**：在多数据集、多骨干模型上验证了通用性和鲁棒性。
- **效率**：推理时仅需两次LLM调用，相对RankRAG有17倍加速。
- **可解释性**：动态k分布可视化（Figure 5）展示了RL训练前后的变化。
- **数据效率**：用更少训练数据达到顶级性能。

### 不足与局限

- 仅使用list-wise重排序，未探索point-wise或pair-wise方法。
- 优化以整体文档集合为单位，未考虑逐步选择或自适应终止。
- 仅使用DPO作为RL算法，未尝试PPO、GRPO等on-policy方法（但框架兼容）。
- 实验未报告多次运行的统计误差，单次结果可能存在波动。
- 奖励函数中多项系数采用相等值（0.2,0.2,0.2,0.2,0.2），未系统调优，但附录显示不同超参数下性能稳定。
- 训练数据仅150k，且主要来自Alpaca、KILT等公开数据集，领域泛化性需更多验证。

（完）
