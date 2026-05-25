---
title: "DragLoRA: Online Optimization of LoRA Adapters for Drag-based Image Editing in Diffusion Model"
title_zh: DragLoRA：面向扩散模型中拖拽式图像编辑的 LoRA 适配器在线优化
authors: "Siwei Xia, Li Sun, Tiantian Sun, Qingli Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=b74kufhhsk"
tags: ["query:real-ir"]
score: 9.0
evidence: 扩散模型中的拖拽式图像编辑
tldr: DragLoRA 将 LoRA 适配器集成到基于扩散模型的拖拽式编辑中，通过引入辅助训练机制增强运动监督的表示能力，解决了传统方法因特征表示不足导致的精度受限和点跟踪搜索空间过大引起的效率低下问题。实验表明，该方法在编辑精度和速度上均有提升，为交互式图像编辑提供了更实用的技术方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1759, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1672, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 755, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1749, \"height\": 1808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1747, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1031, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1546, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b74kufhhsk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1400, \"height\": 894, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 974, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1762, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 702, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 833, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 517, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b74kufhhsk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 990, \"height\": 263, \"label\": \"Table\"}]"
motivation: 传统拖拽式扩散编辑方法面临运动监督精度不足和点跟踪效率低的挑战。
method: 提出 DragLoRA，将低秩适配器融入拖拽编辑流程，并引入辅助训练增强适配器训练。
result: 显著提升了拖拽编辑的精度与效率，实现了更准确的前景物体操控。
conclusion: DragLoRA 为基于扩散模型的交互式图像编辑提供了更精确和高效的解决方案。
---

## Abstract
Drag-based editing within pretrained diffusion model provides a precise and flexible way to manipulate foreground objects. Traditional methods optimize the input feature obtained from DDIM inversion directly, adjusting them iteratively to guide handle points towards target locations. However, these approaches often suffer from limited accuracy due to the low representation ability of the feature in motion supervision, as well as inefficiencies caused by the large search space required for point tracking. To address these limitations, we present DragLoRA, a novel framework that integrates LoRA (Low-Rank Adaptation) adapters into the drag-based editing pipeline. To enhance the training of LoRA adapters, we introduce an additional denoising score distillation loss which regularizes the online model by aligning its output with that of the original model. Additionally, we improve the consistency of motion supervision by adapting the input features using the updated LoRA, giving a more stable and accurate input feature for subsequent operations. Building on this, we design an adaptive optimization scheme that dynamically toggles between two modes, prioritizing efficiency without compromising precision. Extensive experiments demonstrate that DragLoRA significantly enhances the control precision and computational efficiency for drag-based image editing. The Codes of DragLoRA are available at: https://github.com/Sylvie-X/DragLoRA.

---

## 论文详细总结（自动生成）

好的，我将根据您提供的论文文本，以资深学术论文分析助手的身份，为您生成一份结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：基于扩散模型的拖拽式图像编辑允许用户通过指定“控制点”和“目标点”来直观地操控图像中的物体。传统方法通常直接优化由 DDIM 反演得到的输入潜在特征，以实现运动监督和点追踪。
*   **核心问题**：传统方法存在两大局限：
    *   **精度不足**：在运动监督阶段，被优化的输入潜在特征的表征能力有限，导致变形不够精确。
    *   **效率低下**：点追踪需要在较大的特征空间内进行搜索，计算成本高昂。
*   **研究动机与整体含义**：本文旨在解决上述精度和效率问题，提出了一种名为 DragLoRA 的新框架，通过将可动态优化的 LoRA 适配器集成到预训练的扩散模型中，替代传统的直接优化潜在特征的方式，从而增强模型的变形能力并提升编辑效率。

### 2. 论文提出的方法论

DragLoRA 的核心思想是将编辑控制从静态的潜在特征中解耦，转而通过在线学习 LoRA 适配器的参数来实现。其关键技术包括：

*   **核心思想：动态 LoRA 优化**
    *   不再直接优化 DDIM 反演的潜在特征 $z_{35}$，而是通过反向传播运动监督损失来更新集成在 U-Net 注意力层中的 LoRA 参数 ($\Delta\theta$)。这扩展了优化空间，使变形控制更精细。
*   **关键技术细节**
    *   **双目标优化 (DOO)**：为了解决单纯用拖拽损失 ($L_{drag}$) 优化 LoRA 会导致模型偏离原始生成能力的问题，引入了一个额外的**去噪分数蒸馏损失 ($L_{DDS}$)** 作为正则化项。该损失通过比较原始 U-Net 和 LoRA 增强的 U-Net 对被扰动特征的噪声预测，约束 LoRA 模型不偏离原始模型太远，从而保持图像保真度。
    *   **输入潜在特征自适应 (ILFA)**：设计了一个“去噪-再加噪”的循环过程。在每一步，输入的潜在特征 $z_t$ 先使用 DragLoRA 去噪一步得到 $z_{t-1}$，再加入随机高斯噪声回到 $z_t$。这个循环能将控制点的位移信息累积并传递到潜在特征空间中，使特征与 LoRA 学到的变形轨迹保持一致，即使在停止更新 LoRA 后，仅靠特征自适应也能驱动控制点移动。
    *   **自适应优化方案 (ASS)**：动态切换两种模式以平衡效率和精度：
        1.  **DOO + ILFA 模式**：当点追踪质量不佳（如出现遮挡或纹理模糊）时，同时进行 LoRA 优化和输入特征自适应。
        2.  **ILFA-Only 模式**：当点追踪质量足够高（`minD`值小且追踪点接近预期位置）时，暂停 LoRA 的梯度更新，仅使用输入特征自适应来驱动控制点，从而避免冗余计算，大幅提升效率。
    *   **高效点追踪 (EPT)**：通过缩小搜索区域（如采用“距离更近”或“角度更近”的候选区域，而非传统的邻域搜索）来加速点追踪过程，减少计算量。

### 3. 实验设计

*   **数据集/场景**：实验主要在三个公开的拖拽式编辑基准上进行：
    *   **DragBench**
    *   **Drag100**
    *   **VITON-HD** (虚拟试衣)
    *   同时使用了**私有数据集**。
*   **基准方法与对比对象**：DragLoRA 与众多当前最优的拖拽式编辑方法进行了比较，覆盖了不同类型：
    *   **基于优化的方法 (Optim-based)**：DragDiffusion, DragNoise, StableDrag, EasyDrag, GoodDrag, FreeDrag, DragText, AdaptiveDrag, ClipDrag, GDrag。
    *   **基于编码器的方法 (Enc-based)**：InstantDrag, LightningDrag。
    *   **免训练的方法 (TrFree)**：SDE-Drag, FastDrag。
*   **评价指标**
    *   **图像保真度**：1-LPIPS (与原始图像的感知相似度), CLIP score (在逆向编辑任务“Drag-Back”中评估特征一致性)。
    *   **编辑精度**：MD (Mean Distance，编辑后控制点与目标点的平均距离)。论文还提出了改进的 **m-MD (masked-MD)**，将搜索范围限制在编辑区域内，以减少 DIFT 在整个图像中搜索带来的误差。

### 4. 资源与算力

*   **GPU 型号与数量**：所有 DragLoRA 实验均在一块 **NVIDIA RTX 4090 GPU** 上完成。
*   **训练时长**：论文提到，为单张图像预训练重建 LoRA (RecLoRA) 需 80 步，耗时约 **48 秒**，但此过程可离线完成且参数可复用。在线编辑过程的耗时见表1，DragLoRA 的编辑时间为 **29.84 秒**，而 Fast 版本则缩短至 **22.89 秒**。
*   **特殊说明**：对比方法 EasyDrag 因资源需求更大，单独在一台 NVIDIA A40 GPU 上评估。

### 5. 实验数量与充分性

*   **实验组数**：实验数量充足，涵盖了定性、定量和消融研究。
    *   **定性分析**：展示了 DragLoRA 与 DragDiffusion, DragNoise, GoodDrag 等在 DragBench 等数据集上的可视化对比（Figure 1, 4, 5, 6）。
    *   **定量分析**：在 DragBench 上与 14 种不同方法进行了详细的指标对比（Table 1）。此外，还进行了独特的“Drag-Back”逆向编辑评估（Figure 5, Table 2）。
    *   **消融实验**：通过逐步添加 DOO, ILFA, EPT, ASS 模块，系统地验证了每个组件对 LPIPS 和 MD 指标的贡献（Table 3）。并分析了 ILFA 中不同加噪策略（DDIM vs. DDPM）的影响（Table 4）和 EPT 中不同搜索区域（Table 5）的性能。
*   **充分性与客观性**：实验设计较为充分和客观。作者不仅与大量现有工作进行了公平对比（使用相同的基准和指标），还提出了改进的 m-MD 指标来缓解现有评估指标的潜在问题。消融实验清晰地揭示了各模块的有效性，增强了结果的可靠性。

### 6. 论文的主要结论与发现

*   DragLoRA 通过在线优化 LoRA 适配器替代传统的潜在特征优化，能有效实现更精细、更精确的拖拽式图像编辑。
*   提出的双目标优化 ($L_{drag}$ + $L_{DDS}$) 在实现精准变形的同时，成功保留了原图的语义保真度，解决了 LoRA 的无限制微调带来的不稳定性。
*   输入潜在特征自适应 (ILFA) 和自适应优化方案 (ASS) 的协同工作，能够在保证编辑精度的前提下，显著减少不必要的梯度更新，从而大幅提升编辑效率（在优化类方法中耗时最低）。
*   高效点追踪策略 (EPT) 通过缩小搜索范围，进一步提升了编辑过程的效率。
*   综合来看，DragLoRA 在编辑精度和计算效率两方面都达到了当前最优水平。

### 7. 优点

*   **创新性强**：首次将动态 LoRA 微调引入拖拽式编辑框架，将优化对象从数据（潜在特征）转变为模型（适配器参数），思想新颖。
*   **问题解决导向明确**：精准地指出了传统方法“精度”和“效率”两大痛点，并针对性地提出了 DOO 和 ASS 等解决方案，逻辑清晰。
*   **效率提升显著**：通过 ILFA 和 ASS 的巧妙设计，在保证甚至提升编辑质量的同时，大幅降低了时间成本，具有很高的实用价值。
*   **评估全面**：不仅包含常规的定量和定性对比，还引入了“Drag-Back”评估和消融研究，并对现有评价指标（MD）的缺陷进行了分析和改进（提出 m-MD），体现了严谨的科学态度。

### 8. 不足与局限

*   **评估指标依赖性**：论文本身指出，LPIPS 在编辑幅度大时会失效，而 MD 因 DIFT 搜索全局可能不准确。虽然提出了 m-MD，但作者承认其在图像失真情况下可能虚高，表明量化评估仍存在挑战。
*   **未进行用户调研**：作者明确指出，鉴于量化指标不够直接和精确，未来计划进行用户调研。缺少主观评价是目前的一个局限。
*   **挑战性案例处理不佳**：论文承认在一些高难度案例中表现不佳，如“将遮挡面部的相机移开”这类需要复杂内容生成的场景，效果和其他方法一样不理想。
*   **超参数敏感性**：方法中包含了多个阈值（如 $l_2, d_1, d_2$）用于模式切换和点追踪控制，其在不同数据分布下的鲁棒性可能需要进一步验证，文中未对此进行敏感性分析。

（完）
