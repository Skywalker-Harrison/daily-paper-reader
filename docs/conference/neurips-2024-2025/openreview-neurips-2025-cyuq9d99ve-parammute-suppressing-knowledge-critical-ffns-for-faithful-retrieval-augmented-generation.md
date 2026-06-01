---
title: "ParamMute: Suppressing Knowledge-Critical FFNs for Faithful Retrieval-Augmented Generation"
title_zh: ParamMute：抑制知识关键型前馈网络以实现忠实检索增强生成
authors: "Pengcheng Huang, Zhenghao Liu, Yukun Yan, Haiyan Zhao, Xiaoyuan Yi, Hao Chen, Zhiyuan Liu, Maosong Sun, Tong Xiao, Ge Yu, Chenyan Xiong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CyUq9D99vE"
tags: ["query:fie-rag"]
score: 9.0
evidence: 抑制LLM内部参数知识以提升RAG忠实性，直接相关于事实性推理
tldr: ParamMute研究发现RAG的不忠实生成与中深层前馈网络子集过度激活相关。通过抑制这些知识关键型FFN单元，强制模型依赖外部检索证据。在多项事实性基准上显著提升忠实性，且不损害通用能力。该工作直接面向RAG事实性改进，为少样本事实性推理提供了关键方法：通过控制内部知识影响，使模型专注于检索到的句子语言学证据进行推理。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1418, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1412, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1412, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1427, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 451, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1421, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cyuq9d99ve/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 694, \"height\": 319, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 661, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1387, \"height\": 857, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1387, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 652, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1305, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 467, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 514, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1087, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cyuq9d99ve/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1169, \"height\": 839, \"label\": \"Table\"}]"
motivation: RAG模型仍会产生与检索证据矛盾的不忠实输出，源于内部参数知识的过度干扰。
method: 识别并抑制中深层FFN中导致不忠实生成的子集，促使模型依赖外部证据。
result: 在不损失模型通用能力的情况下，大幅提升RAG输出对于检索证据的忠实性。
conclusion: ParamMute有效缓解了RAG不忠实问题，对基于语言学特征的句子事实性推理具有直接价值。
---

## Abstract
Large language models (LLMs) integrated with retrieval-augmented generation (RAG) have improved factuality by grounding outputs in external evidence. However, they remain susceptible to unfaithful generation, where outputs contradict retrieved context despite its relevance and accuracy. Existing approaches aiming to improve faithfulness primarily focus on enhancing the utilization of external context, but often overlook the persistent influence of internal parametric knowledge during generation. In this work, we investigate the internal mechanisms behind unfaithful generation and identify a subset of mid-to-deep feed-forward networks (FFNs) that are disproportionately activated in such cases. Building on this insight, we propose Parametric Knowledge Muting through FFN Suppression (ParamMute), a framework that improves contextual faithfulness by suppressing the activation of unfaithfulness-associated FFNs and calibrating the model toward retrieved knowledge. To evaluate our approach, we introduce CoFaithfulQA, a benchmark specifically designed to evaluate faithfulness in scenarios where internal knowledge conflicts with accurate external evidence. Experimental results show that ParamMute significantly enhances faithfulness across both CoFaithfulQA and the established ConFiQA benchmark, achieving substantial reductions in reliance on parametric memory. These findings underscore the importance of mitigating internal knowledge dominance and provide a new direction for improving LLM trustworthiness in RAG. All codes are available at https://github.com/OpenBMB/ParamMute.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：尽管检索增强生成（RAG）通过外部证据提升了LLM的生成事实性，但模型仍会产出与检索上下文相矛盾的“不忠实”输出。现有方法主要聚焦于增强对外部上下文的利用（如提示策略、解码技巧、微调对齐），却忽视了内部参数知识（parametric knowledge）在生成过程中的持久影响。
- **研究动机**：本文首次从内部机制层面探究不忠实生成的成因，发现中深层前馈网络（FFN）子集在不忠实生成时呈过度激活状态，表明这些FFN存储了与检索证据冲突的强内部知识，抑制其激活可迫使模型转向信赖检索证据。
- **整体含义**：本文指明提升RAG忠实性的新方向——主动控制内部参数知识的干涉，而非仅强化外部上下文融合。这项工作对基于语言学事实性推理（如句子级证据利用）具有直接借鉴价值。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：提出“Parametric Knowledge Muting through FFN Suppression (ParamMute)”框架，分两阶段实现：
    1. **抑制阶段**：识别并抑制那些与不忠实生成高度相关的FFN层（称为UA-FFNs），减少内部参数知识的影响。
    2. **适应阶段**：通过偏好优化校准模型，使其偏好利用外部检索知识进行生成。

- **关键技术细节**：
    - **UA-FFNs识别**：基于激活比（activation ratio）度量。对每个FFN层，在不忠实子集 $D^-$ 和忠实子集 $D^+$ 上计算平均激活比，定义激活间隙 $\Delta R^l$，选取前 $N$ 个间隙最大的层作为UA-FFNs。
    - **激活抑制**：对选中的UA-FFNs层，引入抑制系数 $\lambda \in [0,1]$，重构FFN计算公式：
      $$\text{FFN}^l(x_i^l) = \left(\lambda \cdot \sigma(K^l x_i^l)\right)^\top V^l, \quad \text{if } l \in L_{\text{sup}}$$
      $\lambda=0$ 时完全抑制该层，$\lambda=1$ 保持原始行为。
    - **知识适应模块**：联合优化两个损失：
        - 知识增强训练 $L_{\text{KAT}}$：最大化给定上下文 $c$ 下生成真实答案 $y^*$ 的对数似然。
        - 知识偏好优化 $L_{\text{KPO}}$：采用最大间隔损失，鼓励模型在有无上下文时都偏向外部知识：
          $$L_{\text{KPO}} = \max\left(0,\ \gamma - \log P(y^*|q,c) + \log P(y^*|q)\right)$$
    - 训练时采用LoRA高效微调，降低参数量。

## 3. 实验设计：数据集、benchmark、对比方法

- **数据集 & Benchmark**：
    - **CoFaithfulQA**（本文新构建）：从HotpotQA、NewsQA、NQ、SearchQA、SQuAD、TriviaQA六个开放域QA数据集构建，通过自一致性过滤和多模型冲突检测获得忠实/不忠实子集，专注于内部知识与外部证据冲突的现实场景。
    - **ConFiQA**（已建立benchmark）：三个子集（Question Answering、Multi-hop Reasoning、Multi-Conflicts），共18,000个实例。
    - **FaithEval**（附加评估）：对抗性上下文场景。
- **对比方法**（均基于LLaMA3-8B-Instruct骨干）：
    - Prompt-based：Attr prompt、O&I prompt
    - Decoding-based：COIECD（熵约束对比解码）
    - Fine-tuning：SFT、KAFT（反事实数据增强）
    - Alignment：C-DPO（上下文DPO）、DDR（可微数据奖励）
- **评估指标**：上下文召回率（ConR↑）、记忆召回率（MemR↓）、记忆率（MR = MemR/(MemR+ConR)↓），反映模型对检索证据 vs. 内部知识的偏好程度。

## 4. 资源与算力

- 论文**未明确说明**具体的GPU型号、数量及总训练时长。
- 训练细节：总训练步数2100，batch size 32，学习率1e-4，采用LoRA（r=16）以节省显存。所有实验在单个节点上完成，推测使用多张GPU（如A100或同等），但未公开具体配置。

## 5. 实验数量与充分性

- **实验覆盖广泛**：主结果在CoFaithfulQA（6子集）和ConFiQA（3子集）上报告；扩展至FaithEval；噪声检索设置；不同骨干模型（LLaMA-3.2-1B/3B、Qwen-2.5-0.5B~14B）共9种模型；消融实验（组件、抑制策略、层选择）；超参数敏感性（λ、N、α:β）；知识使用行为剖析；因果干预验证。
- **约15组以上关键实验**，涵盖多种场景和变体，统计上充分。
- **公平性**：所有基线采用相同骨干和训练数据量；消融实验控制变量（如抑制层位置、组件移除）。整体实验设计客观、可重复。

## 6. 论文的主要结论与发现

- ParamMute在CoFaithfulQA上平均ConR提升约6.17%，MemR降低约4%；在ConFiQA上MemR降低54.63%（绝对值）。
- 抑制UA-FFNs（而非MHA、整个层或随机参数）是提升忠实性的关键；底部/随机层抑制效果差。
- 在LLaMA和Qwen系列（1B~14B）上均有效，且对较大模型效果更显著（更大模型更强地依赖参数知识，抑制收益更大）。
- 抑制后模型对上下文答案的语义相似度提高，对参数答案相似度降低；无上下文时困惑度剧增，有上下文时困惑度极低，表明成功校准知识使用偏好。
- 软抑制机制（调整λ）可实现灵活的知识控制，而不损害非上下文任务（如数学推理）性能（λ=0时下降，λ=1时恢复甚至超过基线）。

## 7. 优点

- **方法创新**：从机制层面（FFN激活）而非仅行为层入手解决问题，首次识别并抑制与不忠实生成直接相关的FFN子集。
- **构建高质量基准CoFaithfulQA**：通过自一致性过滤+双模型冲突检测+人工验证，确保反映真实知识冲突场景，区别于现有合成反事实数据集。
- **实验全面且严谨**：覆盖多数据集、多模型规模、多种设置（无噪声/有噪声、有无上下文任务）、多组件消融，结论可靠。
- **可控性强**：软抑制系数λ和偏好损失中的动态γ提供了灵活的知识权衡，实际部署时可调节。
- **开源代码与数据**：促进可重复性研究。

## 8. 不足与局限

- **检索设置受限**：CoFaithfulQA构建时保证上下文包含答案，未覆盖检索失败导致的“未忠实”场景，实际RAG中检索质量波动可能影响结论外推。
- **抑制粒度较粗**：当前抑制整个FFN层，未探索神经元或更细粒度干预，可能误抑一些对通用能力有用的知识（但通过调节λ可缓解）。
- **模型规模局限性**：实验限于8B以下的模型，虽然包括14B，但更大模型（如70B+）中FFN激活模式是否一致尚未验证。
- **未评估训练效率**：未提供训练时间、显存占用等具体数据，实际部署成本不明。
- **伦理考量**：抑制内部知识可能被误用于掩盖事实或引入偏见，论文虽在附录中提及，但未提供具体的防护措施。

（完）
