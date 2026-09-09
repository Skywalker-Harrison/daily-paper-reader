<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-09-09
- 运行时间：2026-09-09 22:44:30 UTC
- 运行状态：成功
- 本次总论文数：30
- 精读区：12
- 速读区：18

### 今日简报（AI）
今日完成30篇论文筛选，精读12篇、速读18篇，重点关注安全与语音两大方向。

最值得看的两篇9.0分工作：一篇提出大模型越狱评估的效度问题，另一篇实现代码转换语音的免训练局部口音控制。

建议优先精读这两篇，并搭配速读中的“TTS模型成员推断攻击”一文，警惕语音合成服务的隐私泄露风险。
- 详情：[/202609/09/README](/202609/09/README)

### 精读区论文标签
1. [Validity-Aware Jailbreak Evaluation for Large Language Models](/202609/09/2609.00498v1-validity-aware-jailbreak-evaluation-for-large-language-models)  
   标签：评分：9.0/10、query:llm-attack
   evidence：面向大语言模型越狱的有效性感知评测方法，关注步骤正确性
2. [Phrase-Localized Language-Contrastive Guidance: Training-Free Localized Accent Control for Code-Switching Text-to-Speech](/202609/09/2609.01016v1-phrase-localized-language-contrastive-guidance-training-free-localized-accent-control-for-code-switching-text-to-speech)  
   标签：评分：9.0/10、query:speech-tech
   evidence：多语言/跨语言文本转语音中的局域口音控制
3. [Summary of the ChinaVoices Challenge 2026: Data, Tasks, Baseline, and Methods](/202609/09/2609.03471v1-summary-of-the-chinavoices-challenge-2026-data-tasks-baseline-and-methods)  
   标签：评分：9.0/10、query:speech-tech
   evidence：ChinaVoices 2026挑战赛覆盖16个中文方言类别，设置方言语种识别与方言ASR，直接满足方言语音处理识别需求
4. [SAFEGuard: Detect Optimization-Based Jailbreak Attacks Through Harmful Semantic Analysis and Fluency Measurement](/202609/09/2609.05850v1-safeguard-detect-optimization-based-jailbreak-attacks-through-harmful-semantic-analysis-and-fluency-measurement)  
   标签：评分：9.0/10、query:llm-attack
   evidence：基于有害语义分析与流畅度测量检测优化式越狱攻击
5. [Qwen-Audio-3.0-ASR Technical Report](/202609/09/2609.07549v1-qwen-audio-30-asr-technical-report)  
   标签：评分：9.0/10、query:speech-tech
   evidence：基于MoE与LLM的语音识别系统，面向区域方言与自发语音处理
6. [TontaubeV1: Streaming Text-to-Speech with Hierarchical Codec Modeling and Bounded Context](/202609/09/2609.08703v1-tontaubev1-streaming-text-to-speech-with-hierarchical-codec-modeling-and-bounded-context)  
   标签：评分：9.0/10、query:qwen-tts
   evidence：使用Qwen3派生transformer的TTS模型，并预测话语时长
7. [Separating Syntax from Language: A Mechanistic Account of Translation in Multilingual LLMs](/202609/09/2609.01356v1-separating-syntax-from-language-a-mechanistic-account-of-translation-in-multilingual-llms)  
   标签：评分：8.0/10、query:cross-lang
   evidence：多语言大模型中的翻译机制与跨语言语义迁移；翻译输出可分离为句法过程与表层语言过程
8. [SpeakPay: Domain-Adaptive LoRA Fine-Tuning of Whisper for Low-Resource Nepali Financial Speech Recognition](/202609/09/2609.01737v1-speakpay-domain-adaptive-lora-fine-tuning-of-whisper-for-low-resource-nepali-financial-speech-recognition)  
   标签：评分：8.0/10、query:speech-tech
   evidence：面向低资源尼泊尔金融语音识别，与低资源语言语音技术需求高度相关
9. [GlyphAnchor: Enhancing Visual Text Rendering via Position-Anchored Glyph Priors](/202609/09/2609.02349v1-glyphanchor-enhancing-visual-text-rendering-via-position-anchored-glyph-priors)  
   标签：评分：8.0/10、query:mtg-bench
   evidence：面向文生图的字形渲染增强，可支撑非拉丁字母和罕见字符的文本渲染
10. [Building and Evaluating Fixed-Voice Thai TTS from Synthetic Speech](/202609/09/2609.03502v1-building-and-evaluating-fixed-voice-thai-tts-from-synthetic-speech)  
   标签：评分：8.0/10、query:low-res-tts
   evidence：直接面向低资源语言语音合成：用短参考音色与合成语音构建泰语固定音色合成系统
11. [AlcaTRAz - Anchored Tree-Rule Defense Against Jailbreaks](/202609/09/2609.03693v1-alcatraz---anchored-tree-rule-defense-against-jailbreaks)  
   标签：评分：8.0/10、query:llm-attack
   evidence：面向大模型越狱的提示级防御方法，与越狱攻击研究直接相关
12. [Mind the Gap: Exposing LLM Translation Blind Spots Using the AlphaMWE Multilingual Parallel Corpus](/202609/09/2609.06634v1-mind-the-gap-exposing-llm-translation-blind-spots-using-the-alphamwe-multilingual-parallel-corpus)  
   标签：评分：8.0/10、query:cross-lang
   evidence：在多个语言对上用MWE评测大模型翻译, 揭示与字面/非字面倾向相关的盲区

### 速读区论文标签
1. [Hearing the Whispers: Black-Box Membership Inference Attacks on Finetuned TTS Models](/202609/09/2609.01723v1-hearing-the-whispers-black-box-membership-inference-attacks-on-finetuned-tts-models)  
   标签：评分：7.0/10、query:llm-attack
   evidence：针对微调TTS语音模型的黑盒成员推理攻击，属于语音模型安全与隐私漏洞主题
2. [AVERT: Audio-Verified Adjudication for Spoken Dialogue State Tracking](/202609/09/2609.01828v1-avert-audio-verified-adjudication-for-spoken-dialogue-state-tracking)  
   标签：评分：7.0/10、query:speech-tech
   evidence：利用音频验证修正口语对话状态追踪中的ASR错误
3. [To What Extent Do Large Language Models Understand Bangla Idioms?](/202609/09/2609.03410v1-to-what-extent-do-large-language-models-understand-bangla-idioms)  
   标签：评分：7.0/10、query:cross-lang
   evidence：测试大语言模型对孟加拉语习语的理解，关系到习语字面与非字面意义的把握
4. [Alignment-Free Text-Audiobox for Voice Dubbing and Full-Duplex Dialogue Synthesis](/202609/09/2609.03992v1-alignment-free-text-audiobox-for-voice-dubbing-and-full-duplex-dialogue-synthesis)  
   标签：评分：7.0/10、query:speech-tech
   evidence：采用无对齐潜在扩散的语音配音与对话合成方法
5. [Cross-Lingual Representation Alignment by Token-Level Optimal Transport in a Language-Agnostic Space](/202609/09/2609.06381v1-cross-lingual-representation-alignment-by-token-level-optimal-transport-in-a-language-agnostic-space)  
   标签：评分：7.0/10、query:cross-lang
   evidence：基于最优传输的跨语言词元级表示对齐方法，直接面向跨语言语义迁移能力提升
6. [LoGAN: Multilingual Font Localization with Generative Agents](/202609/09/2609.07029v1-logan-multilingual-font-localization-with-generative-agents)  
   标签：评分：7.0/10、query:mtg-bench
   evidence：面向多语言字体本地化，用字形级扩散模型生成其他文字的完整字符集，可服务于非拉丁文字渲染
7. [Beyond One-Shot Expansion: Contrastive Evidence Exploration for Multi-Hop Retrieval](/202609/09/2609.07050v1-beyond-one-shot-expansion-contrastive-evidence-exploration-for-multi-hop-retrieval)  
   标签：评分：7.0/10、query:fie-rag
   evidence：面向多跳RAG检索的无训练框架，增强证据覆盖并抑制噪声，可用于改进RAG少样本推理
8. [AuK Technical Report: An Open-Source Foundational Model for Speech Generation and Editing](/202609/09/2609.08936v1-auk-technical-report-an-open-source-foundational-model-for-speech-generation-and-editing)  
   标签：评分：7.0/10、query:speech-tech
   evidence：开源语音生成与编辑基础模型，涉及语音合成方向
9. [TASTE2: Text-Aligned Speech Modeling and Deployment toward Full-Duplex Voice Interaction](/202609/09/2609.08956v1-taste2-text-aligned-speech-modeling-and-deployment-toward-full-duplex-voice-interaction)  
   标签：评分：7.0/10、query:speech-tech
   evidence：全双工语音建模与文本对齐合成
10. [BiMTokenizer: Preserving Semantic-Acoustic Balance in Low-Bitrate Speech Tokenization via Bidirectional State-Space Modeling](/202609/09/2609.00562v1-bimtokenizer-preserving-semantic-acoustic-balance-in-low-bitrate-speech-tokenization-via-bidirectional-state-space-modeling)  
   标签：评分：6.0/10、query:speech-tech
   evidence：低比特率语音词元化，在语音大模型连接中兼顾语义与声学，可用于语音合成/识别技术主线
11. [Forbid Your Attention: Fooling Multimodal Large Language Models by Selectively Removing Intrinsic Focus in Spectral Domain](/202609/09/2609.00788v1-forbid-your-attention-fooling-multimodal-large-language-models-by-selectively-removing-intrinsic-focus-in-spectral-domain)  
   标签：评分：6.0/10、query:llm-attack
   evidence：在频域上攻击多模态大语言模型的新方法，属于大模型安全对抗鲁棒性研究
12. [Ready to Speak: Aligning LLMs for TTS-Friendly Text Generation](/202609/09/2609.01246v1-ready-to-speak-aligning-llms-for-tts-friendly-text-generation)  
   标签：评分：6.0/10、query:speech-tech
   evidence：将LLM输出对齐为适合TTS朗读的文本并提供TTS到ASR评测，属语音合成研究链路。
13. [TimeSteer: Inference-Time Speech Scheduling in Joint Audio-Visual Diffusion Models](/202609/09/2609.01277v1-timesteer-inference-time-speech-scheduling-in-joint-audio-visual-diffusion-models)  
   标签：评分：6.0/10、query:qwen-tts
   evidence：生成中语音时间调度的推理时控制，与时长或时间可控的语音生成相关
14. [SALA: Semantic-Aware Logical Alignment for Complex Reasoning in In-Context Learning](/202609/09/2609.02336v1-sala-semantic-aware-logical-alignment-for-complex-reasoning-in-in-context-learning)  
   标签：评分：6.0/10、query:fie-rag
   evidence：面向少样本上下文学习的语义感知示例选择方法，可迁移至检索增强的少样本推理场景
15. [NE-R1: Enhancing Named Entity Recognition Model via Reinforcement Learning](/202609/09/2609.02366v1-ne-r1-enhancing-named-entity-recognition-model-via-reinforcement-learning)  
   标签：评分：6.0/10、query:fie-rag
   evidence：将强化学习与按需检索结合用于命名实体识别，可迁移至少样本语言任务
16. [VoxReason: Listener-Free Evaluation of Source-Grounded Speech Planning Before Synthesis](/202609/09/2609.03203v1-voxreason-listener-free-evaluation-of-source-grounded-speech-planning-before-synthesis)  
   标签：评分：6.0/10、query:speech-tech
   evidence：合成前语音规划的无听者评测方法
17. [Decoupling Turn-Taking from Semantics: A Decoupled Data Approach for Finite-State-Machine-Based Full-Duplex Dialogue](/202609/09/2609.03321v1-decoupling-turn-taking-from-semantics-a-decoupled-data-approach-for-finite-state-machine-based-full-duplex-dialogue)  
   标签：评分：6.0/10、query:speech-tech
   evidence：用真实语音学习轮次、用文本对话塑造语义的全双工对话方法
18. [Translation as a Decision Space: A Multi-Agent Perspective on Low-Resource Dialect Generation](/202609/09/2609.04048v1-translation-as-a-decision-space-a-multi-agent-perspective-on-low-resource-dialect-generation)  
   标签：评分：6.0/10、query:cross-lang
   evidence：将低资源方言翻译重构为决策空间，涉及跨语言翻译策略


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
