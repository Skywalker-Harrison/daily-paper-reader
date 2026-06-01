---
title: Reliable Decision‑Making via Calibration‑Oriented Retrieval‑Augmented Generation
title_zh: 基于校准的检索增强生成实现可靠决策
authors: "Chaeyun Jang, Deukhwan Cho, Seanie Lee, Hyungi Lee, Juho Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Rgk129n73h"
tags: ["query:fie-rag"]
score: 6.0
evidence: 基于校准的检索增强生成用于可靠决策
tldr: 现有RAG方法仅关注检索相关性，未考虑人类决策校准。提出校准导向的RAG，通过优化检索文档使模型输出更可靠，减少错误信息对决策的影响。实验表明校准效果提升，但未涉及少样本或语言学特征。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1321, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1384, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1426, \"height\": 2103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1426, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgk129n73h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1332, \"height\": 281, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 699, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 701, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1172, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1458, \"height\": 584, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1018, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 887, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 584, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1384, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1264, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1374, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1387, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1388, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgk129n73h/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1098, \"height\": 809, \"label\": \"Table\"}]"
motivation: 传统RAG未针对决策校准优化，导致模型可能输出错误信息误导用户。
method: 提出校准导向的RAG，将决策校准纳入检索优化目标。
result: 在决策任务上提高了校准性和准确性。
conclusion: 校准导向的RAG能提升基于LLM的决策可靠性。
---

## Abstract
Recently, Large Language Models (LLMs) have been increasingly used to support various decision-making tasks, assisting humans in making informed decisions. However, when LLMs confidently provide incorrect information, it can lead humans to make suboptimal decisions. To prevent LLMs from generating incorrect information on topics they are unsure of and to improve the accuracy of generated content, prior works have proposed Retrieval Augmented Generation (RAG), where external documents are referenced to generate responses. However, previous RAG methods focus only on retrieving documents most relevant to the input query, without specifically aiming to ensure that the human user's decisions are well-calibrated. To address this limitation, we propose a novel retrieval method called Calibrated Retrieval-Augmented Generation (CalibRAG), which ensures that decisions informed by RAG are well-calibrated. Then we empirically validate that CalibRAG improves calibration performance as well as accuracy, compared to other baselines across various datasets.

---

## 论文详细总结（自动生成）

# 基于校准的检索增强生成实现可靠决策（CalibRAG）——论文总结

## 1. 核心问题与研究动机

- **背景**：大型语言模型（LLMs）被广泛应用于辅助人类决策，但其可能自信地输出错误信息（幻觉），导致用户过度依赖并做出次优决策。检索增强生成（RAG）通过引入外部文档可缓解幻觉，但现有RAG方法仅关注检索与查询最相关的文档，**并未针对人类决策的校准（calibration）进行优化**。
- **核心问题**：如何使RAG在支持决策时不仅能提供准确信息，还能输出**经过校准的置信度**（即预测置信度与实际正确概率一致），从而避免用户因高置信度错误信息而做出错误判断。

## 2. 方法论

### 2.1 核心思想
提出**CalibRAG**框架，训练一个**预测函数 \(f(t, q, d)\)**，输入用户风险偏好（解码温度 \(t\)）、查询 \(q\)、候选文档 \(d\)，输出该文档辅助用户做出正确决策的概率（置信度）。推理时，利用该函数对检索出的Top-K文档进行**重排序**，选择预测置信度最高的文档来生成最终指导与置信度。

### 2.2 关键技术细节

1. **合成监督数据生成**：
   - 从TriviaQA、SQuAD2.0、WikiQA提取问题-答案对 \((x, y)\)。
   - 为每个 \(x\) 生成开放式查询 \(q\)，并用检索模型获取Top-20文档。
   - 对每个 \((t, q, d)\) 三元组：
     - RAG模型 \(M\) 根据文档生成指导 \(z\)。
     - 用户代理模型 \(U\)（基于LLM）在温度 \(t\) 下采样 \(R=10\) 次决策，用评估模型 \(G\)（GPT-4o-mini）判断决策是否正确。
     - 计算正确比例作为**软标签** \(b \in [0,1]\)。
   - 构建训练集 \(\mathcal{S} = \{(t, q, d, b)\}\)。

2. **预测函数建模**：
   - 特征提取器 \(f_{\text{feat}}\)：采用冻结的LLM \(M\)，取倒数第二层最后一个token的隐藏状态。
   - 温度编码：对 \(t\) 使用傅里叶位置编码 \(\text{PE}(t)\)，经线性投影后加到特征上。
   - 分类头：在特征上接线性层，输出置信度 \(c = f(t,q,d) = \sigma(W_{\text{head}}^\top (f_{\text{feat}} + W_p\text{PE}(t)) + b_{\text{head}})\)。
   - 使用LoRA微调LLM部分参数，其余头参数可学习。
   - 训练损失：对数损失（二元交叉熵），为严格适当评分规则，利于校准。

3. **推理流程**：
   - **阶段1**：检索Top-K文档（K=20）。
   - **阶段2**：用 \(f(t,q,d)\) 对文档打分，按置信度降序排列；若最高置信度低于阈值 \(\epsilon=0.5\)，则进入阶段3；否则进入阶段4。
   - **阶段3（可选）**：重写查询 \(q\)，再次检索并重复阶段1-2。
   - **阶段4**：用选中文档生成指导 \(z\)，输出置信度 \(c\)，供用户决策。

## 3. 实验设计

### 3.1 数据集与场景
- **训练数据**：TriviaQA、SQuAD2.0、WikiQA（共20,870训练样本，4,125验证样本）。
- **通用域评估**：Natural Questions (NQ)、WebQA、HotpotQA（零样本）。
- **医学域评估**：BioASQ-Y/N、MMLU-Med、PubMedQA（MIRAGE基准，使用域内检索器MedCPT，评估跨域泛化）。

### 3.2 对比方法
- **不确定性校准基线**：
  - Calibration Tuning（CT-LoRA、CT-probe）
  - 口头化置信度（Linguistic-LoRA、Number-LoRA）
- **重排序与鲁棒RAG基线**：
  - Cross-encoder (MiniLM-L6-v2)
  - LLM-rerank (GPT-3.5-turbo)
  - SelfRAG

### 3.3 评估指标
- AUROC（准确性）、ACC（准确率）、ECE（期望校准误差）、Brier Score（BS）；在图中以“1-ROC、1-ACC”形式展示（值越低越好）。

## 4. 资源与算力

- **硬件**：NVIDIA RTX 3090 和 RTX A6000 GPUs。
- **框架**：PyTorch 2.1.2、HuggingFace Transformers、PEFT。
- **训练细节**：最大步数10,000，批次大小1或4，梯度累积步数[1,4]。
- **未明确说明**：具体GPU数量、训练总时长、推理时算力消耗等未提供。

## 5. 实验数量与充分性

- **主要对比实验**：在通用域（NQ、WebQA）使用BM25和Contriever两种检索器；在医学域（BioASQ-Y/N、MMLU-Med、PubMedQA）使用MedCPT检索器。均与多个基线对比。
- **重排序对比**：HotpotQA上对比Cross-encoder和LLM-rerank。
- **鲁棒RAG对比**：NQ、WebQA上对比SelfRAG。
- **消融实验**：
  - 温度条件化 vs 无温度条件化。
  - 检索文档数K的影响（5,10,20,40）。
  - 查询重公式化（Stage 3）的效果。
  - 不同用户模型（Phi-4、DeepSeek-Distill）的鲁棒性。
  - 阈值 \(\epsilon\) 的影响。
  - 在BEIR基准（SciFact、TREC-COVID）上的额外验证。
- **各实验均报告3个随机种子的均值和标准差**，统计严谨。

**评价**：实验丰富，覆盖多领域、多检索器、多基线类型，消融充分，对比客观。但所有评估依赖GPT-4o-mini自动判断，可能引入模型偏好偏差；未进行真实用户实验。

## 6. 主要结论

- CalibRAG在**所有评估数据集**和**所有指标**上均优于现有不确定性校准基线和重排序基线。
- 温度条件化建模显著提升校准性能，尤其在用户行为变化时。
- 重排序（基于预测置信度）和查询重公式化可进一步提升准确性。
- 即使在不使用重排序的情况下，CalibRAG的预测函数本身也能提供更好的校准。
- 在未见过的检索器和跨域（通用→医学）场景下鲁棒性好。

## 7. 优点

- **新颖性**：首次将决策校准作为RAG优化的直接目标，区别于仅优化相关性的传统方法。
- **方法设计合理**：通过温度编码模拟用户风险偏好，用软标签（自一致性采样）训练预测函数，严格适当评分规则保证校准性。
- **实用性强**：推理时仅需对候选文档进行一次前向预测，避免为每个文档生成完整指导，高效。
- **实验全面**：涵盖通用/医学域、两种检索器类型、多组基线、充分消融，结果统计显著。

## 8. 不足与局限

- **依赖合成数据与额外训练**：构建合成数据集和训练预测函数引入额外开销；预测函数需基于特定LLM（Llama-3.1-8B），迁移性待验证。
- **评估自动化**：依赖GPT-4o-mini评估正确性，可能引入模型自身偏差，且未能覆盖所有可能的用户决策语义。
- **用户模拟**：使用LLM代理用户（U），无法完全反映真实人类决策中的复杂行为（如部分依赖、知识背景）。
- **领域泛化**：医学域实验中，训练数据不含医学样本，虽表现良好，但其他低资源领域可能受限。
- **阈值设定**：默认\(\epsilon=0.5\)依赖实验调优，缺乏理论指导。
- **未讨论隐私/公平性**：未分析决策任务中可能涉及的敏感偏差。

（完）
