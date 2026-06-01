---
title: "Superposition Prompting: Improving and Accelerating Retrieval-Augmented Generation"
title_zh: 叠加提示：改进并加速检索增强生成
authors: "Thomas Merth, Qichen Fu, Mohammad Rastegari, Mahyar Najibi"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=r8k5JrGip6"
tags: ["query:fie-rag"]
score: 6.0
evidence: 减少干扰的RAG提示方法，可应用于少样本场景
tldr: 本文提出叠加提示方法，无需微调即可让LLM同时处理多个文档，有效缓解RAG中的分心问题。该方法可直接用于预训练Transformer，提升RAG在少样本等场景下的准确性和效率。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 730, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1755, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 768, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1459, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1489, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1578, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8k5jrgip6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 989, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1509, \"height\": 1142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1735, \"height\": 1092, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1695, \"height\": 1711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 1279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8k5jrgip6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1103, \"height\": 460, \"label\": \"Table\"}]"
motivation: RAG中长上下文推理成本高且存在分心现象，需要无需微调的改进方法。
method: 提出叠加提示方法，将多个输入文档叠加处理，使LLM同时关注所有文档，避免分心。
result: 在多个RAG基准上，叠加提示显著提升性能并降低推理成本。
conclusion: 叠加提示是一种高效且即插即用的RAG增强方法，可广泛适用。
---

## Abstract
Despite the successes of large language models (LLMs), they exhibit significant drawbacks, particularly when processing long contexts. Their inference cost scales quadratically with respect to sequence length, making it expensive for deployment in some real-world text processing applications, such as retrieval-augmented generation (RAG). Additionally, LLMs also exhibit the "distraction phenomenon", where irrelevant context in the prompt degrades output quality. To address these drawbacks, we propose a novel RAG prompting methodology, *superposition prompting*, which can be directly applied to pre-trained transformer-based LLMs *without the need for fine-tuning*. At a high level, superposition prompting allows the LLM to process input documents in parallel *prompt paths*, discarding paths once they are deemed irrelevant. We demonstrate the capability of our method to simultaneously enhance time efficiency across a variety of question-answering benchmarks using multiple pre-trained LLMs. Furthermore, our technique significantly improves accuracy when the retrieved context is large relative the context the model was trained on. For example, our approach facilitates a $93\times$ reduction in compute time while *improving* accuracy by $43\%$ on the NaturalQuestions-Open dataset with the MPT-7B instruction-tuned model over naive RAG.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大语言模型（LLM）在处理长上下文时存在两个关键缺陷：一是推理成本随序列长度二次增长（$O(n^2)$），在检索增强生成（RAG）中因需拼接多个文档而尤为昂贵；二是“分心现象”（distraction phenomenon），即无关上下文会显著降低输出质量。
- **整体含义**：现有加速方法往往需要修改模型架构或重新训练/微调，代价高昂。本文旨在提出一种无需微调、可直接应用于预训练 Transformer 的提示方法，在提升 RAG 推理效率的同时改善准确率。

### 2. 方法论

- **核心思想**：将输入文档组织成**有向无环图（DAG）**，各文档与查询构成并行“提示路径”（prompt paths），允许 LLM 独立处理各路径，并基于重要性评分丢弃无关路径，从而实现并行计算、缓存与剪枝。
- **关键技术细节**：
  - **ForkJoin 拓扑**：将查询复制 $n_d$ 份（每份与一个文档配对），所有路径共享相同的 preamble（系统提示），但相互独立。最终通过剪枝保留 top-k 路径，合并其 KV 缓存用于生成回答。
  - **路径剪枝（Path Pruning）**：利用贝叶斯公式计算每个文档 $d_i$ 相对于查询 $q$ 的后验概率 $P(d_i|q,p)$ 作为重要性分数，依据分数保留 top-k 文档。
  - **位置分配（Equilibrium Positioning）**：不同于简单的左对齐或右对齐，本文提出“平衡定位”，将重叠路径按调和均值 $S(D)$ 线性排布，避免短文档因位置偏移受到不公平的注意力惩罚。该方法支持连续位置值（适合 ALiBi，对 RoPE 通过线性插值适应）。
  - **路径缓存（Path Caching）**：在预处理阶段预先计算并缓存 preamble 和所有文档的 KV 缓存（不依赖查询），在线服务时直接读取，避免重复计算。
  - **路径并行（Path Parallelization）**：由于各路径相互独立，可在批维度或分布式节点上并行处理所有查询副本的 KV 缓存和 logits 计算，降低用户等待的墙钟时间。
- **算法流程**：
  1. **预处理阶段**：对 preamble 和文档序列计算位置（Algorithm 1），生成并缓存 KV 缓存（Algorithm 2）。
  2. **在线服务阶段**（Algorithm 3）：接收查询后，将查询复制并与各文档 KV 缓存拼接，并行计算所有路径的 logits；利用贝叶斯公式计算每条路径的显著性，保留 top-k 路径；合并保留路径的 KV 缓存，自回归生成回答。

### 3. 实验设计

- **数据集**：
  - **NaturalQuestions-Open**：开放域问答基准，20 个文档设定，报告 Best EM Subspan（准确率）。
  - **MuSiQue**：多跳推理数据集，报告 Answer EM 和 F1。对多跳场景采用“迭代叠加”（iterative superposition），多次应用剪枝选择。
- **Benchmark**：对比方法包括：
  - Naive LLM-RAG（基线）
  - BM-25、TF-IDF、Contriever（检索后 RAG）
  - Attention Sort（按注意力排序重排文档）
  - Prompt Cache（模块化注意力复用）
- **模型**：
  - OpenELM-3B-Instruct（RoPE）
  - BLOOMZ-3B / 7.1B
  - MPT-7B-Instruct（ALiBi）
  - 均使用公开预训练检查点，无任何额外训练/微调。
- **评估指标**：理论加速比（基于 fvcore 计算的理论 FLOP 减少）、CUDA 实际加速比（在 NVIDIA A100 80GB 上测量）、准确率（Best EM Subspan / F1）。

### 4. 资源与算力

- 文中**未明确说明**训练所用的 GPU 数量、时长或具体算力开销，因为该方法无需任何训练或微调，仅需推理。
- 推理测量在单张 **NVIDIA A100 80GB** 上进行，报告了 CUDA 加速比（但实际加速比低于理论值，作者归因于内存瓶颈）。
- 作者指出，实际部署中可能需额外内存（用于 KV 缓存）和辅助计算资源（用于并行化），但未量化具体规模。

### 5. 实验数量与充分性

- **实验组数**：共涉及 3 个模型家族、4 个具体模型、2 个数据集，每个数据集上对比了 6-7 种方法。
- **消融实验**：
  - 位置分配策略（左对齐 vs. 平衡定位）
  - 路径剪枝显著性指标（贝叶斯 vs. 注意力分数 vs. 不剪枝）
  - 叠加因子（$\gamma=1$ 对应经典 RAG，$\gamma=20$ 为完全叠加）
  - top-k 剪枝数（k=1,2,4,8）
  - 各项优化（剪枝、缓存、并行）的独立贡献
- **充分性与公平性**：
  - 实验设计较为全面，覆盖不同架构（ALiBi 与 RoPE）和规模。
  - 所有方法使用相同 prompt 模板（附录 F 提供实例），文档顺序随机化以消除位置偏差。
  - 对比方法中，BM-25/TF-IDF 等检索后 RAG 已为其假定最优 top-k，但本文的超参（如 top-k）也经过扫描，符合公平原则。
  - 主要不足：未在更长上下文或大模型（如 70B+）上验证，且理论加速比与实际加速比存在较大差距（后者低约 1 个数量级），作者承认需优化内存瓶颈。

### 6. 主要结论与发现

- **推理效率**：叠加提示在 NaturalQuestions-Open 上实现最高 **93.7× 理论加速比**（MPT-7B-Instruct），远超 Prompt Cache（91.8×）和 BM-25（7.0×）等基线。
- **准确率提升**：在 MPT-7B-Instruct 上，叠加提示准确率比 Naive LLM-RAG 提升 43%（0.465 vs. 0.026），且优于所有对比方法。
- **多跳推理**：在 MuSiQue 上，叠加提示（结合迭代剪枝）在 F1 和 EM 上均优于基线。
- **无需长上下文训练**：通过将有效序列长度从约 3000 降为约 200 token，使非长上下文 LLM 也能胜任长文档 RAG。
- **消融验证**：平衡定位优于左对齐；贝叶斯显著性优于注意力分数；叠加因子 $\gamma=20$（完全叠加）通常最优，但 $\gamma=10$ 在某些模型上取得更高准确率。

### 7. 优点

- **零微调**：可直接应用于任意预训练 Transformer，无需额外训练或架构修改。
- **同时提升效率与准确性**：通过剪枝消除了分心文档对 LLM 的干扰，同时因序列长度大幅缩短而降低计算量。
- **高度模块化**：路径缓存和并行化设计充分利用了 RAG 场景中文档独立的特性，可实现预处理与在线解耦。
- **理论框架清晰**：将提示建模为有向无环图，并给出了形式化算法（Algorithm 1-3），易于复现。
- **开源实现**：提供 GitHub 代码仓库，增强可复现性。

### 8. 不足与局限

- **实际加速比远低于理论值**：由于 FLOP 大幅减少后内存带宽成为瓶颈，CUDA 实测加速比仅为理论值的 1/10 左右，实际落地需工程优化（如融合 CUDA kernel）。
- **模型规模局限**：实验最大模型为 7B 参数（BLOOMZ-7B、MPT-7B），未验证在 13B/70B 等更大模型上的行为。
- **数据集有限**：仅使用两个问答数据集（单跳与多跳），未测试在更复杂任务（如总结、表格推理）或领域（如法律、医疗）中的泛化性。
- **超参数敏感**：top-k 和叠加因子需要针对具体任务调优（如 MuSiQue 上迭代次数 $t$ 和 $k$ 影响显著），论文未提供自动确定规则。
- **多跳推理限制**：迭代叠加中后续文档的 KV 缓存无法预缓存（依赖前文），导致加速比大幅下降（如从 60× 降至 4×）。
- **RoPE 兼容性**：虽然实验显示 OpenELM（RoPE）也能工作，但作者未研究微调是否能进一步提升连续位置插值的性能。

（完）
