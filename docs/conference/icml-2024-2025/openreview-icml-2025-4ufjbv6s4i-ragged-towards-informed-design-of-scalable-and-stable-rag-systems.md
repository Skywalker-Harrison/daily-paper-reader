---
title: "RAGGED: Towards Informed Design of Scalable and Stable RAG Systems"
title_zh: RAGGED：面向可扩展且稳定RAG系统的知情设计
authors: "Jennifer Hsia, Afreen Shaikh, Zora Zhiruo Wang, Graham Neubig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=4ufjBV6S4I"
tags: ["query:fie-rag"]
score: 6.0
evidence: RAG系统评估框架可转移至少样本叙实性推理
tldr: RAGGED框架系统评估了多种检索器和阅读器配置下的RAG性能，发现阅读器对噪声的鲁棒性是决定RAG稳定性和可扩展性的关键因素。该框架为设计适用于少样本叙实性推理的高效RAG系统提供了指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 788, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 824, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 854, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 851, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 847, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 598, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1746, \"height\": 1057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1738, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 735, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 823, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4ufjbv6s4i/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 827, \"height\": 568, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1463, \"height\": 993, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 704, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 415, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1393, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1392, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1340, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1305, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4ufjbv6s4i/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 815, \"height\": 1109, \"label\": \"Table\"}]"
motivation: RAG系统性能依赖配置，不恰当的设置会降低可靠性，需要系统性的评估方法。
method: 提出RAGGED框架，在多种检索器-阅读器配置、检索深度和数据集上进行大规模实验评估。
result: 发现阅读器对噪声的鲁棒性决定RAG系统稳定性和可扩展性，部分阅读器从更深检索中受益，另一些则因分心内容退化。
conclusion: RAGGED框架有助于指导RAG系统设计，提高其在不同任务中的稳定性和性能。
---

## Abstract
Retrieval-augmented generation (RAG) enhances language models by integrating external knowledge, but its effectiveness is highly dependent on system configuration. Improper retrieval settings can degrade performance, making RAG less reliable than closed-book generation. In this work, we introduce RAGGED, a framework for systematically evaluating RAG systems across diverse retriever-reader configurations, retrieval depths, and datasets. Our analysis reveals that reader robustness to noise is the key determinant of RAG stability and scalability. Some readers benefit from increased retrieval depth, while others degrade due to their sensitivity to distracting content. Through large-scale experiments on open-domain, multi-hop, and specialized-domain datasets, we show that retrievers, rerankers, and prompts influence performance but do not fundamentally alter these reader-driven trends. By providing a principled framework and new metrics to assess RAG stability and scalability, RAGGED enables systematic evaluation of retrieval-augmented generation systems, guiding future research on optimizing retrieval depth and model robustness.

---

## 论文详细总结（自动生成）

# 论文总结：RAGGED: Towards Informed Design of Scalable and Stable RAG Systems

## 1. 核心问题与整体含义

- **研究动机**：检索增强生成（RAG）系统通过集成外部知识提升语言模型性能，但其有效性严重依赖于系统配置（如检索深度、模型选择等）。不当配置可能导致性能下降，甚至不如无检索的封闭式生成。现有研究结论不一致（如检索深度增加带来提升还是退化），且缺乏系统评估框架。
- **整体含义**：本文旨在回答“何时以及为什么RAG有帮助或有害”，并提供一个系统框架来指导RAG系统设计。核心发现是**阅读器（Reader）对检索噪声的鲁棒性**是决定RAG稳定性和可扩展性的关键因素，而非仅依赖检索器质量。

## 2. 方法论

- **核心思想**：提出 **RAGGED**（Retrieval-Augmented Generation Generalized Evaluation Device）框架，系统评估不同读者-检索器配置、检索深度和数据集下的RAG性能。引入两个新指标：
  - **RAG稳定性得分（RSS）**：衡量模型在最优检索深度附近性能的波动程度。  
    `RSS = min_{k∈[k*-Δ, k*+Δ] \{k*}} (性能 at k / 性能 at k*)`  
    取窗口内最差比例，值越接近1表示越稳定。
  - **RAG可扩展性系数（RSC）**：衡量模型在检索深度增加时累积的性能增益，直到性能停滞或下降。  
    基于梯形法则积分 `RSC = Σ_{i=1}^{last gain} 0.5*(k_{i+1}-k_i)*(F1_i+F1_{i+1})`，并用阈值ε确定最后增益点。
- **关键技术细节**：
  - 阅读器行为分为两类：**improve-then-plateau**（随k增加先提升后平缓）和 **peak-then-decline**（先达到峰值后下降）。
  - 实验覆盖多种检索器（BM25、ColBERT、Contriever）和阅读器（FlanT5-XXL、Flan-UL2、LLaMA2/3系列、GPT-3.5、Claude-3-Haiku、GPT-4o部分）。
  - 额外分析：检索噪声切片（有/无黄金段落）、提示策略（是否要求关注相关段落）、重排序（Reranker）的影响。
- **算法流程**：对所有配置遍历k=1到50，计算F1和召回率，再计算RSS和RSC。同时对比无上下文基线（closed-book），并分析不同条件下的性能变化。

## 3. 实验设计

- **数据集与场景**：
  - **Natural Questions (NQ)**：Wikipedia单跳问答，包含2837个查询。
  - **HotpotQA**：Wikipedia多跳问答，需要综合多个段落推理，5600个查询。
  - **BioASQ (Task 11B)**：PubMed生物医学问答，3837个查询，评估领域专用性。
- **Benchmark**：以无上下文生成（closed-book）为基线，对比检索增强性能。还使用CRAG数据集进行初步验证。
- **对比方法**：
  - 检索器：BM25（词法）、ColBERT（神经）、Contriever（无监督密集）。
  - 阅读器：开源（FlanT5-XXL 11B、Flan-UL2 20B、LLaMA2 7B/70B、LLaMA3 8B/70B），闭源（GPT-3.5-turbo、Claude-3-Haiku、GPT-4o部分）。
  - 额外对比：重排序（reranker）、“相关”提示（relevant prompt）、有/无黄金段落条件、不同检索器之间的性能差异。

## 4. 资源与算力

- 论文明确提到：闭源模型调用花费约300美元。开源模型使用**NVIDIA A6000 GPU**，环境配备**60GB RAM**，平均响应时间约**1.1秒/查询**（batch size 50）。但**未明确**GPU数量、训练时长或具体训练算力消耗（所有实验均为推理评估，无模型训练）。

## 5. 实验数量与充分性

- **实验数量**：大规模系统性实验，涵盖：
  - 8种阅读器（含不同参数量） × 3种检索器 × 3个数据集 × 多个检索深度（1~50） → 数以千计的配置组合。
  - 消融实验包括：有/无黄金段落切片分析、提示与重排序组合、不同检索器对比（ColBERT vs BM25 vs Contriever）、RSS/RSC参数敏感性（ε和Δ变化）。
  - 额外验证：CRAG数据集、GPT-3.5 vs GPT-4o比较、LLM语义评估（Prometheus）。
- **充分性与公平性**：实验覆盖开放域、多跳、专业领域，比较充分。对比了无检索基线，控制了变量。但存在局限：只使用了F1作为主要指标（补充了LLM评估），未测试其他噪声类型（如对抗性、过时信息），提示策略单一，未涉及模型训练。

## 6. 主要结论与发现

1. **阅读器噪声鲁棒性是关键**：决定RAG稳定性和可扩展性的首要因素是阅读器能否过滤噪声，而不是检索器质量。
2. **两种阅读器行为**：
   - **improve-then-plateau**（如FlanT5、GPT-3.5）：对噪声鲁棒，随k增加性能提升并逐渐饱和，适合大检索深度。
   - **peak-then-decline**（如LLaMA、Claude-3-Haiku）：对噪声敏感，过早达到峰值后性能下降，需谨慎控制k。
3. **检索深度需动态调整**：更大k并非总是更好，最优k取决于阅读器特性。
4. **检索器提升不直接转化为阅读器增益**：即使ColBERT召回率高，对噪声敏感阅读器在深k下表现反而更差。
5. **提示和重排序影响有限**：重排序有帮助但不能改变阅读器基本趋势；提示对鲁棒阅读器无效，对敏感阅读器有一定帮助但在专业领域可能有害。
6. **多跳任务从检索中获益更多**：因为需要综合多个信息片段。
7. **专业领域（BioASQ）**：检索改进对性能提升更直接，因为领域术语提供了更强信号。

## 7. 优点

- **系统性**：提出统一框架RAGGED和量化指标（RSS/RSC），比传统单一k或F1更全面地评估RAG行为。
- **大规模实证**：覆盖多种模型、检索器、数据集和消融条件，结论具有较强泛化性。
- **揭示核心矛盾**：明确指出阅读器鲁棒性比检索质量更关键，挑战了“更好的检索=更好的RAG”的普遍假设。
- **实用导向**：为实践者提供具体指导（如对某些模型应限制检索深度，对另一些可大胆增加）。
- **可复现**：代码和框架公开，标准化评估流程。

## 8. 不足与局限

- **评估指标单一**：主要依赖F1，虽然补充了LLM语义评估，但未采用多种自动指标（如ROUGE、BLEU、准确率等）。
- **噪声类型覆盖有限**：仅使用自然检索产生的噪声，未涉及对抗性、过时、矛盾或精心构造的误导性文档。
- **提示策略简单**：仅测试一个“相关注意”指令，未探索更精细的提示工程或指令调优。
- **闭源模型黑盒**：无法分析内部机制，对LLaMA和Claude下降原因只能推测（如训练数据或架构）。
- **RSS对称窗口假设**：未考虑方向不对称性（论文提及但未深入），可能不完全反映过度检索与缺失检索的不同影响。
- **任务范围局限**：仅限问答任务，未评估生成、摘要等场景。
- **未评估训练策略**：未探究通过对噪声鲁棒性进行微调或指令调优是否能改变阅读器行为。

（完）
