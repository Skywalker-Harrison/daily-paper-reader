---
title: "Retrieval is Not Enough: Enhancing RAG through Test-Time Critique and Optimization"
title_zh: 检索还不够：通过测试时批评与优化增强RAG
authors: "Jiaqi Wei, Hao Zhou, Xiang Zhang, Di Zhang, Zijie Qiu, Noah Wei, Jinzhe Li, Wanli Ouyang, Siqi Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cnUq7GkS6d"
tags: ["query:fie-rag"]
score: 7.0
evidence: RAG框架通过批评机制解决事实一致性
tldr: 标准RAG常无法确保模型推理与检索证据一致，导致事实错误。AlignRAG重新将RAG定义为检索增强推理，提出基于批评驱动的对齐框架，通过迭代优化使推理轨迹与证据约束对齐。实验表明该方法显著减少事实不一致，直接服务于需要强事实依据的句子叙实性推理任务，为语言学特征与RAG结合提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 1006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 498, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 723, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 535, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 545, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cnuq7gks6d/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1348, \"height\": 1018, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 909, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 738, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 661, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cnuq7gks6d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 385, \"label\": \"Table\"}]"
motivation: RAG中模型推理与检索证据脱节导致事实不一致，需要对齐。
method: 提出批评驱动对齐（CDA）的迭代框架，检验并修正推理与证据之间的偏差。
result: AlignRAG在多个事实性基准上减少推理不一致，提升生成可靠性。
conclusion: 对齐机制是提升RAG事实一致性的关键，适用于事实性检测任务。
---

## Abstract
Retrieval-augmented generation (RAG) has become a widely adopted paradigm for enabling knowledge-grounded large language models (LLMs). However, standard RAG pipelines often fail to ensure that model reasoning remains consistent with the evidence retrieved, leading to factual inconsistencies or unsupported conclusions. In this work, we reinterpret RAG as \textit{Retrieval-Augmented Reasoning} and identify a central but underexplored problem: \textit{Reasoning Misalignment}—the divergence between an LLM's internal reasoning trajectory and the evidential constraints provided by retrieval. To address this issue, we propose \textsc{AlignRAG}, a novel iterative framework grounded in \textit{Critique-Driven Alignment (CDA)}. We further introduce \textsc{AlignRAG-auto}, an autonomous variant that dynamically terminates refinement, removing the need to pre-specify the number of critique iterations. At the heart of \textsc{AlignRAG} lies a \textit{contrastive critique synthesis} mechanism that generates retrieval-sensitive critiques while mitigating self-bias. This mechanism trains a dedicated retrieval-augmented \textit{Critic Language Model (CLM)} using labeled critiques that distinguish between evidence-aligned and misaligned reasoning. Empirical evaluations show that our approach significantly improves reasoning fidelity. Our 8B-parameter CLM improves performance over the Self-Refine baseline by \textbf{12.1\%} on out-of-domain tasks and outperforms a standard 72B-parameter CLM by \textbf{2.2\%}. Furthermore, \textsc{AlignRAG-auto} achieves this state-of-the-art performance while dynamically determining the optimal number of refinement steps, enhancing efficiency and usability. \textsc{AlignRAG} remains compatible with existing RAG architectures as a \textit{plug-and-play} module and demonstrates strong robustness under both informative and noisy retrieval scenarios. Overall, \textsc{AlignRAG} offers a principled solution for aligning model reasoning with retrieved evidence, substantially improving the factual reliability and robustness of RAG systems. Our source code is provided at \href{https://github.com/upup-wei/RAG-ReasonAlignment}{link}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：标准检索增强生成（RAG）管道尽管能检索到相关文档，但模型生成的推理过程往往与检索到的证据不一致，导致事实错误或未支持的结论。作者将这一问题定义为 **“推理错位”（Reasoning Misalignment）**——即LLM的内部推理轨迹与检索提供的证据约束之间的偏离。
- **研究动机**：现有方法多关注改善检索质量或生成鲁棒性，但缺乏对推理步骤与证据显式对齐的机制；自反思方法（如Self-RAG）存在自偏置且需要架构修改。作者重新将RAG理解为“检索增强推理”（Retrieval-Augmented Reasoning），认为RAG应包含结构化推理阶段，而错位会在这三个阶段发生：相关性评估、查询-证据映射、证据整合合成。
- **整体含义**：提出**AlignRAG**框架，通过测试时批评驱动对齐（Critique-Driven Alignment, CDA）动态纠正推理错位，提高RAG系统的事实可靠性和鲁棒性。

## 2. 论文提出的方法论
### 核心思想
- 将RAG推理视为一个可迭代优化的过程，通过一个专门的批评语言模型（Critic Language Model, CLM）在测试时生成基于检索证据的批评，指导生成器逐步对齐证据。
- 提出**对比批评合成（Contrastive Critique Synthesis, CCS）**机制，通过对比“弱模型”（易错）和“强模型”（正确）的推理轨迹，训练CLM生成证据敏感且无自偏置的批评。

### 关键技术细节
- **训练数据构建**：构建结构化数据集 $S = \{(q_i, a_i, D_i, c_i)\}$，其中质量向量 $c_i = (r_i, h_i, m_i)$ 从相关性、帮助性、完整性三个正交维度标注检索上下文质量。设计多层次上下文粒度层级，模拟不同答案性条件。
- **对比批评合成**：对于每个查询，用弱模型生成错位响应 $y_{\text{unexp}}$，用强模型生成对齐响应 $y_{\text{exp}}$。构建偏好增强输入 $X_{\text{pref}} = (q, D, y_{\text{exp}}, y_{\text{unexp}})$，训练CLM学习条件分布 $P_{\text{critic}}(\text{critique}|X_{\text{pref}})$，生成批评 $\Delta y_{\text{unexp}}$。
- **Critic LLM训练**：采用**批评微调（CFT）**，将批评生成视为条件序列生成任务，最大化 $\log p_\theta(\Delta y_{\text{unexp}} | I_{\text{critic}})$，其中 $I_{\text{critic}} = (q, D, y_{\text{unexp}}, y_{\text{exp}})$。同时介绍替代方法**批评偏好优化（CPO）**，基于DPO框架进行偏好对齐。
- **测试时对齐（CDA）**：初始响应 $y_0 = M_{\text{gen}}(q, D)$，迭代执行：$y_{t+1} = M_{\text{gen}}(y_t \oplus \Delta y_t)$，其中 $\Delta y_t$ 由CLM生成。最终输出 $y_T$。
- **自动变体AlignRAG-auto**：训练CLM同时输出控制标记 `[Good]` / `[Bad]`，若判为 `[Good]` 则终止迭代，无需预设迭代次数。

### 公式/算法流程（文字说明）
- 训练阶段：通过弱模型和强模型生成对比推理路径 → 使用结构化模板合成批评 → 以CFT或CPO训练CLM。
- 推理阶段：初始生成 → CLM评估并产生批评 → 生成器结合批评进行细化 → 若AlignRAG-auto且判为 `[Good]` 则停止。

## 3. 实验设计
### 数据集与场景
- **训练集**：从 PopQA、TriviaQA、NaturalQuestions、2WikiMultiHopQA、ASQA 各采样2000条，共10K训练数据。
- **评估集**：五个**域内**基准（同上训练集对应测试集）+ 两个**域外（OOD）** 基准：HotpotQA、SQuAD。涵盖事实问答、多跳推理、长文本生成。
- **检索条件**：默认Top-K=5；还设置**噪声检索**（文档不含答案）和**信息检索**（文档含答案）场景。

### 基准方法
- 非检索基准：Chain-of-Thought (CoT)
- 标准RAG：Vanilla Reasoning
- 训练时优化：RetRobust、InstructRAG
- 测试时优化：Self-RAG、Self-Refine
- 自身变体：AlignRAG-fixed、AlignRAG-auto

### 评估指标
- 大部分任务用准确率（Accuracy），ASQA用严格EM（str-em）。
- 三个骨干模型：Qwen2.5-7B-Instruct、Qwen2.5-14B-Instruct、LLaMA3.1-8B-Instruct。

## 4. 资源与算力
论文附录A.2明确说明：
- GPU：2张 NVIDIA A100（80GB）
- 训练：LoRA微调，2 epochs，学习率1e-5，AdamW优化器，每设备batch size=16，梯度累积，bf16精度。
- 具体训练时长未提及，但基于2张A100，LoRA微调10K数据量应较为高效。

## 5. 实验数量与充分性
- **实验数量**：主实验在5个域内基准+2个域外基准上，对比多种方法，包括三个骨干模型。此外包含：
  - 迭代次数影响分析（1-5轮，7个基准）
  - 检索质量鲁棒性分析（噪声/信息场景）
  - 集成到InstructRAG的plug-and-play实验
  - CLM不同训练策略的消融（Frozen CLM、Trained CLM、Trained CLM+CCS）
  - 对比不同CLM监督策略（Vanilla Critique Synthesis、Direct 72B CLM、Ours）
  - 自动变体对比
- **充分性**：实验覆盖了多种骨干、多领域、不同检索质量、OOD泛化、迭代机制、消融，设计较为全面。
- **客观/公平**：与强基线Self-Refine、Self-RAG、InstructRAG等公平对比，使用一致评估设置。但报告结果无误差线（单次运行），可能缺乏统计显著性。

## 6. 论文的主要结论与发现
- AlignRAG在所有骨干和域内/域外基准上取得了SOTA性能，显著超越Self-Refine、Self-RAG等测试时优化方法。
- 8B参数的CLM在OOD任务上比Self-Refine提升12.1%，甚至优于72B的普通CLM 2.2%，验证了对比批评训练的泛化能力。
- AlignRAG在噪声检索（无答案文档）下表现出最强鲁棒性，有效过滤干扰并激活参数知识。
- 自动变体AlignRAG-auto在减少计算量的同时不牺牲准确性，自动确定最优迭代次数。
- 作为即插即用模块，可集成至现有RAG管道（如InstructRAG），在OOD上提升高达9.4%（Qwen2.5-14B）。

## 7. 优点
- **方法创新**：首次系统定义并解决“推理错位”问题，提出对比批评合成机制有效缓解自偏置。
- **技术亮点**：训练专属CLM进行证据敏感批评，而非依赖生成器自我批评；AlignRAG-auto动态停止策略提升效率。
- **实验全面**：覆盖多种骨干、多类型任务、OOD、噪声/信息检索、集成不同管道，消融实验充分。
- **实用性**：即插即用，无需修改现有RAG架构；代码开源。
- **鲁棒性**：在检索质量差时仍能保持较高性能，证明“当检索失败时，AlignRAG依然有效”。

## 8. 不足与局限
- **单次运行**：主要实验未报告误差棒或统计显著性检验（附录提及仅运行一次），结果稳定性尚需验证。
- **极端检索失败**：当检索完全不相关时，CLM的批评质量下降，可能基于参数记忆“过校正”导致新错误，论文案例也证实了此问题。
- **微调开销**：需额外训练CLM模型，虽然训练成本相对低，但仍需标注数据（训练集10K条）。
- **应用限制**：尽管即插即用，但最佳集成可能需针对不同生成器微调，标准化程度有限。
- **领域覆盖**：OOD基准仅两个（HotpotQA、SQuAD），更广泛的领域泛化能力有待验证。
- **潜在偏置**：训练数据源于五个特定基准，CLM可能继承数据中语言或文化偏置，论文未深入讨论。

（完）
