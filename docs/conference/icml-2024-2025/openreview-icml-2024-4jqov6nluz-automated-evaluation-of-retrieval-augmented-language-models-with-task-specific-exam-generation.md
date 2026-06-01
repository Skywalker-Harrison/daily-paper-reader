---
title: Automated Evaluation of Retrieval-Augmented Language Models with Task-Specific Exam Generation
title_zh: 使用任务特定考试自动评估检索增强语言模型
authors: "Gauthier Guinet, Behrooz Omidvar-Tehrani, Anoop Deoras, Laurent Callot"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=4jqOV6NlUz"
tags: ["query:fie-rag"]
score: 5.0
evidence: 自动化RAG评估方法，可应用于事实性推理任务
tldr: 评估RAG系统任务精度的现有方法成本高且不透明。本文提出自动生成合成考试并利用项目反应理论评估，能有效选择最优RAG组件并迭代改进考试。该方法可直接用于factivity推理RAG系统的性能评估与组件选择。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 810, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 831, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1728, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1721, \"height\": 1275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 858, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 868, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 870, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 867, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1737, \"height\": 1156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 858, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 866, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 858, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 869, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 870, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 867, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 868, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 869, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 849, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 849, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 846, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4jqov6nluz/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 845, \"height\": 539, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1796, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 772, \"height\": 875, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 769, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1753, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4jqov6nluz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1772, \"height\": 2036, \"label\": \"Table\"}]"
motivation: 需要成本高效且可解释的方法来评估RAG系统任务特定精度。
method: 基于文档语料自动生成多项选择考试，并利用项目反应理论优化考试质量。
result: 该方法能有效选择RAG系统的最优组件，并给出可解释的评估结果。
conclusion: 提供了一种自动化、可解释的RAG评估策略，可迁移至factivity推理任务。
---

## Abstract
We propose a new method to measure the task-specific accuracy of Retrieval-Augmented Large Language Models (RAG). Evaluation is performed by scoring the RAG on an automatically-generated synthetic exam composed of multiple choice questions based on the corpus of documents associated with the task. Our method is an automated, cost-efficient, interpretable, and robust strategy to select the optimal components for a RAG system. We leverage Item Response Theory (IRT) to estimate the quality of an exam and its informativeness on task-specific accuracy. IRT also provides a natural way to iteratively improve the exam by eliminating the exam questions that are not sufficiently informative about a model's ability. We demonstrate our approach on four new open-ended Question-Answering tasks based on Arxiv abstracts, StackExchange questions, AWS DevOps troubleshooting guides, and SEC filings. In addition, our experiments reveal more general insights into factors impacting RAG performance like size, retrieval mechanism, prompting and fine-tuning. Most notably, our findings show that choosing the right retrieval algorithms often leads to bigger performance gains than simply using a larger language model.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：如何低成本、自动化且可解释地评估检索增强大语言模型（RAG）在特定任务上的事实准确性？
- **背景**：现有评估方法要么依赖人工标注（成本高、不可扩展），要么使用通用基准（无法反映任务特定性能），且缺乏可解释性。RAG系统涉及多个组件（LLM、检索、上下文学习），需要一种能比较不同组件组合的方法。
- **整体含义**：提出一种基于自动生成任务特定选择题考试并利用项目反应理论（IRT）进行评分与优化的评估框架，实现标准化、可解释、可迭代改进的RAG评估。

## 2. 论文提出的方法论
### 核心思想
- 基于任务语料库，由LLM自动生成多项选择题（含一个正确选项、三个干扰项），构成“考试”。
- 通过RAG系统在考试上的得分（正确率）评估其性能，并利用IRT模型对题目质量和模型能力进行联合估计，获得更鲁棒、可分解的评估指标。
- 进一步通过迭代丢弃低区分度题目，优化考试的信息量。

### 关键技术细节
- **考试生成**：
  - 使用LLM（LlamaV2-70B）为每个文档生成候选题目和答案。
  - 过滤：正则表达式解析、候选选项随机排序（防止位置偏差）、自包含检查（避免显式引用文档）、基于Jaccard相似度和嵌入相似度的鉴别器质量过滤（去除干扰项与正确答案或文档过于相似的低质量题目）。
- **点评估**：
  - 对每个RAG管道，计算其在考试上的正确率。选择答案时采用最长长度惩罚对数似然法（来自Gao et al. 2023a）。
- **聚合评估（IRT）**：
  - 使用三参数逻辑模型（3PL）：  
    \( P(X=1|\theta, g_i, d_i, b_i) = g_i + (1-g_i) \frac{1}{1+\exp(-d_i(\theta - b_i))} \)
    - \(\theta\)：模型能力；\(b_i\)：难度；\(d_i\)：区分度；\(g_i\)：猜测因子。
  - **分层IRT模型**：将能力分解为 \(\theta_m = \theta_{\text{llm}(m)} + \theta_{\text{ret}(m)} + \theta_{\text{icl}(m)}\)，分别对应LLM、检索、上下文学习三个组件的能力贡献。
  - 通过最大化对数似然函数联合估计所有模型能力与题目参数，使用L-BFGS-B求解器。
- **迭代考试优化**：
  - 算法1：在每轮中，拟合IRT后丢弃区分度最低的 \(r\) 分位数题目（\(r \approx 10\%\)），保留高信息量的题目，从而提升整体考试信息量。

## 3. 实验设计
### 数据集/场景
- 构建了4个开放域问答任务，每个任务对应一个知识语料库：
  - **tops**（AWS DevOps）：1249个AWS故障排除网页，4536个文档块。
  - **tarx**（Arxiv）：13000篇论文摘要，来自13个研究领域。
  - **tstk**（StackExchange）：977个问答对，来自18个标签。
  - **tsec**（SEC Filings）：493个财务报告章节（来自10家公司）。

### Benchmark/对比方法
- **RAG管道组合**：共45种组合，包括：
  - 5种检索机制：ClosedBook（无检索）、Oracle（访问生成题目的源文档），以及3类经典检索：
    - 稠密：MultiQA、SIAM（Siamese网络）
    - 稀疏：BM25
    - 混合：DPR（SIAM+BM25）、DPRV2（MultiQA+BM25）
  - 3种LLM：Mistral-7B、LlamaV2-13B、LlamaV2-70B
  - 3种上下文学习（ICL）：0、1、2个示例
- **基线/上下界**：ClosedBook作为下界（反映参数知识），Oracle作为上界（反映从正确文档提取答案的能力）。
- **对比分析方法**：点评估（正确率表格）、分层IRT能力分析、Bloom分类法分析、语义类型分析。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。
- 提到使用了LlamaV2-70B生成考试题目（推理），以及Mistral-7B、LlamaV2-13B/70B进行评估（推理），IRT模型拟合采用L-BFGS-B优化（计算量不大）。
- 总体算力需求属于中等水平，但由于未详细报告，无法精确量化。

## 5. 实验数量与充分性
- **实验数量**：在4个数据集上，对45种RAG组合进行了点评估（每个组合获得一个正确率），并进行了IRT模型拟合（含分层分解）。此外，对每个任务进行了Bloom分类分析和语义类型分析，以及迭代改进实验（k步）。
- **充分性与公平性**：
  - 检索方法覆盖了稠密、稀疏、混合三大类主流方法，LLM覆盖7B到70B三个规模，ICL覆盖0、1、2示例，组合较全面。
  - 设置了ClosedBook和Oracle作为上下界，保证了比较的合理性。
  - 考试生成使用单独模型（LlamaV2-70B）与评估模型不重叠，避免数据泄露。
  - 进行了随机化候选选项、过滤低质量题目等预处理，减少偏差。
  - 不足：未对比其他RAG评估方法（如RAGAs、ARES）进行直接比较，而是通过逻辑论证说明其优势；实验主要集中在选择题格式，未扩展到生成式评估。

## 6. 论文的主要结论与发现
1. **检索机制选择比增大模型规模更重要**：在许多任务上，切换更好的检索方法带来的性能提升超过从7B升级到70B。
2. **混合检索通常最好**：DPRV2（MultiQA+BM25+Cross-encoder重排）在多数任务上优于纯稠密或纯稀疏方法。
3. **任务特定性**：没有一种检索方法在所有任务上绝对最优；例如，BM25在Arxiv和SEC任务上表现更好（关键词明显），而MultiQA在StackExchange上更强。
4. **封闭知识任务中，LLM是瓶颈**：对于LLM未见过的专有文档（如SEC），Oracle得分远高于ClosedBook，说明检索至关重要。
5. **不良检索可能比无检索更差**：如SIAM在某些任务上低于ClosedBook。
6. **IRT提供深入诊断**：通过分层IRT可量化每个组件的能力贡献；通过题目信息函数可识别哪些类型的问题最有区分度（如“what”和“which”问题对低能力模型更有区分力，“when”问题对高能力模型更有区分力）。
7. **迭代改进可提升考试信息量**：通过丢弃低区分度题目，考试的信息函数在多数能力区域得到帕累托改善。

## 7. 优点
- **完全自动化**：无需人工标注，仅需任务语料库和LLM，可扩展。
- **可解释性强**：正确率直观，IRT提供题目级和组件级分析，Bloom分类和语义分析揭示模型强弱项。
- **成本高效**：仅需推理LLM生成和评估，无需训练新模型。
- **鲁棒性**：通过IRT加权减少低质量题目的影响，迭代优化进一步提升考试质量。
- **开源可用**：提供代码仓库，便于复现和适配新任务。

## 8. 不足与局限
- **考试形式限制**：仅使用多项选择题，无法直接评估生成式回答的忠实度、完整性和流畅性等维度。对于需要自由回答的任务（如摘要、对话），该方法不直接适用。
- **依赖生成LLM质量**：题目生成的质量受限于LLM（LlamaV2-70B），可能引入偏差；过滤步骤虽能排除部分低质量题目，但无法完全消除。
- **未与其他评估方法直接对比**：论文未在相同数据集上运行RAGAs、ARES等最新方法进行定量比较，仅通过理论分析论证优势，说服力有限。
- **任务覆盖有限**：所有任务均为英文开放域QA，未测试多语言或领域特定（如医疗、法律）场景。
- **迭代改进的局限**：当前仅通过丢弃题目来提升信息量，未尝试生成更优质的新题目或自适应题目选择。
- **算力和环境未透明**：缺乏计算资源报告，不利于复现和公平比较。
- **仅评估事实准确性**：未覆盖其他重要维度，如安全性、偏见、毒性等。

（完）
