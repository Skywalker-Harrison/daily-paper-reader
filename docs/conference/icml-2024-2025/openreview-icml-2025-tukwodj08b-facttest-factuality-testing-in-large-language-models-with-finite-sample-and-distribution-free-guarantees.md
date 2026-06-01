---
title: "FactTest: Factuality Testing in Large Language Models with Finite-Sample and Distribution-Free Guarantees"
title_zh: FactTest：具有有限样本和无分布保证的大语言模型事实性测试
authors: "Fan Nie, Xiaotian Hou, Shuhang Lin, James Zou, Huaxiu Yao, Linjun Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tuKwODJ08b"
tags: ["query:fie-rag"]
score: 6.0
evidence: 用于LLM的事实性测试框架
tldr: 大型语言模型常生成幻觉内容，缺乏可靠的事实性保证。FactTest提出一个新颖框架，将幻觉检测形式化为假设检验问题，可对Type I错误进行用户指定上界的控制。该方法无需分布假设，有限样本即可提供高概率正确性保证。该框架为事实性检测提供了理论严谨的工具，可迁移至叙事性推理中的事实性判断。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1668, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 776, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1239, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1588, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1400, \"height\": 2146, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1668, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1100, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1100, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tukwodj08b/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1703, \"height\": 1501, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1599, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1155, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1600, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1597, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1602, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1423, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1421, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1251, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1070, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 629, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1336, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tukwodj08b/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 893, \"height\": 265, \"label\": \"Table\"}]"
motivation: LLM生成内容的事实性缺乏形式化验证，亟需统计保证。
method: 将幻觉检测作为假设检验问题，通过有限样本无分布方法控制Type I错误。
result: 在多个数据集上证明能有效控制错误率，提供高概率正确性保证。
conclusion: FactTest为LLM事实性评估提供了首个统计保证框架，可推广到事实性检测任务。
---

## Abstract
The propensity of large language models (LLMs) to generate hallucinations and non-factual content undermines their reliability in high-stakes domains, where rigorous control over Type I errors (the conditional probability of incorrectly classifying hallucinations as truthful content) is essential. Despite its importance, formal verification of LLM factuality with such guarantees remains largely unexplored.
In this paper, we introduce FactTest, a novel framework that statistically assesses whether an LLM can provide correct answers to given questions with high-probability correctness guarantees. We formulate hallucination detection as a hypothesis testing problem to enforce an upper bound of Type I errors at user-specified significance levels. Notably, we prove that FactTest also ensures strong Type II error control under mild conditions and can be extended to maintain its effectiveness when covariate shifts exist. Our approach is distribution-free and works for any number of human-annotated samples. It is model-agnostic and applies to any black-box or white-box LM. Extensive experiments on question-answering (QA) benchmarks demonstrate that FactTest effectively detects hallucinations and enable LLMs to abstain from answering unknown questions, leading to an over 40% accuracy improvement.

---

## 论文详细总结（自动生成）

# 论文总结：FactTest：具有有限样本和无分布保证的大语言模型事实性测试

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：大语言模型（LLMs）在生成文本时容易产生“幻觉”（hallucination），即输出不准确、非事实性的内容。在高风险领域（如医疗、法律）中，需要严格控制在错误地将幻觉认定为正确内容时的概率（即Type I错误）。然而，现有的幻觉检测方法（如基于检索、微调或不确定性估计）大多无法提供统计保证。
- **动机**：首次将LLM事实性评估形式化为一个假设检验问题，并提供一个有限样本、无分布假设的统计框架，确保Type I错误率低于用户指定的显著性水平α，同时还能控制Type II错误（漏检真实正确内容的概率），并处理协变量偏移（covariate shift）场景。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将幻觉检测视为Neyman-Pearson分类问题，构造一个二元分类器 f̂_α(q, M(q)) = I(η̂(q, M(q)) > τ̂_α)，其中η̂是得分函数（衡量模型回答正确性的置信度），τ̂_α是基于校准数据集中错误样本（y=0）的得分排序统计量确定的阈值。
- **关键技术细节**：
  - **校准数据集构建**：将已有标注数据集D按模型回答是否正确分为正确子集D₁和错误子集D₀。
  - **阈值选择**：对D₀中样本计算得分{Ti}，升序排列得T(1) ≤ ... ≤ T(n0)，并设T(n0+1)=+∞。选择最小k使得 v(k) = Σ_{j=k}^{n0} C(n0, j) (1-α)^j α^{n0-j} ≤ δ，则阈值 τ̂_α = T(k)。该选择保证Type I错误超过α的概率 ≤ δ。
  - **Type II错误分析**：证明了在温和条件下，所构造的分类器的Type II错误接近最优贝叶斯分类器，给出了上界表达式。
  - **协变量偏移扩展**：当校准数据与目标分布不同但条件分布相同（P(y|q,M(q))不变）时，通过重要性采样（rejection sampling）校正分布，仍然保持Type I错误控制。
  - **与PAC风格共形预测的联系**：证明了本方法等价于PAC共形预测（使用负得分作为符合性得分），但额外提供了Type II错误分析，这是共形预测文献中未涉及的。

## 3. 实验设计
- **数据集与场景**：
  - QA任务：ParaRel（开放生成）、HotpotQA（多跳推理）、WiCE（自然语言推理，多选）、FEVER（事实验证，多选）。
  - 分布偏移场景：ParaRel-OOD（不同领域的问题）用于测试协变量偏移扩展。
- **基准方法**：Base（原始模型）、SelfCheckGPT（基于NLI的零资源检测）、SAPLMA（基于激活分类器）、R-Tuning（拒绝感知微调）、Finetune-All/Finetune-Half（全量/半量微调）。
- **对比方法**：FactTest使用三种得分函数：Vanilla Entropy (VE)、Semantic Entropy (SE)、Kernel Language Entropy (KLE)，每种采样5/10/15次生成，共9个变体。还测试了将FactTest应用于黑盒API（GPT-4o Mini、Claude-3.5、Gemini-1.5等）。
- **评估指标**：精度（模型愿意回答的问题上的正确率）、Type I误差（FPR）、Type II误差（FNR）。

## 4. 资源与算力
- 文中明确提到：“All experiments are implemented on 4 Nvidia H100-80GB GPUs.” 训练参数：学习率2e-5，1个epoch。未提供总训练时长。

## 5. 实验数量与充分性
- **实验组数**：覆盖4个数据集、3种模型大小（3B/7B/13B）、多种得分函数组合（≥9个FactTest变体）、两个显著性水平（α=0.05, 0.10）、与多种基线对比（包括微调方法、黑盒API）。另外还有协变量偏移实验（使用OOD数据集）、消融实验（对比不同得分函数、共形预测变体）、Type I/II误差曲线、Answer Rate分析等。
- **充分性与公平性**：实验设计较为全面，基准方法均按原始设置复现，FactTest与基线在同一测试集上比较，对比时控制数据量（如微调基线使用全量数据，FactTest仅用一半数据进行校准）。且测试了分布外场景、不同规模模型、指令微调模型、黑盒模型，具有良好的客观性。但未提供跨多个随机种子重复实验的报告（可能隐含在概率保证中）。

## 6. 主要结论与发现
- FactTest能够显著提升LLM在拒绝未知问题后的精度（准确率提升超过40%），且Type I误差始终低于设定的显著性水平α（如α=0.05时，经验FPR≤0.05）。
- 在跨域分布偏移场景下，经过重要性采样校正后仍能保持Type I错误控制，且精度优于所有基线。
- 在仅使用一半训练数据用于校准的情况下，FactTest-t的精度仍显著优于使用全部训练数据的R-Tuning等微调方法（例如在HotpotQA上提升34%）。
- 得分函数越能准确反映正确性（如KLE），FactTest的Type II错误越低，精度越高。
- 将FactTest应用于黑盒API（通过开源模型计算得分）也能显著提高可靠性（如GPT-4o Mini精度提升33%）。

## 7. 优点
- **理论贡献**：首次将LLM事实性检测形式化为有统计保证的假设检验问题，同时控制Type I和Type II错误，并建立了与Neyman-Pearson分类和PAC共形预测的联系。
- **模型无关性与数据效率**：无需微调，仅需少量校准样本（任意数量），适用于白盒和黑盒模型。
- **鲁棒性**：扩展至协变量偏移场景，处理真实世界分布漂移。
- **实验验证充分**：在多个数据集、模型、得分函数上验证，覆盖分布内和分布外场景，并与多种基线公平比较，结论可靠。

## 8. 不足与局限
- **得分函数有限**：仅测试了三种基于熵的得分函数，可能不是最优的；作者也指出探索更多得分函数可进一步提升性能。
- **离线校准**：框架是离线模式，未扩展至在线实时测试；提及可作为未来工作。
- **校准依赖少量标注数据**：虽然理论上任意样本数均可，但实践中校准数据量过小可能导致阈值过于保守或无法拒绝（全部拒绝）。
- **协变量偏移处理需假定密度比已知有限**：实际应用中密度比需估计，可能引入误差，文中使用逻辑回归近似，但未对估计误差做理论分析。
- **Type II错误控制依赖于得分函数质量**：得分函数若不能有效区分正确/错误回答，Type II错误可能较高。
- **实验未报告重复次数和方差**：尽管理论保证是概率性的，但缺少多次运行结果，难以评估结果稳定性。

（完）
