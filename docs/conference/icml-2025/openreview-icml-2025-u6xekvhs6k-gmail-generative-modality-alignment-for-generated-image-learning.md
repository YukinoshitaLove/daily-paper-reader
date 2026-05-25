---
title: "GMAIL: Generative Modality Alignment for generated Image Learning"
title_zh: GMAIL：面向生成式图像学习的生成模态对齐
authors: "Shentong Mo, Sukmin Yun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=u6xeKVHS6K"
tags: ["query:real-ir"]
score: 4.0
evidence: 将生成图像视为独立模态，桥接真实与合成域
tldr: 该论文提出GMAIL框架，将生成图像作为独立模态，在潜在空间中与真实图像对齐，避免直接替换导致的模式坍塌，实现生成图像的有效利用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1664, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 815, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1634, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1738, \"height\": 1163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 1164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1745, \"height\": 1171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1743, \"height\": 1168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1742, \"height\": 1166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u6xekvhs6k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1742, \"height\": 1166, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1559, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 845, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1299, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1145, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 704, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1201, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 646, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 788, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1392, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1234, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 570, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 633, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 788, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u6xekvhs6k/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 963, \"height\": 181, \"label\": \"Table\"}]"
motivation: 直接使用生成图像训练模型可能导致模式坍塌，因域差异。
method: 将生成图像视为单独模态，通过多模态对齐在潜在空间桥接。
result: 实验证明该方法避免模式坍塌，提高生成图像的训练效果。
conclusion: 模态对齐策略为生成数据在训练中的可靠使用提供了新框架。
---

## Abstract
Generative models have made it possible to synthesize highly realistic images, potentially providing an abundant data source for training machine learning models. Despite the advantages of these synthesizable data sources, the indiscriminate use of generated images as real images for training can even cause mode collapse due to modality discrepancies between real and synthetic domains. In this paper, we propose a novel framework for discriminative use of generated images, coined \textit{GMAIL}, that explicitly treats generated images as a separate modality from real images. Instead of indiscriminately replacing real images with generated ones in the pixel space, our approach bridges the two distinct modalities in the same latent space through a multi-modal learning approach. To be specific, we first fine-tune a model exclusively on generated images using a cross-modality alignment loss and then employ this aligned model to further train various vision-language models with generated images. By aligning the two modalities, our approach effectively leverages the benefits of recent advances in generative models, thereby boosting the effectiveness of generated image learning across a range of vision-language tasks. Our framework can be easily incorporated with various vision-language models, and we demonstrate its efficacy throughout extensive experiments. For example, our framework significantly improves performance on image captioning, zero-shot image retrieval, zero-shot image classification, and long caption retrieval tasks. It also shows positive generated data scaling trends and notable enhancements in the captioning performance of the large multimodal model, LLaVA.

---

## 论文详细总结（自动生成）

# GMAIL 论文详细总结

## 1. 核心问题与整体含义
- **问题背景**：生成模型（如扩散模型）可合成高度逼真的图像，为模型训练提供丰富的数据来源。然而，若直接将生成图像当作真实图像使用，会因真实域与合成域之间的**模态差异**导致**模式坍塌**，模型性能严重下降。
- **整体含义**：提出框架 **GMAIL**，将生成图像显式地视为独立于真实图像的**独立模态**，通过多模态学习在潜在空间中对齐两者，而非在像素空间混用，从而安全、有效地利用生成数据增强视觉‑语言模型训练。

## 2. 方法论
### 核心思想
- **双模态建模**：使用**两个独立的图像编码器**（真实编码器 $f_r$ 和生成编码器 $f_g$），分别处理真实图像和生成图像，避免单一编码器被合成伪影主导。
- **交叉模态对齐**：在对齐损失（公式 1）的作用下，拉近同一描述对应的真实图像与生成图像在共享潜在空间中的距离，同时保持文本编码器 $h$ 仅关注共享的语义交集，忽略合成特有的伪影。
- **两阶段流程**：
  - **Gen‑CLIP 流**：冻结真实编码器，仅用生成图像微调生成编码器（采用 LoRA 高效适配），并加入对齐损失。
  - **推理时 CLIP 流**：对真实图像仍使用原真实编码器，保证模型在真实域上的鲁棒性。
- **与视觉‑语言模型集成**：将对齐后的图像表示接入 CLIPCap、LLaVA、Llama3 等大型多模态模型，进一步微调下游任务。

### 关键技术细节
- **对齐损失（式 1）**：基于对比学习的 InfoNCE 形式，最大化配对生成‑真实图像 embedding 的余弦相似度，同时最小化非配对对的相似度。温度系数 $\tau = 0.07$。
- **LoRA 微调**：秩设为 4，仅更新少量参数，防止遗忘真实表示，比全参数微调更高效且效果更优。
- **投影层**：分别为真实和生成模态学习独立的投影层，将图像特征映射到联合空间。

## 3. 实验设计
### 任务与数据集
- **图像字幕**：COCO (train2014 生成图像，val2014 评估)
- **零样本图像‑文本检索**：COCO、Flickr30k
- **零样本图像分类**：8 个标准数据集（DTD, Stanford Cars, SUN397, Food101, Aircraft, Oxford Pets, Caltech101, ImageNet）
- **长字幕检索**：ShareGPT4V
- **视觉问答**：ScienceQA, MMMU
- **缩放趋势分析**：使用 COCO、CC3M、CC12M 的生成图像训练

### 对比方法
- **基线**：CLIP、Long‑CLIP、ClipCap、IFCap、LLaVA、Llama3 等在原真实数据或混入生成数据下的版本
- **消融**：有无对齐损失、不同 LoRA 秩（2/4/6）、全微调、单/双投影、是否使用对齐、仅真实数据 vs 混用 vs GMAIL 对齐

### 生成模型
- 主要采用 **Stable Diffusion v2**，生成规模与原始训练集一一对应（COCO 56 万张，CC3M 330 万张，CC12M 1200 万张）。
- 补充实验使用 **FLUX**，验证对生成器变化的鲁棒性。

## 4. 资源与算力
- **生成阶段**：使用 NVIDIA A100‑80GB GPU。
  - COCO：5 GPU‑days
  - CC3M：30 GPU‑days
  - CC12M：109 GPU‑days
- **微调阶段**：对齐训练步数 50k，训练时间约 10 小时（COCO 实验），显存占用约 28 GB，FLOPs 约 85.5 G。
- 相比无对齐的混用基线，GMAIL **收敛更快 (60k vs 70k 步)**，计算效率更高。

## 5. 实验数量与充分性
- **实验组数众多**：涵盖 4 大任务、10+ 个数据集、多个模型骨架，实验总量超过 20 组对比或有数据的表格。
- **消融实验充分**：验证了对齐损失、双投影、LoRA 秩、训练步数相等、计算开销，以及替换生成器（FLUX）的影响。
- **对比公平、客观**：所有方法均使用相同的生成数据集、评估协议，并报告了多个指标，与近期代表性工作（SynCLR、SigLIP、Task2Sim）进行了对比。

## 6. 主要结论与发现
- **GMAIL 显著提升性能**：在图像字幕上，GMAIL+ClipCap 的 B@4 提升 5.97；LLaVA+ GMAIL 的 CIDEr 提升 12.09；零样本检索和分类也有一致增益。
- **有效防止模式坍塌**：通过将生成图像作为独立模态，避免了混合训练时合成伪影主导表示的问题。
- **良好的可扩展性**：随着生成数据规模扩大（COCO→CC3M→CC12M），性能持续上升。
- **兼容主流多模态模型**：对 LLaVA、Llama3、Long‑CLIP 等均带来稳定提升，且对齐损失与双投影可应用于纯真实数据训练时也略有改进。

## 7. 优点
- **概念清晰**：将生成图像视为独立模态，并显式对齐，有别于以往“混用”的简单思路。
- **方法简洁有效**：仅需少量 LoRA 参数和对比对齐损失，即可大幅缓解模态差异。
- **实验全面扎实**：覆盖多种任务、多个基线、不同规模数据和生成器，消融完整，提供了充分的证据。
- **实用性强**：框架即插即用，可直接接入现有视觉‑语言模型训练流程，计算开销可控。

## 8. 不足与局限
- **依赖生成模型质量**：生成图像仍可能存在细微伪影，若生成模型存在系统性偏差，对齐结果可能继承该偏差。
- **未充分探讨不同生成架构的影响**：主实验仅用 Stable Diffusion v2，虽补充了 FLUX，但缺少对 GAN、自回归模型等生成的系统性分析。
- **下游任务覆盖有限**：主要聚焦于视觉‑语言理解任务，对物体检测、分割等密集预测任务未做验证。
- **计算成本**：大规模生成图像（如 1200 万张）仍需要可观的 GPU 资源，可能限制资源受限场景下的应用。

（完）
