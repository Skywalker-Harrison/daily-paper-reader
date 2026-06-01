---
title: "HyperGraphRAG: Retrieval-Augmented Generation via Hypergraph-Structured Knowledge Representation"
title_zh: HyperGraphRAG：通过超图结构化知识表示的检索增强生成
authors: "Haoran Luo, Haihong E, Guanting Chen, Yandan Zheng, Xiaobao Wu, Yikai Guo, Qika Lin, Yu Feng, Zemin Kuang, Meina Song, Yifan Zhu, Anh Tuan Luu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ravS5h8MNg"
tags: ["query:fie-rag"]
score: 6.0
evidence: 超图结构化知识表示的RAG，支持更丰富的关联推理
tldr: HyperGraphRAG首次将超图引入RAG，用超边表示二元以上关系，突破传统图RAG的二元关系限制。构建了包含知识超图构建、检索和生成的完整流程。在医学、农业等多个领域实验表明，超图表示能捕获更复杂的事实关联，提升生成准确性。虽未明确聚焦事实性推理，但其处理n元关系的能力有助于整合句子中多个语言学特征进行综合判断。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 687, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1369, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 726, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1402, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1420, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 696, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1407, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1411, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1414, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ravs5h8mng/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1409, \"height\": 2136, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ravs5h8mng/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ravs5h8mng/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 955, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ravs5h8mng/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 733, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ravs5h8mng/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1469, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ravs5h8mng/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1425, \"height\": 1801, \"label\": \"Table\"}]"
motivation: 现有图RAG只能表示二元关系，限制了对多元关系的建模，需要超图结构。
method: 构建知识超图，用超边连接多个实体，实现n元关系检索和生成。
result: 在多领域RAG任务中优于基于普通图的RAG方法，尤其适合复杂关联查询。
conclusion: HyperGraphRAG丰富了RAG的知识表示能力，可潜在用于联合多个句子语言学特征的事实性推理。
---

## Abstract
Standard Retrieval-Augmented Generation (RAG) relies on chunk-based retrieval, whereas GraphRAG advances this approach by graph-based knowledge representation. However, existing graph-based RAG approaches are constrained by binary relations, as each edge in an ordinary graph connects only two entities, limiting their ability to represent the n-ary relations (n >= 2) in real-world knowledge. In this work, we propose HyperGraphRAG, the first hypergraph-based RAG method that represents n-ary relational facts via hyperedges. HyperGraphRAG consists of a comprehensive pipeline, including knowledge hypergraph construction, retrieval, and generation. Experiments across medicine, agriculture, computer science, and law demonstrate that HyperGraphRAG outperforms both standard RAG and previous graph-based RAG methods in answer accuracy, retrieval efficiency, and generation quality.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：HyperGraphRAG

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：标准RAG基于文本块检索，GraphRAG尽管利用图结构，但普通图的边仅连接两个实体，只能表示二元关系，无法有效建模现实世界中普遍存在的n元关系（n≥2，如医疗诊断中“男性高血压患者、血清肌酐水平115-133 μmol/L、轻度肌酐升高”四元关系）。这种限制导致知识表示稀疏、信息丢失，影响检索和生成质量。
- **背景**：现有图RAG方法（GraphRAG、LightRAG、PathRAG、HippoRAG2）均依赖二元关系，无法捕获涉及多个实体的复杂事实。
- **整体含义**：HyperGraphRAG首次引入超图（hypergraph）作为知识表示结构，通过超边（hyperedge）直接连接n个实体，突破二元限制，实现更完整、更具表达力的知识表示，从而提升RAG的准确性、检索效率和生成质量。

## 2. 方法论

### 核心思想
- 用超图 \( G_H = (V, E_H) \) 表示知识，其中每条超边 \( e_H \in E_H \) 连接2个或更多实体 \( V_{e_H} = (v_1, v_2, ..., v_n), n \geq 2 \)。每个超边包含自然语言描述和置信度分数；每个实体包含名称、类型、解释和置信度分数。
- 构建、检索、生成三阶段管道。

### 关键技术细节
1. **知识超图构建**
   - **n元关系提取**：通过LLM（GPT-4o-mini）和专门设计的提示（见附录A.1），从文档中提取n元关系事实 \( F_n = (e_H, V_{e_H}) \)，其中超边用自然语言描述，实体附带属性。每个超边有完整性分数(0-10)，每个实体有重要性分数(0-100)。
   - **二分图存储**：将超图转换为二分图 \( G_B = (V_B, E_B) \)，其中 \( V_B = V \cup E_H \)，\( E_B = \{(e_H, v) | v \in V_{e_H}\} \)，支持高效查询和增量更新。
   - **向量表示存储**：对超边和实体分别用同一嵌入模型（text-embedding-3-small）生成向量，存储到向量库 \( E_H \) 和 \( E_V \)。

2. **超图检索策略**
   - **实体提取**：从用户问题中提取关键实体 \( V_q \)（通过LLM提示）。
   - **实体检索**：利用余弦相似度，从实体向量库中检索与 \( V_q \) 最相关的实体，结合实体分数排序，设置阈值 \( \tau_V \) 和数量限制 \( k_V \)。
   - **超边检索**：直接对用户问题 \( q \) 进行相似度检索，返回最相关的超边，类似地结合分数和阈值。
   - **双向扩展**：从检索到的实体出发，获取所有关联超边；从检索到的超边出发，获取所有关联实体。合并形成完整的事实集 \( K_H \)。

3. **超图引导生成**
   - **知识融合**：将检索到的n元关系事实 \( K_H \) 与传统块检索结果 \( K_{\text{chunk}} \) 合并。
   - **生成增强**：使用统一CoT提示，LLM基于融合的知识生成最终答案。

### 算法流程（文字描述）
1. 对每个文档，通过LLM提取超边和实体，构建超图并存储为二分图+向量。
2. 给定查询 \( q \)，先提取实体，再分别检索实体和超边（top-60），双向扩展得到所有n元事实。
3. 检索top-5文本块，与n元事实合并。
4. 将合并的知识和查询送入LLM，生成包含<think>推理和<answer>答案的响应。

## 3. 实验设计

- **数据集**：5个领域知识库
  - **Medicine**：最新国际高血压指南（2024 ESC指南）。
  - **Agriculture**、**Computer Science (CS)**、**Legal**、**Mix**（混合领域）来自UltraDomain。
  - 每个领域采样512个问题：256个二元源（基于二元关系）、256个n元源（基于n≥3关系），问题通过跳数（1、2、3跳）均匀分布，并由人工验证。
- **Benchmark**：对比6种基线方法：
  - **NaiveGeneration**（直接生成，无检索）
  - **StandardRAG**（块检索）
  - **GraphRAG**、**LightRAG**、**PathRAG**、**HippoRAG2**（四种图RAG方法，均为二元关系）
- **评估指标**：
  - **F1**：词级准确率。
  - **R-S (Retrieval Similarity)**：检索知识与真实知识片段的余弦相似度。
  - **G-E (Generation Evaluation)**：LLM作为裁判，评估7个维度（正确性、相关性、事实性、全面性、知识性、逻辑连贯性、多样性），取平均后与F1再平均。

## 4. 资源与算力

- **模型**：使用OpenAI GPT-4o-mini进行提取和生成，text-embedding-3-small用于嵌入。**未涉及本地训练**，因此不报告GPU型号和训练时长。
- **服务器**：80核CPU、512GB RAM。
- **参数**：检索k值：实体检索k=60、超边检索k=60、块检索k=5，采用统一阈值。

论文**未明确说明**使用的GPU资源、训练时间等，因为所有算法均调用API执行，不涉及模型训练。

## 5. 实验数量与充分性

- **主实验**：表2展示了5个领域×3个指标×3种源类型（二元源、n元源、整体）的比较，共15个场景，每个场景报告F1、R-S、G-E。结果一致显示HyperGraphRAG领先。
- **消融实验**（图4）：在医学领域逐一移除实体检索、超边检索、块融合，以及同时移除所有模块，验证各组件的贡献。
- **检索效率分析**（图6）：(a) 不同top-k对F1、R-S、G-E和Token长度的影响；(b) 在不同检索长度限制下F1对比。
- **生成质量分析**（图7）：7个维度上的评分对比。
- **时间与成本分析**（表3）：知识构建和生成阶段的时间/成本对比。
- **案例分析**（附录H）：一个医疗问答案例的详细对比。

**充分性评价**：实验覆盖多个领域、多种问题类型、多种基线，消融实验和效率分析较全面。使用统一生成提示保证公平性。但所有实验**仅基于GPT-4o-mini一个LLM**，未报告其他LLM（如Llama、Claude）的结果，可能缺乏泛化性。

## 6. 主要结论与发现

1. **总体性能**：HyperGraphRAG在所有领域和所有指标上全面超越标准RAG和现有图RAG方法。相比StandardRAG，整体F1提升+7.45，R-S提升+7.62，G-E提升+3.69。
2. **n元源优势**：在n元源问题上，HyperGraphRAG提升尤其显著（F1 +5.3、R-S +6.4、G-E +2.9），证实超图在多元关系建模上的优势。
3. **消融验证**：实体检索、超边检索、块融合均对最终性能有重要贡献，移除三者后性能大幅下降至接近NaiveGeneration。
4. **检索效率**：HyperGraphRAG在相同检索长度下获得更高F1，表明超图表示的单位信息密度更高。
5. **生成质量**：在正确性、相关性、事实性等维度上显著领先。
6. **时间成本**：构建阶段适中的时间和成本（3.084秒/1k tokens，$0.0063/1k tokens），生成阶段略高于标准RAG但优于多数图RAG方法，达到性能/效率的良好平衡。

## 7. 优点

- **理论创新**：首次将超图引入RAG，突破二元关系限制，提出了更通用的知识表示范式。
- **方法完整性**：提供了从构建、存储、检索到生成的完整管道，各模块设计清晰合理。
- **存储友好**：二分图转换使超图能利用现有图数据库高效查询。
- **检索增强**：双向扩展策略确保了检索到的n元事实的完整性。
- **实验全面**：多领域、多指标、多基线、消融和效率分析，案例研究详细。
- **可复现性**：提供数据和代码。

## 8. 不足与局限

- **LLM依赖**：整个流程严重依赖外部LLM（GPT-4o-mini）进行提取和生成，未探索开源模型替代方案，成本和延迟可能较高。
- **领域覆盖有限**：尽管涉及五个领域，但包含大规模文本（如医学指南、法律文档），未验证超图在高度动态或噪声数据上的鲁棒性。
- **未评估不同嵌入模型**：默认使用text-embedding-3-small，未消融不同嵌入模型的影响。
- **超参数未深入优化**：k值和阈值设置基于经验，未进行系统搜索。
- **扩展性考虑**：附录I讨论了多模态、强化学习、联邦学习、基础模型等未来方向，但当前版本仅处理纯文本。
- **应用限制**：对于纯二元关系场景，超图优势可能不明显；构建阶段需大量LLM调用，可能不适合低资源场景。
- **可解释性**：未深入分析超图如何影响LLM的推理过程，案例仅展示输出差异而非内部机制。

（完）
