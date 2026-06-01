---
title: "SeCon-RAG: A Two-Stage Semantic  Filtering and Conflict-Free Framework for Trustworthy RAG"
title_zh: SeCon-RAG：一种两阶段语义过滤和无冲突的可信RAG框架
authors: "Xiaonan si, Meilin Zhu, Simeng Qin, Lijia Yu, Lijun Zhang, Shuaitong Liu, Xinfeng Li, Ranjie Duan, Yang Liu, Xiaojun Jia"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tTwZhy8JqY"
tags: ["query:fie-rag"]
score: 5.0
evidence: 语义过滤与冲突消解的可信RAG，与确保事实一致性相关
tldr: SeCon-RAG提出两阶段语义过滤和无冲突框架：首先通过实体-意图-关系提取器进行语义和聚类过滤，然后处理文档间矛盾信息。该方法旨在防御语料投毒的同时保留有用信息。实验证明在保障生成可信度方面优于现有防御。对于少样本事实性推理，该框架可帮助滤除噪声证据，确保检索到的句子特征准确可靠。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1282, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1125, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1066, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1158, \"height\": 916, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ttwzhy8jqy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1101, \"height\": 818, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 832, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 835, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ttwzhy8jqy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 200, \"label\": \"Table\"}]"
motivation: 现有RAG防御过度过滤导致信息丢失，需要更智能的语义过滤和矛盾处理。
method: 提取查询和文档的实体、意图和关系，进行语义和聚类筛选，后处理冲突以生成一致回复。
result: 在多个领域数据集上降低了污染影响，同时保持了生成内容的完整性。
conclusion: SeCon-RAG实现了可信RAG，为少样本推理中的证据筛选提供了有效方法。
---

## Abstract
Retrieval-augmented generation (RAG) systems enhance large language models (LLMs) with external knowledge but are vulnerable to corpus poisoning and contamination attacks, which can compromise output integrity. Existing defenses often apply aggressive filtering, leading to unnecessary loss of valuable information and reduced reliability in generation.
To address this problem, we propose a two-stage semantic filtering and conflict-free framework for trustworthy RAG. 
In the first stage, we perform a joint filter with semantic and cluster-based filtering  which is guided by the Entity-intent-relation extractor (EIRE). EIRE extracts entities, latent objectives, and entity relations from both the user query and filtered documents, scores their semantic relevance, and selectively adds valuable documents into the clean retrieval database. 
In the second stage, we proposed an EIRE-guided conflict-aware filtering module, which analyzes semantic consistency between the query, candidate answers, and retrieved knowledge before final answer generation, filtering out internal and external contradictions that could mislead the model.
Through this two-stage process, SeCon-RAG effectively preserves useful knowledge while mitigating conflict contamination, achieving significant improvements in both generation robustness and output trustworthiness.
Extensive experiments across various LLMs and datasets demonstrate that the proposed SeCon-RAG markedly outperforms state-of-the-art defense methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

检索增强生成（RAG）系统通过引入外部知识提升了大型语言模型（LLM）的事实准确性和时效性，但也因此面临严重的语料投毒和检索污染攻击。攻击者通过向检索库中注入精心构造的恶意文档，可以误导模型输出错误答案，从而破坏RAG系统的可信性。现有的防御方法（如基于困惑度检测、投票聚合、粗粒度过滤）存在两个主要局限：

- **粗粒度过滤**会同时移除有害内容和有用信息，导致信息损失。
- **缺乏冲突解决机制**，无法处理检索文档之间、以及检索知识与模型内部知识之间的矛盾，导致生成结果不可信。

为了解决这些问题，本文提出了**SeCon-RAG**，一个**两阶段语义过滤与无冲突框架**，旨在在抵御语料投毒的同时尽可能地保留有用信息，并通过语义一致性检查消除内部和外部矛盾，从而提升RAG生成的鲁棒性和可信度。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 2.1 核心思想

SeCon-RAG的核心是引入**结构化语义信息**来指导过滤和推理过程。它设计了一个**实体-意图-关系提取器（EIRE）**，将文档分解为实体、意图和关系三元组，在此基础上实现两阶段防御：

- **第一阶段：语义与聚类联合过滤（SCF）** —— 在检索前从统计和语义两个维度剔除恶意文档。
- **第二阶段：冲突感知过滤（CAF）** —— 在生成前检查查询、候选答案和检索知识之间的语义一致性，丢弃存在矛盾的文档。

### 2.2 关键技术细节

#### EIRE（Entity-Intent-Relation Extractor）
对每个文档 \(d\)，使用提示词让LLM输出：
- **实体集 \(E_d\)**：显式或隐式提及的关键实体。
- **意图 \(I_d\)**：文档的核心目的或结论。
- **关系集 \(R_d\)**：实体间的语义关系（如“被…驾驶”、“赢得…”）。

#### 第一阶段：SCF（语义与聚类联合过滤）
**（a）聚类过滤（Clustering-Based Filtering）**  
将所有文档嵌入向量后，用K-means聚类得到K个簇。对每个簇，计算每个文档与簇中心的余弦相似度，若超过阈值 \(\tau_{\text{cluster}}\) 则视为恶意文档（因为投毒文档通常在嵌入空间中紧密聚集）。过滤集 \(D_{\text{cluster}}\) 包含所有相似度不超过阈值的文档。

**（b）语义图过滤（Semantic Graph-Based Filtering）**  
基于EIRE为每个文档构建语义图 \(G_d\)（节点为实体，边为关系）。构造一个由少量人工验证的正确文档组成的参考集 \(D_{\text{cor}}\)，并生成其语义图 \(G_{\text{cor}}\)。对候选文档 \(d\)，使用LLM比较 \(G_d\) 与 \(G_{\text{cor}}\) 的结构相似性，输出得分 \(ss_G(d, D_{\text{cor}}) \in [0,1]\)。若得分低于阈值 \(\tau_{\text{semantic}}\)，则标记为恶意。

**联合决策**：采用保守的**AND逻辑**——只有当文档同时被聚类过滤和语义图过滤标记为可疑时，才将其移除。最终保留的语料为 \( \tilde{D} = D' \setminus (D_{\text{cluster}} \cap D_{\text{semantic}}) \)。

#### 第二阶段：CAF（冲突感知过滤）
在检索出 top-k 文档后，对每个文档 \(d\) 使用 EIRE 提取语义结构，并从三个维度评估：
- **查询一致性（Q）**：文档的意图和实体是否与用户查询对齐。
- **文档间一致性（C）**：文档与其他检索文档在关系和上下文上是否一致。
- **模型内部知识一致性（M）**：文档中的关键实体是否与LLM的内部知识事实兼容。

LLM根据这三个维度判断文档是**可信的、有毒的、冲突的或无关的**，只保留被判定为“可信”的文档用于最终生成。最终答案 \(A(q) = F(q, \tilde{D}_{\text{CAF}})\)。

### 2.3 算法流程（文字描述）

1. 输入查询 \(q\)、语料库 \(D\)、验证正确文档集 \(D_{\text{cor}}\)、生成模型 \(F\)。
2. **SCF阶段**：
   - 对所有文档进行向量嵌入并K-means聚类。
   - 对每个文档计算簇内相似度，根据 \(\tau_{\text{cluster}}\) 得到 \(D_{\text{cluster}}\)。
   - 对每个文档用EIRE提取语义结构并构建语义图，与 \(G_{\text{cor}}\) 比较得到语义得分，根据 \(\tau_{\text{semantic}}\) 得到 \(D_{\text{semantic}}\)。
   - 联合过滤得到最终保留语料 \(\tilde{D}\)。
3. **CAF阶段**：
   - 从 \(\tilde{D}\) 中检索 top-k 文档得到 \(D_k(q)\)。
   - 对每个文档，用EIRE提取语义结构，并从Q、C、M三个维度进行一致性评估。
   - 只保留评估为“可信”的文档。
4. 使用保留的文档与查询生成最终答案。

## 3. 实验设计

### 3.1 数据集
- **Natural Questions (NQ)**
- **HotpotQA**
- **MS-MARCO**

这三个数据集均为开放域问答基准，对应大规模语料库。

### 3.2 攻击设置
- **语料投毒攻击（PoisonedRAG）**：注入与查询相关的恶意文档，投毒比例设置 20% 和 100%（主要结果），附录中还测试了 40%、60%、80% 等比例。
- **提示注入攻击（PIA）**：通过扰动离散令牌构造对抗性提示，在推理时误导模型。

### 3.3 对比方法（baselines）
- **VanillaRAG**：标准RAG基线。
- **InstructRAG**：通过自合成推理指导检索。
- **AstuteRAG**：基于启发式选择融合内部和外部知识。
- **TrustRAG**：使用聚类过滤和投票决议，是当前最优的防御方法之一。

### 3.4 评估指标
- **Accuracy (ACC)**：生成答案与真实答案完全匹配的比例。
- **Attack Success Rate (ASR)**：投毒查询导致模型产生错误答案的比例。

### 3.5 验证正确文档集
从每个数据集中手动选取10个干净文档构建 \(D_{\text{cor}}\)。

### 3.6 使用的LLM
- **Mistral-12B**
- **Qwen-7B**
- **LLaMA-3.1-8B**
- **GPT-4o**
- **DeepSeek-R1**

涵盖开源和闭源、不同规模的模型。

### 3.7 嵌入模型（用于检索和聚类）
- MiniLM
- SimCSE
- BERT
- BGE

## 4. 资源与算力

论文中提到：**所有实验在 NVIDIA A100-SXM4-40GB GPU 上运行**。但未明确说明使用了多少块GPU、训练时长或总计算量。由于方法主要基于推理（LLM调用），无模型训练，计算开销主要来自多次LLM查询（EIRE提取、语义相似度比较、CAF判断）。运行时分析显示，每个批次（batch）平均耗时约1.21–1.45分钟，比TrustRAG慢约0.5分钟，但比VanillaRAG慢得多。总体上算力需求适中，但未给出精确的卡时统计。

## 5. 实验数量与充分性

### 5.1 主要实验
- **表1**：在三个数据集、五种LLM、四种设置（Clean、PIA、PoisonedRAG-20%、PoisonedRAG-100%）下对比了SeConRAG与四个baseline的ACC和ASR。共 \(3 \times 5 \times 4 = 60\) 组结果。
- **附录A.4.1**：按不同投毒比例（0%/20%/40%/60%/80%/100%）扩展了三个数据集上五种LLM的详细对比（表3-5），每组数据都包含ACC和ASR。

### 5.2 消融实验
- **核心模块消融（图3）**：分别移除SCF和CAF，比较三个数据集上的ACC和ASR。
- **SCF子组件消融（表6）**：单独使用聚类过滤、单独使用语义过滤、两者结合。
- **EIRE模块消融（表7）**：有/无EIRE。
- **验证正确文档集消融（表8）**：有/无 \(D_{\text{cor}}\)。

### 5.3 其他分析
- **运行时分析（图4）**：比较所有方法在不同攻击设置下的时间开销。
- **嵌入模型鲁棒性（表2）**：对四种嵌入模型在三种数据集、不同投毒比例下的表现。
- **阈值敏感性分析（表9、表10）**：对 \(\tau_{\text{cluster}}\) 和 \(\tau_{\text{semantic}}\) 在不同模型上的影响。

### 充分性评价
实验覆盖了多种数据集、多种模型规模（7B–大型闭源模型）、多种攻击类型（语料投毒与提示注入）、多种投毒比例（0%–100%）、多种嵌入模型，并进行了全面的消融。对比基线包括了当前最先进的防御方法。实验设计较为充分、客观。但论文未报告误差棒或统计显著性检验，仅说明“all reported results are averages of multiple runs with an error of ±1%”。

## 6. 主要结论与发现

1. **SeCon-RAG在几乎所有设置下都取得了最优或接近最优的ACC和最低的ASR**。例如在HotpotQA + GPT-4o + 100%投毒下，ACC达到83.6%，ASR仅2.4%，优于TrustRAG（80.9%/2.7%）和AstuteRAG（67.3%/24.1%）。
2. **两阶段框架不可或缺**：消融显示，移除SCF或CAF都会显著降低ACC、大幅提升ASR，特别是CAF的缺失导致ASR飙升（如100%投毒下ASR从8%升至56%）。
3. **EIRE模块和验证文档集至关重要**：启用EIRE后ASR显著下降，正确文档集进一步提升了过滤精度。
4. **SeCon-RAG在干净语料上性能也不下降甚至有时提升**（如Mistral-12B在NQ上干净ACC达82%，高于TrustRAG的73%），说明防御机制并未过度压制有用内容。
5. **对阈值和嵌入模型不敏感**：在合理范围内改变 \(\tau_{\text{cluster}}\) 和 \(\tau_{\text{semantic}}\) 或更换嵌入模型，性能保持稳定。
6. **运行时开销适中**：尽管比简单基线慢，但在实际应用中可接受，且安全收益显著。

## 7. 优点

1. **首次将结构化语义信息引入RAG防御**：EIRE提取的实体-意图-关系三元组为细粒度过滤和冲突检测提供了可解释的基础。
2. **两阶段互补设计**：SCF负责粗粒度批量过滤，CAF负责细粒度语义一致性校验，两者合作既有效移除恶意内容又保留有用信息。
3. **保守的AND逻辑**：同时被聚类和语义过滤标记才移除，减少了误伤。
4. **泛化能力强**：在多种LLM（小至7B，大至GPT-4o）、多种嵌入模型、多种攻击方式下均表现稳定。
5. **干净环境下无性能损失**：甚至比基线更好，证明方法不会因防御而牺牲常规性能。
6. **阈值不敏感**：降低了超参数调优负担，易于部署。

## 8. 不足与局限

1. **推理延迟**：由于需要多次LLM调用（EIRE提取、语义图比较、CAF判断），SeCon-RAG的运行时比简单基线慢（约1.2–1.45分钟/批次），在延迟敏感场景中可能受限。
2. **依赖高质量语义提取**：EIRE的表现受限于LLM对文档的结构化理解能力，对领域特定或噪声较大的文本可能效果不佳。
3. **需要少量人工验证的“正确文档”集**：文中从每个数据集中手动选取10个干净文档。虽然量小，但在实际新领域中仍需人工操作。
4. **未提供统计显著性检验**：误差仅以±1%说明，缺乏置信区间或p值，严谨性略有不足。
5. **仅评估了开放域QA任务**：未在摘要、对话、代码生成等其他RAG应用上测试，泛化范围有待扩展。
6. **未考虑白盒自适应攻击**：攻击者如果知道防御机制，可能设计针对性更强的投毒文档绕过SCF的聚类或语义图检测。论文未讨论此对抗场景。

（完）
