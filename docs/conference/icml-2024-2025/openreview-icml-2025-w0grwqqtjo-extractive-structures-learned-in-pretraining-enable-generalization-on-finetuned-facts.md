---
title: Extractive Structures Learned in Pretraining Enable Generalization on Finetuned Facts
title_zh: 预训练中学习的提取结构使得对微调事实的泛化成为可能
authors: "Jiahai Feng, Stuart Russell, Jacob Steinhardt"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=W0GrWqqTJo"
tags: ["query:fie-rag"]
score: 6.0
evidence: 语言模型对微调事实的泛化，与事实性推理相关
tldr: 本文引入提取结构框架解释预训练语言模型如何泛化到微调后的事实推理。通过分析模型组件（如MLP和注意力头）的协调作用，揭示了泛化机制，为开发基于语言特征的事实性检测方法提供了理论支持。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 710, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 772, \"height\": 794, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 727, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1750, \"height\": 1083, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 834, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 1205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 1228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1605, \"height\": 1218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1777, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1781, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1780, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1778, \"height\": 1205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1777, \"height\": 1201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1779, \"height\": 1195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1779, \"height\": 1196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1779, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1608, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1607, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1608, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-w0grwqqtjo/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1607, \"height\": 1206, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-w0grwqqtjo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-w0grwqqtjo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 709, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-w0grwqqtjo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 581, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-w0grwqqtjo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1780, \"height\": 857, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-w0grwqqtjo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 369, \"label\": \"Table\"}]"
motivation: 语言模型微调后能泛化到新事实的隐含含义，但其机制尚不明确。
method: 提出提取结构框架，识别存储训练事实的组件和查询处理的上游下游组件。
result: 在多个事实推理任务上验证了提取结构的存在，并解释泛化过程。
conclusion: 预训练期间学习到的提取结构是语言模型事实泛化的关键机制。
---

## Abstract
Pretrained language models (LMs) can generalize to implications of facts that they are finetuned on. For example, if finetuned on "John Doe lives in Tokyo," LMs correctly answer "What language do the people in John Doe's city speak?'' with "Japanese''. However, little is known about the mechanisms that enable this generalization or how they are learned during pretraining.
We introduce extractive structures as a framework for describing how components in LMs (e.g., MLPs or attention heads) coordinate to enable this generalization. The structures consist of informative components that store training facts as weight changes, and upstream and downstream extractive components that query and process the stored information to produce the correct implication. We hypothesize that extractive structures are learned during pretraining when encountering implications of previously known facts. This yields two predictions: a data ordering effect where extractive structures can be learned only if facts precede their implications, and a weight grafting effect where extractive structures can be grafted to predict counterfactual implications.
We empirically show these effects in the OLMo-7b, Llama 3-8b, Gemma 2-9b, and Qwen 2-7b models.
Of independent interest, our results also indicate that fact learning can occur at both early and late layers, which lead to different forms of generalization.

---

## 论文详细总结（自动生成）

### 论文总结：Extractive Structures Learned in Pretraining Enable Generalization on Finetuned Facts

#### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：预训练语言模型（LM）在微调新事实后，能够自动泛化到该事实的隐含含义（例如，微调“John Doe 住在东京”后，模型能回答“John Doe 所在城市的人说什么语言？”→“日语”）。这种泛化被称为“out-of-context reasoning”（OCR）或“ripple effects”。然而，其背后的计算机制以及该机制在预训练中如何获得，尚不明确。
- **意义**：理解OCR机制有助于解释LM的能力与失败模式，指导安全、鲁棒的模型设计，并为知识编辑等应用提供理论基础。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：提出“extractive structures”框架，将OCR分解为三种组件在推理时的协调。
  - **Informative components**：在微调时以权重变化存储事实（例如“John Doe”→“Tokyo”）。
  - **Upstream extractive components**：解析输入提示，生成适当的中间激活以查询informative component。
  - **Downstream extractive components**：处理informative component的输出，产生正确的隐含结论（例如“Tokyo”→“Japanese”）。
- **关键技术细节**：
  - **因果指标**：基于计算图定义三类得分，通过干预权重或激活来测量组件重要性。
    - Informative score：\(I_C = R[W_C \leftarrow W'_C] - R\)
    - Downstream score：\(D_C = R[y_C \leftarrow f_C(z'_C, W_C)] - R\)
    - Upstream score：\(U_C = (R[W_{late} \leftarrow W'_{late}] - R[W_{late} \leftarrow W'_{late}, y_C \leftarrow y^*_C]) - (R - R[y_C \leftarrow y^*_C])\)
  - **线性化近似**：为高效计算，将上述指标线性化（利用梯度），只需几次前向/反向传播即可近似。
  - **机制学习假设**：OCR能力源于预训练中模型在遭遇已知事实的隐含含义时，学习如何从权重中提取事实并产生正确隐含。这导致两个可检验预测：**数据顺序效应**（事实必须出现在隐含之前）和**权重嫁接效应**（提取结构可转移到反事实事实）。

#### 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **FIRST-HOP**：虚构名→城市（新事实），城市→语言（已知）。隐含需要组合第一跳新事实与第二跳已知事实。
  - **SECOND-HOP**：城市→虚构名（新事实），地标→城市（已知）。隐含需要组合第一跳已知事实与第二跳新事实。
  - **虚构隐含数据集（Sec 6）**：用随机动物代替语言，构造虚构关系“dax”（事实）和“wug”（隐含），用于研究提取结构的起源。
- **基准**：主要基于OLMo-7b，并在Llama 3-8b、Gemma 2-9b、Qwen 2-7b上验证。
- **对比方法**：
  - **层冻结实验**：比较冻结早期层（前24层）与后期层（后8层）对两种数据集泛化的影响。
  - **数据顺序实验**：比较“事实优先”“隐含优先”“混合”三种顺序下的OCR能力。
  - **权重嫁接实验**：将训练隐含的权重变化嫁接到反事实事实模型上，与直接训练隐含的权重变化对比。

#### 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量或训练总时长。仅提到使用Adam优化器、学习率3×10⁻⁶、batch size 8、训练8个epoch。硬件资源未披露。

#### 5. 实验数量与充分性
- **实验数量**：
  - 在OLMo-7b上对FIRST-HOP和SECOND-HOP进行了完整提取结构定位（图5）。
  - 层冻结实验（表2、表4）涵盖两种数据集和多种冻结策略。
  - 数据顺序实验（图6）包含三种顺序，在OLMo-7b及另外三个模型上重复（附录I）。
  - 权重嫁接实验（表3）在多个模型和多种学习率/epoch配置下进行了系统扫描（附录I）。
  - 学习率敏感性分析（附录H）覆盖了5种学习率和4种epoch数量。
- **充分性**：实验设计较全面，包括因果定位、消融、跨模型验证、超参数扫描。但仅在合成数据集上验证，未在真实世界知识或更复杂推理任务上测试。总体充分，但泛化性有待扩展。

#### 6. 主要结论与发现
- **提取结构存在**：在OLMo-7b中成功定位到informative、upstream、downstream组件，且与潜在两跳推理机制一致（早期中间层MLP负责第一跳，后期层MLP和注意力头负责第二跳）。
- **不同层不同泛化**：早期层存储的事实用于第一跳泛化，后期层存储的事实用于第二跳泛化。冻结早期层仅损害FIRST-HOP，冻结后期层仅损害SECOND-HOP。
- **数据顺序效应**：在继续预训练中，“事实优先”或“混合”顺序使模型具备OCR能力，而“隐含优先”则显著削弱，支持提取结构学习的假设。
- **权重嫁接效应**：将“事实+隐含”训练的权重变化嫁接到反事实事实模型上，模型能正确预测反事实隐含，说明提取结构可迁移。
- **额外发现**：存在除提取结构之外的次要OCR机制（隐含优先顺序下仍有少量泛化）。

#### 7. 优点
- **框架新颖**：提出“extractive structures”统一解释OCR的编码和解码过程，提供可操作性因果指标。
- **线性化方法高效**：通过梯度近似大大降低因果干预的计算成本，适用于大规模模型。
- **多模型验证**：在OLMo-7b、Llama 3-8b、Gemma 2-9b、Qwen 2-7b上均观察到主要效应，增强结论稳健性。
- **揭示事实存储冗余性与分层泛化差异**：对知识编辑等领域有直接启示——编辑时应修改多层以实现不同泛化。
- **动态视角**：指出优化不仅是模型选择，更与数据顺序相关，挑战传统统计学习观点。

#### 8. 不足与局限
- **任务局限**：仅研究两跳推理这一种OCR形式，未验证其他类型隐含（如对称关系、多跳、反事实等）。
- **合成数据集**：所有实验基于人工构造的虚构事实，可能无法完全反映真实知识泛化的机制。
- **学习率敏感**：OCR成功与否强烈依赖学习率，且在不同模型中表现不稳定，替代机制的存在削弱了纯粹依赖提取结构的解释力。
- **权重嫁接效果有限**：嫁接后也能部分保留原隐含，表明模型同时记住了隐含对，提取结构与记忆共存。
- **资源信息缺失**：未报告具体算力消耗，不利于复现和成本评估。
- **未探索大规模模型**：实验限于7B-9B参数规模，更大型模型（如70B）的行为可能不同。

（完）
