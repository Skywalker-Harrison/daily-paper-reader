---
title: Re-ranking Reasoning Context with Tree Search Makes Large Vision-Language Models Stronger
title_zh: 基于树搜索的推理上下文重排序使大型视觉语言模型更强
authors: "Qi Yang, Chenghao Zhang, Lubin Fan, Kun Ding, Jieping Ye, Shiming Xiang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DJcEoC9JpQ"
tags: ["query:fie-rag"]
score: 6.0
evidence: 多模态RAG框架结合树搜索重排序，可迁移至事实性推理
tldr: 多模态RAG在视觉问答中面临推理样例稀缺和检索知识响应不稳定等问题。RCTS通过构建富含推理模式的知识库，并采用蒙特卡洛树搜索对检索上下文进行重排序。实验表明该方法显著提升了LVLMs在复杂推理任务上的表现。其树搜索重排序策略可推广至语言领域的RAG事实推理。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 827, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1617, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1567, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1568, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1577, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1803, \"height\": 74, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 72, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 1487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1737, \"height\": 2017, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1748, \"height\": 1851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1746, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1703, \"height\": 2195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1738, \"height\": 2176, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 887, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1703, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 203, \"label\": \"Table\"}]"
motivation: 多模态RAG存在推理样例不足和检索知识响应不稳定。
method: 构建推理上下文增强知识库，并用蒙特卡洛树搜索进行重排序。
result: 在视觉问答基准上，RCTS显著优于现有RAG方法。
conclusion: 树搜索重排序是提升RAG系统检索质量的有效策略。
---

## Abstract
Recent advancements in Large Vision Language Models (LVLMs) have significantly improved performance in Visual Question Answering (VQA) tasks through multimodal Retrieval-Augmented Generation (RAG). However, existing methods still face challenges, such as the scarcity of knowledge with reasoning examples and erratic responses from retrieved knowledge. To address these issues, in this study, we propose a multimodal RAG framework, termed RCTS, which enhances LVLMs by constructing a Reasoning Context-enriched knowledge base and a Tree Search re-ranking method. Specifically, we introduce a self-consistent evaluation mechanism to enrich the knowledge base with intrinsic reasoning patterns.  We further propose a Monte Carlo Tree Search with Heuristic Rewards (MCTS-HR) to prioritize the most relevant examples.  This ensures that LVLMs can leverage high-quality contextual reasoning for better and more consistent responses. Extensive experiments demonstrate that our framework achieves state-of-the-art performance on multiple VQA datasets, significantly outperforming In-Context Learning (ICL) and Vanilla-RAG methods. It highlights the effectiveness of our knowledge base and re-ranking method in improving LVLMs.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）
- 大型视觉语言模型（LVLMs）在视觉问答（VQA）中表现出色，但存在幻觉问题，包括事实不一致和指令不匹配。  
- 现有的多模态检索增强生成（RAG）方法主要解决事实一致性，而指令不匹配（如无法按用户意图正确推理）尚未被充分关注。  
- 论文指出两个主要挑战：① 知识库中缺乏包含推理过程的示例，导致检索到的样例难以提供深层逻辑；② 检索到的示例质量不稳定，可能反而降低响应质量。  
- 目标：通过构建富含推理上下文的知识库，并利用树搜索重排序，提升LVLMs在指令对齐与推理上的能力，使其从“仅知道答案”进阶为“理解推理模式”。

## 2. 方法论
### 核心思想
提出 **RCTS**（Reasoning Context and Tree Search）框架，基于训练不限的多模态RAG，包含三个关键组件：  
1. **推理上下文生成**：利用自一致性评估自动为知识库中每个问答对生成推理思路。  
2. **混合嵌入检索**：融合文本和图像特征的嵌入，计算用户查询与知识库样本的相似度，取得前N个候选。  
3. **蒙特卡洛树搜索与启发式奖励（MCTS-HR）**：将候选样本作为动作空间，通过树搜索重排序，选出最优的K个示例作为上下文。

### 关键技术细节
- **推理上下文生成（Sec 3.2）**：  
  - 对知识库中的每个问答对 (Q_kb, A_kb)，LVLM生成N_c个候选推理上下文 {C_i}。  
  - 然后将每个C_i与Q_kb拼接，让LVLM预测答案，并与地面真值A_kb比对，得到得分Score_i。  
  - 选择得分最高的C_i作为该问答对的推理上下文。  
- **混合嵌入检索（Sec 3.3）**：  
  - 文本编码器F_L提取问题嵌入E_T，图像编码器F_I提取图像嵌入E_I，拼接得到混合嵌入E = [E_T, E_I]。  
  - 对知识库同样处理，计算用户查询嵌入与每个库嵌入的逐对最大相似度得分，取Top-N。  
- **MCTS-HR（Sec 3.4）**：  
  - **动作空间**：Top-N个候选样本，每个带相似度得分s_i。  
  - **节点选择**：根据UCT值（Upper Confidence Bound for Trees，公式11）选择未完全扩展的节点。  
  - **动作采样**：基于相似度概率分布 P(a_i)=s_i/∑s_j 从剩余动作空间采样。  
  - **展开与模拟**：达到最大深度K（即K-shot）时，拼接该分支所有动作与用户查询，由LVLM生成回答。  
  - **奖励函数**：包含自一致性启发式奖励（公式7）和互启发式奖励（公式8），加权得到最终奖励（公式9）。  
    - 自奖励：用生成的推理上下文C_i多次预测，比较一致性。  
    - 互奖励：用当前分支的回答作为上下文，去回答知识库中其他样本的问题，比较预测与真实答案。  
  - **反向传播**：更新父节点价值Q（公式10）。  
  - **终止条件**：达到最大rollout数或早期停止（根节点与叶节点答案一致）。

## 3. 实验设计
- **数据集**：  
  - 推理类：ScienceQA（科教多选）、MMMU（大学学科多选）、MathV（数学推理多选/计算）。  
  - 非推理类：VizWiz（视觉问题真/假或短语回答）、VSR-MC（空间关系多选，由原VSR改造而来）。  
  - 知识库构建：使用各数据集的训练/验证集，评估集为对应的测试/开发集，无样本重叠（见表1）。
- **基准方法**：  
  - Zero-Shot（无示例）  
  - ICL（随机选择K个示例）  
  - Vanilla-RAG（直接取Top-K检索结果，不使用推理上下文）  
  - RCTS（本文方法）
- **主模型**：Qwen2-VL (2B/7B)、InternVL-2 (8B)。超过7B的模型使用4位AWQ量化，在单卡4090（24GB）上运行。
- **实验组数**：  
  - 表2：三个推理数据集在三种LVLM上的主结果。  
  - 表3：两个非推理数据集在Qwen2-VL (7B)上的结果。  
  - 表4：消融研究（单独去掉推理上下文或MCTS-HR）。  
  - 表5：α权重敏感性分析。  
  - 图5(a/b)：奖励策略与rollout数量影响。  
  - 表6：推理上下文生成质量验证。  
  - 图6及附录D：定性分析/重排序过程示例。
- **公平性**：所有实验采用相同的LVLM和量化设置，对比方法均在同一环境下评估，消融实验完整，参数（α、rollout数等）有独立分析。

## 4. 资源与算力
- 论文明确指出：超过7B参数的LVLM（如Qwen2-VL 7B、InternVL-2 8B）在单张NVIDIA 4090（24GB）GPU上通过AWQ 4-bit量化实现。  
- 未明确说明训练的总时长或GPU数量，因为RCTS是training-free框架，无需额外训练；计算主要来自LVLM的推理和MCTS的多次rollout。  
- 每批实验的rollout数默认为10，树宽最大3，深度K=3；这些参数在消融中进行了调整分析，但整体计算开销显著高于Vanilla-RAG。

## 5. 实验数量与充分性
- 覆盖了5个VQA数据集、3种不同规模/类型的LVLM，结果展示全面。  
- 消融实验包括：推理上下文、MCTS-HR、奖励形式、α权重、rollout数量等，几乎每个关键组件都做了控制变量分析。  
- 定性分析提供了具体案例（附录D），展示了重排序前后的差异及成功/失败场景。  
- 但实验仅评估了有限的LVLM（均为Qwen和InternVL系列），未在开源社区其他流行模型（如LLaVA、CogVLM）上验证；且非推理数据集仅使用了一个模型。  
- 总体而言，实验设计较为充分且公平，比较对象涵盖了常见的零样本、随机ICL和基线RAG方法。

## 6. 主要结论与发现
- RCTS在所有数据集和LVLM上显著优于Zero-Shot、ICL和Vanilla-RAG。  
  - 在ScienceQA上，Qwen2-VL (2B)从零样本67.18%提升至78.99%，相较Vanilla-RAG提升7.05%。  
  - 在MathV上，Qwen2-VL (7B)从24.67%提升至28.95%，取得新SOTA。  
  - 在非推理数据集VizWiz和VSR-MC上，也分别获得+1.61%和+3.05%的提升。  
- 推理上下文和MCTS-HR两者互补，单独使用均有提升，组合后效果最佳。  
- 自一致性奖励与互奖励的混合（hybrid）比单独使用任一奖励更好，α=0.2为最优设置。  
- 生成推理上下文的可靠性高（在ScienceQA上达到100%，在复杂MMMU上接近100%）。  
- 当知识库中存在高度相似的样例时，RCTS能稳定选出正确示例；但在缺少相关样本时（如MMMU部分领域），提升有限且可能失败。

## 7. 优点
- **自动化推理上下文构建**：无需人工标注，利用LVLM自身的自一致性机制自动生成且验证，大幅提升知识库质量。  
- **训练免（training-free）**：不更新模型参数，只通过检索和重排序增强，可即插即用于任意多模态LVLM。  
- **树搜索重排序（MCTS-HR）**：将上下文选择建模为序列决策问题，通过探索-利用平衡找到最优示例顺序，优于固定Top-K检索。  
- **混合模态检索**：同时利用文本和图像特征，更全面衡量相似性。  
- **启发式奖励设计**：自一致性与互一致性双重约束，使得奖励更能反映示例对回答的正面贡献。  
- **实验充分且结果显著**：在多个推理和非推理数据集上获得一致提升，消融实验验证各个组件有效性。

## 8. 不足与局限
- **依赖知识库质量**：若知识库中缺乏与用户查询相似的样例，即使重排序也无法弥补（如图16所示失败案例），导致提升有限。  
- **计算开销大**：MCTS-HR需要多次LVLM推理（rollout数10次，每个rollout还会调用多次回答生成），相比Vanilla-RAG显著增加推理时间，论文未讨论效率/延迟。  
- **可拓展性受限**：仅评估了Qwen2-VL和InternVL-2，未在更多LIama-Adapter、LLaVA-NeXT等流行模型上验证。  
- **基准选择单一**：非推理类数据集仅用了一个模型（Qwen2-VL 7B），未报告跨模型一致性。  
- **参数敏感性**：奖励权重α、rollout数、树宽等需手动调节，默认值可能不通用。  
- **应用范围**：主要针对多选/简短回答的VQA，对于开放式生成或长文本回答任务未探索。

（完）
