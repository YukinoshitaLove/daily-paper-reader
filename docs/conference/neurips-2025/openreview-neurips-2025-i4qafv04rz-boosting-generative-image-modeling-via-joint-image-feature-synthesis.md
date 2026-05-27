---
title: Boosting Generative Image Modeling via Joint Image-Feature Synthesis
title_zh: 通过联合图像-特征合成提升生成图像建模能力
authors: "Theodoros Kouzelis, Efstathios Karypidis, Ioannis Kakogeorgiou, Spyros Gidaris, Nikos Komodakis"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=i4qAfV04rZ"
tags: ["query:real-ir"]
score: 6.0
evidence: 通过联合合成潜在和语义特征进行生成图像建模
tldr: 潜在扩散模型在图像生成中占据主导，但表示学习与生成模型难以集成。本文提出潜语义扩散方法，联合生成VAE潜变量和DINO语义特征，仅需对Diffusion Transformer进行微小修改，显著提升生成质量与训练效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1372, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 712, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1314, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 628, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 659, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1371, \"height\": 1235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1296, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1295, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1294, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1295, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1296, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1298, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1297, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i4qafv04rz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1297, \"height\": 815, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 582, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 815, \"height\": 747, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 690, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 696, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 679, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 803, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 875, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 443, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i4qafv04rz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1299, \"height\": 418, \"label\": \"Table\"}]"
motivation: 表示学习与生成模型之间的鸿沟限制了扩散模型的潜力。
method: 提出联合建模低层图像潜变量和高层语义特征的潜语义扩散方法。
result: 在生成质量和训练效率上取得显著提升。
conclusion: 联合图像-特征合成为扩散模型引入表示学习能力。
---

## Abstract
Latent diffusion models (LDMs) dominate high-quality image generation, yet integrating representation learning with generative modeling remains a challenge. We introduce a novel generative image modeling framework that seamlessly bridges this gap by leveraging a diffusion model to jointly model low-level image latents (from a variational autoencoder) and high-level semantic features (from a pretrained self-supervised encoder like DINO). Our latent-semantic diffusion approach learns to generate coherent image-feature pairs from pure noise, significantly enhancing both generative quality and training efficiency, all while requiring only minimal modifications to standard Diffusion Transformer architectures. By eliminating the need for complex distillation objectives, our unified design simplifies training and unlocks a powerful new inference strategy: Representation Guidance, which leverages learned semantics to steer and refine image generation. Evaluated in both conditional and unconditional settings, our method delivers substantial improvements in image quality and training convergence speed, establishing a new direction for representation-aware generative modeling.

---

## 论文详细总结（自动生成）

好的，以下是对您提供的论文《Boosting Generative Image Modeling via Joint Image-Feature Synthesis》的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

-   **核心问题**：主流的潜在扩散模型（LDMs）在高质量图像生成方面表现出色，但它们在训练过程中存在内在矛盾：为精确重建图像的低级细节（VAE潜变量）与学习有意义的语义表示（这对下游任务至关重要）之间存在张力。这导致LDMs通常无法像专门的自监督学习方法（如DINOv2）那样学习到高质量的语义特征。一个关键问题是：如何有效地利用表示学习来增强生成建模的性能？
-   **研究动机**：先前的工作（如REPA）表明，通过蒸馏预训练自监督表示来提升扩散模型内部特征的语义质量，可以改善生成质量和收敛速度。受此启发，本文探索一种更直接、更有效的方法来利用表示学习。
-   **整体含义**：本文的核心主张是，与其像REPA那样通过复杂的蒸馏目标将扩散特征与外部表示对齐，不如直接在同一个扩散过程中**联合建模**图像本身（具体是其VAE潜变量）和从预训练视觉编码器（如DINOv2）提取的高层语义特征。这使得模型能够学习两者的联合分布，从而直接受益于高质量的语义信息，提升生成性能。

### 2. 论文提出的方法论：核心思想、关键技术细节

-   **核心思想**：提出 **ReDi (Representation Diffusion)** 框架，将VAE潜变量（低层细节）和DINOv2特征（高层语义）视为一个**联合模态**，在一个统一的扩散过程中进行建模和生成。
-   **关键技术细节**：
    -   **联合前向扩散过程**：同时向VAE潜变量 `x0` 和语义特征 `z0` 添加噪声：
        `xt = √¯αt x0 + √(1-¯αt) ϵx`
        `zt = √¯αt z0 + √(1-¯αt) ϵz`
    -   **联合训练目标**：模型 `ϵθ` 需要同时预测两个噪声。损失函数为：
        `L_joint = E[ ||ϵx_θ - ϵx||² + λz ||ϵz_θ - ϵz||² ]`
    -   **Token融合策略**：为了在Diffusion Transformer中处理这两种模态，提出了两种简单的融合方式：
        1.  **Merged Tokens（合并令牌）**：将VAE和语义特征的tokens在通道维度上直接相加。
        2.  **Separate Tokens（独立令牌）**：将两种tokens在序列维度上拼接。
        默认采用计算效率更高的**Merged Tokens**策略。
    -   **PCA降维**：为解决DINOv2特征通道数远大于VAE潜变量而导致模型容量分配不均的问题，首先对DINOv2特征进行PCA降维（默认降至8维），使其通道数与VAE潜变量更平衡。
    -   **表示引导（Representation Guidance）**：一种新的推理引导策略。在推理时，模型可以同时生成图像和其对应的语义表示。`表示引导` 利用模型在生成过程中预测的语义表示来指导图像的生成，使其更符合语义特征。其核心公式是对预测噪声进行修正：
        `ˆϵθ(xt, zt, t) = ϵθ(xt, t) + wr (ϵθ(xt, zt, t) - ϵθ(xt, t))`
        这类似于Classifier-Free Guidance，但引导信号是联合模型自身的语义预测。

### 3. 实验设计：数据集、Benchmark与对比方法

-   **数据集**：所有实验均在 **ImageNet** 数据集上进行，分辨率为 **256x256**。
-   **Benchmark**：主要使用 **FID** (Fréchet Inception Distance) 作为核心评估指标，同时也报告了 sFID、Inception Score (IS)、Precision (Pre.) 和 Recall (Rec.)。
-   **对比方法**：
    -   **基线模型**：
        -   **DiT** (Peebles & Xie, 2023) 及其变体 DiT-B/2, L/2, XL/2
        -   **SiT** (Ma et al., 2024) 及其变体 SiT-XL/2
    -   **核心对比方法**：**REPA** (Yu et al., 2025)，该方法通过蒸馏DINOv2特征来提升DiT性能。
    -   **其他SOTA方法**：包括自回归模型（VAR, MagViTv2, MAR）和其他潜在扩散模型（LDM, U-ViT, MaskDiT, MDT, FasterDiT等）。

### 4. 资源与算力

-   **文中明确说明**：
    -   **GPU型号与数量**：所有训练和采样实验均使用 **8块 NVIDIA A100 40GB GPU**。
    -   **训练配置**：批量大小为 **256**。

### 5. 实验数量与充分性

-   **实验数量**：论文进行了大量且详尽的实验，覆盖了以下几个维度：
    1.  **不同模型规模**：在 DiT 和 SiT 的 B/2, L/2, XL/2 三种规模上均进行了实验（表1）。
    2.  **有无引导**：在无分类器引导（No CFG，表1）和有分类器引导（With CFG，表2）两种设置下评估。
    3.  **条件与无条件生成**：在类条件生成（表1, 2）和无条件生成（表3）两种任务上实验。
    4.  **对比分析**：与最先进的方法（表2）及核心竞争对手 REPA（表1, 2, 图2）进行了对比。
    5.  **消融实验**：
        -   **表示引导的有效性**（表3, 4）。
        -   **PCA主成分数量**的影响（图7）。
        -   **Merged Tokens 与 Separate Tokens 的效果对比**（表6）。
        -   **与REPA的互补性**验证（表5）。
-   **充分性与公平性**：
    -   实验设计**非常充分**，涵盖了主要的评估维度，结果具有说服力。例如，图2所示的训练曲线清晰地展示了其在收敛速度上的巨大优势（相比DiT快23倍）。
    -   实验设置**相对客观公平**，所有方法均在ImageNet 256x256标准基准上评估，并使用ADM官方评估套件计算FID，保证了对比的可信度。

### 6. 论文的主要结论与发现

1.  **显著提升生成质量**：ReDi在生成质量上（FID）显著超越了DiT和SiT基线，并在相同或更少的训练迭代下超越REPA。例如，DiT-XL/2 + ReDi仅需400K迭代，FID就达到了8.7，而基线的DiT-XL/2需要7M迭代才能达到9.6。
2.  **极大加速训练收敛**：ReDi可以**将DiT和SiT的训练收敛速度提升约23倍**。相比REPA，也**快约6倍**。
3.  **表示引导的有效性**：提出的`表示引导`能进一步提升生成质量，尤其对**无条件生成**任务帮助巨大，能显著缩小其与有条件生成模型之间的性能差距。
4.  **与REPA互补**：ReDi的目标与REPA的目标是互补的，两者结合可以取得更好的效果。

### 7. 优点

-   **简洁有效**：方法本身非常简洁，仅需对标准DiT架构进行最小修改，避免了复杂的蒸馏目标，易于实现和部署。
-   **创新性强**：首次提出将图像和语义特征作为联合模态在扩散模型中直接建模，并提出利用其进行`表示引导`，思路新颖。
-   **性能卓越**：在生成质量和训练效率上均取得了非常显著的提升，尤其是在加速训练方面的效果令人印象深刻。
-   **分析深入**：通过详尽的消融实验（PCA降维、Token融合策略、表示引导影响等），深入分析了方法中各个组件的作用和最佳实践，具有很高的研究价值。

### 8. 不足与局限

-   **视觉表示来源单一**：当前方法仅探索了DINOv2一种视觉表示。未来工作可以探索集成多种不同语义/结构属性的视觉表示，可能会带来进一步的提升。
-   **降维方式简单**：使用PCA进行降维是有效的，但并非最优。作者也指出，更复杂的压缩技术（如训练一个自动编码器）可能更好地保留特征的表达力。
-   **计算成本**：虽然Merged Tokens策略保持了计算效率，但Separate Tokens策略（最大FLOPs版本）会因增加序列长度而导致计算量近乎翻倍（吞吐量减半），这在追求性能时是一个权衡。
-   **潜在的社会影响**：生成模型的性能提升可能被滥用于制造深度伪造和传播虚假信息，存在潜在的负面社会影响。

（完）
