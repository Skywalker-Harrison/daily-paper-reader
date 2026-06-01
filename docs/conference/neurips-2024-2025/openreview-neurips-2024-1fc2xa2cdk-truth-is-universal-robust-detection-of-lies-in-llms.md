---
title: "Truth is Universal: Robust Detection of Lies in LLMs"
title_zh: 真理是通用的：鲁棒检测LLM中的谎言
authors: "Lennart Bürger, Fred A. Hamprecht, Boaz Nadler"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=1Fc2Xa2cDK"
tags: ["query:fie-rag"]
score: 6.0
evidence: 通过激活子空间检测LLM谎言
tldr: 大语言模型能撒谎，现有检测方法泛化性差。发现存在一个通用二维子空间，真话与谎言的激活向量沿该子空间可分离，提出基于该子空间的鲁棒谎言检测方法。在多数据集上表现良好，与事实性检测直接相关，但未使用RAG或少样本。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1143, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 578, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 513, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1075, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 988, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1007, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 734, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 574, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1014, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1176, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1449, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 664, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 657, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1446, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1006, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1175, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1448, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 666, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 573, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1445, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1007, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1175, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1448, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 667, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 655, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1445, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1007, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1175, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1447, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 666, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 572, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1445, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1011, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1175, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1448, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-1fc2xa2cdk/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 666, \"height\": 473, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-1fc2xa2cdk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1491, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-1fc2xa2cdk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1296, \"height\": 293, \"label\": \"Table\"}]"
motivation: LLM会输出虚假陈述，需要鲁棒的检测方法。
method: 发现并利用真/假语句激活向量的二维子空间进行检测。
result: 在多个数据集上实现了高泛化性检测。
conclusion: 存在通用谎言检测子空间，可用于LLM输出真实性判断。
---

## Abstract
Large Language Models (LLMs) have revolutionised natural language processing, exhibiting impressive human-like capabilities. In particular, LLMs are  capable of "lying", knowingly outputting false statements. Hence, it is of interest and importance to develop methods to detect when LLMs lie. Indeed, several authors trained classifiers to detect LLM lies based on their internal model activations. However, other researchers showed that these classifiers may fail to generalise, for example to negated statements. 
In this work, we aim to develop a robust method to detect when an LLM is lying. To this end, we make the following key contributions: (i) We demonstrate the existence of a two-dimensional subspace, along which the activation vectors of true and false statements can be separated. Notably, this finding is universal and holds for various LLMs, including Gemma-7B, LLaMA2-13B, Mistral-7B and LLaMA3-8B. Our analysis explains the generalisation failures observed in previous studies and sets the stage for more robust lie detection;
(ii) Building upon (i), we construct an accurate LLM lie detector. Empirically, our proposed classifier achieves state-of-the-art performance, attaining 94\% accuracy in both distinguishing true from false factual statements and detecting lies generated in real-world scenarios.

---

## 论文详细总结（自动生成）

# 论文《Truth is Universal: Robust Detection of Lies in LLMs》中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

大语言模型（LLM）不仅能生成看似合理的文本，还能“撒谎”——即在知情的情况下输出虚假陈述。已有研究表明，LLM可能因指令或利益驱动而进行战略性欺骗，甚至在被训练为诚实的情况下也会撒谎。因此，如何稳健地检测LLM是否在撒谎是一个重要而尚未完全解决的问题。

现有方法主要分为两类：
- **基于输出的黑盒方法**（如Pacchiardi et al. 2023）。
- **基于内部激活的探针方法**：通过训练分类器在LLM内部激活向量上区分真伪陈述。例如Azaria & Mitchell (2023)的MLP，以及Burns et al. (2023)、Zou et al. (2023)、Li et al. (2024)的线性分类器，后者的工作暗示存在一个“真理方向”（truth direction）。

然而，Levinstein & Herrmann (2024)发现这些分类器在从肯定句泛化到否定句时失败。Marks & Tegmark (2023)虽证明LLM内部确实存在线性的真值表示，但未能解释失败的根本原因——是否存在一个单一的通用真理方向，还是存在多个窄域方向。

**本文核心问题**：是否存在一个**通用且鲁棒**的谎言检测方向，能够跨不同陈述类型、跨主题、跨语言甚至跨真实世界谎言场景泛化？答案是肯定的。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 发现LLM内部存在一个**二维子空间**，真伪陈述的激活向量在该子空间中可被线性分离。
- 该子空间由两个正交方向张成：
  - **通用真理方向 \( t_G \)**：对所有陈述（肯定/否定）均从假指向真。
  - **极性敏感真理方向 \( t_P \)**：对肯定句从假到真，对否定句从真到假（即方向反转）。
- 之前仅用肯定句训练得到的“肯定真理方向” \( t_A \) 是 \( t_G \) 和 \( t_P \) 的线性组合，因此无法泛化到否定句。

### 技术细节
**激活提取**：
- 向LLM依次输入每个陈述，从残差流（residual stream）的某一层（对LLaMA3-8B为第12层）的最后一个token提取激活向量 \( a_{ij} \in \mathbb{R}^d \)。
- 选择该层的依据：该层上真假陈述的类间方差/类内方差比最大。

**监督学习两个方向**：
- 设每个陈述 \( s_{ij} \) 的真值标签 \( \tau_{ij} \in \{-1,1\} \)，极性 \( p_i \in \{-1,1\} \)（肯定句+1，否定句-1）。
- 假设激活向量可近似为：  
  \[
  \hat{a}_{ij} = \mu_i + \tau_{ij} t_G + \tau_{ij} p_i t_P
  \]
  其中 \( \mu_i \) 是该主题下所有陈述的平均激活向量。
- 通过最小化均方误差 \(\sum \|a_{ij} - \hat{a}_{ij}\|^2\) 得到 \( t_G \) 和 \( t_P \) 的闭式解（普通最小二乘法）。

**TTPD（Training of Truth and Polarity Direction）算法流程**：
1. 从训练数据中学习通用真理方向 \( t_G \)（如上）。
2. 通过逻辑回归学习极性方向 \( p \)，该方向从否定句指向肯定句。
3. 将训练激活向量投影到 \( t_G \) 和 \( p \) 这两个一维方向，得到二维表示。
4. 在二维投影上训练一个逻辑回归分类器。
- 对新语句分类时，将其激活向量投影到同样的二维空间，应用上述分类器。

**与基线方法的对比**：
- **LR**：直接在原始激活上训练逻辑回归（带偏置）。
- **CCS**（Burns et al.）：在对比对（肯定-否定）上寻找满足一致性约束的方向。
- **MM**（Marks & Tegmark）：真均值和假均值的差作为方向，再学习偏置。

## 3. 实验设计：数据集、场景、基准方法与对比方法

### 数据集
**主题特定数据集**（主要用于训练和评估泛化性）：
- 6个肯定句数据集：`cities`, `sp_en_trans`, `element_symb`, `animal_class`, `inventors`, `facts`（来自Azaria & Mitchell和Marks & Tegmark）。
- 每个数据集通过插入“not”得到对应的否定句版本（前缀`neg_`）。
- 此外，构造逻辑合取（`_conj`）、逻辑析取（`_disj`）和德语翻译（`_de`）版本，共36个主题特定数据集。

**多样测试集**：
- `common_claim_true_false`（Casper et al. 2023，经Marks & Tegmark平衡后4450条）
- `counterfact_true_false`（Meng et al. 2022，经修改后31964条）

**真实世界谎言场景**：
- 基于Pacchiardi et al. (2023)的26个角色扮演场景（每个场景有“有撒谎激励”和“无撒谎激励”两个版本），LLaMA3-8B-Instruct生成回答，共208个响应，手动分为“明确真实”、“明确谎言”、“模糊真实”、“模糊谎言”和“其他”五类。

### 对比方法
- **LR**（逻辑回归）
- **CCS**（对比一致搜索）
- **MM**（质心差探针）
- **TTPD**（本文提出）

### 实验设置
- 训练数据：从所有主题特定数据集的肯定和否定句中，每个主题取等量样本，保证主题平衡。
- 评估指标：准确率（Accuracy）和/或AUROC。
- 使用留一主题法（leave-one-topic-out）来测试对未见主题的泛化。
- 对每种方法报告多次运行（通常10或20次）的平均值和标准差。

## 4. 资源与算力

论文中明确说明：
- 计算LLaMA3-8B所有约45000条陈述的激活向量，在**单个Nvidia Quadro RTX 8000（48 GB）GPU**上耗时**不到两小时**。
- 其他实验（分类器训练、PCA等）的计算需求相比运行LLM可忽略。
- 未提及更详细的算力消耗（如总GPU小时数）。

## 5. 实验数量与充分性

实验较为充分，主要体现在：
- **主题泛化实验**：留一主题法，在所有6个主题数据集上交叉验证，报告20次随机子采样的均值和标准差。
- **陈述类型泛化实验**：在逻辑合取、析取、德语翻译、`common_claim`和`counterfact`等5种未见类型上测试，每种报告20次实验。
- **真实世界谎言实验**：在208个模型响应上分类，并额外分析不同类别的准确率。
- **消融分析**：通过PCA验证二维子空间的存在性；通过投影去除二维子空间后检测剩余线性结构；对比不同训练集组合（肯定句/否定句/合取句）对泛化的影响。
- **跨模型验证**：在LLaMA2-13B-chat、Mistral-7B-Instruct、Gemma-7B-Instruct、Gemma-2-27B-Instruct、LLaMA3-8B-base上重复主要实验，结果均支持二维子空间存在。
- **失败模式分析**：附录D讨论了TTPD和LR在泛化时的两类失败模式（偏置未泛化、方向未泛化）。

**充分性评价**：实验覆盖了多个维度（主题、陈述类型、语言、真实场景、模型家族），且进行了统计分析，整体公平、客观。但真实场景数据量较小（仅208个响应，明确撒谎49个），可能影响统计稳定性。

## 6. 论文的主要结论与发现

1. **存在二维真理子空间**：在不同LLM家族（LLaMA、Gemma、Mistral）中，真假语句的激活向量在一个二维子空间内可线性分离，包含一个通用真理方向 \( t_G \) 和一个极性敏感方向 \( t_P \)。
2. **解释先前失败原因**：仅用肯定句训练得到的“肯定真理方向”是 \( t_G \) 和 \( t_P \) 的线性组合，因此在否定句上失效。
3. **二维性稳定**：引入逻辑连接词、德语句子等新类型后，PCA显示前两个主成分仍主导真值相关方差，不出现第三个显著成分。
4. **TTPD方法达到最先进性能**：
   - 在未见主题上准确率约94%（与LR相当）。
   - 在未见陈述类型（合取/析取/德语）上泛化能力显著优于LR、CCS和MM。
   - 在真实世界谎言检测上准确率达94%，远超LR（79%）、CCS（73%）、MM（91%）。
5. **跨模型通用性**：该二维子空间在多个不同规模、不同家族的LLM中一致出现，支持自然抽象假设。

## 7. 优点：方法或实验设计上的亮点

- **理论洞察深刻**：揭示了之前泛化失败的根本原因，从一维真理方向扩展为二维子空间，具有重要理论意义。
- **方法简洁高效**：TTPD仅需OLS和逻辑回归，计算开销小，易复现。
- **实验设计系统全面**：从主题、陈述类型、语言、真实场景、多模型多个维度评估泛化性，结果可信度高。
- **公平比较**：对基线方法（MM）也扩展了偏置学习，确保公平。
- **开放代码和数据集**：提供GitHub仓库，促进可复现研究。

## 8. 不足与局限

- **真实场景数据量小**：仅26个场景、208个响应，且手动分类存在主观性，可能引入偏差。
- **方法局限性**：
  - TTPD目前只使用了二维子空间中的一个维度（\( t_G \)），未充分挖掘\( t_P \)的潜在信息（非线性分类器可能进一步提升）。
  - 偏置泛化有时失败，导致所有预测偏向某一类（附录D）。
- **泛化范围有限**：仅测试了英语和德语、合取/析取等有限类型，对其他语言、更复杂语义结构（如隐含谎言、反事实）未验证。
- **维度性声明保守**：论文仅称“至少二维”，可能还有其他线性或非线性结构未被发现。
- **应用限制**：方法需要访问模型内部激活，不适用于完全黑盒场景；且未探讨对模型输出的干预效果。
- **计算资源报告不够详细**：未给出总GPU小时、模型大小与推理时间等细节。

（完）
