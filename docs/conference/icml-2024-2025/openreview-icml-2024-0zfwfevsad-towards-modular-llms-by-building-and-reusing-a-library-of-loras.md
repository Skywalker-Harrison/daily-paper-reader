---
title: Towards Modular LLMs by Building and Reusing a Library of LoRAs
title_zh: 通过构建和重用LoRA库实现模块化大语言模型
authors: "Oleksiy Ostapenko, Zhan Su, Edoardo Ponti, Laurent Charlin, Nicolas Le Roux, Lucas Caccia, Alessandro Sordoni"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=0ZFWfeVsaD"
tags: ["query:fie-rag"]
score: 5.0
evidence: 模块化LoRA库通过路由实现少样本任务泛化，可关联少样本RAG适应
tldr: 本文提出基于模型聚类的MBC方法构建LoRA库，以及Arrow路由机制实现零样本和少样本任务泛化。该方法可复用到RAG场景，通过预训练的适配器库快速适应新任务，减少计算开销。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 787, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 770, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 879, \"height\": 539, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 746, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 687, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 656, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1682, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1656, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1664, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1655, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1654, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1771, \"height\": 2067, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 2075, \"label\": \"Table\"}]"
motivation: 面对大量参数高效适配器，如何重用它们以提升新任务性能。
method: 提出MBC聚类方法构建适配器库，以及Arrow零样本路由机制动态选择相关适配器。
result: 在多个少样本任务上优于现有方法，实现了有效的任务泛化。
conclusion: 通过适配器库和路由机制，可实现模块化LLM的高效任务扩展。
---

## Abstract
Given the increasing number of parameter-efficient adapters of large language models (LLMs), how can we reuse them to improve LLM performance on new tasks? We study how to best build a *library* of adapters given multi-task data and devise techniques for both *zero-shot* and *supervised* task generalization through *routing* in such library. We benchmark existing approaches to build this library and introduce model-based clustering, $\texttt{MBC}$, a method that groups tasks based on the similarity of their adapter parameters, indirectly optimizing for transfer across the multi-task dataset. In order to reuse the library, we present a novel zero-shot routing mechanism, $\texttt{Arrow}$, which enables dynamic selection of the most relevant adapters for new inputs without the need for retraining. We experiment with several LLMs, such as Phi-2 and Mistral, on a wide array of held-out tasks, verifying that MBC-based adapters and Arrow routing lead to superior generalization to new tasks. Thus, we make steps towards creating modular, adaptable LLMs that can match or outperform traditional joint training.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：随着大语言模型（LLM）参数高效适配器（如LoRA）数量日益增多，如何有效构建并重用这些适配器库，以提升模型对新任务的泛化能力（包括零样本和少样本监督场景）？

- **研究动机**：开源社区中大量独立训练的LoRA适配器已形成隐式“库”，但现有方法通常需要联合训练或访问训练数据才能路由。论文旨在实现一种**模块化LLM**：先构建适配器库，再设计无需重训练的路由机制，使各适配器能按需组合，从而匹配甚至超越传统联合训练的性能。

- **整体含义**：提出端到端的模块化方案，包括库构建（MBC）和路由（Arrow），为LLM的协作训练、异步更新和资源高效适配提供了新范式，有潜力降低计算门槛并促进模型复用。

## 2. 论文提出的方法论

### 2.1 库构建方法

- **核心思想**：利用任务间LoRA参数的相似性作为代理指标指导任务聚类，然后为每个聚类训练一个共享适配器，从而在减少任务干扰的同时促进正向迁移。

- **关键技术细节**：
  - **模型聚类（MBC）**：
    1. 先对每个任务独立训练一个LoRA适配器（私人适配器）。
    2. 将所有LoRA参数展平并拼接成矩阵，通过SVD降维。
    3. 计算任务间余弦相似度矩阵，用K-means聚类，得到K个任务簇。
    4. 合并每个簇内所有任务的训练数据，为每个簇训练一个LoRA适配器。
  - **控制计算量**：第一阶段用40%训练步数，第二阶段用60%，总步数与基线一致。

- **对比的其他库构建方法**：
  - **Private**：每个任务独立训练，无信息共享。
  - **Shared**：所有任务联合训练一个适配器。
  - **Poly / MHR**：联合训练K个基适配器，每个任务由基适配器线性组合表示。

### 2.2 路由方法

- **零样本路由（Arrow）**：
  - 对每个LoRA适配器（在每层）进行SVD分解，取右第一奇异向量作为该适配器的“原型”。
  - 推理时，对每个token的隐藏状态，计算其与所有原型点积的绝对值作为logits，选择top-k个适配器，然后线性组合其参数。
  - **优势**：无需训练数据，无需联合训练，逐层逐token路由，计算高效。

- **其他零样本路由对比**：
  - **μ路由**：均匀平均所有适配器参数。
  - **TP路由**：训练一个任务预测器，根据输入预测任务，再选择对应适配器。
  - **CM路由**：用隐藏表示均值作为原型，计算与当前隐藏状态的余弦相似度。

- **监督路由**：
  - **Poly路由**：通过学习任务专属路由系数（参数）组合适配器。
  - **LoraHub路由**：用无梯度优化学习路由系数。
  - **π-tuning**：基于Fisher信息矩阵嵌入检索相似适配器并微调。

## 3. 实验设计

### 3.1 数据集与场景

- **多任务训练数据**：Flan v2中的256个任务（排除SNI任务）。
- **零样本评估**：10个常见下游任务，包括常识推理（WinoGrande, HellaSwag, PIQA）、问答（BoolQ, OpenbookQA, ARC-easy/hard）、代码（HumanEval, MBPP）、通用推理（BBH）。
- **监督适配评估**：12个保留的SNI任务（每个任务不同类别），使用100%和10%训练数据两种设置。
- **额外实验**：还包括StableLM 3B上的零样本实验，以及数据低至0.5%的少样本实验。

### 3.2 基座模型与训练细节

- **基座模型**：Phi-2（2.8B）、Mistral 7B，以及部分实验中的StableLM 3B。
- **LoRA配置**：rank=4，dropout=0.05，学习率1e-4，仅修改注意力层和输出投影。
- **簇数量**：默认K=10（基于上游验证损失和下游性能的最优选择）。
- **MBC阶段分配**：第一阶段40%步数训练私人适配器，第二阶段60%训练聚类适配器。

### 3.3 对比方法

- **基线方法**：
  - **Base**：不做任何适配的基座模型。
  - **FullFT**：全参数微调。
  - **Shared**：单LoRA联合训练。
  - **Private-μ**：私人适配器库 + 均匀路由。
  - **MHR-μ / Poly-μ**：多基适配器库 + 均匀路由。
- **路由对比**：μ、TP、CM、Arrow（零样本）；Poly、LoraHub、π-tuning（监督）。
- **库构建消融**：随机聚类任务、随机聚类样本、基于嵌入聚类。

## 4. 资源与算力

- **文中未明确说明**所使用GPU型号、数量及具体训练时长。仅提及训练需控制步数以保证公平比较（如MBC两阶段共25000步/适配器），但未给出硬件配置细节。
- 可以推测实验在标准GPU集群（如NVIDIA A100或V100）上完成，但具体信息缺失。

## 5. 实验数量与充分性

- **实验数量丰富**：至少包含以下主要实验组：
  - **零样本**：10个任务 + 12个SNI任务（两个基座模型），共约22个任务结果。
  - **监督适配**：12个SNI任务在100%和10%数据下（Phi-2和Mistral）。
  - **消融实验**：聚类方法对比（RandomTask、RandomExamples、Embeddings）；簇数量影响（10, 20, 40等）。
  - **路由对比**：零样本下对比μ、TP、CM、Arrow；监督下对比Poly、LoraHub。
  - **额外**：StableLM零样本、SNI零样本、数据极低时的少样本实验。
- **充分性评估**：
  - **充分**：覆盖了多种基座模型、多个任务类型、两种泛化场景，消融实验完整。
  - **公平**：所有方法使用相同LoRA配置和总计算预算；MBC通过两阶段控制步数。
  - **偏差风险**：主要关注LoRA，未验证其他适配器类型；训练任务选自Flan v2，非完全随机；基座模型限于Phi-2和Mistral-7B，未在更大模型（如LLaMA-13B+）上验证。

## 6. 论文的主要结论与发现

1. **私人适配器库 + Arrow路由**可以匹配甚至超越全参数微调（Phi-2）和联合训练（Mistral）的零样本性能，说明异步训练的适配器可通过后验路由有效协同。
2. **MBC库构建**在零样本和监督场景下均优于Private、Shared、Poly/MHR等基线，且均匀路由（μ）即足够有效，无需复杂路由。
3. **Arrow路由**是零样本场景下最鲁棒的方法，在私人库上显著优于均匀路由，在MBC库上也有提升；且无需任何训练数据。
4. 对于小规模库（如MBC的10个适配器），路由带来的增益有限（对比均匀路由），可能是因为线性LoRA的叠加性。
5. 在监督适配中，同时微调解器权重和路由系数（MBC-Poly）比仅优化路由（LoraHub）表现更好。

## 7. 优点

- **模块化与可扩展性**：库构建和路由分离，支持异步训练和增量扩展。
- **路由高效且无数据依赖**：Arrow仅需适配器参数（SVD），无需训练数据或联合训练。
- **聚类方法创新**：利用LoRA参数相似性指导任务分组，间接提升跨任务迁移。
- **实验全面**：覆盖零样本和少样本，多个基座模型，消融完整，对比方法丰富。
- **性能优异**：MBC-μ在多个场景下超越传统联合训练，Private-Arrow在零样本下接近最优。

## 8. 不足与局限

- **仅验证LoRA一种适配器**：未探索软提示、MLP适配器等其他类型，库构建和路由的通用性待验证。
- **规模限制**：实验限于2.8B-7B模型，在大规模模型（如70B）上的行为和效率未测试。
- **聚类依赖第一阶段私人训练**：需要额外计算开销；虽然通过总步数控制，但流程比直接联合训练复杂。
- **零样本路由仅在token级top-k选择**，且默认k=4，未系统研究k值对性能的影响（仅在附录中提及温度设置）。
- **监督适配中LoraHub表现明显低于Poly**，但论文归因于其不微调解器参数；然而这可能也与无梯度优化策略更差有关，未充分控制变量。
- **缺乏计算资源报告**：无法评估方法的实际训练/推理成本。
- **任务覆盖局限**：训练集仅使用Flan v2中的256个任务，未涵盖更多领域（如数学、多语言等）。
- **Arrow路由的理论理解不足**：仅凭经验验证了原型与任务关联性，未从理论上分析为何能正确路由。

（完）
