---
title: Can Knowledge-Graph-based Retrieval Augmented Generation Really Retrieve What You Need?
title_zh: 基于知识图谱的检索增强生成真的能检索到你所需吗？
authors: "Junchi Yu, Yujie Liu, Jindong Gu, Philip Torr, Dongzhan Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=po0eyoYFUa"
tags: ["query:fie-rag"]
score: 5.0
evidence: 知识图谱RAG检索优化
tldr: 现有基于知识图谱的RAG方法在检索复杂查询所需准确且多样信息时存在困难。本文提出GraphFlow框架，利用过程奖励模型（PRM）来监督检索过程，使检索与查询的知识需求对齐。GraphFlow无需昂贵的过程级监督信号，即可从文本丰富的知识图谱中高效检索相关知识。实验显示，GraphFlow在多个真实世界查询上显著提升了检索准确性和多样性，为知识图谱增强的RAG提供了更可靠的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 988, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1234, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1305, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 632, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1123, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1251, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1138, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-po0eyoyfua/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1152, \"height\": 761, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-po0eyoyfua/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-po0eyoyfua/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1402, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-po0eyoyfua/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-po0eyoyfua/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1405, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-po0eyoyfua/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1185, \"height\": 693, \"label\": \"Table\"}]"
motivation: 现有KG-based RAG检索准确性和多样性不足，过程监督信号昂贵。
method: 提出GraphFlow，采用过程奖励模型对齐检索与查询知识需求。
result: 在多个真实查询上，GraphFlow检索准确性和多样性显著优于基线。
conclusion: 过程奖励模型可有效改善KG-based RAG的检索质量，降低监督成本。
---

## Abstract
Retrieval-Augmented Generation (RAG) based on knowledge graphs (KGs) enhances large language models (LLMs) by providing structured and interpretable external knowledge.
However, existing KG-based RAG methods struggle to retrieve accurate and diverse information from text-rich KGs for complex real-world queries.
Process Reward Models (PRMs) offer a way to align the retrieval process of KG-based RAG with query-specific knowledge requirements, 
but they heavily rely on process-level supervision signals that are expensive and hard to obtain on KGs.
To address this challenge, we propose GraphFlow, a framework that efficiently retrieves accurate and diverse knowledge required for real-world queries from text-rich KGs.
GraphFlow employs a transition-based flow matching objective to jointly optimize a retrieval policy and a flow estimator.
The flow estimator factorizes the reward of the retrieval outcome into the intermediate retrieval states.
Such reward factorization guides the retrieval policy to retrieve candidates from KGs in proportion to their reward.
This allows GraphFlow to explore high-quality regions of KGs that yield diverse and relevant results. 
We evaluate GraphFlow on the STaRK benchmark, which includes real-world queries from multiple domains over text-rich KGs. 
GraphFlow outperforms strong KG-RAG baselines, including GPT-4o, by 10\% on average in hit rate and recall. 
It also shows strong generalization to unseen KGs, demonstrating its effectiveness and robustness.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **背景**：基于知识图谱（KG）的检索增强生成（RAG）能够为大型语言模型（LLM）提供结构化和文本化的外部知识，在医疗、化学、物理等领域展现出潜力。
- **核心问题**：现有KG-based RAG方法（包括检索式和智能体式）在处理复杂查询时，难以同时保证**检索的准确性**和**多样性**。复杂查询（如“列出A大学发表的B主题论文”）不仅需要利用关系结构，还需要理解实体文本描述，且通常对应多个正确目标，现有方法容易漏检或检索内容重复。
- **过程奖励模型（PRM）的困境**：PRM理论上可以通过步骤级监督对齐检索行为，但获取KG上细粒度的过程奖励信号（每一步的好坏）成本极高，通常只能获得最终结果的好坏（结果奖励）。

## 2. 方法论：GraphFlow
- **核心思想**：将KG上的检索建模为一个多步决策过程，并采用**生成流网络（GFlowNet）** 的框架，使得采样到的检索轨迹的概率与其结果奖励成正比（`P(τ) ∝ R(τ)`）。这样既能保证高奖励轨迹被高频采样（准确性），又能自然促进多样性（避免只集中于少数最优轨迹）。
- **关键技术细节**：
  - **状态、动作、奖励定义**：状态为当前已访问节点文档集合+查询，动作为选择下一邻居节点，奖励由最终检索文档是否支持查询决定（0/1）。
  - **流估计与信用分配**：引入一个流估计器 `F(s)` 为每个中间状态分配非负的“流值”，该流值隐式地分解了最终奖励，从而在没有过程奖励信号的情况下，为每一步提供了训练信号。
  - **详细平衡目标（Detailed Balance with Local Exploration, DBLE）**：通过局部探索（在当前节点随机探索多个邻居轨迹），联合优化以下损失函数：
    ```
    L = Σ_i [log F(s_t) - log F(s'_{t+1,i}) + log P(s'_{t+1,i}|s_t)]^2
    ```
    其中 `P(s'|s)` 由LLM策略网络计算，`F` 由流头网络估计。设定边界条件 `log F(s0)=log F(sT)=0`（轨迹起点和终点流值相等），保证流守恒。
  - **基于LLM的实现**：使用LLaMA3-8B-Instruct作为骨干，添加策略头（Policy Head）和流头（Flow Head），通过LoRA高效微调。分别使用不同的提示模板编码状态和状态-动作对，利用最后token的embedding作为输入。
- **与SFT/PRM的对比**：SFT本质上是行为克隆（正样本强迫学习），PRM需要人工标注步骤偏好。GraphFlow通过流估计自动实现了过程监督，且更灵活。

## 3. 实验设计
- **数据集与Benchmark**：使用**STaRK benchmark**，包含三个真实世界的文本丰富KG：
  - **STaRK-AMAZON**（电商产品检索）
  - **STaRK-MAG**（学术文献检索，基于OGB和Microsoft Academic Graph）
  - **STaRK-PRIME**（生物医学实体检索）
- **对比方法**：
  - **检索式方法**：DenseRetriever（SentenceBERT）、G-Retriever（PCST算法）、SubgraphRAG（可学习子图检索）。
  - **智能体式方法**：ToG（树搜索）+ LLaMA3-8B/ GPT-4o、SFT（监督微调）、PRM（过程奖励模型）。所有智能体方法都使用LLaMA3-8B作为骨干（除ToG+GPT-4o外），且GraphFlow与SFT、PRM使用相同训练数据。
- **评估指标**：Hit@1/5、MRR（准确性）；Recall@20和去重Recall@20（多样性）。所有方法对每个查询检索20次。

## 4. 资源与算力
- 论文在附录G明确说明：所有实验使用**8或16块NVIDIA A800-SXM4-80GB GPU**，以及**56个Intel Xeon Platinum 8336C CPU**。
- 训练细节：LoRA适配器（秩r=32），batch_size=1（8 GPU），梯度累积步数2，学习率1e-5，训练1个epoch（在STaRK三个数据集上分别训练，每个数据集规模不同，但训练一轮即收敛）。

## 5. 实验数量与充分性
- **实验组数**：共呈现了3张主表（Table 1-3）和4张主图（Figure 3-4），以及附录中的多个补充实验（跨域泛化、不同难度级别的多样性分析）。
- **充分性评价**：
  - 对比了多种主流基线（检索式2-3种，智能体式3-4种），且包含了使用GPT-4o的强基线。
  - 在三个不同领域、不同规模的数据集上验证，覆盖电商、学术、生物医学。
  - 不仅报告了准确率，还专门报告了多样性指标（去重Recall），并利用Seper分数量化检索对QA的信息增益。
  - 进行了跨域泛化实验（在一个域上训练，在另一个域上测试）和困难案例分析（按目标数量分层）。
- **公平性**：所有智能体方法（SFT, PRM, GraphFlow）使用相同的LLM backbone（LLaMA3-8B）、相同的LoRA设置、相同的训练数据，并进行了重排序（rerank）实验，确保比较公平。

## 6. 主要结论与发现
- **GraphFlow在检索准确性和多样性上全面超越现有方法**：在STaRK的三个数据集上，Hit@1、Hit@5、MRR、Recall@20、D-R@20等指标均显著优于最强基线ToG+GPT-4o（平均提升约10%）。
- **无需过程奖励信号**：GraphFlow仅使用结果奖励（是否检索到正确答案）就能实现过程级别的指导，将PRM的成本降至零。
- **更强的跨域泛化能力**：在未见过的KG上，GraphFlow的Hit@1仍保持领先，说明其避免了对少数目标的过拟合。
- **在困难查询上表现突出**：当查询对应15个以上正确目标时，GraphFlow的多样性优势更加明显。

## 7. 优点
- **方法论创新**：将GFlowNet引入KG-based RAG，巧妙解决了过程监督缺失问题，实现了“无需过程奖励的过程对齐”。
- **兼顾准确性与多样性**：传统方法（SFT/PRM）倾向于最大化似然，会导致检索结果集中；GraphFlow通过奖励比例采样自然促进多样性，且不牺牲准确性。
- **实现高效**：使用LoRA微调LLM，训练仅需1个epoch，即可达到显著优于冻结GPT-4o的效果，计算成本可控。
- **实验设计严谨**：多指标、多数据集、多难度级别、跨域验证，且包含了很强的GPT-4o基线，结论可靠。

## 8. 不足与局限
- **依赖初始实体识别**：检索过程需要先定位起始节点（通过向量相似度），如果初始节点选择错误，后续轨迹可能无效。
- **计算开销仍然存在**：虽然训练成本低，但推理阶段每次探索需要调用LLM评估多个候选动作（局部探索时k=4），在大型KG上可能仍有延迟。
- **泛化实验仅覆盖两个新域**：附录提到“我们只在两个新域上评估了泛化能力”，可能不够充分（原文仅评价了跨域，未明确两个域的来源，但实际STaRK有三个域，跨域泛化可能是在其中两个训练，第三个测试）。
- **缺乏消融实验**：未对局部探索数量k、流头设计、边界条件等超参数进行系统性消融分析，难以判断各部分贡献。
- **下游任务验证有限**：论文主要评估检索结果的质量，未展示将这些检索结果输入到下游LLM后的最终问答或生成效果（虽然用了Seper分数近似，但缺失端到端评估）。
- **潜在偏差**：STaRK数据集本身可能包含特定领域的偏差（如学术、生物医学），在其他领域（如法律、金融）的表现未知。

（完）
