---
title: Taming Rectified Flow for Inversion and Editing
title_zh: 驯服整流流用于逆映射与编辑
authors: "Jiangshan Wang, Junfu Pu, Zhongang Qi, Jiayi Guo, Yue Ma, Nisha Huang, Yuxin Chen, Xiu Li, Ying Shan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=uDreZphNky"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出RF-Solver，一种无需训练的提高整流流模型逆映射精度的采样器，用于图像/视频编辑
tldr: 针对整流流扩散模型在生成图像和视频时逆映射不准确的问题，本文提出RF-Solver，通过推导精确的整流流ODE并利用高阶泰勒展开估计非线性分量，显著提升ODE求解精度，从而无需训练即可实现高精度的图像和视频编辑，性能优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 876, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1037, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 761, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1747, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1742, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1755, \"height\": 985, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1746, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 847, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1418, \"height\": 1148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1762, \"height\": 1304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-udrezphnky/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 844, \"height\": 487, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 800, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 871, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-udrezphnky/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 878, \"height\": 519, \"label\": \"Table\"}]"
motivation: 整流流扩散模型逆映射误差大，限制了下游编辑任务的效果。
method: 推导精确ODE并进行高阶泰勒展开，以训练无关采样器提升逆映射精度。
result: 在图像和视频编辑任务中显著提高了逆映射精度和编辑效果。
conclusion: RF-Solver为基于整流流的高保真编辑提供了有效工具。
---

## Abstract
Rectified-flow-based diffusion transformers like FLUX and OpenSora have demonstrated outstanding performance in the field of image and video generation. Despite their robust generative capabilities, these models often struggle with inversion inaccuracies, which could further limit their effectiveness in downstream tasks such as image and video editing. To address this issue, we propose RF-Solver, a novel training-free sampler that effectively enhances inversion precision by mitigating the errors in the ODE-solving process of rectified flow. Specifically, we derive the exact formulation of the rectified flow ODE and apply the high-order Taylor expansion to estimate its nonlinear components, significantly enhancing the precision of ODE solutions at each timestep. Building upon RF-Solver, we further propose RF-Edit, a general feature-sharing-based framework for image and video editing. By incorporating self-attention features from the inversion process into the editing process, RF-Edit effectively preserves the structural information of the source image or video while achieving high-quality editing results. Our approach is compatible with any pre-trained rectified-flow-based models for image and video tasks, requiring no additional training or optimization. Extensive experiments across generation, inversion, and editing tasks in both image and video modalities demonstrate the superiority and versatility of our method. The source code is available at https://github.com/wangjiangshan0725/RF-Solver-Edit.

---

## 论文详细总结（自动生成）

好的，这是对论文《Taming Rectified Flow for Inversion and Editing》的结构化总结。

### 1. 论文的核心问题与整体含义

本论文聚焦于基于整流流（Rectified Flow, RF）的生成模型（如 FLUX 和 OpenSora）在图像和视频编辑下游任务中的性能瓶颈。

*   **研究动机**：尽管 FLUX 等模型在文本到图像/视频（T2I/T2V）的基础生成任务上表现卓越，但它们在**逆映射（Inversion）**任务上存在显著误差。即将真实图像/视频映射回噪声潜空间再重构时，结果与原始输入严重偏离（如物体位置、人物外观改变）。
*   **核心问题**：作者通过分析发现，这种不准确性源于现有模型在求解整流流常微分方程（ODE）时，采用的一阶欧拉方法**精度不足**，导致每个时间步的微小误差累积，最终造成显著的重构失真。
*   **整体含义**：为了解决这一根本性问题，本文旨在**根本性地提升 RF ODE 的求解精度**，并在此基础上构建一个通用、无需训练的框架，以解锁 RF 模型在高质量图像和视频编辑任务上的潜力。

### 2. 论文提出的方法论

论文提出了两个核心方法：用于提升采样和逆映射精度的 **RF-Solver**，以及基于此的编辑框架 **RF-Edit**。

#### RF-Solver：高阶微分方程求解器

核心思想是引入更高阶的数值近似来求解 RF ODE，从而减少单步求解误差。

*   **推导精确 ODE 形式**：作者首先利用常数变易法给出了 RF ODE 的精确积分形式：$\mathbf{Z}_{t_{i-1}} = \mathbf{Z}_{t_i} + \int_{t_i}^{t_{i-1}} v_\theta(\mathbf{Z}_\tau, \tau) d\tau$。
*   **泰勒展开近似非线性项**：对于难以直接积分的神经网络项 $v_\theta$，作者采用 $n$ 阶泰勒展开在 $t_i$ 时刻对其进行估计，从而将积分项转化为可解析计算的高阶项之和。
*   **实用算法（二阶）**：实验发现 $n=2$ 时即可有效平衡性能与开销。其核心采样步更新公式为：
    $\mathbf{Z}_{t_{i-1}} = \mathbf{Z}_{t_i} + (t_{i-1} - t_i)v_\theta(\mathbf{Z}_{t_i}, t_i) + \frac{1}{2}(t_{i-1} - t_i)^2 v^{(1)}_\theta(\mathbf{Z}_{t_i}, t_i)$
    其中，$v^{(1)}_\theta$ 是一阶导数，通过额外进行一次微小的前向步（步长 $\Delta t=0.01$）来计算，具体为 $v^{(1)}_\theta(\mathbf{Z}_{t_i}, t_i) \approx \frac{\hat{v}_{t_i+\Delta t} - \hat{v}_{t_i}}{\Delta t}$。这使得每个时间步的误差从 $O(h_i^2)$ 降低到 $O(h_i^3)$。
*   **逆映射形式**：通过反转上述采样过程，得到同样更高精度的逆映射公式。
*   **通用性**：RF-Solver 是一个即插即用的通用采样器，无需任何额外训练或优化。

#### RF-Edit：基于特征共享的编辑框架

为了解决编辑任务中仅依赖逆映射噪声先验会导致源图结构被过度修改的问题，RF-Edit 引入了自注意力特征共享机制。

*   **核心机制**：在逆映射过程的最后 $n$ 步和最后 $M$ 个 Transformer 块中，提取并存储自注意力层的 **Value (V) 特征**。在去噪编辑阶段，用这些存储的源图 V 特征替换对应时间步和层的 V 特征，从而在执行目标提示词修改的同时，强力保持源图像/视频的结构信息。
*   **针对不同模态的架构适配**：
    *   **图像编辑**：以 FLUX 为骨干，在其**单流块（Single Blocks）**中实施特征共享，因为这些块融合了文本和图像特征。
    *   **视频编辑**：以 OpenSora 为骨干，在其**空间自注意力模块**中实施特征共享，以捕捉并保留源视频的空间结构。

### 3. 实验设计

论文为验证方法的有效性和通用性，设计了覆盖图像和视频两大模态、多项任务的全面实验。

*   **数据集/场景**：
    *   **文生图**：使用 MS-COCO 验证集，随机选择 10,000 张图像及其标题。
    *   **图像逆映射/编辑**：使用 MS-COCO 验证集（逆映射）、DIV2K 数据集及社交媒体收集的真实图像（编辑），利用 GPT-4o 生成或人工精炼提示词。
    *   **视频逆映射/编辑**：使用来自社交媒体的约 40 个视频（逆映射），以及遵循先前工作的视频数据（编辑）。
*   **基准对比方法**：
    *   **文生图**：DPM-Solver++、标准 RF 采样器、Heun 采样器。
    *   **图像编辑**：P2P、DiffEdit、SDEdit、PnP、Pix2Pix、RF-Inversion。
    *   **视频编辑**：FateZero、FLATTEN、COVE、RAVE、Tokenflow。
    *   **底层模型**：主要使用 FLUX（图像）和 OpenSora（视频），也展示了在  HunyuanVideo 上的应用。
*   **评估指标**：
    *   **生成质量**：FID、CLIP Score。
    *   **重构精度**：MSE、LPIPS、SSIM、PSNR。
    *   **编辑质量**：LPIPS（衡量与源图的结构一致性）、CLIP Score（衡量与目标文本的一致性）、VBench 指标（主体一致性、运动平滑度、美学质量、成像质量，用于视频）。

### 4. 资源与算力

论文正文和附录中**未明确提及**所使用 GPU 的型号、数量或具体训练时长。因其方法是**无需训练的**，所有实验均基于预训练模型进行推理，这可能意味着对算力资源的需求主要集中在推理阶段，但文中没有给出具体的开销数据（虽然由于 RF-Solver 每步需要两次前向传播，其单步计算量会翻倍，但作者通过减半总步数来保证函数评估次数 NFE 的公平比较）。

### 5. 实验数量与充分性

论文的实验设计**非常充分且客观**。

*   **实验组数多且覆盖面广**：实验横跨 T2I 生成、图像和视频的逆映射与重建、图像编辑、视频编辑等多个任务。
*   **对比方法全面**：在每个任务上都与多个主流的、具有针对性的基线方法进行了对比，保证了比较的公平性和说服力。
*   **消融实验严谨**：针对 `RF-Solver` 的泰勒展开阶数和 `RF-Edit` 的特征共享步数进行了消融研究，清晰地证明了设计选择的有效性和影响。
*   **公平性考量**：在比较时，作者特别注意保证相同的函数评估次数（NFE），通过为基线方法加倍步数来抵消 `RF-Solver` 每步计算量翻倍的影响，这是一个重要的公平比较设计。

### 6. 论文的主要结论与发现

*   **RF-Solver 能显著提升求解精度**：通过实验定量（重构 MSE 大幅降低）和定性（图 2 中的误差曲线）证明了其能有效减少 ODE 求解过程中的误差累积。
*   **RF-Solver 在多个任务上表现更优**：
    *   在基础文生图任务上，超越了标准 RF 和 Heun 采样器，生成质量更高。
    *   在逆映射和重构任务上，精度远超现有方法。
*   **RF-Edit 实现了高质量编辑**：结合 RF-Solver 和特征共享后，RF-Edit 在图像和视频编辑任务上，既能忠实执行编辑指令（高 CLIP Score），又能很好地保持源内容结构，整体性能优于多种现有 SOTA 方法。

### 7. 优点

*   **方法优雅且根本**：从数学上推导出精确的 ODE 形式，并使用泰勒展开来系统性地提升精度，这是一个非常扎实和本质的解法，而非简单的工程修补。
*   **无需训练，通用性强**：作为一个即插即用的采样器，`RF-Solver` 可以无缝应用于任何预训练的 RF 模型（如 FLUX、OpenSora、HunyuanVideo），极大地降低了使用门槛和计算成本。
*   **分析深刻**：通过跟踪和可视化逆映射-重构过程中的潜变量 MSE，直观地揭示了误差累积问题是导致失败的关键，为后续研究提供了洞察。
*   **公平的实验设计**：通过控制 NFE 来比较不同阶数的采样器，保证了对比的公平性。
*   **首个探索者**：在 RF 模型上系统性地探索和解决了视频编辑这一复杂任务。

### 8. 不足与局限

*   **额外计算开销**：`RF-Solver` 的每步需要两次神经网络前向传播来计算导数，虽然通过减少总步数保持了 NFE 一致，但这种“以深度换广度”的策略是否在所有场景下都最优，以及额外的特征存储和替换操作的显存开销，文中未做详细分析。
*   **超参数敏感性**：`RF-Edit` 的特征共享步数和层数对编辑结果影响较大（如图 7 所示），其最优值可能因图像而异，实际使用中可能仍需手动调整。
*   **局限性讨论不充分**：论文主要展示了成功案例，对失败情况或方法的局限性讨论较少。例如，对于结构变化极大的编辑（如大幅度改变视角），特征共享机制是否会限制编辑的多样性，文中未深入探讨。
*   **资源消耗未量化**：如前所述，缺少对推理阶段显存占用、延迟等资源消耗指标的定量报告。

（完）
