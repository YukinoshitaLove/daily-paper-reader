---
title: "Morse: Dual-Sampling for Lossless Acceleration of Diffusion Models"
title_zh: Morse：扩散模型的无损加速双采样方法
authors: "Chao Li, Jiawei Fan, Anbang Yao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Gdcwm4LLfb"
tags: ["query:real-ir"]
score: 7.0
evidence: 双采样框架无损加速扩散模型
tldr: 提出Morse双采样框架，通过Dash模型跳步采样和Dot模型残差反馈，实现扩散模型的无损加速。该方法可应用于各类预训练扩散模型，显著减少推理步数，同时保持生成质量，为实际部署提供了高效方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1511, \"height\": 1133, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1600, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1609, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 1040, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 1039, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 840, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 841, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1647, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1748, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1608, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1063, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1551, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1282, \"height\": 2202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1280, \"height\": 2195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1538, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1538, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1537, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1539, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1531, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1539, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1541, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1539, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1537, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1539, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gdcwm4llfb/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1535, \"height\": 261, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 819, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 414, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 402, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 648, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 520, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1594, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 768, \"height\": 734, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 913, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1241, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gdcwm4llfb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1230, \"height\": 139, \"label\": \"Table\"}]"
motivation: 扩散模型推理慢，需要无损加速方法。
method: 利用跳步采样和残差反馈，两个模型协同进行双采样加速。
result: 实现了扩散模型的无损加速，适用于各种模型类型。
conclusion: Morse为扩散模型提供了一种简单有效的无损加速策略。
---

## Abstract
In this paper, we present $Morse$, a simple dual-sampling framework for accelerating diffusion models losslessly. The key insight of Morse is to reformulate the iterative generation (from noise to data) process via taking advantage of fast jump sampling and adaptive residual feedback strategies. Specifically, Morse involves two models called $Dash$ and $Dot$ that interact with each other. The Dash model is just the pre-trained diffusion model of any type, but operates in a jump sampling regime, creating sufficient space for sampling efficiency improvement. The Dot model is significantly faster than the Dash model, which is learnt to generate residual feedback conditioned on the observations at the current jump sampling point on the trajectory of the Dash model, lifting the noise estimate to easily match the next-step estimate of the Dash model without jump sampling. By chaining the outputs of the Dash and Dot models run in a time-interleaved fashion, Morse exhibits the merit of flexibly attaining desired image generation performance while improving overall runtime efficiency. With our proposed weight sharing strategy between the Dash and Dot models, Morse is efficient for training and inference. Our method shows a lossless speedup of 1.78$\times$ to 3.31$\times$ on average over a wide range of sampling step budgets relative to 9 baseline diffusion models on 6 image generation tasks. Furthermore, we show that our method can be also generalized to improve the Latent Consistency Model (LCM-SDXL, which is already accelerated with consistency distillation technique) tailored for few-step text-to-image synthesis. The code and models are available at https://github.com/deep-optimization/Morse.

---

## 论文详细总结（自动生成）

好的，以下是针对论文《Morse: Dual-Sampling for Lossless Acceleration of Diffusion Models》的结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

-   **核心问题**：扩散模型（Diffusion Models）虽然生成质量高，但其迭代式降噪生成过程通常需要数百步推理，导致采样效率低下，计算开销巨大。现有加速方法（如设计更快求解器、知识蒸馏）虽有效，但通常伴随性能损失或仅限于特定场景。
-   **研究动机**：论文观察到大多数扩散模型支持“跳步采样”（Jump Sampling），即在不访问所有时间步的情况下进行生成。这虽然能加速，但会因跳过中间步骤的信息丢失而损害生成质量。
-   **整体含义**：论文旨在从一个更**通用化的视角**解决上述问题，提出一种名为 Morse 的无损双采样加速框架。其核心思想是：即使对于任意的预训练扩散模型和采样器，也能通过一种新颖的模型协作方式，在提升推理效率的同时，**无损地**保持生成质量，即达到速度与质量的更优权衡。

### 2. 论文提出的方法论

-   **核心思想**：Morse 框架将传统的单模型迭代生成过程，重塑为两个模型——**Dash** 和 **Dot** 的交替交互协作。
    -   **Dash 模型**：即为待加速的预训练扩散模型，但其**在跳步采样机制下运行**，为采样效率的提升留出空间。
    -   **Dot 模型**：一个**比 Dash 模型快 N 倍**的轻量模型。它的任务是学习在 Dash 模型当前的跳步采样点，根据轨迹信息（当前样本、时间步和噪声估计）**生成残差反馈**，从而将当前的噪声估计提升到 Dash 模型在**非跳步**情况下去往下一步的估计水平，补偿了跳步带来的信息损失。
-   **关键技术细节与流程**：
    -   **噪声估计公式**：Morse 重新定义了生成过程中的噪声估计方式：
        `zt_i = θ(xt_i, t_i)`, 当 `t_i` 属于 Dash 模型的采样步集合 `S`；
        `zt_i = zt_s + η(xt_s, xt_i, zt_s, t_s, t_i)`, 当 `t_i` 不属于 `S`。
        其中 `θ` 是 Dash 模型，`η` 是 Dot 模型，`ts` 是 Dash 最近经过的跳步点。
    -   **权重共享策略**：Dot 模型通过在 Dash 模型结构的顶层和底层添加少量、低通道数的降采样/上采样块来构建。由于输入分辨率通过降采样降低，且跳跃连接的自注意力层被简化，Dot 模型速度远快于 Dash。训练时，Dash 模型的共享权重被冻结，只训练新增的块和轻量级的低秩适应（LoRA）模块，训练成本极低。
    -   **推理流程**：在生成过程中，Dash 和 Dot 模型以时间交错的方式运行。按照预定的时序安排，在 Dash 的采样点上由 Dash 独立估计噪声，在这些点之间则插入多步由 Dot 模型完成的快速残差估计，从而在不增加总延迟的情况下，增加了有效的采样步数。

### 3. 实验设计

-   **数据集/场景**：
    -   **无条件/条件图像生成**：CIFAR-10 (32×32)、CelebA (64×64)、ImageNet (64×64)、CelebA-HQ (256×256) 和 LSUN-Church (256×256)。
    -   **文本到图像生成**：在 MS-COCO 验证集上评估 Stable Diffusion v1.4，在 MS-COCO 上评估 LCM-SDXL。
-   **基准模型**：广泛评估了 9 个基线扩散模型，涵盖不同的架构（U-Net， 自注意力）、模型大小（3500万到8.6亿参数）、采样器（DDPM, DDIM, SDE, DPM-Solver）和条件策略（无条件和基于分类器引导）。
-   **对比方法**：
    -   **主要基线**：各扩散模型在不使用 Morse 加速时的原始性能。
    -   **先进加速方法**：与特征重用方法（DeepCache， PFDiff）以及时间步调度优化方法（AYS）进行了对比。
    -   **蒸馏模型增强**：将 Morse 应用于已通过蒸馏加速的 LCM-SDXL，展示了其互补性。

### 4. 资源与算力

-   **硬件平台**：
    -   **训练**：
        -   大多数实验：服务器配有 8 块 NVIDIA GeForce RTX 3090 或 RTX 4090 GPU。
        -   Stable Diffusion 实验：配有 8 块 NVIDIA Tesla V100 GPU 的服务器。
    -   **推理与速度测试**：主要在单块 NVIDIA GeForce RTX 3090 GPU 上进行，并在 RTX 4090 和 Tesla V100 上进行了跨平台验证。
-   **训练成本**：论文强调 Dot 模型训练开销极低。以 Stable Diffusion 为例，Dash 模型使用约 20 亿图文对预训练，而 Dot 模型仅需约 **200 万图文对（不到 0.1%）** 和 **100,000 次迭代**进行微调，总训练成本仅为训练 Dash 模型的 0.1%左右，显存占用也降低了 19.8%。

### 5. 实验数量与充分性

-   **实验组合丰富**：论文设计了约 15 组主要实验和消融实验，覆盖了**不同采样器、不同数据集、不同网络架构、不同条件生成策略**等多个维度，实验规模庞大。
-   **充分性**：实验非常充分。它不仅验证了 Morse 在广泛条件下的通用性（6个基准、9个基线模型），还对其核心设计进行了详尽的消融研究，包括轨迹信息不同成分的作用、不同调度的比例、Dot 模型架构变体等。
-   **客观公平性**：对比客观公平。对比基线（如 DeepCache, PFDiff, AYS）时，采用的是各自论文中报告的结果或严格遵循其官方设置复现；评估指标采用通用的 FID 和 CLIP Score；加速比计算通过插值拟合延迟-性能曲线得出，较为严谨。

### 6. 论文的主要结论与发现

-   **无损加速效果显著**：在 6 个图像生成任务、9 个基线模型上，Morse 取得了平均 1.78 倍到 3.31 倍的**无损**加速，即在相同推理延迟下，FID 指标与原始模型保持一致甚至更好。
-   **通用性强**：Morse 与网络架构、采样器（离散/连续）、生成策略（条件/无条件）正交，作为一个通用插件可广泛加速各类扩散模型。
-   **训练极高效**：通过权重共享和 LoRA 机制，Dot 模型的训练数据量和计算成本远低于从头训练或蒸馏一个完整模型。
-   **可与蒸馏方法互补**：Morse 能进一步加速已被蒸馏的模型（如 LCM-SDXL），证明了其与现有加速方案的兼容和互补性。
-   **核心设计有效**：消融实验证实，利用 Dash 模型的**轨迹信息**对 Dot 模型的残差估计至关重要；`N` 倍速度差和交错的调度策略是实现无损加速的关键。

### 7. 优点

-   **创新性强**：提出了一个全新的“双模型交互”加速范式，利用轻量模型学习残差来弥补跳步信息损失，区别于传统的蒸馏或快采样器路径。
-   **“即插即用”与高效训练**：Dot 模型可直接在任意预训练模型上低成本微调，无需修改原模型架构，部署和训练都很高效。
-   **无损加速**：明确追求并实现了“无损”加速，这在扩散模型加速领域是一个极具吸引力的特性，意味着没有以牺牲生成质量为代价。
-   **实验全面扎实**：在多个维度和高难度任务（如大模型文本到图像生成）上进行了充分验证，并与同期的先进方法进行了对比，结论可靠。

### 8. 不足与局限

-   **引入额外模型依赖**：推理需要同时部署 Dash 和 Dot 两个模型，尽管 Dot 模型轻量，但仍会增加总参数部署量和一定的工程复杂性。
-   **性能上限受 Dash 模型制约**：Morse 的加速效果受限于 Dash 模型本身的质量。若 Dash 模型在极端少步下性能很差，Morse 也难以完全补偿。
-   **调度策略尚可优化**：文中提到 Dot 和 Dash 的采样步调度（如交换步数和顺序）多基于简单启发式规则（如均匀采样），可能存在更优的自适应调度策略来进一步提升效率。
-   **文本到图像的评估粒度**：在 LCM-SDXL 实验部分，因 FID 指标随步数变化不单调，仅使用了 CLIP Score 评估，评估维度不够全面。对于 Stable Diffusion 的评估也指出 FID 与步数非单调关系，评价协议存在一定复杂性。
-   **为训练 Dot 模型仍需成对数据**：尽管所需数据量极小，但其训练过程依然需要从目标数据分布中采样图像，不能做到完全的免训练。

（完）
