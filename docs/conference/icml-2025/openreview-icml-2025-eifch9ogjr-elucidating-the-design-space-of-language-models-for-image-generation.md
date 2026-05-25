---
title: Elucidating the design space of language models for image generation
title_zh: 语言模型用于图像生成的设计空间阐释
authors: "Xuantong LIU, Shaozhe Hao, Xianbiao Qi, Tianyang Hu, Jun Wang, Rong Xiao, Yuan Yao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EIfCH9OgjR"
tags: ["query:real-ir"]
score: 4.0
evidence: 探究语言模型用于图像生成的设计空间，非扩散模型复原
tldr: 本研究系统探索了语言模型在图像生成中的设计空间，发现通过合理选择分词、建模和采样策略，无需针对视觉的特殊设计即可达到接近最先进的性能。但该工作聚焦于自回归图像生成，与图像修复和扩散模型关联较弱。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1682, \"height\": 1266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1700, \"height\": 1996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1592, \"height\": 2110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1264, \"height\": 1550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1776, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1728, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1723, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1662, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 898, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1599, \"height\": 855, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1600, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1598, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1223, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1734, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1557, \"height\": 2271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1557, \"height\": 2269, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 658, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 1088, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 830, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1416, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 768, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1694, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1704, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 638, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1019, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1304, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1367, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1143, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1341, \"height\": 554, \"label\": \"Table\"}]"
motivation: 现有方法要么使用专门设计，要么未充分探索LLM在视觉任务中的潜力。
method: 系统研究LLM的标记化、扫描模式、词汇设计等对图像生成的影响。
result: LLM通过正确选择可实现接近SOTA的图像生成性能。
conclusion: 揭示了LLM在图像生成中的扩展行为，但方法偏向自回归而非扩散。
---

## Abstract
The success of large language models (LLMs) in text generation has inspired their application to image generation. However, existing methods either rely on specialized designs with inductive biases or adopt LLMs without fully exploring their potential in vision tasks. In this work, we systematically investigate the design space of LLMs for image generation and demonstrate that LLMs can achieve near state-of-the-art performance without domain-specific designs, simply by making proper choices in tokenization methods, modeling approaches, scan patterns, vocabulary design, and sampling strategies. We further analyze autoregressive models' learning and scaling behavior, revealing how larger models effectively capture more useful information than the smaller ones. Additionally, we explore the inherent differences between text and image modalities, highlighting the potential of LLMs across domains. The exploration provides valuable insights to inspire more effective designs when applying LLMs to other domains. With extensive experiments, our proposed model, **ELM** achieves an FID of 1.54 on 256$\times$256 ImageNet and an FID of 3.29 on 512$\times$512 ImageNet, demonstrating the powerful generative potential of LLMs in vision tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
* **研究动机**：大型语言模型（LLMs）在文本生成上的成功推动其在图像生成领域的应用，但现有方法要么引入强烈的领域特定归纳偏置（如多尺度生成、随机排列），要么未充分挖掘LLM本身的潜力。
* **核心问题**：系统性地**揭示并阐释语言模型应用于图像生成时的完整设计空间**，以回答“只做正确的设计选择，无需为视觉任务定制特殊架构，LLM能否达到顶尖图像生成性能”这一关键问题。
* **整体含义**：验证了纯语言模型范式的跨模态迁移能力，为构建统一的、可扩展的多模态基础模型提供了重要的方法论见解和实验依据。

## 2. 论文提出的方法论
论文并非提出全新算法，而是通过详尽的消融实验定义了一套最优设计组合，最终形成模型`ELM`。其核心技术选择如下：

*   **图像标记化**：全面比较`VQGAN`（矢量量化）和`BAE`（二元自编码器），确定**BAE为最优标记器**。BAE通过逐标量二值化（$z_d^q = \text{sign}(z_d)$）生成离散码，实现了100%的码本利用率，重建（rFID）和生成（gFID）性能均显著优于VQGAN。
*   **建模方式**：比较自回归（AR）和掩码语言模型（MLM），发现**AR模型在图像生成质量和训练效率上均一直优于MLM**，且展现出良好的模型缩放定律，避免了MLM后期过度拟合导致的多样性下降问题。
*   **序列扫描模式**：比较了行光栅、列光栅、之字形及对角线之字形五种将2D图像块展平为1D序列的方式，确认**行主序光栅扫描（row-raster）性能最佳**，但发现AR模型对各种扫描模式都能有效学习。
*   **词汇设计**：利用BAE的灵活性，探索了二进制代码分解策略。将原始高维码（如 $D=16$）**分解为两个子码（如 2-8）是最优策略**，能在降低计算量和预测复杂度的同时，利用更强的标记器提升效果。并且，更强的标记器（更大 $D$）需要匹配更大容量的模型。
*   **采样策略**：验证了**高随机性至关重要**。对AR模型，采用较高的`top-k`值进行采样；对MLM，引入较高系数的Gumbel噪声。同时，**线性增加的分类器无关引导（CFG）尺度**被证实为最佳引导策略。

## 3. 实验设计
*   **主数据集/Benchmark**：256$\times$256 ImageNet类条件图像生成。使用`FID`为主要评估指标，辅以Inception Score、Precision和Recall。
*   **对比方法**：在统一benchmark下，与多类代表性模型进行了全面比较：
    *   **扩散模型**：DiT-L/2, DiT-XL/2, SiT-XL/2。
    *   **掩码语言模型**：MaskGIT。
    *   **自回归模型**：VQGAN, LlamaGen（LlamaGen-L/XL/XXL/3B）。
    *   **其他创新范式**：VAR（Visual Autoregressive）, MAR（Masked Autoregressive）。
*   **泛化与拓展实验**：
    *   **高分辨率迁移**：在512$\times$512 ImageNet上进行微调，验证从低分辨率向高分辨率的高效迁移能力。
    *   **跨数据集测试**：在CelebA（人脸）和DTD（纹理）数据集上训练，验证对特定域数据的适应性。
    *   **零样本能力**：测试类别插值生成和图像编辑任务。

## 4. 资源与算力
文中明确提到了模型的训练资源：
*   **GPU型号**：80GB A800 GPU。
*   **训练配置与时长**：
    *   **L和XL尺寸模型**：使用**8块A800 GPU**，完成400个epoch训练分别约需**6.4天和10天**。
    *   **XXL尺寸模型**：使用**16块A800 GPU（2个节点，每节点8卡）**，完成400个epoch训练约需**12天**。

## 5. 实验数量与充分性
论文包含**大量且结构化的消融与对比实验**，覆盖了整个设计空间，论证非常充分和客观。
*   **核心组件消融**：针对标记器（VQGAN vs. BAE）、建模方法（AR vs. MLM）、扫描模式（5种）、词汇分解策略（多种`n-m`组合）、采样超参数（CFG scale、top-k、噪声系数、迭代次数）等，每个维度均设置了受控实验，并固定其他变量。
*   **可解释性分析**：通过可视化不同大小AR模型的注意力图，分析其学习行为（关注局部与全局信息之别），为缩放定律提供了机制层解释。同时定量分析了图像与文本标记的随机性差异。
*   **对比广度**：在最终性能对比中，纳入了扩散、MLM、AR、VAR等多种主流范式下的最新模型，且参数量级从2亿到31亿不等，对比公平全面。

## 6. 论文的主要结论与发现
*   **设计选择优于领域特化**：仅凭在标记化、建模、词汇、采样等设计空间做出正确选择，无需任何视觉领域特定的归纳偏置，LLM框架（ELM）就能在ImageNet上取得接近最先进的图像生成性能（256$\times$256 FID 1.54）。
*   **AR模型的主导地位**：在图像生成中，AR模型在生成质量、可扩展性和避免过拟合方面均优于MLM。
*   **BAE标记器的优越性**：BAE解决了VQGAN的码本坍缩问题，具备更强的重建和生成能力。
*   **知识学习和缩放行为**：AR模型的浅层关注局部信息，深层或更大模型能捕获长程全局依赖，这很好地解释了模型缩放定律——模型扩大，不仅能降低损失，还能学到更丰富的全局结构。
*   **模态的根本差异**：图像标记的分布比文本标记更随机、更缺乏顺序性，这解释了LLM生成图像时训练损失高但仍能生成高质量图像的原因，并凸显了推理时采样的重要性。

## 7. 优点
*   **系统性与洞察力**：像一篇“生存手册”，对LLM图像生成的设计空间进行了教科书级别的归纳和实证，结论清晰、具有启发性。
*   **方法简洁高效**：ELM模型仅用标准LLaMA架构和纯AR生成，证明了“Less is More”，降低了工程复杂度。
*   **分析与可视化深刻**：通过注意力图可视化、码本统计等，不仅展示“是什么”，更解释“为什么”，加深了对模型行为的理解。
*   **实用的设计指南**：文中得出的“将码本一分为二”、“大词表配大模型”、“高随机性采样”等具体技巧，具有极高的实用参考价值。

## 8. 不足与局限
*   **训练目标有待革新**：论文承认传统的next-token交叉熵损失对于高度随机的图像标记可能并非最优，高训练损失成为瓶颈，未来需要探索更合适的损失函数（如扩散损失）。
*   **实验范围局限**：标记器和生成模型仅在ImageNet上训练，其结论在更大规模、更复杂的数据集（如LAION）上的泛化性有待验证。
*   **任务单一**：主要聚焦于类别条件生成，未探索更具挑战和更实用的文本到图像生成（Text-to-Image），这限制了其对主流文生图应用的直接影响。
*   **生成效率**：虽然提到了效率分析，但作为自回归模型，其推理时的序列生成速度本质上慢于扩散模型（在同等序列长度下），这是一个固有的应用限制。

（完）
