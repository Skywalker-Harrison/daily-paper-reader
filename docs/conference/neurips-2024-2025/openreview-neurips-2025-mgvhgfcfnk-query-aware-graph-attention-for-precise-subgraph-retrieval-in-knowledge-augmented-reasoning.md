---
title: Query-Aware Graph Attention for Precise Subgraph Retrieval in Knowledge-Augmented Reasoning
title_zh: 查询感知图注意力实现知识增强推理中的精确子图检索
authors: "Yuanye Xu, Yue Zhang, Ning Fu"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=MGvhGFCFNK"
tags: ["query:fie-rag"]
score: 6.0
evidence: 基于查询感知子图检索的知识图谱增强生成
tldr: 知识图谱增强生成中现有方法难以精准检索图证据。提出查询感知子图检索框架，利用语义和关系信息动态检索相关子图，提升复杂多跳推理的事实准确性。实验证明有效性，但未涉及少样本或语言学特征。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1169, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 887, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 1340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgvhgfcfnk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 956, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 777, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 731, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 725, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 732, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1069, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgvhgfcfnk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1375, \"height\": 1296, \"label\": \"Table\"}]"
motivation: KG-RAG在多跳推理中面临结构化证据检索不精准的问题。
method: 提出查询感知图注意机制，动态检索与查询相关的子图。
result: 在复杂推理任务上提升了事实准确性。
conclusion: 查询感知的子图检索能增强KG-RAG的推理能力。
---

## Abstract
In recent years, Retrieval-Augmented Generation (RAG) has demonstrated great potential in enhancing the factual accuracy of large language models (LLMs) in open-domain question answering. Incorporating knowledge graphs (KGs) as external knowledge sources into the RAG paradigm is a promising direction. However, KG-RAG systems for complex multi-hop reasoning tasks still face significant challenges in precisely retrieving structured evidence highly relevant to the query. Existing approaches struggle to dynamically and accurately retrieve graph-based evidence by effectively leveraging query semantics and relational information. To address these challenges, we propose a novel framework called Query-aware Subgraph Retrieval Augmented Generation (QSRAG), centered around a new attention-based architecture termed Query-Relational Graph Attention Network (QR-GAT). QR-GAT is a graph attention mechanism that learns expressive representations of triples by capturing intricate interactions between the query context and relation types. Based on these representations, a scoring module assigns fine-grained relevance scores to triples in the KG, enabling precise subgraph retrieval for downstream reasoning. These structured evidence subgraphs, enriched with confidence scores, are then provided to an LLM to enhance its reasoning capability. Extensive experiments on two widely-used multi-hop Knowledge Graph Question Answering (KGQA) datasets, WebQSP and CWQ, demonstrate that our approach achieves state-of-the-art retrieval performance, particularly excelling in identifying complex multi-hop evidence. KGQA results further show that QSRAG delivers state-of-the-art or competitive performance on both datasets. Our work highlights the effectiveness of query-aware graph attention for accurate structured evidence retrieval, and its potential to enhance knowledge-augmented reasoning with large language models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：大语言模型（LLM）在开放域问答中依赖静态、有限的内知识，在需要精确事实支撑或复杂多跳推理的任务中表现不佳。检索增强生成（RAG）通过引入外部知识（如知识图谱KG）可缓解此问题，但现有KG-RAG方法在多跳查询的结构化证据检索中仍面临三大障碍：
  1. 难以准确识别多跳推理路径上的关键证据，易受无关邻居或冗余信息干扰；
  2. 查询语义与图结构之间的交互建模不足，很多图神经网络（GNN）方法独立编码图而不动态融入查询意图；
  3. 检索噪声和LLM上下文窗口有限导致有效信息被稀释，且一些方法依赖迭代LLM调用增加延迟。
- **整体含义**：本文提出一个**查询感知子图检索增强生成框架（QSRAG）**，核心是**查询-关系图注意力网络（QR-GAT）**，通过动态融合查询语义与关系类型来精准检索KG中的相关子图，从而增强LLM在复杂多跳推理中的事实准确性。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：在检索阶段，利用一种新型图注意力机制QR-GAT，该机制在学习节点表示时不仅考虑图结构，还显式注入查询嵌入和关系类型，从而对三元组进行细粒度相关性评分，选取top-k三元组构成精确的结构化证据子图；在推理阶段，将这些子图及其置信度分数以文本提示形式输入LLM（LLaMA-3.1-8B-Instruct、GPT-4o-mini或GLM-4-Air），采用上下文学习生成答案。
- **关键技术细节**：
  - **实体与查询编码**：使用gte-large-en-v1.5编码器获取实体嵌入e_i、关系嵌入r_ij和问题嵌入q。
  - **节点初始化**：\( x_i^{(0)} = \text{Dropout}([e_i \| q \| p_i]) \)，其中p_i是主题实体标识one-hot向量。
  - **两层投影**：将节点表示通过线性层变换为\( z_i^{(l)} \)和\( z_j^{(l)} \)。
  - **注意力分数计算**：包含基础项和查询-关系增强项：
    - \( \alpha_{ij,\text{base}}^{(l)} = a^{(l)\top} \cdot \text{LeakyReLU}(z_i^{(l)} + z_j^{(l)} + W_e^{(l)} \cdot r_{ij}) \)
    - \( \alpha_{ij,\text{plus}}^{(l)} = (W_q^{(l)} \cdot q)^\top \cdot (W_r^{(l)} \cdot r_{ij}) \)
    - 最终注意力：\( \alpha_{ij}^{(l)} = \text{softmax}_j(\alpha_{ij,\text{base}}^{(l)} + \alpha_{ij,\text{plus}}^{(l)}) \)
  - **多跳注意力更新**：使用多头注意力和层归一化更新节点表示。采用双向QR-GAT（BiQR-GAT）同时编码正向和反向边，最终表示\( h_i = [\vec{h}_i \| \overleftarrow{h}_i] \)。
  - **三元组评分**：基于最终节点表示和查询，通过两层MLP计算三元组分数：\( s(h, r, t) = W_2 \cdot \text{ReLU}(W_1 \cdot [q \| h_h \| r \| h_t]) \)。
  - **训练与推理**：使用二元交叉熵损失训练检索器（正例为最短路径上的三元组，负例随机采样）。推理时对所有候选三元组评分，取top-k构造子图。
  - **推理阶段**：将子图三元组和置信度分数格式化为“(head, relation, tail) (Confidence: 0.96)”形式的文本提示，输入LLM生成答案。

## 3. 实验设计
- **数据集**：
  - **WebQSP**：4,737个问题，最多两跳推理，基于Freebase。
  - **CWQ**：34,699个问题，更复杂多跳，基于Freebase。
- **评价指标**：
  - 检索阶段：三元组Recall@k、答案Recall@k。
  - KGQA阶段：Micro-F1、Macro-F1、Hit、Hit@1。
- **基线方法**：包括SR+NSM w/ E2E、Retrieve-Rewrite-Answer、RoG、G-Retriever、GNN-RAG、SubgraphRAG等，覆盖语义解析、路径预测、GNN检索等多种技术路线。
- **实现细节**：默认在推理时使用top-100三元组；也探索了50、200等取值。LLM温度设为0。作者复现了SubgraphRAG的部分结果以确保公平比较。

## 4. 资源与算力
- 文中仅提及使用**K100-Ai集群**完成模型训练和推理，未明确说明GPU具体型号、数量或训练时长。因此**算力细节不透明**，仅能推断为高性能计算环境。

## 5. 实验数量与充分性
- **实验组数**：
  - 检索性能对比（表1）：在2个数据集上与7种基线比较，报告Triplet Recall和Answer Recall。
  - KGQA推理性能对比（表2）：在2个数据集上与多个基线比较，包含4个指标，并展示了不同LLM（Llama、GPT-4o-mini、GLM-4-Air）和不同top-k（50/100/200）的结果。
  - 检索top-k影响（表3）：系统分析k从50到500对检索指标的影响。
  - 推理top-k影响（表4）：分析k从50到500对Macro-F1和Hit的影响。
  - 消融实验（表5）：去除查询-关系增强项（α_plus）后的性能对比。
  - 置信度阈值消融（表6）：比较无置信度、有置信度以及不同过滤阈值的效果。
  - 附录中还提供了多个问答示例（正确和错误案例）。
- **充分性与客观性**：
  - 对比方法涵盖了当前主流KG-RAG方法，并且作者声明复现了SubgraphRAG、RoG、GNN-RAG的结果以确保公平。
  - 消融实验验证了关键组件的贡献；对top-k的敏感性分析表明存在最优值，解释了性能峰值和下降原因。
  - 实验设计较为全面，但在**统计显著性检验**（如误差棒、置信区间）方面有所缺失，且未报告多次运行的标准差。

## 6. 主要结论与发现
- **检索性能**：QR-GAT在WebQSP和CWQ上均达到SOTA，Triplet Recall分别比SubgraphRAG提高2.5%和11.3%，Answer Recall在CWQ上提高4.5%。
- **推理性能**：QSRAG在WebQSP上Micro-F1达到55.50（优于RoG和SubgraphRAG），Hit@1最高达81.50；在CWQ上Micro-F1达50.29，优于基线。不同LLM下均表现稳定。
- **关于top-k**：检索Recall随k增加单调上升，但推理性能先升后降，说明过多噪声会干扰LLM；最佳k约为100-200。
- **关于置信度**：直接使用置信度分数比阈值过滤更有效，过滤可能丢弃有用信息。
- **消融验证**：查询-关系增强项对检索性能至关重要，移除后Triplet Recall下降约6%（WebQSP）。

## 7. 优点
- **创新性**：提出了查询-关系图注意力机制QR-GAT，将查询语义和关系类型显式融入注意力计算，弥补了传统GAT缺乏查询感知的不足。
- **检索精确性**：能够对单个三元组进行细粒度评分并全局排序，生成的子图更紧凑、噪声更少。
- **框架灵活性**：推理阶段采用插件式LLM，无需微调，可直接使用现有模型；兼容多种LLM（Llamma、GPT、GLM）。
- **实验充分**：在多个维度（不同数据集、不同LLM、不同top-k、消融、置信度策略）进行了系统评估，结论可信。

## 8. 不足与局限
- **实验覆盖有限**：仅使用Freebase上的两个KGQA数据集（WebQSP和CWQ），未在更大规模或领域KG上验证（如Wikidata、生物医学图）。两个数据集均基于单一KG，泛化性存疑。
- **算力信息缺失**：未提供GPU型号、数量、训练/推理时间等详细计算资源，影响可复现性。
- **统计显著性缺失**：未报告多次运行的误差棒或置信区间，无法判断结果的波动性。
- **对top-k敏感**：推理性能在k过大时下降，需人工调优最佳阈值；在实际应用中如何自动确定最优k未探索。
- **置信度分数利用不足**：阈值过滤效果反而不如无过滤，说明置信度分数质量或利用方式有待改进（例如可以引入动态过滤或软加权）。
- **未讨论少样本或零样本场景**：所有实验均为有监督训练检索器，未评估在无训练数据下的迁移能力。
- **语言与多模态局限**：仅处理英文问题，未涉及中文或其他语言；也未考虑图像、表格等多模态输入。

（完）
