---
title: "OmniGen-AR: AutoRegressive Any-to-Image Generation"
title_zh: OmniGen-AR：自回归任意到图像生成
authors: "Junke Wang, Xun Wang, Qiushan Guo, Peize Sun, Weilin Huang, Zuxuan Wu, Yu-Gang Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Gxw10T7uOm"
tags: ["query:real-ir"]
score: 9.0
evidence: 统一的自回归任意输入到图像生成框架
tldr: 现有自回归图像生成方法局限于单一模态条件（如文本）。本文提出首个统一自回归任意到图像生成框架OmniGen-AR，通过共享视觉分词器和文本分词器离散化各种视觉条件及文本提示，在单一模型中支持文本、空间信号等多样输入。实验表明其在多种条件生成任务上达到竞争性能，展现了图像生成领域的通用性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 774, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 827, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 892, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1408, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 288, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 292, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 280, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1414, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 533, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 670, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 794, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 538, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 588, \"height\": 342, \"label\": \"Table\"}]"
motivation: 现有自回归图像生成模型仅支持单模态条件输入，缺乏处理多样化控制信号的能力。
method: 构建统一自回归框架，通过共享视觉分词器将不同模态条件离散化，实现任意到图像生成。
result: 在多种条件图像生成任务上取得了与当前方法相当或更优的性能。
conclusion: OmniGen-AR为多条件图像生成提供了统一高效的解决方案。
---

## Abstract
Autoregressive (AR) models have demonstrated strong potential in visual generation, offering competitive performance with simple architectures and optimization objectives. However, existing methods are typically limited to single-modality conditions, \eg, text or category labels, restricting their applicability in real-world scenarios that demand image synthesis from diverse forms of controls. In this work, we present \system, the first unified autoregressive framework for Any-to-Image generation. By discretizing various visual conditions through a shared visual tokenizer and text prompts with a text tokenizer, \system supports a broad spectrum of conditional inputs within a single model, including text (text-to-image generation), spatial signals (segmentation-to-image and depth-to-image), and visual context (image editing, frame prediction, and text-to-video generation). To mitigate the risk of information leakage from condition tokens to content tokens, we introduce Disentangled Causal Attention (DCA), which separates the full-sequence causal mask into condition causal attention and content causal attention. It serves as a training-time regularizer without affecting the standard next-token prediction during inference. With this design, \system achieves new state-of-the-art results across a range of benchmark, \eg, 0.63 on GenEval and 80.02 on VBench, demonstrating its effectiveness in flexible and high-fidelity visual generation.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有自回归（AR）视觉生成模型（如 LLamaGen、SimAR）通常仅限于单模态条件输入（如文本或类别标签），无法处理实际应用中多样的控制信号（如语义分割图、深度图、参考图像、历史帧等）。这限制了它们在真实场景中的通用性。
- **整体含义**：为了填补这一空白，论文提出了 **OmniGen-AR**——首个**统一的、支持任意输入到图像（Any-to-Image）**的自回归生成框架。该模型在单一架构内可处理文本、空间信号（分割/深度）、视觉上下文（图像编辑、帧预测、文本到视频生成）等多种条件，展现了自回归模型在多条件图像生成中的巨大潜力。

---

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过**共享视觉分词器**将不同模态的视觉条件（分割图、深度图、待编辑图像等）和待生成的图像统一离散化为 token 序列，并使用**文本分词器**处理文本提示。然后训练一个**仅解码器（decoder-only）的自回归 Transformer**，以“下一 token 预测”方式对整个多模态序列建模。
- **关键技术细节**：
  - **视觉与文本 token 化**：采用统一的图像-视频联合分词器 Cosmos-DV8×16×16 将图像/条件编码为离散 token；文本使用 Qwen2.5 分词器。
  - **序列构造**：对于空间/图像条件任务，序列形式为 `[文本 tokens, 条件 tokens, 内容 tokens]`；对于纯文本条件任务，序列为 `[文本 tokens, 内容 tokens]`。
  - **Disentangled Causal Attention (DCA)**：
    - 针对条件 token 向内容 token 可能产生的**信息泄漏**问题（尤其是在图像编辑、帧预测等任务中），DCA 将完整的因果注意掩码拆分为**条件因果注意**和**内容因果注意**两部分，阻止内容 token 在训练时访问条件 token（但仍允许条件 token 感知自己的位置）。
    - 训练时以一定概率（默认 10%）随机替换标准因果注意力为 DCA，作为**正则化手段**；推理时仍使用标准因果注意力，不影响效率。
  - **训练与推理**：使用语言建模损失（cross-entropy）训练；推理时采用标准 next‑token 预测 + Classifier-Free Guidance（CFG）提升生成质量。

---

## 3. 实验设计：数据集、benchmark、对比方法

- **训练数据**：三阶段训练（SI → IV → MT），使用公开和内部数据，包括 CC3M、CC12M、OpenImages、SAM1B、Megalith、Panda70M、HD-VILA-100M、JourneyDB、Synthetic-dataset-1M、MagicBrush、Instruct-Pix2Pix、SEED-Edit、MultiGen 深度/分割数据集、OpenSora-pexels-45k、OpenVid-1M 等。所有图像/视频使用 Qwen2-VL 重标注。
- **Benchmark 与任务**：
  - **文本到图像**：GenEval（报告对象数量、颜色、位置等指标）。
  - **文本到视频**：VBench（质量、语义、总分）。
  - **帧预测**：Kinetics-600（FVD，零样本评估）。
  - **图像编辑**：Emu-Edit 测试集（CLIP 文本相似度 CT、CLIP 图像相似度 CI）。
  - **空间条件生成**：分割到图像 (ADE20K, mIoU)、深度到图像 (MultiGen-Depth-Eval, RMSE)。
- **对比方法**：涵盖扩散模型（SDv1.5/v2.1、PixArt‑α、CogVideo、LaVie、OpenSora 等）和自回归模型（LLamaGen、SimAR、ControlAR、EditAR、OmniGen、Show-o、Emu3 等），参数规模从 0.5B 到 13B 不等。

---

## 4. 资源与算力

- **GPU 型号与数量**：64 块 A100 GPU。
- **超参数**：全局 batch size = 256；SI/IV 阶段学习率 1e-4，分辨率 512；MT 阶段学习率 2e-5，分辨率 1024；使用 AdamW 优化器，无 warm‑up 和学习率衰减。
- **训练时长**：论文未明确给出总训练时间，仅说明分三个阶段训练。

---

## 5. 实验数量与充分性

- **实验数量**：开展了**六大类任务**（文本到图像、文本到视频、帧预测、图像编辑、分割到图像、深度到图像）的对比实验；并进行了**多种消融研究**：
  - DCA 替换概率 (0%、5%、10%、20%、30%) 对 VBench、Emu-Edit、分割任务的影响。
  - 联合训练 vs. 单独训练的协同效应。
  - 模型规模 (0.5B vs. 1.5B) 的定性/定量对比。
- **充分性与公平性**：实验覆盖了主流 benchmark，对比方法涵盖近期重要模型（扩散和 AR 均有），多数结果达到 SOTA 或接近 SOTA。消融实验设计合理，验证了 DCA 的有效性。但部分对比使用带 prompt rewriting 的版本（如 Infinity、Emu3），可能对公平性略有影响；论文也承认联合训练在 T2I/T2V 上性能略降，体现了诚实的讨论。

---

## 6. 论文的主要结论与发现

- **性能领先**：OmniGen-AR（1.5B）在 GenEval 上取得 **0.63**，超越同参数 AR 模型（SimAR 0.61）和许多扩散模型；在 VBench 上取得 **80.02**，首次让离散 token AR 模型突破 80 分。
- **DCA 有效**：以 10% 概率替换标准因果注意力可显著提升图像编辑的指令遵循能力（CLIP 文本相似度从 0.15 提升至 0.20），并小幅改善空间条件生成。
- **多任务协同**：联合训练提升了编辑和空间条件生成性能（利用基础生成能力的迁移），但会轻微损害 T2I 和 T2V，表明不同任务数据质量和分布存在差异。
- **模型缩放收益**：从 0.5B 扩至 1.5B 在各类任务上均带来明显提升，说明更大的模型能更好地理解复杂指令并产生高质量内容。

---

## 7. 优点：方法或实验设计上的亮点

- **统一框架**：首次将 AR 模型扩展到任意条件（文本、空间、视觉上下文），无需多个专用适配器或编码器，体现了 AR 范式的灵活性和可扩展性。
- **DCA 的创新设计**：训练时正则化、推理时无额外开销，简洁有效，且与 CFG 互补。
- **共享视觉分词器**：利用图像-视频联合 tokenizer 统一处理不同视觉条件，简化流程且利于跨任务知识迁移。
- **系统消融**：对 DCA 概率、联合训练策略、模型规模等关键因素均做了定量/定性分析，实验设计系统全面。
- **在多个 benchmark 达到 SOTA**，尤其是 VBench 上 AR 模型首次超过 80 分，验证了 AR 路线的竞争力。

---

## 8. 不足与局限

- **指令遵循局限性**：在复杂空间/关系指令下（如“移除长椅上的包”误移除了人）仍会失败，表明当前模型对精细语言-视觉对齐理解不足。
- **稀疏控制信号生成质量低**：深度/分割条件生成时出现模糊或结构不一致的结果，可能源于训练数据中此类对齐样本不足或噪声较大。
- **联合训练导致 T2I/T2V 性能轻微下降**：提示不同任务数据质量差异带来的权衡，尚未完美解决。
- **计算资源需求高**：64 块 A100 GPU，未公布总训练时间，复现成本较高。
- **未提供开源代码/权重**（仅承诺发布），当前可追溯性有限。
- **未充分讨论社会风险**如偏见、深度伪造等伦理问题（虽然论文提及未来可借鉴 CoT 提升推理能力，但在安全方面未深入探讨）。

---

（完）
