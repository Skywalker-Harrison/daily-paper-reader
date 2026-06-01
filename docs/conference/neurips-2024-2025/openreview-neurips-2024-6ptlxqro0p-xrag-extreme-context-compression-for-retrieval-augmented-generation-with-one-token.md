---
title: "xRAG: Extreme Context Compression for Retrieval-augmented Generation with One Token"
title_zh: xRAG：基于单令牌的检索增强生成极端上下文压缩
authors: "Xin Cheng, Xun Wang, Xingxing Zhang, Tao Ge, Si-Qing Chen, Furu Wei, Huishuai Zhang, Dongyan Zhao"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=6pTlXqrO0p"
tags: ["query:fie-rag"]
score: 5.0
evidence: RAG的极端上下文压缩方法，高效融合检索与生成
tldr: xRAG提出一种极端上下文压缩方法，将文档嵌入作为检索模态特征融入语言模型表示空间，仅需一个令牌即可替代原文。该方法冻结检索器和语言模型，只训练模态桥，保持即插即用特性。实验表明极端压缩下仍能保持RAG性能，为高效RAG系统提供了新思路，可潜在应用于few-shot场景的快速知识集成。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1362, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1362, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-6ptlxqro0p/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 732, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1384, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1221, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1374, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1381, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1391, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1194, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1281, \"height\": 811, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 697, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 693, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-6ptlxqro0p/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1383, \"height\": 433, \"label\": \"Table\"}]"
motivation: 传统RAG需保留全文，导致计算开销大，需要更极致的上下文压缩。
method: 将密集检索中的文档嵌入视为检索模态特征，通过模态融合桥接与语言模型表示空间对齐，实现单令牌压缩。
result: 在极端压缩下仍保持与完整上下文相当的RAG性能，且可复用离线嵌入。
conclusion: xRAG实现了极致压缩且保留即插即用，为RAG实际部署提供了高效方案。
---

## Abstract
This paper introduces xRAG, an innovative context compression method tailored for retrieval-augmented generation. xRAG reinterprets document embeddings in dense retrieval--traditionally used solely for retrieval--as features from the retrieval modality. By employing a modality fusion methodology, xRAG seamlessly integrates these embeddings into the language model representation space, effectively eliminating the need for their textual counterparts and achieving an extreme compression rate. 
In xRAG, the only trainable component is the modality bridge, while both the retriever and the language model remain frozen. This design choice allows for the reuse of offline-constructed document embeddings and preserves the plug-and-play nature of retrieval augmentation. 
Experimental results demonstrate that xRAG achieves an average improvement of over 10% across six knowledge-intensive tasks, adaptable to various language model backbones, ranging from a dense 7B model to an 8x7B Mixture of Experts configuration. xRAG not only significantly outperforms previous context compression methods but also matches the performance of uncompressed models on several datasets, while reducing overall FLOPs by a factor of 3.53. Our work pioneers new directions in retrieval-augmented generation from the perspective of multimodality fusion, and we hope it lays the foundation for future efficient and scalable retrieval-augmented systems.

---

## 论文详细总结（自动生成）

# xRAG: Extreme Context Compression for Retrieval-augmented Generation with One Token - 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：检索增强生成（RAG）通过检索外部知识提升LLM性能，但将整个文档拼接到提示中导致推理成本急剧增加，且易超出LLM的上下文长度限制。如何在不牺牲检索增强优势的前提下，实现极致的上下文压缩？
- **动机**：现有压缩方法（如软提示、硬提示编辑）要么需要存储大量激活值（不适合大规模文档库），要么压缩率有限。作者注意到：现代密集检索系统通过对比学习已将文档内容蒸馏到单个高维嵌入中，该嵌入几乎包含与原文相同的信息。因此，可将文档嵌入视为一种“检索模态”特征，直接融合到LLM表示空间，从而摒弃原文，实现极端压缩。
- **整体含义**：xRAG开创了将RAG上下文压缩视为模态融合问题的全新方向，实现了一个token替代整篇文档的极致压缩，同时保持或接近未压缩RAG的性能，并大幅提升计算效率。

## 2. 方法论

### 核心思想
- 将密集检索的文档嵌入（原本仅用于检索）重新定义为“检索模态”特征，通过一个可训练的模态投影器（Modality Bridge）将其映射到LLM的表示空间，从而在输入中仅添加一个token（即投影后的嵌入），替换原文。
- 检索器和LLM均冻结，只有投影器可训练，保证即插即用，并允许复用离线构建的文档嵌入。

### 关键技术细节
- **投影器设计**：一个简单的两层MLP，参数仅占Mistral-7b的0.46%，占Mixtral-8x7b的0.07%。
- **两阶段训练策略**：
  1. **Paraphrase Pretraining**（无监督）：在未标注语料上，使用自然语言指令（如“[X] The above text could be paraphrased as: [D]”）让LLM从文档嵌入重建原文档，训练范式为语言建模（公式1：最小化交叉熵损失）。
  2. **Context-aware Instruction Tuning**（有监督）：使用阅读理解、开放域QA、摘要等混合数据，优化两个目标：
     - **语言模型损失**（公式2）：给定投影后的嵌入和问题，生成答案。
     - **自蒸馏损失**（公式3）：最小化xRAG（学生）与未压缩RAG（教师）输出分布的KL散度，提升鲁棒性。
  - 最终损失：`L = L_nll + α * L_kd`，α设为2.0。
- **流程**：查询 → 检索获得文档嵌入 → 通过投影器得到单token表示 → 与查询嵌入拼接送入冻结LLM → 生成答案。

## 3. 实验设计

### 数据集 / 场景
- **知识密集型任务（共6个）**：
  - 开放域QA：Natural Questions (NQ), TriviaQA, Web Questions (WebQA)
  - 多跳QA：HotpotQA
  - 长文本QA：TruthfulQA
  - 事实核查：FactKG
- 评估指标：Exact Match (EM) 用于QA；Accuracy用于FactKG；F1和Rouge-L用于TruthfulQA。
- 检索语料：Wikipedia 2021年12月dump，约3700万个段落（每段平均180 token）。

### Benchmark / 对比方法
- **基线**：
  - 无检索（w/o retrieval）—— 下界
  - 标准RAG（w/ retrieval，未压缩）—— 上界
  - 离散压缩方法：TF-IDF（压缩为1个token）作为下界
  - LLMLingua（两种压缩率：†和‡）
- **骨干模型**：Mistral-7b（密集7B）和Mixtral-8x7b（MoE 8x7B），均使用指令微调版本。

## 4. 资源与算力

- **硬件**：8× Nvidia A100 GPU。
- **训练配置**：
  - Paraphrase Pretraining：batch size 12，gradient accumulation 4，max seq len 336，训练约200万样本（1 epoch）。
  - Instruction Tuning：batch size 4，gradient accumulation 2，max seq len 1024，训练约95.5万样本（1 epoch）。
- **优化器**：AdamW，学习率6e-3（预训练）/ 2e-5（指令微调），线性warmup 0.03。
- **推理效率**：使用Torch Profiler测量CUDA时间和GFLOPS，所有实验在同一硬件环境（Nvidia A100 + AMD EPYC 7V12 CPU）进行。

## 5. 实验数量与充分性

- **主要实验**：表1展示了在两个骨干模型、6个数据集上xRAG与基线的性能对比，共12组核心结果。
- **消融实验**（表3、表4、表11）：
  - 训练策略消融：去掉预训练、指令微调、语言模型损失、自蒸馏损失，以及使用LoRA调优作为对照。
  - 数据混合消融：单独使用阅读理解、QA、摘要数据调优。
  - 嵌入模型消融：对比SFR、E5-Mistral、E5-Large、BGE-Large、BGE-Base、Dragon、DPR等7种嵌入模型。
- **效率分析**（表2）：对比RAG与xRAG在4个数据集上的CUDA时间和GFLOPS。
- **鲁棒性分析**（图4）：提出Resilience Rate和Boost Rate，在4个数据集上对比LLMLingua、xRAG和RAG。
- **案例分析**（图5-10）：展示xRAG在混乱检索下的鲁棒性及错误案例。
- **充分性与客观性**：实验覆盖了多种任务类型、两种规模骨干、多种基线，消融完整，统计显著性（p<0.05）有提及。对比方法选择合理（仅包括满足即插即用和内存高效的压缩方法）。总体充分、公平且客观。

## 6. 主要结论与发现

- **极致的压缩能力**：xRAG将文档从平均175.1个token压缩至1个token，压缩率达178倍。
- **性能接近甚至超越未压缩RAG**：
  - 在Mistral-7b上，xRAG相对无检索提升16.2%，未压缩RAG提升19.4%，差距很小。
  - 在Mixtral-8x7b上，xRAG提升9.7%，甚至超过未压缩RAG的8.0%（可能因RAG受噪声文档干扰）。
- **效率大幅提升**：相比RAG，xRAG减少CUDA时间1.64倍，减少GFLOPS 3.53倍。
- **鲁棒性强**：xRAG的Resilience Rate（保持正确回答）显著高于RAG，受噪声检索影响小；Boost Rate虽略低于RAG，但高于LLMLingua。
- **消融分析关键点**：
  - 预训练和指令微调均重要；自蒸馏损失对鲁棒性贡献更大。
  - 阅读理解和摘要数据均能提升性能，说明指令微调提升的是利用投影信息的能力，而非任务特定知识。
  - 更强的嵌入模型（如SFR）带来更好下游性能。

## 7. 优点

- **创新视角**：首次将RAG上下文压缩视为模态融合问题，借鉴多模态对齐思路，洞察深刻。
- **极致压缩且高效**：仅一个token，参数增量极小（<0.1%），计算开销大幅降低。
- **保持即插即用**：冻结检索器和LLM，可复用离线文档嵌入，适合实际部署。
- **两阶段训练设计合理**：预训练对齐模态，指令微调结合自蒸馏提升鲁棒性和下游性能。
- **鲁棒性出色**：自蒸馏使模型在面对噪声检索时能依赖内部知识，避免被误导。
- **广泛的验证**：跨6个知识密集型任务、2种骨干模型、多种检索器、多种压缩基线，结果一致且有深度分析。

## 8. 不足与局限

- **检索方式局限**：仅考虑单向量密集检索（如DPR、SFR），未探索稀疏检索（BM25）或多向量检索（ColBERT）。作者认为多向量检索可为xRAG提供更多灵活性，是未来方向。
- **推理能力不足**：在多跳推理任务（HotpotQA、FactKG）上，xRAG与未压缩RAG仍有明显差距。可能原因是训练数据缺少推理导向的样本，提升推理能力是未来工作。
- **仅支持Top-1检索**：未探索多文档场景（Top-K）。xRAG在多文档时输入长度仍为K个token，而RAG则会增长K倍，因此xRAG在多文档场景更具优势，但当前未验证。
- **模型规模有限**：仅验证了7B和8x7B MoE，未在更大模型（如70B）上实验，泛化性未知。
- **潜在风险**：由于压缩极度激进，极端情况下可能丢失关键信息，尤其当嵌入质量不高时。论文未讨论对数据隐私或公平性的影响。

（完）
