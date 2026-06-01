---
title: "POQD: Performance-Oriented Query Decomposer for Multi-vector retrieval"
title_zh: POQD：面向性能的多向量检索查询分解器
authors: "Yaoyang Liu, Junlin Li, Yinjun Wu, zhen chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oktw116wt2"
tags: ["query:fie-rag"]
score: 7.0
evidence: 通过优化多向量检索的查询分解来提升RAG性能
tldr: 多向量检索在信息检索任务中表现优异，但其查询分解质量高度依赖人工且难以联合优化。POQD框架利用大语言模型进行查询分解，并通过大模型优化器搜索分解提示，同时提出端到端训练算法。实验表明该方法在多个IR基准上提升了RAG系统的检索效率。该工作为RAG系统的检索组件提供了可优化的分解策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 772, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 842, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 724, \"height\": 199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1653, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 2403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oktw116wt2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1750, \"height\": 2115, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1553, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1746, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 974, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 616, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1644, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 642, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oktw116wt2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 832, \"height\": 407, \"label\": \"Table\"}]"
motivation: 多向量检索依赖查询分解，但分解优化与下游RAG系统联合训练存在不可微且低效的问题。
method: 利用大语言模型生成查询分解，并通过基于大模型的优化器搜索最佳提示，配合端到端交替训练。
result: 在多个信息检索基准上，POQD显著提升了多向量检索的性能和RAG系统的效率。
conclusion: POQD提供了一种有效且可自动化的查询分解方法，可用于改进RAG系统的检索质量。
---

## Abstract
Although Multi-Vector Retrieval (MVR) has achieved the state of the art on many information retrieval (IR) tasks, its performance highly depends on how to decompose queries into smaller pieces, say phrases or tokens. However, optimizing query decomposition for MVR performance is not end-to-end differentiable. Even worse, jointly solving this problem and training the downstream retrieval-based systems, say RAG systems could be highly inefficient. To overcome these challenges, we propose Performance-Oriented Query Decomposer (POQD), a novel query decomposition framework for MVR. POQD leverages one LLM for query decomposition and searches the optimal prompt with an LLM-based optimizer. We further propose an end-to-end training algorithm to alternatively optimize the prompt for query decomposition and the downstream models. This algorithm can achieve superior MVR performance at a reasonable training cost as our theoretical analysis suggests. POQD can be integrated seamlessly into arbitrary retrieval-based systems such as Retrieval-Augmented Generation (RAG) systems. Extensive empirical studies on representative RAG-based QA tasks show that POQD outperforms existing query decomposition strategies in both retrieval performance and end-to-end QA accuracy. POQD is available at https://github.com/PKU-SDS-lab/POQD-ICML25.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：多向量检索（Multi-Vector Retrieval, MVR）通过将查询和文档分解为更细粒度的单元（如 token 或短语）并计算 MaxSim 得分，已在多项信息检索任务上取得最优性能。但现有 MVR 方法（如 ColBERT）通常将查询分解为单个 token，这种粗粒度的分解方式可能引入噪声（例如示例中 token “kong” 与无关图像产生高相似度），导致检索精度下降。
- **核心问题**：查询分解的质量直接影响 MVR 以及下游检索增强生成（RAG）系统的性能。然而，优化查询分解（生成更合适的子查询）是一个**不可微**的过程（子查询无法传播梯度），且与下游 RAG 模型联合训练效率极低。因此，如何自动、高效地生成最优的子查询是亟待解决的挑战。
- **整体含义**：提出一种面向性能的查询分解框架 POQD，通过 LLM 生成子查询并利用 LLM-based optimizer 搜索最优提示，再结合交替训练算法，在不显著增加训练成本的前提下显著提升 RAG 系统的检索与问答准确率。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- 使用一个 **LLM（Query Decomposer）** 根据输入查询生成若干子查询（短语级），另一个 **LLM（Prompt Optimizer）** 负责迭代优化生成子查询所用的**提示（prompt）**，使得子查询能够提升下游性能。
- 为解决不可微问题，将优化目标转化为**提示搜索**（prompt search），利用 LLM-based optimizer（基于 OPRO 框架）根据历史 prompt 及对应的损失值生成新的 prompt。
- 提出**端到端交替训练算法**（Algorithm 2），在外循环中优化提示（通过 Algorithm 1），在内循环中仅训练下游生成器模型几个 epoch，从而兼顾效率与性能。

### 关键技术细节
1. **提示优化（固定下游模型 Θ）**：
   - Algorithm 1：给定当前提示 `p_old`，初始化 `LS = [(p_old, L(Θ; p_old))]`。
   - 循环：用 Prompt Optimizer（输入历史 `LS`）生成新 prompt `p`；用 Query Decomposer 按 `p` 对训练集所有查询生成子查询；计算训练损失 `L(Θ; p)` 加入 `LS`；若损失下降不足 α 或重复 κ 次则终止。
   - 生成子查询后，需过滤掉不属于原查询的 token（减轻幻觉）。
2. **端到端训练（同时优化提示和下游模型）**：
   - Algorithm 2：随机初始化 `p_old`。
   - 外循环：调用 Algorithm 1 获得新提示 `p_new` 及相应子查询；若 `p_new == p_old` 则终止；否则固定 `p_new`，训练下游模型 Θ 共 `τ` 次迭代（默认 τ=3）；更新 `p_old ← p_new`。
   - 外循环结束后，用最终提示固定训练 Θ 至收敛。
3. **理论分析**（Theorem 4.4）：在 μ-PL* 条件和 L-smoothness 假设下，证明选择合适的 α 和 τ 可使 `L(Θ*(p_old); p_old) - L(Θ*(p_new); p_new) ≥ α - (1-μ/(2L))^τ M`，从而保证每次更新提示能降低收敛损失。

### 算法流程（文字说明）
- 输入：训练查询集合 `Q_train`，下游系统参数 Θ。
- 初始化随机提示 `p_old`。
- 重复：
  1. 固定 Θ，运行提示优化（Algorithm 1），输出优化后的提示 `p_new` 及对应的子查询。
  2. 若 `p_new` 未改变则终止。
  3. 固定 `p_new`，用生成的子查询训练下游模型 Θ 共 τ 步（最小化损失 `L(Θ; p_new)`）。
- 最后用最终提示训练 Θ 至收敛，得到最优参数 Θ*。

## 3. 实验设计

### 数据集与场景
- **图像问答（Image QA）**：WebQA（图像部分）、MultiModalQA、ManyModalQA。
- **文本问答（Text QA）**：WebQA（文本部分）、MultiModalQA（文本部分）、ManyModalQA（文本部分）。
- **多跳文本问答**：StrategyQA（仅用于端到端问答准确性评测，不报告检索指标，因为无 ground-truth 文档）。

### Benchmark 与对比方法
- **Dense retrieval**：传统单向量密集检索。
- **ColBERT**：原版 ColBERT，分 token 层次。
- **ColBERT-orig**：使用 ColBERT 自带的嵌入模型（fine-tuned BERT on MSMARCO）。
- **Supervised Query Decomposition (S-QD)**：基于 Llama3.1-8B 在 StrategyQA 上微调的序列到序列模型。
- **Unsupervised Query Decomposition (U-QD)**：OUNS 方法。
- **In-Context Learning based Query Decomposition (ICL-QD)**：人工设计提示进行 ICL。
- **In-Context Learning with Feedback (ICLF-QD)**：在 ICL 基础上增加子查询质量反馈。
- **POQD**（本文方法）。

### 实验设置细节
- 检索模型：文本使用 Sentence-Bert（默认），图像使用 CLIP（默认）。ColBERT 和 ColPali 使用各自嵌入模型。
- 生成器模型：单跳文本 QA 使用 Llama3.1-8B；图像 QA 使用 Llava-v1.5-7B；多跳 QA 使用冻结 GPT-4。
- 默认超参数：α=0.02，τ=3，κ=5。
- 检索 Top-1 图像，Top-2 文本。

## 4. 资源与算力

- 论文未明确说明使用的 GPU 型号、数量、总训练时长等具体算力信息。
- 仅在时间分析中提到：训练一个 epoch 最多约需 1 小时（对于大图像 QA 数据集），且总体训练时间主要由生成器训练主导，提示优化开销极小（图 4）。
- 因此，算力细节是缺失的。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验：分别在图像 QA 和文本 QA 上各 3 个数据集，报告检索准确率（Hit@1/Hit@2）和端到端问答准确率（Exact Match）。
  - 消融实验：α 的影响、τ 的影响、不同 LLM 作为分解器的影响、过滤步骤的影响、检索数量 K 的影响、不同生成器模型的影响、不同嵌入模型的影响。
  - 定性分析：展示分解子查询示例及检索图像对比。
  - 对比查询重写方法（额外对比）。
- **充分性**：实验覆盖了多个数据集、多种基线、多个消融维度，结果一致表明 POQD 优于所有对比方法。实验设计比较充分，消融实验验证了关键超参数和组件的作用。
- **公平性**：
  - 对 ColBERT 报告了两个版本（自有嵌入与默认嵌入），避免不公平比较。
  - 所有方法（除 ColBERT 外）使用相同的嵌入模型、生成器、训练策略。
  - 在 StrategyQA 上使用冻结 GPT-4 且仅替换检索方式，公平对比。
  - 但 S-QD 微调了 Llama3.1-8B，而 ICL/ICLF/POQD 使用同一 LLM 作为分解器（GPT-4 或 DeepSeek），可能存在模型能力差异。

## 6. 主要结论与发现

- POQD 在所有数据集上均取得了**最佳检索准确率**（Hit@1/2）和**最高端到端问答准确率**，提升幅度显著（例如在 MultiModalQA 图像 QA 上 QA 准确率提升高达 12.61%）。
- POQD 显著优于传统 token 级分解（ColBERT）和现有基于 LLM 的分解方法（ICL-QD、ICLF-QD、S-QD、U-QD）。
- 训练开销可控：提示优化时间远小于生成器训练时间，总体训练时间与常规 RAG 训练接近。
- 消融实验表明：α=0.02、τ=3 是效果与效率的合理折中；过滤步骤对性能有正面影响；POQD 在不同 LLM、不同生成器、不同嵌入模型下均表现鲁棒。
- 理论分析验证了交替训练算法能够保证每次提示更新降低收敛损失。

## 7. 优点

- **方法创新**：将查询分解的不可微优化转化为 LLM prompt 搜索，并设计交替训练算法，兼顾效率与性能，可无缝集成到现有 RAG 系统中。
- **理论支撑**：提供了收敛性证明，保障了算法的有效性。
- **实验全面**：覆盖图像和文本两种模态，单跳与多跳任务，多个数据集，大量消融，结果一致且显著。
- **实用性强**：代码开源，训练成本可控，推理时间中分解查询的开销可忽略，适合实际部署。

## 8. 不足与局限

- **算力资源未明确**：未报告 GPU 型号、数量、具体训练时间，不利于复现和成本评估。
- **对 LLM 的依赖**：使用两个 LLM（Prompt Optimizer 和 Query Decomposer），均为 GPT-4 或 DeepSeek，成本较高；虽实验显示改用较小模型仍有效，但未深入分析不同规模 LLM 的影响。
- **实验覆盖范围有限**：仅聚焦 RAG 问答任务，未在纯检索任务（如 MSMARCO）上验证；未见对比更前沿的查询分解方法（如基于可微搜索的方法）。
- **超参数敏感性**：α 和 τ 需要手动设置，虽给出了默认值，但在新任务上可能需要调优。
- **假设较强**：理论分析依赖于 μ-PL* 条件和 L-smoothness，这些在大型语言模型上是否严格成立存疑。
- **可能存在的偏差**：S-QD 使用了 StrategyQA 训练集，而其他方法（包括 POQD）未使用该数据集训练，导致比较不尽公平（尽管作者在消融中尝试了不同分解 LLM 来缓解）。

（完）
