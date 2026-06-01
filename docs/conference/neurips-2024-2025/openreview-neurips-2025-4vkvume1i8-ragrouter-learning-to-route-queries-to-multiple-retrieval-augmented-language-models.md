---
title: "RAGRouter: Learning to Route Queries to Multiple Retrieval-Augmented Language Models"
title_zh: RAGRouter：学习将查询路由至多个检索增强语言模型
authors: "Jiarui Zhang, Xiangyu Liu, Yong Hu, Chaoyue Niu, Fan Wu, Guihai Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4VKVUmE1I8"
tags: ["query:fie-rag"]
score: 4.0
evidence: RAG查询路由方法
tldr: 本文针对多个检索增强大语言模型响应质量参差不齐的问题，提出RAGRouter智能路由方法。该方法将检索文档对模型能力的影响融入路由框架，通过学习动态选择最合适的检索增强LLM，避免静态参数依赖。实验表明，RAGRouter能显著提升多模型系统的整体准确性和鲁棒性，为RAG系统部署提供了高效实用的方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 712, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 721, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1427, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1409, \"height\": 1140, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 595, \"height\": 558, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 1130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 589, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1303, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1045, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 915, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1175, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1072, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1438, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1438, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1095, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 544, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1442, \"height\": 346, \"label\": \"Table\"}]"
motivation: 现有路由方法忽略检索文档的动态影响，导致RAG多模型系统性能不稳定。
method: 提出RAGRouter，定义检索增强LLM路由问题，将检索文档纳入路由学习。
result: 在知识密集型任务上，RAGRouter显著优于静态路由基线和单模型。
conclusion: 动态路由考虑文档效应能有效提升RAG多模型系统的整体质量。
---

## Abstract
Retrieval-Augmented Generation (RAG) significantly improves the performance of Large Language Models (LLMs) on knowledge-intensive tasks. However, varying response quality across LLMs under RAG necessitates intelligent routing mechanisms, which select the most suitable model for each query from multiple retrieval-augmented LLMs via a dedicated router model. We observe that external documents dynamically affect LLMs' ability to answer queries, while existing routing methods, which rely on static parametric knowledge representations, exhibit suboptimal performance in RAG scenarios. To address this, we formally define the new retrieval-augmented LLM routing problem, incorporating the influence of retrieved documents into the routing framework. We propose RAGRouter, a RAG-aware routing design, which leverages document embeddings and RAG capability embeddings with contrastive learning to capture knowledge representation shifts and enable informed routing decisions. Extensive experiments on diverse knowledge-intensive tasks and retrieval settings, covering open and closed-source LLMs, show that RAGRouter outperforms the best individual LLM and existing routing methods. With an extended score-threshold-based mechanism, it also achieves strong performance-efficiency trade-offs under low-latency constraints. The code and data are available at https://github.com/OwwO99/RAGRouter.

---

## 论文详细总结（自动生成）

## 论文总结：RAGRouter：学习将查询路由至多个检索增强语言模型

### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在检索增强生成（RAG）框架下，不同大语言模型（LLM）利用外部文档的回答能力存在显著差异——有些模型能准确提取并整合信息，有些则易受噪声干扰产生错误。这种异构性表明，为每个查询动态选择最合适的检索增强LLM（即“路由”），有望超越单一最强模型的性能。
- **关键矛盾**：现有LLM路由方法（如RouterDC、GraphRouter、EmbedLLM等）均假设模型知识是**静态**的，仅依赖查询与模型固有参数知识的匹配。但在RAG场景中，外部文档会动态改变模型的实际知识状态：原本答不对的模型可能因检索而答对，原本答对的模型可能因检索噪声而答错。这种“知识表示漂移”使静态路由策略严重失效。
- **整体含义**：首次正式定义**检索增强LLM路由问题**，将检索文档的影响纳入路由框架。通过明确建模文档特征与模型RAG能力，实现动态、准确的路由决策，从而提升多模型RAG系统的整体质量与鲁棒性。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：构建一个RAG感知的路由器RAGRouter，其核心是显式建模检索引起的**知识表示更新**：每个LLM在RAG下的有效知识表示为 \( v'_k = v_k + v_f \)，其中 \( v_k \) 是静态参数知识嵌入，\( v_f \) 是文档驱动的融合知识表示（由文档语义、查询-文档交叉特征和模型RAG能力三部分通过多头注意力融合得到）。
- **关键技术细节**：
  - **架构设计**（图2）：
    - 查询编码器（Query Encoder）与文档编码器（Document Encoder）共享参数，输出查询嵌入 \( v_q \) 和文档嵌入 \( v_d \)。
    - 交叉编码器（Cross Encoder）处理查询-文档对，输出交互表示 \( v_c \)。
    - LLM知识嵌入层（Knowledge Embedding Layer）和RAG能力嵌入层（RAG Capability Embedding Layer）均为可学习的向量，分别表示模型的先验知识和使用文档的能力。
    - 多头注意力融合 \( v_r, v_d, v_c \) 得到 \( v_f \)，更新知识表示为 \( v'_k = v_k + v_f \)。
    - 路由决策基于查询嵌入与各模型更新后知识表示的余弦相似度，选择相似度最高的模型。
  - **优化策略**：采用**对比学习**，以查询嵌入为锚点，构建两类正负样本对：
    - **跨设置对比（CSC）**：跨非RAG和RAG设置，从同一模型的不同知识状态（如非RAG答错 vs. RAG答对）中选取正负样本。
    - **设置内对比（ISC）**：在同一设置内，从不同模型的回答正确性中选取正负样本。
    - 联合交叉熵对比损失与二元分类损失（正则化项），总损失 \( L = L_{CT} + \lambda L_{CLS} \)。
  - **延迟感知扩展**：增加“分数阈值”机制——预排序LLM效率列表，路由时若最高分模型 \( M_i \) 的分数与更高效模型 \( M_j \) 的分数差 ≤ θ，则选择 \( M_j \)，实现精度-效率灵活权衡。

### 3. 实验设计

- **数据集与场景**：
  - 5个知识密集型任务：PopQA、MedMCQA、Natural Questions (NQ)、WebQuestions (WebQ)、TriviaQA (TQA)。
  - 检索设置：本地检索（Wikipedia + BGE-large）；在线检索（DuckDuckGo API）；带噪声检索（在Wikipedia段落中注入无关、反事实等噪声）。
- **Benchmark**：评估指标使用“正确精确匹配”（Exact Match）。对比基线包括：单模型（15个开源LLM，参数0.5B~72B，如Qwen2.5、Llama3、Gemma2等）、规则基线（Random、Weighted、Oracle Single Best）、现有非RAG感知路由方法（Prompt LLM、GraphRouter、RouterDC、KNN Router、矩阵分解MF）。
- **对比方法**：全部基线均非RAG感知。RAGRouter是唯一显式建模文档和RAG能力的方法。

### 4. 资源与算力

- **显式说明**：所有实验均在一张NVIDIA RTX 4090D GPU上完成。训练时冻结编码器除最后两个Transformer层外的所有参数，优化器为AdamW，学习率5e-5，batch size 64，训练10 epochs。推理时RAGRouter的峰值显存占用约4147 MiB，平均推理时间0.011秒/实例，参数约136M。

### 5. 实验数量与充分性

- **实验组**：
  - 主实验结果（表2）：在5个任务×2~4种检索设置下，对比10+方法。
  - 含封闭源LLM实验（表3）：在NQ和WebQ上额外加入GPT-4o、DeepSeek-R1等。
  - 延迟感知路由（图4、表4、表9）：在MedMCQA（Local/Online）、TriviaQA等任务上，绘制精度-延迟曲线并计算Area、Peak Acc、Latency Gap-to-Match。
  - 消融实验（表5、表6）：去掉交叉编码器、去掉RAG能力嵌入层、去掉ISC、去掉CSC。
  - 敏感性分析：嵌入维度（表10）、分类损失权重λ（表11）、候选LLM集合大小与异质性（表7）。
  - 交叉域迁移（表15）：MedMCQA→HotpotQA、NQ→MedMCQA。
  - 噪声鲁棒性（表16）：在TriviaQA的4种噪声子集上对比。
  - 跨任务泛化（表17）：在WikiASP摘要任务上验证。
  - 失败案例分析（表12~14）：量化路由失败类型并提供成功/失败示例。
- **充分性评价**：实验覆盖充分，涵盖多种任务、多种检索质量、多种模型规模（从0.5B到72B，含封闭源）、多种对比基线（包括规则、静态路由、RAGRouter变体），并进行了全面的消融和敏感性分析。实验设计较为客观、公平。

### 6. 主要结论与发现

- RAGRouter在所有任务和设置上**显著优于现有非RAG感知路由方法**以及最佳单模型：平均准确率64.46%，超最佳单模型（Llama-3.3-70B，60.85%）+3.61%，超Oracle Single Best（61.22%）+3.24%。
- 在融合封闭源强模型（GPT-4o、DeepSeek-R1）时，依然能提升+1.67%~+7.71%的准确率，且对强模型调用率仅44.79%。
- 延迟感知扩展使RAGRouter在精度-延迟权衡曲线上全面优于基线，能够以更低延迟匹配甚至超过最强单模型的准确率。
- 消融实验证实：交叉编码器、RAG能力嵌入层、跨设置对比与设置内对比均对最终性能有正向贡献，缺一不可。
- 模型多样性（小型+大型混合）比单一规模集合更有利于路由增益，因为异质性模型互补性更强。
- 在跨域迁移和不同噪声类型下，RAGRouter表现稳定，说明其学习了可泛化的、与检索文档相关的模型能力差异。

### 7. 优点

- **创新性强**：首次明确处理RAG场景下文档引起的动态知识漂移，为路由问题引入新的维度和机制。
- **架构设计合理**：显式分离参数知识、文档语义、查询-文档交互、模型RAG能力，并通过多头注意力融合，符合直觉。
- **优化策略有效**：对比学习的正负样本构造同时利用跨设置和设置内两种来源，能够捕捉知识转移模式，增强判别力。
- **实用性强**：分数阈值扩展机制使得在低延迟约束下仍能取得良好精度-效率折中，且整体模型轻量（136M参数，单GPU可跑）。
- **实验充分、结果详实**：大量对比、消融、迁移、噪声、延迟分析，验证方法有效且稳健。
- **代码和数据开源**：提供https://github.com/OwwO99/RAGRouter，利于复现和延展。

### 8. 不足与局限

- **实验覆盖偏差**：依赖的15个候选LLM虽涵盖多个系列，但主要基于开源模型（除部分API调用），未包括所有代表性模型（如Claude、Gemini等），可能对路由性能上限有影响。
- **任务类型局限**：主要集中于知识密集型问答，虽在摘要任务（WikiASP）上做了验证，但未涉及代码生成、推理、对话等更广泛的RAG应用场景。
- **静态路由假设风险**：RAGRouter本身假设候选LLM池固定，无法动态增删模型；若模型池频繁变动，需重新训练嵌入层。
- **对比学习依赖正确答案**：需要大量带标签的查询-文档-答案三元组，这在实际部署中获取成本可能较高；论文未讨论少样本或无监督情景。
- **延迟优化机制较简单**：分数阈值法是一种启发式策略，可进一步探索更精细的混合延迟优化或在线学习。
- **安全性/公平性分析缺失**：论文未讨论路由可能引入的偏见或安全风险（如对少数群体问题的系统性错误路由）。
- **统计显著性未报告**：论文未报告误差棒或置信区间，部分结果可能受单次运行随机性影响。

（完）
