---
title: "Mask-Enhanced Autoregressive Prediction: Pay Less Attention to Learn More"
title_zh: 掩码增强自回归预测：少关注以学更多
authors: "Xialie Zhuang, Zhikai Jia, Jianjin Li, Zhenyu Zhang, Li Shen, Zheng Cao, Shiwei Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=73FyDmYsdn"
tags: ["query:fie-rag"]
score: 6.0
evidence: 增强LLM的上下文检索能力，有利于RAG中的少样本学习
tldr: 大语言模型在关键信息检索上存在不足。MEAP通过将掩码语言建模无缝融入自回归预测，增强模型的上下文检索能力。该方法无需双向注意力或编码器-解码器结构，且在预训练和推理中无额外开销。实验表明MEAP显著提升了LLM的上下文检索和少样本学习性能。该技术可促进RAG系统中少样本场景的推理。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 688, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 669, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 670, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 848, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 854, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73fydmysdn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 853, \"height\": 440, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1519, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 464, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1519, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1614, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1615, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1214, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 748, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 600, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1180, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 692, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 933, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1509, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1661, \"height\": 916, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1659, \"height\": 960, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1661, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73fydmysdn/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 757, \"height\": 413, \"label\": \"Table\"}]"
motivation: LLM在检索关键信息方面存在缺陷，影响少样本学习。
method: 在自回归预测中随机掩码少量token，在不改变解码器架构的前提下将MLM集成到NTP训练。
result: 显著提升LLM的上下文检索能力和多个NLU基准的少样本性能。
conclusion: MEAP是一种简单有效的训练范式，可增强LLM的信息检索能力。
---

## Abstract
Large Language Models (LLMs) are discovered to suffer from accurately retrieving key information. To address this, we propose Mask-Enhanced Autoregressive Prediction (MEAP), a simple yet effective training paradigm that seamlessly integrates Masked Language Modeling (MLM) into Next-Token Prediction (NTP) to enhance the latter's in-context retrieval capabilities. Specifically, MEAP first randomly masks a small fraction of input tokens and then directly performs the standard next-token prediction autoregressive using a decoder-only Transformer. MEAP eliminates the need for bidirectional attention or encoder-decoder architectures for MLM, incurring no additional computational overhead during pre-training or inference. Intensive experiments demonstrate that MEAP substantially outperforms NTP on key information retrieval and long-context reasoning tasks, while performing on par or better on commonsense reasoning tasks. The benefits of MEAP also extend to supervised fine-tuning, where it shows remarkable advantages in lost-in-the-middle scenarios, outperforming NTP by 11.77% percentage points. Our analysis indicates that MEAP’s effectiveness arises from its ability to promote more distinguishable attention scores by concentrating on a reduced set of non-masked tokens. This mechanism improves the model’s focus on task-relevant signals while mitigating the influence of peripheral context. These findings position MEAP as a promising training paradigm for large language models. Code has been submitted.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有大型语言模型（LLM）基于下一个词预测（NTP）的训练范式，虽然在文本生成和扩展性上表现优异，但**在从长上下文中准确检索关键信息方面存在严重缺陷**（例如“Lost in the Middle”现象）。而掩码语言建模（MLM）虽擅长信息检索，但通常需双向注意力或编码器-解码器架构，不适合现代解码器-only LLM的高效扩展。
- **研究动机**：如何在不引入额外计算开销、不改变解码器架构的前提下，将MLM的优势（精确检索）与NTP的优势（生成连贯性）有机结合，提升LLM的上下文检索和长文本推理能力。
- **整体含义**：提出一种轻量级、即插即用的训练范式MEAP，可无缝集成到现有NTP流程中，显著增强LLM对关键信息的捕捉与利用，同时保持原有的扩展效率。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：在标准自回归预训练过程中，**随机掩码一小部分输入token（占比P）**，然后直接进行从左到右的下一个词预测。掩码操作迫使模型在没有完整上下文的情况下学习，从而增强其对关键信息的敏感度，并使注意力分布更可区分。
- **关键技术细节**：
  - **预训练阶段**：对输入序列 `X = (x1, x2, ..., xn)` 按比例 `P` 随机替换为 `[MASK]`，得到 `X'`。仍使用**因果掩码（causal mask）**，从左到右预测每个位置的token（包括掩码位置）。掩码比例 `P=15%`。
  - **微调阶段**：将训练样本复制一份，对复制序列随机掩码（`P=10%`），然后将原始序列与掩码副本拼接成一个更长的输入。**仅对掩码token和答案token计算交叉熵损失**，保证关键信息不被删除。仅当答案长度超过50 token时应用MEAP，否则用标准NTP。
- **算法流程**（文字描述）：
  1. 输入序列 `X`，按比例 `P` 随机选择位置替换为 `[MASK]`，得到 `X'`。
  2. 将 `X'` 送入解码器-only Transformer，以因果掩码方式逐位置预测下一个token（包括预测 `[MASK]` 位置的真实token）。
  3. 损失函数为标准NTP的交叉熵，对所有位置（包括掩码位置）进行预测。
  4. 推理时与标准NTP完全一致，无需任何额外改动。
- **数学公式**（简要描述）：
  - 预训练：`p_θ(X') = ∏_{t=1}^T p_θ(x_t | x_{<t})`，其中 `x_{<t}` 中包含掩码token。
  - 微调：`L(θ) = -∑_{t ∈ U_q ∪ U_m} log p_θ(x_t | x_{<t}; ̂x_{<t})`，其中 `{̂x}` 为掩码副本。

### 3. 实验设计：使用的数据集/场景、benchmark、对比方法

- **数据集与场景**：
  - **预训练**：SlimPajama（627B token），训练1.1B参数的LLaMa-style模型。
  - **关键信息检索**：Needle-in-a-Haystack（单针检索，32K/64K上下文）、Multi-Document QA（10文档和20文档，基于NaturalQuestions-Open）。
  - **长上下文推理**：Multi-Needle Reasoning Task (M-RS)。
  - **常识推理**：ARC-c/e、BoolQ、PIQA、HellaSwag、WinoGrande、OBQA（零样本）。
  - **幻觉评估**：XSum、MultiNews、WikiSum（使用GPT-4o等作为幻觉检测器）。
  - **微调**：Alpaca指令数据集；commonsense reasoning同上；Multi-Document QA。
  - **跨模型泛化**：Llama-3.2-3B、Mistral-7B-v0.2、Qwen2.5-14B。
- **基准（benchmark）**：LM Eval Harness；Needle in a Haystack（ROUGE-1）；OpenCompass（M-RS）。
- **对比方法**：主要与**标准NTP**比较。在预训练中控制相同数据量（40B/60B/200B token）和相同模型架构；在微调中控制处理的总token数近似（MEAP 2 epoch vs NTP 4 epoch）。

### 4. 资源与算力

- 文中**未明确说明具体使用的GPU型号、数量或训练时长**。仅提及以下信息：
  - 预训练1.1B模型，上下文长度4096，batch size 256。
  - 使用bfloat16精度、DeepSpeed Zero Stage 2。
  - 预训练数据量从40B到200B token不等。
  - 微调Llama-3-8B使用batch size 512，max sequence length 4096。
- 由于未披露算力细节，难以直接评估训练成本，但作者强调MEAP在预训练和推理阶段 **“无额外计算开销”** （微调时因序列翻倍会增加开销，但通过数据效率补偿）。

### 5. 实验数量与充分性

- **实验数量**：较为丰富，涵盖预训练（不同数据量、不同尺寸模型）、微调、跨模型泛化、消融（掩码比例、掩码策略）、注意力分析等。
  - 预训练：3种数据量（40B/60B/200B） + 3种模型尺寸（100M/500M/1.1B，见附录）。
  - 关键任务：Needle（单针）、MDQA（10/20文档）、M-RS、常识推理（7项）、幻觉（3数据集）。
  - 消融：掩码比例（0.05/0.10/0.15/0.20）、掩码策略（随机/5-span/50-span）。
  - 跨模型：3种开源模型（Llama-3.2-3B, Mistral-7B, Qwen2.5-14B）。
- **充分性评估**：
  - **客观公平**：使用相同架构、相同数据量、相同训练步数（或相近训练token数）进行对比；结果统计显著（附T检验）。
  - **局限性**：预训练仅测试了1.1B规模，更大模型（如7B/70B）未进行预训练对比；微调跨模型泛化仅测试了8B以下模型；幻觉评估仅100个样本，统计稳定性存疑；消融实验仅基于0.3B模型，结论可能不直接适用于大模型。

### 6. 论文的主要结论与发现

1. **关键信息检索显著提升**：MEAP在Needle-in-a-Haystack中，60B token即达到85.8%准确率，而NTP需要200B token才接近（87.1%）；最终200B时MEAP达98.2%，NTP仅87.1%。
2. **长上下文推理改进**：在Multi-Needle Reasoning上平均提升6.6个百分点。
3. **常识推理保持或微升**：预训练后零样本平均提升1.6%；微调后平均提升1.12分。
4. **减少幻觉**：在三个摘要数据集上，MEAP的幻觉率均低于NTP（经多个LLM裁判验证）。
5. **微调“Lost-in-the-Middle”优势**：在20文档MDQA中，MEAP平均提升11.77%。
6. **数据效率突出**：MEAP用60B token即可达到NTP用200B token在Needle任务上的性能。
7. **机制解释**：MEAP使**注意力更可区分**：对掩码token注意力下降53.34%，非掩码token注意力方差增加7.80%；推理时，MEAP将34.5%的注意力分配给答案相关token（NTP仅9.4%）。

### 7. 优点：方法或实验设计上的亮点

- **极其简洁**：仅添加随机掩码操作，不改变模型架构、损失函数形式、推理接口，可在现有NTP代码库中一行改动实现。
- **零额外开销**：预训练和推理阶段计算量、参数量、内存占用与NTP完全相同；微调虽序列翻倍，但通过减少epoch实现高效率（见图5）。
- **通用性强**：在预训练和微调中均有效，且跨不同模型家族（LLaMA, Qwen, Mistral）和规模（3B/7B/14B）均带来一致提升。
- **实验设计严谨**：控制变量（相同数据量、相同总处理token数）进行比较；进行了统计显著性检验（T-test）；在注意力机制上通过量化分析验证了假设，避免了“黑盒”猜测。

### 8. 不足与局限

- **实验规模有限**：预训练仅验证了1.1B模型，未在更大规模（如7B, 13B, 70B）上验证MEAP的预训练效果，其扩展性存疑。
- **微调开销未完全消除**：微调时序列长度加倍，虽然通过数据效率补偿，但在训练吞吐量上可能仍低于NTP（尤其是短序列场景）。
- **掩码比例需人工设定**：预训练最优15%，微调最优10%，且不同任务可能需调整，缺少自适应策略。
- **对比方法单一**：仅与标准NTP对比，未与UL2、UniLM等统一注意力范式比较，也未与Prompt-based检索增强方法对比。
- **幻觉评估样本量小**：仅100个样本，且仅用LLM裁判判断，缺乏人工评估或更稳健的度量（如FactCC）。
- **消融实验规模小**：掩码策略比较基于0.3B模型，结论不一定外推至大模型。
- **未讨论负面迁移**：未分析在高质量数据（如代码、数学推理）上MEAP是否可能损害性能。

（完）
