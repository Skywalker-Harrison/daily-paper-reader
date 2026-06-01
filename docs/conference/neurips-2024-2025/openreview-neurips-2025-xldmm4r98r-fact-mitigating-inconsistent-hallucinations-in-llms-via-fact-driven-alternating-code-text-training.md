---
title: "FACT: Mitigating Inconsistent Hallucinations in LLMs via Fact-Driven Alternating Code-Text Training"
title_zh: FACT：通过事实驱动的代码文本交替训练缓解LLM不一致幻觉
authors: "Xinxin You, Qixin Sun, Chenwei Yan, Xiao Zhang, Chen Ning, Xiangling Fu, Si Liu, Guoping Hu, Shijin Wang, Ji Wu, Xien Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xlDmm4r98R"
tags: ["query:fie-rag"]
score: 5.0
evidence: 事实驱动的训练减少幻觉
tldr: 大语言模型存在不一致幻觉问题。观察到事实文本可映射为编程结构，提出FACT框架通过代码-文本交替训练增强事实推理的准确性。实验显示在多个NLP任务上减少了幻觉，但未涉及RAG或少样本。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 706, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 707, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xldmm4r98r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1104, \"height\": 479, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xldmm4r98r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1384, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xldmm4r98r/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1336, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xldmm4r98r/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1475, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xldmm4r98r/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xldmm4r98r/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1095, \"height\": 242, \"label\": \"Table\"}]"
motivation: LLM在基于事实的推理中常产生不一致幻觉。
method: 将事实文本映射为编程结构，采用代码-文本交替训练。
result: 在多种NLP任务上有效减少幻觉。
conclusion: 代码文本交替训练能提升LLM的事实推理一致性。
---

## Abstract
Inconsistent hallucinations remain a major challenge for large language models (LLMs), undermining the accuracy and reliability of fact-based reasoning in real-world applications. Existing approaches often rely on task-specific training or adaptation, such as hand-crafted synthetic datasets for domain tasks or solutions mainly focused on numerical reasoning, thereby limiting generalizability to broader, unseen NLP tasks. Inspired by the structural rigor and logical consistency of programming languages, we observe that fact-based texts can be mapped to programming structures due to their inherent patterns. We further propose FACT, a novel Fact-driven Alternating Code-text Training framework that alternates between text-to-code and code-to-text prediction. FACT is the first task-agnostic paradigm that embeds code and natural language in a shared semantic space, thereby transferring the logical consistency of code to LLM outputs in NLP tasks. Experiments show that with only a small subset of Wiki-40B-en for training, FACT reduces inconsistent hallucinations by 2.7%–8.0% and improves overall performance by 2.5%–6.1% in three leading LLMs and four diverse datasets covering QA and summarization tasks. This framework offers a new perspective on addressing challenging hallucinations in LLMs, contributing to more reliable AI.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大语言模型（LLMs）在事实推理中常产生**不一致幻觉**，包括**输入冲突**（生成内容与输入矛盾）和**上下文冲突**（生成内容内部矛盾）。这在医疗、法律等真实场景中严重损害可靠性。
- **现有方法局限**：
  - 多数方法依赖**任务特定**的微调或人工构造数据集（如LOGiQA、AR-LSAT），耗时长、可扩展性差。
  - 合成数据方法主要限于**数学推理**（如OpenMathInstruct-1），难以推广到更广泛的NLP任务。
  - 符号增强方法（如SymbCoT）受符号表达力限制，对复杂问题效果不佳。
  - 代码辅助方法（如PoT、PAL）只能处理可转化为可执行代码的问题（主要是数学），无法将代码的逻辑一致性迁移到一般NLP输出。
- **核心动机**：观察到**事实文本**具有固有的结构模式（主体-属性、过程-函数），可映射到**编程语言**的类和函数。利用代码的**结构严谨性和逻辑一致性**，通过训练让LLM在共享语义空间中对齐代码和自然语言，从而减少不一致幻觉。

### 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：提出**FACT（事实驱动的代码-文本交替训练）**，是一种**任务无关**的框架，通过交替进行**文本→代码**和**代码→文本**预测，将代码的逻辑严谨性迁移到LLM的NLP输出中。
- **技术细节**：
  1. **文本过滤**：使用LLM（GPT-3.5）判断文本是否包含适合编程表示的事实信息（过滤后约53.74%保留）。
  2. **交替训练**：
     - **文本→代码**：因缺少真实代码，使用LLM生成**伪标签代码**作为监督信号。输入文本\(t\)和提示\(p_{t2c}\)生成代码\(c\)。
     - **代码→文本**：给定代码\(c\)和提示\(p_{c2t}\)重建原始文本\(t\)，使用原始文本作为目标。
  3. **质量评估与自适应损失**：
     - **语法有效性**：生成的代码通过Python解释器执行，失败则分配相似度\(S_i=0.1\)。
     - **语义保真度**：通过反向重构（生成重组织文本\(c_{reorg}^i\)，执行代码替换变量获得\(c_{reorg}'^i\)），计算与原文本的ROUGE-1和ROUGE-L平均值作为相似度\(S_i\)。
     - **自适应损失**：文本→代码损失按\((1-S_i)\)加权，低质量样本获得更大惩罚。损失公式：\[L_{t2c} = \frac{1}{n}\sum_{i=1}^n (1-S_i) L_{i, t2c}\]。
  4. **迭代优化**：伪代码标签在每轮训练后更新，利用最新模型重新生成，形成良性循环。

### 3. 实验设计
- **训练数据集**：从**Wiki-40B-en**随机抽取10,000条，仅用第一段；过滤后5,374条（事实型），因双向训练共10,748样本/迭代。
- **评估数据集**：
  - **摘要任务**：CNN/Daily Mail、SAMSum（对话摘要）。
  - **问答任务**：SQuAD v2、HaluEval（幻觉评估专用）。
- **基准方法**：
  - Base（原始指令模型）、Naive Prompting（简单提示）、SFT（任务特定微调）、SymbCoT（符号思维链）、Lookback（注意力分析检测缓解幻觉）。
- **骨干模型**：LLaMA-3.1-Instruct-8B、Ministral-Instruct-8B、Qwen-2.5-Instruct-7B（均为7B/8B级别）。
- **评估指标**：
  - **幻觉指标**：AlignScore、UniEval Consistency（摘要）、Anah-v2（QA）。
  - **任务指标**：Coherence、Relevance（摘要）；F1、Exact Match（QA）。

### 4. 资源与算力
- **硬件**：4块 **NVIDIA GeForce RTX 4090（24GB）**。
- **框架与配置**：使用LLaMA-Factory进行训练，**3个epoch**，学习率1e-4，batch size 32，LoRA（rank=8）加速。
- **推理**：所有模型（Base、Prompt、FACT、SFT）使用**贪婪解码**。
- **时长**：论文未明确给出训练总时长，但配置与常见LoRA训练（约几小时）相符。

### 5. 实验数量与充分性
- **主要实验**：表1（幻觉指标）和表2（任务指标）覆盖 **3个骨干模型 × 4个数据集 × 6种方法**（Base、Prompt、SFT、SymbCoT、Lookback、FACT），共96组结果。
- **消融实验**（图4、图5）：在CNN/Daily Mail和SQuAD v2上，分别评估去除“事实过滤”、“文本→代码”、“代码→文本”、“质量评估”四个模块的影响，共8组对比。
- **深入分析**：
  - 代码生成质量趋势（图6）：4轮迭代中可执行代码比例和语义相似度变化。
  - 输入/上下文冲突分析（图7）：使用GPT-4.1和人工各评估100个样本。
  - 过滤模块可靠性：人工标注100样本，真阳性率93%，真阴性率92%。
  - 代码推理效果：两阶段推理（先转代码再生成任务输出）与端到端对比。
- **充分性**：实验覆盖多种任务、多种LLM、多维度指标，并进行了人工验证和消融，设计较为全面、客观。

### 6. 主要结论与发现
- **FACT显著减少不一致幻觉**：在三个LLM上，相比最强基线，平均降低幻觉2.7%–8.0%（AlignScore提升2.5%–6.1%）。
- **任务性能同步提升**：在摘要和QA任务指标上，FACT持续优于所有基线，说明减少幻觉能抑制“幻觉滚雪球”效应，提升生成质量。
- **每个模块不可或缺**：消融显示，去除“代码→文本”路径性能下降最大（平均5.72%），其次是“文本→代码”（4.69%），去除质量评估（4.28%），去除事实过滤（3.29%）。
- **代码质量动态提升**：可执行代码比例从87.28%上升至89.71%，语义相似度上升5.23%后在第三轮迭代后稳定。
- **结构化代码可作为忠实中间表示**：两阶段推理（文本→代码→答案）与端到端FACT相比，指标几乎无损，证明代码能保留核心语义。

### 7. 优点
- **任务无关性**：无需为每个NLP任务设计专用数据集或流程，是一个通用框架。
- **创新性**：首次利用代码-文本交替训练将代码的逻辑严谨性迁移到一般NLP任务输出，开辟新视角。
- **伪标签+质量评估**：有效解决了缺少真实代码标注的问题，并通过两阶段检查保证代码质量，形成自我提升的循环。
- **实验充分**：在多种模型、数据集、指标上验证，并包含人工评估和消融分析，可信度高。
- **开源可复现**：使用公开数据集和主流LLM，代码计划公开。

### 8. 不足与局限
- **实验覆盖有限**：仅针对英文摘要和问答任务，未涉及**多语言、长文本、RAG或少样本学习**场景。
- **代码质量仍有改进空间**：经过三轮训练后仍有13.97%的低质量代码（相似度<0.8），存在缺失方法、属性不完整、类设计不合理、格式化不一致等问题。
- **依赖LLM进行文本过滤**：过滤准确率约93%，但仍有误判，可能引入偏差。
- **计算资源明确但未报告总时间**：未估算总训练时间及能耗。
- **方法复杂度**：需要多轮迭代（3轮）生成伪标签并评估，训练成本高于简单SFT。
- **未在更大规模模型（如70B）上验证**：实验限于7B/8B级别，在更大模型上的泛化性和效果不确定。

（完）
