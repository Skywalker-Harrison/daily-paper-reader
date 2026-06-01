---
title: "From Complex to Atomic: Enhancing Augmented Generation via Knowledge-Aware Dual Rewriting and Reasoning"
title_zh: 从复杂到原子：通过知识感知的双重改写与推理增强增强生成
authors: "Jinyu Wang, Jingjing Fu, Rui Wang, Lei Song, Jiang Bian"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PAjCdkkNaU"
tags: ["query:fie-rag"]
score: 5.0
evidence: RAG增强方法，通过知识原子化和推理提升性能，可用于factivity推理
tldr: 当前RAG系统仅依赖检索难以挖掘深层领域知识和进行逻辑推理。本文提出知识感知的双重改写与推理方法，包含知识原子化、查询提议、知识理解和推理四个组件，将复杂问题分解为原子问题，构建连贯推理。实验表明该方法显著提升RAG在专业数据集上的推理能力，可应用于事实性推理任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 815, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1408, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1111, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1692, \"height\": 1040, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1400, \"height\": 1188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1411, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pajcdkknau/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1043, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 891, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 893, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1724, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 567, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 469, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 399, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1812, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 908, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 908, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 907, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1347, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1223, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1050, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1080, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 760, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 762, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 730, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1192, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1088, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1130, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pajcdkknau/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1126, \"height\": 373, \"label\": \"Table\"}]"
motivation: 依赖检索不足以挖掘深层领域知识和进行逻辑推理。
method: 提出知识原子化、查询提议器、知识理解器与推理器四个组件，将复杂问题分解为原子问题。
result: 实验证明该方法能有效提取并利用领域知识构建连贯推理，提升RAG性能。
conclusion: 为RAG系统提供了深度知识挖掘和推理增强方案，可助力factivity推理任务。
---

## Abstract
Recent advancements in Retrieval-Augmented Generation (RAG) systems have significantly enhanced the capabilities of large language models (LLMs) by incorporating external knowledge retrieval. However, the sole reliance on retrieval is often inadequate for mining deep, domain-specific knowledge and for performing logical reasoning from specialized datasets. To tackle these challenges, we present an approach, which is designed to extract, comprehend, and utilize domain knowledge while constructing a coherent rationale. At the heart of our approach lie four pivotal components: a knowledge atomizer that extracts atomic questions from raw data, a query proposer that generates subsequent questions to facilitate the original inquiry, an atomic retriever that locates knowledge based on atomic knowledge alignments, and an atomic selector that determines which follow-up questions to pose guided by the retrieved information. Through this approach, we implement a knowledge-aware task decomposition strategy that adeptly extracts multifaceted knowledge from segmented data and iteratively builds the rationale in alignment with the initial query and the acquired knowledge. We conduct comprehensive experiments to demonstrate the efficacy of our approach across various benchmarks, particularly those requiring multihop reasoning steps. The results indicate a significant enhancement in performance, up to 12.6\% over the second-best method, underscoring the potential of the approach in complex, knowledge-intensive applications.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前检索增强生成（RAG）系统虽然能通过外部知识检索增强大语言模型（LLM）的能力，但仅依赖检索难以挖掘深层、专业化的知识，并执行专业领域中所需的逻辑推理。面对复杂、多跳的问题时，现有方法往往在问题分解、信息检索和推理链构建上存在不足。
- **整体含义**：为了解决上述挑战，本文提出一种知识感知的双重改写与推理框架（KAR³-RAG），旨在将复杂问题原子化分解，同时利用原子知识对齐提升检索效率，并通过迭代推理构建连贯的上下文，从而显著提升 RAG 系统在复杂、知识密集型任务中的表现。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：知识感知的任务分解 + 原子知识对齐（通过双重改写实现查询和文档块的原子化），使系统能在迭代中逐步收集相关上下文并动态调整推理路径。
- **关键技术组件**：
  - **知识原子化器（Knowledge Atomizer）**：利用 LLM 将每个文档块生成多个可被该块回答的原子问题（原子标签），构成原子知识库。
  - **查询提议器（Query Proposer）**：基于原始问题和当前累积上下文，生成多个原子查询提议（atomic query proposals）。
  - **原子检索器（Atomic Retriever）**：对每个原子查询提议，从原子知识库中检索 top-k 最相似的原子标签及其对应块。
  - **原子选择器（Atomic Selector）**：基于原始问题、上下文和所有检索到的原子对，选择最相关的原子对，并将其对应的原始块加入上下文。
- **算法流程（文字描述）**：
  1. 初始化上下文为空；  
  2. 循环最多 N 轮：  
     a. 查询提议器根据原始问题 q 和上下文 Ct-1 生成原子查询提议集合；  
     b. 原子检索器对每个提议检索 top-k 原子标签，返回候选原子对集合；  
     c. 原子选择器从候选列表中选择最有用的原子对（或判定无需更多信息则提前终止）；  
     d. 将所选原子对对应的原始块加入上下文；  
  3. 若终止，将原始问题和最终上下文输入生成器得到最终答案。
- **主要区别**：与 Self-Ask、IRCoT 等方法不同，KAR³ 采用生成多查询提议 + 基于检索结果选择的方式，形成动态的、自适应分解路径，且保留完整块而非仅中间答案作为上下文，减少误差累积。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **主要数据集**：
  - **开放域多跳 QA**: HotpotQA、2WikiMultiHopQA、MuSiQue（各随机采样 500 条，所有上下文合并为统一知识库以增加难度）。
  - **专业法律领域**: 中文 LawBench（6 项任务）和 Open Australian Legal QA。
- **Benchmark 评估**：多跳 QA 上采用 F1、精确匹配（EM）、准确率（Acc，GPT-4 作为裁判）、召回率、精确率；法律基准上额外使用 F1/EM 及 Acc。
- **对比方法**：
  - 零样本 CoT、Naive RAG、Self-Ask（带检索）、IRCoT、Iter-RetGen、SearChain、ProbTree（树形分解）、GraphRAG（本地和全局模式）。
  - 基础 LLM：GPT-4 (1106-Preview) 和 Llama-3.1-70B-Instruct。

## 4. 资源与算力

- **论文未明确说明**使用的 GPU 型号、数量及训练时长（因为方法主要依赖现成 LLM 进行推理，无需额外训练）。仅提到代码已开源（https://github.com/microsoft/PIKE-RAG），并给出了原子知识预处理阶段的 API 调用次数（如 MuSiQue：7120 次调用）和 token 消耗，但未提及硬件配置。

## 5. 实验数量与充分性

- **实验数量丰富**：
  - 在 3 个开放域多跳数据集和 2 个法律基准上均进行了主要对比。
  - 消融实验：对迭代上限 N（1~10）、四个组件的各自替换（原子标签形式、单提议、直接检索块、直接选块）进行了消融。
  - 附加实验：GPT-3.5 上的表现分析、token 消耗对比、替代原子标签（纯文句子 vs. 原子问题）比较、零样本 vs. 少样本提示影响等。
- **充分性评价**：实验设计较为全面，涵盖了不同难度（2~4 跳）、不同领域（开放域/法律）的基准，并与多种代表性方法对比，消融实验设计合理。但是，仅在两个法律基准上评估专业领域，覆盖面仍有进一步扩展空间。另外，所有实验均基于单一数据集采样（500 条），未报告多次随机采样或方差，但属常见做法。

## 6. 论文的主要结论与发现

- KAR³ 在所有数据集和两种 LLM 上均取得优于第二名的性能，在 MuSiQue 上准确率最高提升 20.4%（Llama 3 下 +10.1 绝对点）。
- 知识原子化（原子问题作为标签）相比纯文句子或直接检索块显著提高了检索对齐效果。
- 多查询提议 + 基于检索结果的原子选择策略，比单一确定性子问题生成方法更能应对知识库模式不一致和意图歧义。
- 迭代分解能逐步提高支撑事实召回率和答案准确率，且早停机制可控制成本。
- 方法对 LLM 的推理能力有一定依赖（GPT-3.5 下优势缩小），但开源模型 Llama-3.1-70B 仍能展现明显提升。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次将原子知识对齐（双重改写）融合到 RAG 的迭代分解中，通过“提议→检索→选择”机制实现知识感知的自适应路径搜索。
- **实验全面**：覆盖开放域多跳和法律专业领域，并对比了链式、树式、图式等多种先进方法，消融实验细致，提供了清晰的组件贡献度。
- **实用性**：代码开源；支持零样本运行（无需额外微调）；公开了详细 Prompt。
- **解释性**：记录了每一步分解及原子选择，增强了推理过程的可解释性和透明性。

## 8. 不足与局限

- **对 LLM 推理能力要求高**：在较弱 LLM（如 GPT-3.5）上优势不明显，表明方法依赖强推理模型。
- **计算成本**：需要多次调用 LLM（每次迭代中需查询提议和原子选择），token 消耗高于部分基线方法（如 Self-Ask、Iter-RetGen），可能增加实际部署成本。
- **通用性验证有限**：仅在两个法律基准上测试专业领域，其他专业领域（医疗、金融等）的泛化能力尚未验证；开放域数据集按固定 500 条抽样，未报告多轮随机抽样结果。
- **原子化预处理 overhead**：原子知识的生成需要一次性的 LLM 调用，尽管可通过开源模型降低，但仍增加前期成本。
- **早停机制依赖 LLM 判断**：当 LLM 在“无更多信息需要”与“仍需深入推理”之间模棱两可时，可能提前停止或继续冗余迭代，影响鲁棒性。

（完）
