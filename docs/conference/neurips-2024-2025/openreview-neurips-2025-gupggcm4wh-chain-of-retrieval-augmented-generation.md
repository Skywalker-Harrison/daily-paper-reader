---
title: Chain-of-Retrieval Augmented Generation
title_zh: 检索链增强生成
authors: "Liang Wang, Haonan Chen, Nan Yang, Xiaolong Huang, Zhicheng Dou, Furu Wei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gUPGGCM4WH"
tags: ["query:fie-rag"]
score: 8.0
evidence: 检索链增强生成实现多步推理，可应用于少样本事实性推理
tldr: CoRAG提出一种训练o1风格RAG模型的方法，允许模型逐步检索和推理后再生成答案。通过拒绝采样自动生成中间检索链，弥补现有RAG数据只提供最终答案的不足。实验表明多步检索策略显著提升了复杂查询的准确性。该方法可直接应用于少样本事实性推理任务，动态检索相关句子特征以支持推理过程。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1352, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1375, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1426, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gupggcm4wh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 379, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1382, \"height\": 911, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1360, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 923, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1240, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1417, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gupggcm4wh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1394, \"height\": 554, \"label\": \"Table\"}]"
motivation: 传统RAG单步检索难以应对复杂查询，需要多步动态检索以优化推理。
method: 训练RAG模型在推理过程中逐步重构查询并多次检索，使用拒绝采样生成中间检索链。
result: 在多个复杂推理基准上显著优于单步RAG，且解码策略可扩展计算资源。
conclusion: CoRAG为复杂查询的RAG推理建立了新范式，对少样本推理任务具有直接应用价值。
---

## Abstract
This paper introduces an approach for training o1-like RAG models that retrieve and reason over relevant information step by step before generating the final answer. Conventional RAG methods usually perform a single retrieval step before the generation process, which limits their effectiveness in addressing complex queries due to imperfect retrieval results. In contrast, our proposed method, CoRAG (Chain-of-Retrieval Augmented Generation), allows the model to dynamically reformulate the query based on the evolving state. To train CoRAG effectively, we utilize rejection sampling to automatically generate intermediate retrieval chains, thereby augmenting existing RAG datasets that only provide the correct final answer. At test time, we propose various decoding strategies to scale the model's test-time compute by controlling the length and number of sampled retrieval chains. Experimental results across multiple benchmarks validate the efficacy of CoRAG, particularly in multi-hop question answering tasks, where we observe more than $10$ points improvement in EM score compared to strong baselines. On the KILT benchmark, CoRAG establishes a new state-of-the-art performance across a diverse range of knowledge-intensive tasks. Furthermore, we offer comprehensive analyses to understand the scaling behavior of CoRAG, laying the groundwork for future research aimed at developing factual and grounded foundation models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统检索增强生成（RAG）方法通常仅执行一次检索步骤，然后利用检索结果生成答案。这一范式在应对复杂查询（如多跳问答）时存在瓶颈，因为单次检索无法全面获取所需信息，检索质量直接影响最终生成的可靠性。
- **研究动机**：受到人类解决问题时逐步迭代搜索信息的启发，论文旨在训练类似 OpenAI o1 风格的语言模型，使其能够在生成最终答案之前，动态地、逐步地进行检索和推理，从而突破单次检索的局限。
- **整体含义**：通过显式训练语言模型进行逐步检索（而非仅依赖 prompt 或蒸馏），CoRAG 框架将多步检索与推理过程融合，能够在测试时通过控制检索步数和采样数量来扩展计算资源，实现性能与效率的权衡，为构建更真实、可靠的 RAG 系统奠定基础。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：提出 CoRAG（Chain-of-Retrieval Augmented Generation）框架，让模型在推理过程中**迭代生成子查询并检索**，每步基于当前状态（之前的子查询和子答案）动态重构下一个子查询，从而实现逐步推理和错误修正。
- **关键技术细节**：
  - **检索链生成（Rejection Sampling）**：对于仅提供最终答案的 RAG 数据集，利用一个 LLM（如 Llama-3.1-8B-Instruct）采样生成多条检索链。每条链包含一系列子查询 \(Q_{1:L}\) 和对应的子答案 \(A_{1:L}\)，直到链长达到最大值或子答案正确。然后计算正确答案在给定链条件下的对数似然，选择得分最高的链来增强训练数据。
  - **模型训练**：在增强后的数据上，对基础 LLM 进行全参数微调，使用标准的下一个 token 预测目标，同时训练三个任务：
    - 子查询预测：\(\mathcal{L}_{\text{sub\_query}} = -\log P(Q_i \mid Q, Q_{<i}, A_{<i})\)
    - 子答案预测：\(\mathcal{L}_{\text{sub\_answer}} = -\log P(A_i \mid Q_i, D_{1:k}^{(i)})\)
    - 最终答案预测：\(\mathcal{L}_{\text{final\_answer}} = -\log P(A \mid Q, Q_{1:L}, A_{1:L}, D_{1:k})\)
    训练时使用与数据生成相同的 prompt 模板，使得微调后的模型可以用于下一轮拒绝采样（迭代训练）。
  - **测试时缩放（Test-time Scaling）**：提供多种解码策略来控制测试时的计算量：
    - **Greedy Decoding**：顺序生成 L 个子查询及对应的子答案，然后生成最终答案。
    - **Best-of-N Sampling**：采样 N 条检索链（温度 0.7），以条件对数似然计算的“无相关信息”惩罚分数最低的链作为最佳链，用于最终答案生成。
    - **Tree Search**：广度优先搜索变体，每步扩展多个子查询，进行多次 rollout，选择平均惩罚分数最低的状态继续扩展。
  - **早停机制**（可选）：训练一个额外的停止预测任务，模型在每步后判断信息是否足够，通过调整“Yes”token 的 logit bias 控制停止时机。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **数据集与场景**：
  - **多跳问答**：2WikiMultihopQA、HotpotQA、Bamboogle、MuSiQue。这些数据集需要模型进行多步推理才能回答。
  - **KILT 基准**：涵盖实体链接（AIDA、WnWi、WnCw）、槽填充（T-REx、zsRE）、开放域问答（NQ、HotpotQA、TriviaQA）和事实验证（FEVER）等多样化知识密集型任务，使用隐藏测试集评估。
- **基准对比方法**：
  - 多跳问答：对比了 Few-shot Llama-3.1-8B-Instruct、GPT-4o、Self-RAG-7B、ITER-RETGEN、DRAG、IterDRAG（基于 Gemini 1.5 Flash）、Search-o1-32B（基于 QwQ 和 Bing 搜索），以及一个微调的 Llama-8B 基线（使用相同检索器但无检索链增强）。
  - KILT 基准：对比了 KILT-RAG、SEAL、Atlas-11B、RA-DIT 65B、FiD with RS 以及“Previous Best”（截至 2025-01-10 的公开排行榜最高分）。

## 4. 资源与算力
- 论文明确说明了训练资源：
  - 使用 **8 张 A100 GPU** 进行训练。
  - 多跳问答模型训练耗时 **< 6 小时**（125k 训练样本）。
  - KILT 模型训练耗时 **约 30 小时**（660k 训练样本）。
- 检索链生成阶段使用了 Llama-3.1-8B-Instruct 进行拒绝采样，需要额外的 GPU 时间，但未给出具体数字。论文提到可以通过使用更弱的 LLM（如 Llama-3B）来降低生成成本（弱到强泛化）。

## 5. 实验数量与充分性
- **实验数量**：论文进行了多组实验：
  - 主实验：4 个多跳 QA 数据集上的对比（Table 1），KILT 隐蔽测试集上的对比（Table 2）。
  - 测试时缩放实验：4 个多跳数据集上不同链长 L 和采样数 N 的性能与 token 消费关系（Figure 3），并绘制帕累托前沿。
  - 消融实验：迭代训练、蒸馏 GPT-4o、弱到强泛化、不同检索器（E5-base、BM25）、不同采样温度、不同解码策略在 KILT 验证集上的结果（Table 3, Table 7, Figure 4 等）。
  - 早停机制分析（Figure 5）。
  - 检索召回率对比（Table 4）。
  - 扩展到其他模型族（Qwen3-4B/8B）的实验（Table 9）。
  - 训练数据生成计算量缩放实验（Figure 6）。
  - 无微调情况下的测试时缩放（Figure 7）。
- **充分性与公平性**：实验较为充分，覆盖了多种任务类型和模型规模。对比方法包括强基线和最新工作（如 Search-o1-32B）。论文还报告了 95% 置信区间（Appendix C），承认 Bamboogle 数据集方差大。但部分对比方法（如 DRAG、IterDRAG）基于不同的基础模型（Gemini 1.5 Flash），且 CoRAG 使用了微调，而部分基线（如 DRAG）采用少样本设置，可能造成不公平。论文承认了这一点并指出微调带来了优势。

## 6. 论文的主要结论与发现
- CoRAG 在多跳问答任务上显著优于所有强基线，在 MuSiQue 上 EM 提升超过 10 个点。在 2WikiMultihopQA 上 EM 达到 72.5%，相比微调基线（55.1%）大幅提升。
- 在 KILT 基准上，CoRAG-8B 在所有任务上（除 FEVER 略低于 Atlas-11B）取得了新的最优结果。
- **测试时缩放规律**：增加检索链长度 L 可带来性能提升，但收益递减；增加最佳-N 采样的 N 值对更难的数据集（如 MuSiQue）更有效。EM 与 token 消耗大致呈对数线性关系。
- **检索召回率提升**：CoRAG 通过多步检索显著提高了检索召回率，在 Bamboogle 上 R@10 从 31.2% 提升到 59.2%。
- **鲁棒性**：对不同质量的检索器（E5-large、E5-base、BM25）均有提升，且能通过弱到强泛化（用 3B 模型生成链训练 8B 模型）取得接近的效果。
- **早停机制**：能节省 token 但会牺牲性能，最优配置取决于数据集。
- **自我修正能力**：模型能够在检索链中纠正初始错误，例如在例四中最终正确地定位了诗人的国家。

## 7. 优点
- **方法创新性**：首次将显式的逐步检索训练与测试时计算缩放相结合，提出了一种训练 o1 风格 RAG 模型的实用框架。
- **自动化数据增强**：通过拒绝采样自动生成中间检索链，避免了手动标注，使方法易于扩展到多个数据集。
- **多种解码策略**：提供贪婪、最佳-N 采样、树搜索等灵活控制测试时计算的手段，并进行了系统的帕累托前沿分析。
- **全面的实验分析**：不仅报告了最终性能，还对测试时缩放、早停、检索器鲁棒性、弱到强泛化、训练数据生成计算等多个维度进行了深入分析，提供了丰富的经验证据。
- **跨模型族验证**：在 Qwen3 系列上也验证了有效性，表明框架不局限于 Llama 架构。
- **代码与数据开源**：提供了 GitHub 仓库，有利于复现和后续研究。

## 8. 不足与局限
- **任务覆盖局限**：论文主要聚焦于短答案、易验证的 RAG 任务（多跳 QA、实体链接等），未涉及长文本生成任务（如摘要、报告生成）。长文本评估指标缺乏，且检索链的积累可能引入噪声。
- **与基线比较的公平性**：部分基线（如 DRAG、IterDRAG）未经过微调，而 CoRAG 经过了全参数微调，虽然论文承认这一点，但性能优势部分可能来自微调而非检索链机制本身。
- **计算成本**：拒绝采样生成检索链需要大量 GPU 时间（尤其是使用 8B 模型），虽然提出了弱到强泛化以降低生成成本，但生成过程仍可能成为实际部署的瓶颈。
- **早停机制的代价**：学习停止虽然节省 token，但性能下降明显，实际应用时需谨慎权衡。
- **真实世界应用风险**：尽管旨在提高事实性，但模型仍存在幻觉风险，尤其在复杂长链推理中，任何一步的错误可能积累。对实时性要求高的场景，多步检索可能带来延迟。
- **KILT 上部分任务提升不明显**：对于单步检索即可解决的任务（如 NQ、TriviaQA），CoRAG 的优势较小，可能不适合对所有查询使用相同的多步策略，需要动态决策。

（完）
