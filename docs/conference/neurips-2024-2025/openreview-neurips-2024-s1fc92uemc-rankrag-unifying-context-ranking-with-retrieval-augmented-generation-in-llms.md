---
title: "RankRAG: Unifying Context Ranking with Retrieval-Augmented Generation in LLMs"
title_zh: RankRAG：统一上下文排序与检索增强生成的LLM方法
authors: "Yue Yu, Wei Ping, Zihan Liu, Boxin Wang, Jiaxuan You, Chao Zhang, Mohammad Shoeybi, Bryan Catanzaro"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=S1fc92uemC"
tags: ["query:fie-rag"]
score: 7.0
evidence: RAG方法统一上下文排序与生成
tldr: 现有RAG系统常依赖独立的排序模型和生成模型，导致效率与性能瓶颈。RankRAG通过指令微调单个大型语言模型同时完成上下文排序和答案生成，仅需少量排序数据即可超越专业排序模型。实验表明，基于Llama3的RankRAG-8B在多个RAG基准上达到最先进水平，为将RAG应用于少样本叙实性推理提供了高效的基础框架。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 325, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1066, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s1fc92uemc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1239, \"height\": 341, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 934, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 941, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1110, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1231, \"height\": 982, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 835, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-s1fc92uemc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 1063, \"label\": \"Table\"}]"
motivation: 标准RAG使用独立排序模型效率低，本文旨在通过单一LLM统一排序与生成以提升性能。
method: 对单个LLM进行指令微调，使其同时执行上下文排序和答案生成，并在训练中混合少量排序数据。
result: RankRAG-8B在多个RAG基准上超越包括ChatQA-1.5在内的强基线模型。
conclusion: 统一排序与生成的RAG方法在保持生成质量的同时显著提升检索效率，适用于下游任务。
---

## Abstract
Large language models (LLMs) typically utilize the top-k contexts from a retriever in retrieval-augmented generation (RAG).  In this work, we propose a novel method called RankRAG, which instruction-tunes a single LLM for both context ranking and answer generation in RAG.  In particular, the instruction-tuned LLMs work surprisingly well by adding a small fraction of ranking data into the training blend, and outperform existing expert ranking models, including the same LLM exclusively fine-tuned on a large amount of ranking data.  For generation, we compare our model with many strong baselines, including ChatQA-1.5, an open-sourced model with the state-of-the-art performance on RAG benchmarks.  Specifically,  our Llama3-RankRAG-8B and Llama3-RankRAG-70B significantly outperform Llama3-ChatQA-1.5-8B and Llama3-ChatQA-1.5-70B, respectively, on nine general knowledge-intensive benchmarks for RAG. In addition, it also performs comparably to GPT-4 on five RAG benchmarks in the biomedical domain without instruction fine-tuning on biomedical data, demonstrating its superb capability for generalization to new domains.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前检索增强生成（RAG）系统通常采用“检索-重排序-生成”的流水线，其中重排序往往依赖独立的专家模型（如BERT、T5等）。然而，专用排序模型零样本泛化能力有限，而LLM本身具备强大的语义理解能力，却未被充分用于排序。同时，标准RAG中选取top-k上下文存在两难：k太小可能丢失相关信息（召回不足），k太大则会引入噪声，降低生成质量。
- **核心问题**：能否将上下文排序与答案生成统一在单个LLM中，通过指令微调同时提升检索质量和生成能力？
- **整体含义**：本文提出的RankRAG框架，通过指令微调让同一个LLM既能重排序检索到的上下文，又能基于精选的上下文生成答案。实验表明，仅需加入少量（约5万条）排序数据，即可获得超越专业排序模型的效果，显著提升RAG系统在多种知识密集型任务上的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将上下文排序任务转化为QA形式，与RAG生成任务统一进行指令微调，使LLM学会判断文档与问题的相关性，并利用相关文档生成答案。
- **关键技术细节**：
  - **两阶段训练框架**：
    - **Stage-I：监督微调（SFT）**：在128K条高质量指令跟随数据（包括对话、长文本QA、LLM生成指令、FLAN/COT等）上进行微调，赋予LLM基本的指令跟随能力。
    - **Stage-II：统一指令微调（排序+生成）**：在Stage-I基础上，混合五类数据进行微调：
      1. Stage-I的SFT数据（维持指令跟随能力）；
      2. 上下文丰富的QA数据（如DROP、NarrativeQA等）；
      3. 检索增强的QA数据（SQuAD、WebQuestions，合并金标准与BM25检索结果，共5个段落）；
      4. 上下文排序数据（MS MARCO段落排序数据，约50k条，含人造会话排序数据）；
      5. 检索增强的排序数据（同上数据源，要求LLM同时判断多个段落的相关性并输出相关段落序号）。
  - **统一格式**：所有任务均被转化为 (问题x, 上下文c, 答案y) 的标准化QA格式。例如排序任务的问题指令为：“For the question {question}, access whether the passage is relevant to the question.”，输出True/False。
  - **推理流程**：检索器（如Dragon）先检索top-N个段落 → RankRAG模型对每个段落输出“True”的概率作为相关性得分，重排序得到top-k → 将top-k段落与问题拼接，再次输入RankRAG生成最终答案。
- **数据效率**：仅需约5万条排序数据（占完整MS MARCO的约10%），即可取得优异效果。即使只有5k条，性能也接近饱和。

## 3. 实验设计：数据集、基准与对比方法

- **通用领域数据集（9个）**：
  - 开放域QA：NQ、TriviaQA、PopQA、HotpotQA、2WikimQA
  - 事实验证：FEVER
  - 对话式QA：Doc2Dial、TopiOCQA、INSCIT
- **生物医学领域（5个）**：Mirage基准包含MMLU-med、PubMedQA、BioASQ、MedQA、MedMCQA
- **对比方法**：
  - 无RAG的基线：InstructGPT、PaLM 2、GPT-3.5/4、Mixtral等
  - 有RAG的基线：Atlas、Self-RAG、RECOMP、InstructRetro、RA-DIT、Llama3-Instruct、ChatQA-1.5（最强开源RAG模型）等
- **评价指标**：EM（精确匹配）、Accuracy、F1（按任务选择）

## 4. 资源与算力

- **RankRAG-8B**：使用32块NVIDIA A100 GPU，训练总时长约10小时（Stage-I 4小时，Stage-II 6小时）。
- **RankRAG-70B**：使用128块NVIDIA A100 GPU，训练总时长约16小时（Stage-I 4小时，Stage-II 12小时）。
- 文中明确说明了GPU型号、数量、训练时长，充分透明。

## 5. 实验数量与充分性

- **实验组数**：涵盖了9个通用+5个生物医学共14个基准，包括主实验、消融实验（去除排序、去除RQA/RAR、替换为RAFT、仅Stage-I）、不同骨干（Llama2 7B/13B/70B）、不同检索器（DPR、Contriever）、不同k值、不同重排序文档数N、不同排序数据量、效率分析、案例研究。
- **充分性与客观性**：
  - 所有实验均采用零样本设置（无额外演示），保证公平。
  - 与多个强基线（包括GPT-4、ChatQA-1.5）在同一环境进行比较，且对基线报告了最佳k值。
  - 进行了数据污染检查（字符串匹配），未发现训练数据与测试集重叠。
  - 实验设计全面，覆盖了不同任务类型、模型规模、检索器、数据量等因素，结论可信。

## 6. 论文的主要结论与发现

- **RankRAG显著优于现有RAG方法**：在9个通用基准和5个生物医学基准上，Llama3-RankRAG-8B/70B均大幅超过同等规模的ChatQA-1.5模型，且8B模型即可超越许多更大竞争模型（如InstructRetro 43B、RA-DIT 65B）。
- **数据高效性**：仅需少量（~5万条）排序数据即可达到甚至超越使用完整MS MARCO（~50万条）训练的专业排序模型。
- **泛化能力强**：在生物医学领域未经微调，RankRAG 70B性能达到GPT-4的98%，证明其可快速适应新领域。
- **重排序模块至关重要**：消融实验表明，去除重排序后性能显著下降（平均降幅约3%），验证了排序环节的有效性。
- **鲁棒性强**：即使使用较弱的检索器（DPR、Contriever），RankRAG仍能大幅改进基线。

## 7. 优点

1. **创新性**：首次将上下文排序与RAG生成统一在单个LLM的指令微调中，有效利用LLM的语义理解能力。
2. **数据高效**：仅需少量排序数据即可获得优异性能，实用价值高（降低标注和训练成本）。
3. **泛化性**：无需领域特定微调即可在生物医学等新领域取得接近顶尖模型的效果。
4. **通用性**：适用于多种检索器、多种LLM骨干（Llama2/3），且在不同任务类型（单跳/多跳QA、事实验证、对话QA）上均有效。
5. **分析全面**：做了大量消融和效率分析，结论可靠。

## 8. 不足与局限

1. **仅研究单次检索**：未涉及多轮/迭代检索（如Self-RAG、FLARE），未来可与多步检索结合。
2. **推理延迟**：重排序需要对top-N个段落逐一生成相关性分数，引入了额外计算时间（尽管文中分析比例可控，但N较大时仍有开销）。
3. **实验覆盖**：主要基于英文维基百科语料，在低资源语言、非结构化文档等场景下的表现未知。
4. **潜在偏差**：未讨论排序数据（如MS MARCO）中可能存在的偏见，以及生成结果的事实性和安全性问题。
5. **伦理与社会影响**：论文未深入分析模型可能产生的有害内容或滥用风险。

（完）
