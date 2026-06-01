---
title: "RAPID: Long-Context Inference with Retrieval-Augmented Speculative Decoding"
title_zh: RAPID：基于检索增强推测解码的长上下文推理
authors: "Guanzheng Chen, Qilong Feng, Jinjie Ni, Xin Li, Michael Qizhe Shieh"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=73mDARqOtQ"
tags: ["query:fie-rag"]
score: 5.0
evidence: 将RAG与推测解码结合实现高效长上下文推理
tldr: 长上下文LLM推理的计算开销巨大，传统推测解码在长上下文场景下效率下降。RAPID引入检索增强推测解码，使用基于缩短检索上下文的草稿模型进行推测。该方法不仅加速推理，还能提升生成质量，在长文档处理上优于标准RAG。该框架可降低RAG在长文本事实推理中的延迟。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-73mdarqotq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 815, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73mdarqotq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1654, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-73mdarqotq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 830, \"height\": 1003, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 912, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 798, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 629, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1175, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 771, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-73mdarqotq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1084, \"height\": 230, \"label\": \"Table\"}]"
motivation: 长上下文推理计算开销大，推测解码在长上下文中效率低。
method: 提出RAG草稿模型，在缩短的检索上下文上推测token，结合目标模型验证。
result: 在长上下文基准上，RAPID实现2-3倍加速同时保持或提升生成质量。
conclusion: RAG与推测解码结合可有效解决长上下文推理的效率瓶颈。
---

## Abstract
The emergence of long-context large language models (LLMs) offers a promising alternative to traditional retrieval-augmented generation (RAG) for processing extensive documents. However, the computational overhead of long-context inference presents significant efficiency challenges. While Speculative Decoding (SD) traditionally accelerates inference using smaller draft models, its effectiveness diminishes substantially in long-context scenarios due to memory-bound KV cache operations. We introduce Retrieval-Augmented Speculative Decoding (RAPID), which leverages RAG for both accelerating and enhancing generation quality in long-context inference. RAPID introduces the RAG drafter—a draft LLM operating on shortened retrieval contexts—to speculate on the generation of long-context target LLMs. Our approach enables a new paradigm where same-scale or even larger LLMs can serve as RAG drafters while maintaining computational efficiency. To fully leverage the potentially superior capabilities from stronger RAG drafters, we develop an inference-time knowledge transfer that enriches the target distribution by RAG. Extensive experiments on the LLaMA-3.1 and Qwen2.5 backbones demonstrate that RAPID effectively integrates the strengths of both RAG and long-context LLMs, achieving significant performance improvements (e.g., from 39.33 to 42.83 on InfiniteBench for LLaMA-3.1-8B) with more than 2$\times$ speedups for long-context inference. Our analyses also reveal the robustness of RAPID across various context lengths and retrieval quality.

---

## 论文详细总结（自动生成）

# RAPID：基于检索增强推测解码的长上下文推理

## 1. 核心问题与整体含义

- **研究动机**：长上下文大语言模型（LLM）能够直接处理百万级 token 的文档，但推理时因需要管理巨大的 KV 缓存而导致计算开销巨大、延迟高。传统的推测解码（Speculative Decoding, SD）使用小模型作为草稿模型来加速推理，但在长上下文场景中，草稿模型也需要处理完整上下文，导致 KV 缓存操作成为内存瓶颈，加速效果急剧下降。
- **整体含义**：作者提出 RAPID（Retrieval-Augmented Speculative Decoding），将检索增强生成（RAG）与推测解码相结合，在长上下文推理中既加速又提升生成质量。RAPID 使用一个基于“缩短的检索上下文”的 RAG 草稿模型来推测目标长上下文 LLM 的输出，从而实现高效推理，并允许使用同规模甚至更大规模的模型作为草稿模型。

## 2. 方法论

- **核心思想**：
  1. **RAG 草稿模型**：对长上下文文档进行分块检索，仅将检索到的相关文本段（压缩后的上下文）作为草稿模型的输入，而非全量上下文。这大幅减少了草稿模型的内存占用和计算量。
  2. **检索增强的目标分布**：在推测解码的验证阶段，不是直接使用目标 LLM 的原始分布，而是通过反向蒸馏（将 RAG 草稿模型视为教师，目标 LLM 视为学生）得到一个经 RAG 增强的分布，从而更易接受高质量候选 token，避免因分布不匹配而无效拒绝。
- **关键技术细节**：
  - **上下文压缩**：从原始上下文 C 中检索出相关片段形成压缩上下文 C_S，满足 |C_S| ≤ |C|/λ 且 λ ≫ 1。
  - **推测与验证**：
    - 草稿模型基于 C_S 生成 γ 个候选 token x'_i。
    - 目标模型计算原始 logits z(x'_j)，得到目标分布 p。
    - 草稿模型给出分布 q。
    - 增强后的目标分布：\(\hat{p}(x_i) = \text{softmax}\left( z(x_i)/T + \eta \cdot (q(x_i) - p(x_i)) \right)\)，其中 η 控制蒸馏强度，T 为温度。
    - 接受准则：\(r \leq \min\left(1, \frac{\hat{p}(x'_j)}{q(x'_j)}\right)\)，若拒绝则从残差分布中采样。
  - **知识蒸馏视角**：增强分布的设计源于对 KL 散度蒸馏损失梯度的推导，使得目标分布向草稿分布偏移。
- **算法流程（文字说明）**：
  1. 使用 RAG 检索得到压缩上下文 C_S。
  2. 草稿模型在 C_S 上生成 γ 个候选 token。
  3. 目标模型在完整上下文 C 上计算每个候选 token 的原始分布 p 和 logits。
  4. 结合草稿分布 q 计算增强分布 \(\hat{p}\)。
  5. 顺序验证：若随机数 r 满足接受准则则接受该 token，否则从残差分布中采样一个 token 并终止本轮推测。
  6. 重复直到完整序列生成。

## 3. 实验设计

- **数据集与场景**：
  - **∞Bench**：包括三个子任务——长文档问答（En.QA，F1 指标）、多选题（En.MC，准确率）、摘要（En.Sum，ROUGE-L-Sum），上下文长度超过 100K token。
  - **LongBench v2**：多选任务，上下文长度 8K 到 2M 词，采用中间截断控制在 128K token 内；效率评估使用其中的 Long、CoT 子集（约 120K 上下文 + 1K 生成）。
  - **多轮对话生成**：基于 MT-Bench-101 构建，每个样本包含约 122K token 的对话历史，评估质量（GPT-4 打分）和吞吐量。
- **对比方法**：
  - Long Context (LC)：目标模型直接处理完整上下文。
  - RAG：目标模型仅使用检索到的上下文（同 RAG 草稿模型的输入）。
  - 原始推测解码 (SD)：使用相同草稿模型但采用标准分布。
  - MagicDec：基于 StreamingLLM 压缩 KV 缓存的 SD 变体。
  - 额外对比：TriForce（仅对 LWM-Text-Chat-128K 模型）、MInference（稀疏注意力加速预填充）。
- **评估指标**：性能（准确率/F1/ROUGE）、吞吐量（tokens/sec）、加速比（相对于 LC 基线）、接受率、预填充时间等。

## 4. 资源与算力

- **明确说明**：
  - 对于小规模模型（LLaMA-3.1-8B、Qwen2.5-7B）：使用单张 NVIDIA A800 80GB GPU。
  - 对于大规模模型（LLaMA-3.1-70B、Qwen2.5-72B）：使用 8×A800 80GB GPU 分布式配置。
  - 对于向上推测（小目标 + 大草稿）：小模型用 1 张 A800，大草稿用额外的 7 张 A800（共 8 张）。
- 未明确说明训练时长，仅推理评估。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要结果表（Table 1）涵盖了 4 种目标模型、2 种推测设置（自推测和向上推测）、3 个 ∞Bench 子任务 + LongBench v2 整体 + CoT 子集，共约 10 组配置×多个指标。
  - 额外有：
    - 上下文长度与检索长度影响分析（图 3）：3 种检索长度 × 6 种目标长度。
    - 多轮对话实验（表 2）。
    - 检索质量鲁棒性实验（表 3）：不同 η 值下使用无关上下文。
    - 与 TriForce、MInference 的对比（附录表 6、7）。
    - 成功率与失败率分析（图 2）。
  - 总体实验数量较为丰富，覆盖了不同模型规模、不同任务类型、不同上下文长度和检索配置。
- **充分性与公平性**：
  - 充分性：方法在多个模型家族（LLaMA-3.1、Qwen2.5）上验证，自推测和向上推测均被评估；消融实验（η、检索长度）和鲁棒性测试较全面。
  - 公平性：所有方法在相同 GPU 环境下运行；对比的基线包括标准 RAG、原始 SD、MagicDec 等；接受率、吞吐量等指标均报告。但部分对比（TriForce、MInference）仅在子集上进行，且 MagicDec 在效率上表现较差（慢于 LC），可能对 MagicDec 不太公平（其设计目标是保持生成质量而非极致加速）。

## 6. 主要结论与发现

- **性能提升**：RAPID 在自推测设置下，性能一致优于单独使用 LC 或 RAG（例如 LLaMA-3.1-8B 在 ∞Bench 上从 39.33 提升至 42.83）；向上推测使用时，甚至超过更大模型单独运行（8B+70B RAG 草稿达 49.98，超过 70B LC 的 45.07）。
- **加速效果**：当目标上下文长度超过 32K 时，RAPID 可实现 >2× 加速（如 LLaMA-3.1-8B 自推测 2.10×，70B 自推测 2.69×）；向上推测场景下效率与较小目标模型相近（约 1× 左右）。
- **新范式**：RAPID 允许同规模甚至更大模型作为草稿模型，这得益于短上下文的计算优势。
- **鲁棒性**：即使使用不相关的检索上下文，在适度 η 下仍能保持正增益；更强草稿模型（向上推测）鲁棒性更佳。
- **新兴现象**：RAPID 能正确处理目标模型和草稿模型都失败的情况，显示两者协同产生新能力。

## 7. 优点

- **方法创新**：首次将 RAG 与推测解码深度结合，提出 RAG 草稿模型和检索增强目标分布，实现了加速与质量提升的双重目标。
- **理论与实践的兼顾**：从蒸馏损失梯度推导增强分布，保留理论正确性（附录证明残差分布维持目标分布）；算法流程清晰。
- **效率与性能的平衡**：在加速的同时，通过引入 RAG 草稿模型的知识提升了生成质量，克服了传统 SD 在长上下文下效率退化的问题。
- **实验设计全面**：覆盖多种模型系列、多种任务类型、多种上下文长度配置，并进行了鲁棒性和消融分析。
- **公平性考量**：明确报告了加速比、吞吐量、接受率等效率指标，与多种基线对比。

## 8. 不足与局限

- **实验覆盖不均**：
  - 效率评估主要基于 LongBench v2 的 Long、CoT 子集（120K 上下文），未在更长的上下文（如 1M token）下测试实际加速比。
  - 与 TriForce、MInference 的对比仅在特定模型（LWM-Text-Chat-128K）或单一任务上进行，缺乏在主流模型上的直接对比。
- **检索成本**：RAG 草稿模型需要检索和嵌入计算，虽然论文指出其开销较小（约 1.43 秒），但在超长上下文中检索时间可能随文档增长而增加，论文未深入分析可扩展性。
- **参数敏感性**：蒸馏强度 η 需要针对不同设置手动搜索（5~20 或 40~50），缺乏自适应方法；在无关检索下 η 值过大可能导致性能下降。
- **应用限制**：
  - 依赖有效的检索器（如 BGE-M3），若检索质量较差（如低相似度阈值），可能影响推测质量。
  - 向上推测需要额外 GPU 资源（大草稿模型），实际部署成本可能增加。
- **可解释性不足**：对“新兴现象”（RAPID 单独处理双方都失败的案例）的原因未深入分析，仅归因于协同交互。

（完）
