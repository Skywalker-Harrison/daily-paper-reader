---
title: A Statistical Framework for Data-dependent Retrieval-Augmented Models
title_zh: 数据依赖检索增强模型的统计框架
authors: "Soumya Basu, Ankit Singh Rawat, Manzil Zaheer"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=A9MiJdetnZ"
tags: ["query:fie-rag"]
score: 7.0
evidence: 为检索增强模型提供统计框架，可应用于事实性推理
tldr: 现代ML系统越来越多地使用检索增强模型，但其理论基础尚不清晰。本文提出了一个统计框架，包含数据依赖的检索器以及预测器，并给出了端到端训练方法。理论证明了该框架的泛化误差界。该工作为将RAG应用于事实性推理等任务提供了理论支撑和训练方法论。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-a9mijdetnz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 782, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1558, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1513, \"height\": 818, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1373, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1519, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1520, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a9mijdetnz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1497, \"height\": 211, \"label\": \"Table\"}]"
motivation: 检索增强模型缺乏统一的统计理解和可训练的理论。
method: 提出含检索器和预测器的双组件框架，使用数据依赖度量并推导端到端泛化界。
result: 在检索增强模型上取得了良好性能，并与多种现有训练方法建立了联系。
conclusion: 该框架为理解和训练检索增强模型提供了理论基石。
---

## Abstract
Modern ML systems increasingly augment input instances with additional relevant information to enhance final prediction. Despite growing interest in such retrieval-augmented models, their fundamental properties and training are not well understood. We propose a statistical framework to study such models with two components: 1) a retriever to identify the relevant information out of a large corpus via a data-dependent metric; and 2) a predictor that consumes the input instances along with the retrieved information to make the final predictions. We present a principled method for end-to-end training of both components and draw connections with various training approaches in the literature. Furthermore, we establish excess risk bounds for retrieval-augmented models while delineating the contributions of both retriever and predictor towards the model performance.We validate the utility of our proposed training methods along with the key takeaways from our statistical analysis on open domain question answering task where retrieval augmentation is important.

---

## 论文详细总结（自动生成）

### 论文中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
现代机器学习系统越来越多地通过检索外部相关信息来增强输入实例，以提升预测性能（即检索增强模型，RAM）。尽管这类模型在实际应用中表现优异（如开放域问答、语言建模），但其基础属性和训练方法仍缺乏系统的理论理解。现有研究多集中于启发式训练技巧（如EMDR²、PDist等），但缺少统一的统计框架来阐明检索器与预测器之间的交互作用、泛化行为以及数据存储大小的影响。本文旨在填补这一空白：提出一个正式的统计框架，理论分析RAM的泛化误差界，并设计原则性的端到端训练目标。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程（用文字说明即可）
- **核心思想**：将RAM形式化为一个由**检索器**（retriever）和**预测器**（predictor）组成的双组件模型。检索器通过一个数据依赖的度量（学习到的评分函数）从大型数据存储中选择与输入最相关的信息；预测器则联合处理输入实例和检索到的信息，输出最终预测。
- **关键技术细节**：
  - 定义检索器 \( r_\theta(x,z) \) 生成关于证据 \( z \) 的分布 \( p_{\theta,I}(z|x) = \frac{\exp(r_\theta(x,z))}{\sum_{z'\in I}\exp(r_\theta(x,z'))} \)。
  - 定义预测器 \( h_\xi(x,E) \) 给出类别概率 \( p_\xi(y|x,E) \)。
  - 提出自然的目标函数：最小化指数族损失（log-loss），即 \( \mathcal{L}_n(\xi,\theta;I) = -\frac{1}{n}\sum_i \sum_z p_{\theta,I}(z|x_i) \cdot \log p_\xi(y_i|x_i,z) \)。
  - 该目标可直接端到端联合优化，并与其他方法（如EMDR²、PDist）建立联系：本文目标为EMDR²的上界，与PDist呈反向KL散度关系。
- **算法流程**：采用梯度下降法近似求解，通过Top-K采样或策略梯度（REINFORCE）来高效估计。
- **理论分析**：
  - 将超额风险分解为**泛化误差**（通过Rademacher复杂度与覆盖数上界）、**检索器近似误差**（通过Sobolev空间与MLP逼近定理）和**预测器近似误差**（利用数据存储质量假设）三部分。
  - 假定预测器损失函数 \( g_\xi(x,z) \) 的“差距函数”满足Sobolev平滑性，数据存储满足逼近质量假设。
  - 得到最终超额风险界 \( \Delta_{\ell,I}(\hat{\xi},\hat{\theta}) \leq \tilde{O}\left(\frac{\ell_{\max}}{\sqrt{n}}(L_{\text{ret}}+L_{\text{pred}}|\mathcal{Y}|)\right) + O(\ell_{\max}L_{\text{ret}}^{-4\kappa/3(d_x+d_z)}\log^{1/3}|I|) + O(L_{\text{pred}}^{-2\kappa_I/(d_x+d_z)} + (|\mathcal{Y}|-1)e^{-\ell_{\max}} + c_I|I|^{-\gamma_I}) \)。
  - 这一界揭示了检索器与预测器容量之间的权衡（Pareto曲面），以及数据存储规模对近似误差的贡献。

#### 3. 实验设计
- **数据集**：两个开放域问答基准数据集——NaturalQuestions (NQ) 和 TriviaQA；数据存储采用2018年分块的Wikipedia。
- **评估指标**：精确匹配准确率（Exact Match）和召回率（答案字符串出现在检索文档中的频率）。
- **对比方法**：
  - 无检索器：直接训练预测器；
  - 固定检索器 + 训练预测器；
  - 固定预测器 + 训练检索器（使用不同目标：EMDR²、PDist、Cross-Entropy + Policy Gradient、Cross-Entropy + TopK）；
  - 联合训练（同样使用上述目标）。
- **模型配置**：检索器采用GTR（small/base/large），预测器采用T5（small/base/large），共9种参数规模组合。模型参数范围从96.4M到1073.7M。

#### 4. 资源与算力
论文未明确说明训练所用的GPU型号、数量或具体训练时长。仅在训练细节中提到使用ADAMW优化器，批大小64，训练步数分别为：无检索器40000步、固定检索器20000步、固定预测器20000步、联合训练40000步，并采用了2000步预热。未提及硬件资源，因此无法量化计算成本。

#### 5. 实验数量与充分性
- **实验数量**：在NQ和TriviaQA上均进行了以下配置的完整实验：4种训练范式（no retriever、fixed retriever、fixed predictor、joint training），每种范式下对比了4种训练目标（EMDR²、PDist、CE+PG、CE+TopK），且每种组合覆盖9种模型规模（3x3）。此外还报告了召回率和查询每秒吞吐量（QPS）。总计至少涉及 \( 2 \times (4 \times 4 \times 9) = 288 \) 个主实验（不计重复），规模充分。
- **消融实验**：主要通过改变检索器和预测器大小来观察性能与计算成本之间的权衡，并给出了QPS表格。分析中指出了不同容量组合可达到相似准确率但计算成本差异巨大。
- **公平性**：所有方法均在同一批初始化条件和优化设置下进行比较，且公开检查点，对比较为公平。但未进行统计显著性检验或多次重复实验的报告。

#### 6. 论文的主要结论与发现
- 加入检索组件显著提升性能；固定预测器后训练检索器进一步提升；联合训练效果最优。
- PDist在召回率上最高，但其他目标（如CE+TopK）在最终准确率上有时更优，说明不同目标优化效率不同。
- 检索器和预测器容量存在权衡：例如，达到相同准确率（NQ≥38.8），可选用“大预测器+小检索器”（QPS 135）、“基础双组件”（333）或“小预测器+大检索器”（800），展示了Pareto前沿。
- 理论泛化界表明，泛化误差与数据存储大小呈对数依赖，而近似误差随数据存储增大而减小，衔接实践。

#### 7. 优点
- **理论贡献**：首次为数据依赖的RAM提供统一的统计学习框架，推导出可控的泛化误差界，明确将超额风险分解为检索器误差、预测器误差和泛化误差，并量化了数据存储的作用。
- **方法论创新**：提出了简单自然的目标函数（对数似然期望），并证明其与现有方法（EMDR²、PDist、RLHF）的内在联系，统一了多种训练范式。
- **实践验证**：在标准QA任务上验证了理论洞察（如容量权衡），并通过吞吐量测量展示了实际部署中的选择空间。
- **分析完备性**：涵盖了近似误差（基于Sobolev空间和MLP逼近定理）和泛化误差（基于Rademacher复杂度与覆盖数）。

#### 8. 不足与局限
- **实验覆盖有限**：仅验证了开放域问答任务，未涉及其他典型RAM应用（如语言建模、图像分类、多步推理）。理论假设可能在某些任务中不满足。
- **假设强度**：分析依赖于若干强假设（如\( g_\xi \)的差距函数在Sobolev空间中、数据存储逼近质量假设），这些假设在实际中难以验证，且未讨论违背假设时的鲁棒性。
- **缺乏动态数据存储**：论文假设数据存储固定，未考虑动态更新的场景，而后者是RAM的重要特色。
- **无多步检索**：仅考虑单次检索单一证据（\( k=1 \)），虽然理论上可推广，但未实际实验。
- **未报告重复运行**：未给出多次实验的标准差，可能影响结论的稳定性评估。
- **算力不可复现**：缺少GPU型号和训练时长细节，不利于复现和成本评估。

（完）
