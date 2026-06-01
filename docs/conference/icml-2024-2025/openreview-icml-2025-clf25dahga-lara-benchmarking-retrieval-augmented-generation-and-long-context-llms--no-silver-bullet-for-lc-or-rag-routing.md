---
title: "LaRA: Benchmarking Retrieval-Augmented Generation and Long-Context LLMs – No Silver Bullet for LC or RAG Routing"
title_zh: LaRA：检索增强生成与长上下文大语言模型的基准测试——长上下文或RAG路由没有银弹
authors: "Kuan Li, Liwen Zhang, Yong Jiang, Pengjun Xie, Fei Huang, Shuai Wang, Minhao Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CLF25dahgA"
tags: ["query:fie-rag"]
score: 4.0
evidence: RAG基准测试，可用于factivity推理任务的RAG方法选择
tldr: 现有RAG与长上下文LLM的对比因基准限制而结论不明。本文提出LaRA基准，通过2326个测试用例系统评估两者在不同任务和上下文条件下的表现，揭示了模型能力、上下文长度、任务类型和检索特性共同决定最优选择。该基准可为factivity推理中的RAG路由设计提供参考。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 467, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 1344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1094, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1142, \"height\": 194, \"label\": \"Table\"}]"
motivation: 现有RAG与长上下文LLM对比因基准限制而不明确。
method: 构建包含2326个测试用例的LaRA基准，覆盖4种问答任务和3种长上下文类型。
result: 发现RAG与LC的最优选择取决于模型能力、上下文长度、任务类型和检索特性。
conclusion: 为RAG路由提供了可操作指南，可辅助factivity推理中RAG方案的选择。
---

## Abstract
As Large Language Model (LLM) context windows expand, the necessity of Retrieval-Augmented Generation (RAG) for integrating external knowledge is debated. Existing RAG vs. long-context (LC) LLM comparisons are often inconclusive due to benchmark limitations. We introduce LaRA, a novel benchmark with 2326 test cases across four QA tasks and three long context types, for rigorous evaluation. Our analysis of eleven LLMs reveals the optimal choice between RAG and LC depends on a complex interplay of model capabilities, context length, task type, and retrieval characteristics, offering actionable guidelines for practitioners. Our code and dataset is provided at:https://github.com/Alibaba-NLP/LaRA

---

## 论文详细总结（自动生成）

# 论文总结：LaRA：检索增强生成与长上下文大语言模型的基准测试——长上下文或RAG路由没有银弹

## 1. 论文的核心问题与整体含义（研究动机和背景）
随着大语言模型（LLM）上下文窗口的扩展（如 GPT-4o、Llama 3.2、Claude 3.5 等支持到 128k token），检索增强生成（RAG）在整合外部知识方面的必要性受到质疑。现有关于 RAG 与长上下文（LC）LLM 的对比研究因基准设计缺陷（如上下文长度不足、数据泄露、评估指标不合理、任务设计不现实等）而结论不一，缺乏清晰指引。本文旨在通过构建更严谨的基准 LaRA，系统比较 RAG 和 LC 在不同条件下的表现，为实践者提供可操作的选择指南。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：设计一个能真实反映实际使用场景的基准，涵盖多种上下文类型和任务，并严格控制数据泄露和评估准确性。
- **基准构建**：
  - 选择三种长上下文类型：**小说、学术论文、财务报表**（分别代表不同写作风格和信息密度），均为自然长文本（非人工拼接）。
  - 上下文长度设计为 32k 和 128k token，贴近主流模型能力上限，避免截断。
  - 对小说进行实体替换（使用 GPT-4o 识别并替换角色名称），防止数据泄露。
  - 通过人工编写种子问题 + GPT-4o 生成 QA 对，并迭代优化直到通过率≥90%。
- **任务类型**：四种 QA 任务，评估不同能力：
  - **定位（Location）**：在文本中定位具体信息（如名字、数值）。
  - **推理（Reasoning）**：需要逻辑推导或计算（如推断关系、计算财务数据）。
  - **比较（Comparison）**：综合多个部分信息进行比较（如对比不同段落的数据或观点）。
  - **幻觉检测（Hallucination Detection）**：判断问题是否在上下文中无答案，模型应拒绝回答。
- **评估方式**：使用 GPT-4o 作为评判者（LLM-as-a-judge），并与人工评估计算 Cohen's Kappa 系数（高度一致）以确保可靠性。

## 3. 实验设计：数据集、场景与对比方法
- **数据集**：LaRA 基准包含 **2326 个测试用例**，覆盖四种任务和三种上下文类型（小说、论文、财务报表），每个类型有 32k 和 128k 两种长度。
- **对比方法**：
  - **RAG**：使用 GTE-large-en-v1.5 嵌入模型 + BM25 混合检索，chunk size 600 token，5 chunks，重叠 100 token。
  - **LC**：直接将完整上下文输入模型。
- **评估模型**：11 个 LLM，包括 7 个开源（Llama-3.2-3B/3.1-8B/3.3-70B 等，Qwen-2.5-7B/72B，Mistral-Nemo-12B）和 4 个商业模型（GPT-4o、GPT-4o-mini、Claude-3.5-Sonnet、Gemini-1.5-Pro）。

## 4. 资源与算力
论文未明确提及实验所使用的 GPU 型号、数量或训练时长。仅说明代码和数据集已开源（https://github.com/Alibaba-NLP/LaRA），但未提供具体算力信息。推测实验主要基于 API 调用（如 GPT-4o）和常规开源模型推理，未涉及大规模预训练。

## 5. 实验数量与充分性
- **总实验量**：对 11 个模型在 4 种任务 × 2 种上下文长度下进行 RAG 和 LC 对比，共 11×4×2×2 = 176 组主要实验结果（表 2）。此外还有消融实验：
  - **chunk 数量和大小的影响**（图 2）：在 7B 和 72B 模型上测试不同 chunk 数（5~30）和 chunk 大小（200~2000）。
  - **“Lost in the Middle”分析**（图 6）：控制答案位置，观察 LC 和 RAG 在不同位置的表现。
  - **上下文类型影响**（图 1）。
- **充分性评价**：实验设计较为全面，覆盖了主流模型、多种任务和参数变化。消融实验合理，控制了关键变量（chunk 参数、答案位置、上下文类型）。但未包含多跳推理或更复杂的检索策略（如迭代检索、重排序优化对比），且仅使用一种 RAG 配置（固定 chunk size 和数量），缺乏对检索模块本身的系统消融。

## 6. 论文的主要结论与发现
- **RAG vs. LC 无万能答案**，最优选择取决于模型能力、上下文长度、任务类型和检索特性。
- **模型强度**：弱模型从 RAG 获益更大（如 128k 下 Llama-3.2-3B 和 Mistral-Nemo-12B 分别提升 6.48% 和 38.12%）；强模型（GPT-4o、Claude-3.5）LC 优于 RAG。
- **上下文长度**：32k 时 LC 平均高 2.4%，128k 时 RAG 平均高 3.68%。
- **任务类型**：
  - 定位：两者相近，长上下文时 RAG 占优。
  - 推理：LC 略优（尤其强模型）。
  - 比较：LC 大幅优于 RAG（平均 gap 14~15%）。
  - 幻觉检测：RAG 明显优于 LC，LC 易产生幻觉。
- **上下文类型**：小说最难，论文最简单；LC 在结构化文本（论文、财报）上优势更明显。
- **Chunk 参数**：增大 chunk 数对强模型有益，弱模型存在最优值；chunk 大小影响不如 chunk 数量显著。
- **Lost in the Middle**：LC 存在明显的“中间丢失”现象，RAG 不受答案位置影响。

## 7. 优点
- **基准构建严谨**：解决了现有基准的多个缺陷（长度不足、数据泄露、不合适截断、不合理评估指标），确保公平性。
- **任务设计贴近实际**：四类任务覆盖了真实使用场景（定位、推理、比较、拒答），且问题都是人可能提出的有意义问题。
- **评估可靠性**：使用 GPT-4o 作为评判者并通过 Cohen's Kappa 验证，优于传统 F1/EM 指标。
- **分析全面**：不仅比较整体性能，还深入分析模型规模、上下文长度、任务类型、上下文类型、检索参数和答案位置的影响，结论细致且可操作。
- **消融实验充分**：对 chunk 数量/大小、答案位置等进行了系统分析。

## 8. 不足与局限
- **检索方法单一**：仅采用一种 RAG 配置（固定 chunk size、BM25+嵌入混合检索），未探索更先进的检索策略（如自适应检索、多轮检索、重排序优化），结论可能受限于检索模块质量。
- **未考虑多文档场景**：LaRA 基于单一文档上下文，未评估多文档 RAG 或跨文档比较。
- **上下文类型有限**：仅三种（小说、论文、财报），未覆盖更多样化领域（如法律、医疗、对话等）。
- **数据泄露控制有限**：仅对小说进行实体替换，但论文和财报可能也存在于训练数据中（尽管选自 2024 年，但仍有风险）。
- **计算资源未汇报**：未提及实验所用的 GPU 型号、数量或推理成本，可复现性受影响。
- **依赖 LLM 评判**：尽管验证了与人类一致，但 LLM 作为评判者仍存在偏差风险（尤其对长答案或复杂推理）。
- **未对比不同 RAG 框架**：如是否使用查询重写、分解、摘要等高级组件。
- **未测试超长上下文（>128k）**：论文只测试 32k/128k，未覆盖 256k/1M 等更极端长度。

（完）
