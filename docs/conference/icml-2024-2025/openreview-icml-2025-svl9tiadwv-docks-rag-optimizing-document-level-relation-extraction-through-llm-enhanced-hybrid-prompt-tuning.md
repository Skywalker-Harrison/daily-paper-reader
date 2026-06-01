---
title: "DocKS-RAG: Optimizing Document-Level Relation Extraction through LLM-Enhanced Hybrid Prompt Tuning"
title_zh: DocKS-RAG：通过LLM增强混合提示调优优化文档级关系抽取
authors: "Xiaolong Xu, Yibo Zhou, Haolong Xiang, Xiaoyong Li, Xuyun Zhang, Lianyong Qi, Wanchun Dou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SVl9tIADWV"
tags: ["query:fie-rag"]
score: 5.0
evidence: RAG用于文档级关系抽取这一语言任务，可能适配至句子叙实性
tldr: DocKS-RAG通过引入结构化知识和语义信息增强RAG，用于文档级关系抽取任务。实验表明该方法能有效提取跨句子实体关系，其框架可启发将RAG应用于句子叙实性推理等语言任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-svl9tiadwv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svl9tiadwv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1512, \"height\": 1278, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-svl9tiadwv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1543, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svl9tiadwv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1546, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svl9tiadwv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svl9tiadwv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 169, \"label\": \"Table\"}]"
motivation: 现有基于预训练语言模型的关系抽取方法难以融合结构化知识和推断跨句子隐含关系。
method: 提出DocKS-RAG框架，利用RAG引入额外结构化知识和语义信息，通过混合提示调优增强文档级关系抽取。
result: 在多个文档级关系抽取数据集上取得改进，有效提取跨句子实体关系。
conclusion: 引入结构化语义信息的RAG方法能提升文档级关系抽取性能，为其他语言任务提供思路。
---

## Abstract
Document-level relation extraction (RE) aims to extract comprehensive correlations between entities and relations from documents. Most of existing works conduct transfer learning on pre-trained language models (PLMs), which allows for richer contextual representation to improve the performance. However, such PLMs-based methods suffer from incorporating structural knowledge, such as entity-entity interactions. Moreover, current works struggle to infer the implicit relations between entities across different sentences, which results in poor prediction. To deal with the above issues, we  propose a novel and effective framework, named DocKS-RAG, which introduces extra structural knowledge and semantic information to further enhance the performance of document-level RE. Specifically, we construct a Document-level Knowledge Graph from the observable documentation data to better capture the structural information between entities and relations. Then, a Sentence-level Semantic Retrieval-Augmented Generation mechanism is designed to consider the similarity in different sentences by retrieving the relevant contextual semantic information. Furthermore, we present a hybrid-prompt tuning method on large language models (LLMs) for specific document-level RE tasks. Finally, extensive experiments conducted on two benchmark datasets demonstrate that our proposed framework enhances all the metrics compared with state-of-the-art methods.

---

## 论文详细总结（自动生成）

# DocKS-RAG 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **任务背景**：文档级关系抽取（Document-level Relation Extraction, RE）旨在从整篇文档中提取实体间的结构化三元组（主-关系-宾）。该任务比句子级 RE 更具挑战性，因为实体可能跨句子、跨段落甚至跨章节出现，且存在大量需要推理的隐含关系。
- **现有方法的不足**：
  - 基于预训练语言模型（PLM）的方法（如 BERT）虽然能捕捉上下文，但难以建模实体与关系之间的结构化交互（如实体-实体相互作用）。
  - 基于图的方法（如 GCN、GAT）尝试引入结构化知识，但缺乏足够的语义上下文，且易引入噪声和无关连接。
  - PLM 与知识图谱（KG）存在语义不对齐问题：PLM 训练于非结构化文本，而 KG 是结构化数据，导致模型难以有效利用 KG 中的结构知识。
- **论文目标**：提出 DocKS-RAG 框架，通过引入额外的结构化知识（文档级知识图谱）和语义信息（句子级语义 RAG），并使用混合提示调优（Hybrid Prompt Tuning）增强大语言模型（LLM）在文档级 RE 上的性能。

## 2. 方法论

### 核心思想
DocKS-RAG 包含两个主要阶段：
1. **混合提示生成**：从构建的文档级知识图谱（DocKG）和句子级语义 RAG（SetRAG）中分别检索相关结构知识和语义信息，组合成混合提示。
2. **混合提示调优**：基于大语言模型（LLaMA3-8B）采用参数高效微调（PEFT，具体为 LoRA）进行适配。

### 关键技术细节

#### (1) 文档级知识图谱（DocKG）构建与检索
- **构建**：使用图神经网络（GNN）对文档中的实体和关系进行表示学习。实体和关系初始化为嵌入向量，通过 GNN 层迭代聚合邻居信息更新表示（公式 2-3）。之后计算实体对交互分数（公式 4），并通过 softmax 预测关系概率（公式 5），保留概率大于阈值 τ_er 的三元组构成 DocKG（公式 6）。
- **检索**：给定用户查询 q，利用预训练语言模型（PLM）将其映射为语义向量 h_q，然后计算与 DocKG 中各实体表示的余弦相似度（公式 8），选择相似度大于阈值 τ_eq 的实体及关联关系构成子图 G_q（公式 9），最后通过函数 g_DocKG 将子图转换为结构化提示 P_DocKG（公式 10）。

#### (2) 句子级语义 RAG（SetRAG）
- **分割与嵌入**：将文档分割成句子，使用 PLM（如 BGE）将每个句子编码成向量，构建句子级知识库 SetKB（公式 11-12）。
- **检索**：对查询 q 计算与 SetKB 中句子向量的相似度（公式 13），选出 Top-k 个最相关句子 S_k 及其关联三元组 T_k，通过生成函数 g_SetRAG 得到语义提示 P_SetRAG（公式 15）。

#### (3) 混合提示生成与调优
- **混合提示**：将 P_DocKG 和 P_SetRAG 拼接得到混合提示 P_Hybrid（公式 16）。
- **参数高效微调**：在 LLaMA3-8B 基础上引入 LoRA 适配器模块 A，冻结原参数 θ，仅训练适配器参数（公式 17）。采用余弦学习率调度、3 个 epoch、学习率 5e-5、batch size 2 等设置。

#### 算法流程（伪代码对应 Algorithm 1）
1. 输入：可观测文档 D_u、给定三元组 T_u、图模型 G_m、嵌入模型 E_m、生成函数 Gen、循环次数 T、适配器参数 A、用户查询 Q。
2. 输出：预测三元组 T_p。
3. 训练 G_m 得到 DocKG（KG）。
4. 将 D_u 分割为句子集 S_u，并用 E_m 构建句子知识库 KB。
5. 根据 Q 从 KG 和 KB 中检索相关子图 G_q 和 Top-k 句子 S_k。
6. 生成提示 P_g ← Gen(G_q)，P_s ← Gen(S_k)，拼接得到 P_h。
7. 循环 T 次：用 P_h 和适配器 A 训练 LLM，更新适配器参数。
8. 用新生成的提示 P_h_hat 预测三元组。

## 3. 实验设计

### 数据集
- **DocRED**：基于 Wikipedia 的文档级 RE 基准，包含跨句子、跨段落的实体关系标注。
- **Re-DocRED**：DocRED 的增强版本，引入关系推理方面，标注更丰富。

### Benchmark 对比方法
对比了 13 种方法，包括：
- PLM 基础方法：HIN、ATLOP-BERT、SRLR、GLRE 等。
- 图增强方法：LSR、GAIN、HeterGSAN、SIRE、SSAN、DocuNet、KD-DocRE、KMGRE 等。
- LLM 方法：AutoRE、LMRC。

### 评估指标
- **F1 分数**：平衡精确率和召回率。
- **Ign-F1 分数**：忽略容易识别的句子内关系，更关注隐含跨句子关系的性能。

### 主要实验结果
- 在 DocRED 和 Re-DocRED 的 Dev 和 Test 集上，DocKS-RAG 在所有指标上均优于所有对比方法，取得最高分（见表 1）。例如，DocRED Dev Ign-F1 62.76，F1 63.87；Re-DocRED Dev Ign-F1 74.64，F1 75.31。

### 附加实验
- **DocKG 检索阈值 τ_eq 的影响**（表 3）：在 Re-DocRED Dev 集上测试 τ_eq ∈ {0, 0.2, 0.5, 0.7, 0.9, 1}，峰值在 0.7。
- **SetRAG 检索 Top-k 的影响**（表 4）：k 值测试 {0,1,3,5,8,10}，峰值在 k=5。
- **消融实验**（表 2）：分别去除 DocKG、SetRAG、Hybrid-Prompt Tuning 三个组件，性能均下降，其中去除 Hybrid-Prompt Tuning 下降最剧烈（F1 从 63.87 降至 21.07 左右），说明混合提示调优至关重要。

## 4. 资源与算力
- **文中明确提及**：所有实验使用 PyTorch 实现，在四张 24GB RTX 3090 GPU 上训练。
- **具体训练参数**：LLaMA3-8B 为 backbone，LoRA 秩为 16，学习率 5e-5，batch size 2，训练 3 个 epoch。
- **未提及**：训练总时长、推理时间或具体计算成本。

## 5. 实验数量与充分性
- **实验数量**：共包含
  - 主对比实验（表1）：在 2 个数据集 × 2 个指标 × 2 个分集（Dev/Test）上对比了 13 种基线，产生 4 个主要结果表。
  - 消融实验（表2）：3 个变体在相同设置下对比。
  - 超参数分析（表3、表4）：分别对 τ_eq 的 6 个值和 k 的 6 个值进行实验。
  - 加上 Appendix 中的数据集和基线描述，实验较为全面。
- **充分性评估**：
  - 优点：覆盖了标准数据集、多个基线、消融和超参数分析，展示了各组件的贡献。
  - 可改进点：未在更多样化或跨领域数据集上验证（如生物医学、法律文本）；未报告统计显著性检验；未与更多 LLM 基础方法（如 GPT-4 直接 zero-shot 或 few-shot）进行对比。
  - 总体而言，实验设计合理，结果支持结论，但应用范围有限。

## 6. 主要结论与发现
1. DocKS-RAG 通过结合结构化知识（DocKG）和语义信息（SetRAG）并采用混合提示调优，显著提升了 LLM 在文档级 RE 任务上的性能，在 DocRED 和 Re-DocRED 上均达到 SOTA。
2. 引入 DocKG 能有效建模实体-关系交互，SetRAG 提供上下文相关语义信息，两者互补。
3. 混合提示调优（带 PEFT）远优于仅使用少量示例的 few-shot 学习，后者性能极差（消融实验中去除该组件后 F1 仅约 20-26）。
4. 适当的检索阈值（τ_eq=0.7, k=5）能平衡信息丰富度和噪声抑制。

## 7. 优点
- **方法创新性**：首次将文档级知识图谱与句子级 RAG 结合，通过混合提示调优缓解了结构化知识与语义信息的对不齐问题。
- **模块化设计**：DocKG、SetRAG 和 Hybrid-Prompt Tuning 各组件可独立替换或改进，便于后续扩展。
- **实验验证充分**：不仅在标准基准上取得领先，还通过消融和超参数分析清晰揭示了各组件贡献。
- **应对跨句子关系**：SetRAG 机制显式检索相关句子，有助于捕捉跨句子隐含关系，这是文档级 RE 的核心难点。
- **高效训练**：使用 PEFT（LoRA）仅微调少量参数，计算成本相对可控（四张 RTX 3090）。

## 8. 不足与局限
- **领域泛化性**：仅在 Wikipedia 来源的 DocRED 系列数据集上评估，未在如生物医学、法律等专业领域验证，可能限制其适用性。
- **计算资源依赖**：虽使用 LoRA 减少参数量，但仍需多 GPU 和高内存（24GB×4），对资源有限的研究者不友好。
- **检索噪声风险**：尽管通过阈值控制，但 SetRAG 的 Top-k 检索仍可能引入不相关句子，尤其在长文档或嘈杂数据中。
- **实验设计上的局限**：
  - 未与更多先进的 LLM 基础方法（如 CodeX、GPT-4 的复杂提示工程）对比。
  - 未进行统计显著性检验（如配对 t 检验）。
  - 同步基线方法的结果大多取自原始论文，可能因重现条件不同而有偏差。
- **应用限制**：文档级 RE 的标签空间通常为预定义关系集，若关系类别未在训练中出现，模型无法处理零样本关系提取。
- **文章结构**：论文中包含较长的“Response to Reviewers”章节（占近 2 页），降低了主体内容的紧凑性。

（完）
