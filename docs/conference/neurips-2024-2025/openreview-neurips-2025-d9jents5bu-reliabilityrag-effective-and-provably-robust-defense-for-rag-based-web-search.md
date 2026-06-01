---
title: "ReliabilityRAG: Effective and Provably Robust Defense for RAG-based Web-Search"
title_zh: ReliabilityRAG：针对基于RAG的网络搜索的有效且可证明鲁棒的防御
authors: "Zeyu Shen, Basileal Yoseph Imana, Tong Wu, Chong Xiang, Prateek Mittal, Aleksandra Korolova"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=D9JeNTs5Bu"
tags: ["query:fie-rag"]
score: 4.0
evidence: RAG鲁棒性防御，间接确保RAG输出的事实性
tldr: ReliabilityRAG针对RAG检索语料攻击提出有效且可证明鲁棒的防御框架。利用文档排序等可靠性信息过滤注入样本。虽主要关注安全性，但确保RAG输出不受恶意干扰间接提升了事实可靠性。对于事实性推理任务，可借鉴其可靠性信号来筛选高置信度证据文档。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 546, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 964, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1424, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1425, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d9jents5bu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 566, \"height\": 417, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1459, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1460, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 655, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1261, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1277, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1132, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1143, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1337, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 928, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 882, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 880, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1403, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d9jents5bu/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1412, \"height\": 618, \"label\": \"Table\"}]"
motivation: RAG系统易受检索语料攻击，需要鲁棒防御机制保障输出可靠性。
method: 显式利用检索文档的可靠性信息（如排序）设计防御算法，提供理论鲁棒性保证。
result: 在对抗性攻击下显著提升RAG输出的安全性和可靠性。
conclusion: 该框架为RAG安全提供了重要保障，其可靠性信号也可用于提升事实性推理中的证据质量。
---

## Abstract
Retrieval-Augmented Generation (RAG) enhances Large Language Models by grounding their outputs in external documents. These systems, however, remain vulnerable to attacks on the retrieval corpus, such as prompt injection. RAG-based search systems (e.g., Google’s Search AI Overview) present an interesting setting for studying and protecting against such threats, as defense algorithms can benefit from built-in reliability signals—like document ranking—and represent a non-LLM challenge for the adversary due to decades of work to thwart SEO.

Motivated by, but not limited to, this scenario, this work introduces ReliabilityRAG, a framework for adversarial robustness that explicitly leverages reliability information of retrieved documents.

Our first contribution adopts a graph-theoretic perspective to identify a ``consistent majority'' among retrieved documents to filter out malicious ones. We introduce a novel algorithm based on finding a Maximum Independent Set (MIS) on a document graph where edges encode contradiction. Our MIS variant explicitly prioritizes higher-reliability documents and provides provable robustness guarantees against bounded adversarial corruption under natural assumptions. Recognizing the computational cost of exact MIS for large retrieval sets, our second contribution is a scalable weighted sample and aggregate framework. It explicitly utilizes reliability information, preserving some robustness guarantees while efficiently handling many documents.

We present empirical results showing ReliabilityRAG provides superior robustness against adversarial attacks compared to prior methods, maintains high benign accuracy, and excels in long-form generation tasks where prior robustness-focused methods struggled. Our work is a significant step towards more effective, provably robust defenses against retrieved corpus corruption in RAG.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：检索增强生成（RAG）系统在大语言模型（LLM）中广泛应用，但检索到的文档可能被攻击者污染（如提示注入、语料投毒），导致模型输出恶意或错误内容。现有防御方法（如RobustRAG）通过多数投票等方式提供鲁棒性，但在长文本生成任务中表现不佳，且忽略了检索器提供的**文档可靠性信号**（如搜索引擎排名、权重分数）。
- **核心问题**：如何利用可靠性信号（排序或权重）来构建一个**可证明鲁棒**、同时保持高良性准确率且支持长文本生成的RAG防御框架。
- **整体含义**：提出ReliabilityRAG，通过图理论（最大独立集）和加权采样聚合，显式利用文档可靠性信息，在对抗性攻击下提供理论保证和实验优越性。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 核心思想
- 利用文档间的**矛盾关系**构建“矛盾图”，然后寻找**最大独立集（MIS）**作为筛选后的文档子集，同时利用文档排序（可靠性）作为平局决策依据，优先选择高可靠性文档。

### 关键技术细节
1. **矛盾图构建**：
   - 对每个文档 $x_i$，先用LLM基于孤立文档生成答案 $y_i$（单独回答）。
   - 使用NLI模型（如DeBERTa-v3）对任意两个答案 $(y_i, y_j)$ 判断是否矛盾，若矛盾概率大于阈值 $\beta=0.5$，则在文档节点间添加边。
   - 得到无向图 $G=(V,E)$，节点为文档，边为矛盾。

2. **MIS搜索（Ordinal-Reliability设置）**：
   - 枚举所有子集，选择满足独立集条件且**大小最大**的子集；若多个相同大小，选择**字典序最小**的子集（即优先高排名文档）。
   - 将该子集文档输入LLM生成最终答案。
   - **理论保证**：当NLI错误率有界、恶意文档数不超过一定比例时，MIS不包含恶意文档的概率以指数级趋近于1（定理1）。

3. **加权采样与聚合框架（Cardinal-Reliability设置）**：
   - 当文档数量较大（>20）时，MIS求解指数时间不可行。
   - 使用文档权重（如指数衰减权重 $w(x_i)\propto \gamma^{i-1}$）进行有放回采样，生成 $T$ 个大小为 $m$ 的上下文。
   - 对每个上下文调用LLM生成中间答案，然后用聚合器（可包括MIS）合并所有中间答案。
   - 理论保证：当干净上下文比例足够高，且采样轮数满足霍夫丁不等式条件时，系统以高概率保持鲁棒（定理3）。

## 3. 实验设计
### 数据集与场景
- **QA数据集**：RealtimeQA (RQA)、Natural Questions (NQ)、TriviaQA (TQA) —— 各自采样100/500/500个问题。
- **长文本生成**：Biography generation (Bio) —— 50个传记实体。
- **场景类型**：
  - **良性设置**：无攻击，评估准确率。
  - **对抗攻击**：
    - 提示注入（Prompt Injection）
    - 语料投毒（Corpus Poisoning）
    - 攻击位置：单文档攻击（位置1、10、25、50）和多文档后缀攻击（0~4个或0~20个文档）。
    - 还测试了**自适应攻击**（使恶意文档通过NLI检测）。

### 对比方法（baselines）
- **Vanilla RAG**：无防御的基线。
- **RobustRAG (Keyword)**：现有鲁棒RAG方法。
- **AstuteRAG**：处理知识冲突的方法。
- **InstructRAG**：通过自合成理由去噪的方法。
- 此外，还对比了**MIS (k=10)** 和 **Sampling+MIS (k=50)** 两种变体。

### 评估指标
- QA：GPT-4o作为LLM裁判，判断回答是否正确，输出**准确率（Accuracy %）**。
- Bio：GPT-4o从事实准确性、相关性/召回率、连贯性三方面打分（0-100），输出**LLM-Judge Score**。

## 4. 资源与算力
- **硬件**：实验在**单个NVIDIA A100 (80GB)** GPU上运行。
- **时间**：论文提供了中位延迟数据（表14）：
  - 对于k=10，MIS方法总耗时约0.4~0.6秒（其中孤立回答阶段占主要部分）。
  - 对于k=50，Sampling+MIS总耗时约0.9~1.3秒。
- 未报告训练时长（因为方法无需训练，直接基于预训练模型进行推理）。

## 5. 实验数量与充分性
- **实验量丰富**：
  - 覆盖3个QA数据集 + 1个长文本数据集，共约1150个查询。
  - 使用3种不同规模的LLM（Mistral-7B, Llama3.2-3B, GPT-4o-mini）。
  - 对比4种baseline方法（外加无防御RAG）。
  - 测试了2种攻击类型、多个攻击位置、多文档攻击、自适应攻击。
  - 进行了**消融实验**：参数敏感性（m, T, γ 影响）、NLI退化模拟、不同NLI模型、多轮实验（5次重复+置信区间）。
- **充分性与公平性**：
  - 论文展示了误差棒（95%引导法置信区间），确保统计可靠性。
  - 实验设计覆盖了良性、攻击、参数变化等多种视角，对比方法均为公开可复现的SOTA。整体实验设计系统、客观，足以支撑主要结论。

## 6. 论文的主要结论与发现
1. **MIS方法在k=10时具有显著鲁棒性**：在良性条件下准确率高（与无防御方法相当），且在攻击下大幅优于其他鲁棒方法（如RobustRAG），尤其在Bio长文本生成任务上优势明显。
2. **等级感知特性**：MIS在攻击位于低排名文档时表现更好，体现了对可靠性信号的利用。
3. **Sampling+MIS在k=50时有效扩展**：保持了高良性性能，且在攻击中低排名文档时鲁棒性突出；在多文档后缀攻击下，性能下降比RobustRAG更平缓。
4. **理论保证**：提供了在NLI错误率有界条件下的概率鲁棒性证明，为实际应用提供了可依赖的安全边界。
5. **自适应攻击**：针对NLI的简单自适应攻击虽然能增加恶意文档被选中的概率，但由于输出质量下降（“越狱税”），最终准确率未降低。

## 7. 优点（亮点）
- **创新性**：首次将文档可靠性信号（排序/权重）显式用于RAG对抗防御，并给出图视角下的形式化处理（MIS）。
- **可证明鲁棒性**：提供了非平凡的理论保证（指数级概率），填补了现有方法缺乏严谨证明的空白。
- **实用性与可扩展性**：通过加权采样聚合框架解决MIS的计算瓶颈，适用于大规模检索场景。
- **保持高良性准确率**：相比其他鲁棒方法（如RobustRAG的Keyword投票），MIS在无攻击时几乎没有性能损失，且长文本生成能力显著更强。
- **模块化设计**：MIS作为预处理筛选步骤，可与下游任何聚合器或推理策略组合，具有良好兼容性。

## 8. 不足与局限
- **依赖NLI模型性能**：NLI的准确性直接影响矛盾图的质量，虽然理论考虑了误差，但实际中若NLI被高端对抗攻击则可能失效。论文仅测试了有限自适应攻击。
- **计算开销**：孤立回答阶段需要为每个文档单独调用LLM，增加了延迟（约0.4-0.6秒/查询）。论文提供了优化建议但未系统验证。
- **参数与设计选择为启发式**：如MIS平局选择字典序最小、采样参数(m, T, γ)等，论文虽做了消融，但缺乏最优性证明，不同场景可能需要重新调参。
- **过度依赖搜索引擎可靠性假设**：假定高阶文档更难被攻击，这一假设基于SEO防御，但在其他检索场景（学术语料、企业知识库）可能不直接成立。
- **实验基准性局限**：数据集来自标准学术基准，可能不完全反映真实网络搜索的多样性；评估依赖GPT-4o作为裁判，存在潜在偏差。
- **未深入测试更复杂的自适应攻击**：虽然尝试了一种简单自适应攻击，但更精巧的、利用多文档上下文做条件行为的攻击可能仍能规避检测，论文承认这是未来方向。

（完）
