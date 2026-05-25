---
title: Reliable Image Quality Evaluation and Mitigation of Quality Bias in Generative Models
title_zh: 可靠的图像质量评估与生成模型质量偏差缓解
authors: "Hoin Jung, Shenyu Lu, De Wang, Xiaoqian Wang"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=zC0ZxjXixH"
tags: ["query:real-ir"]
score: 8.0
evidence: 评估并缓解图像生成模型的质量偏差
tldr: 本文指出常用FID指标在跨人口群体评估生成图像质量时存在偏差，提出DQA分数来量化现有指标的可靠性，并设计了缓解生成质量差异的方法。实验表明该方法能有效评估并改善生成模型的公平性。DQA为生成模型评估提供了更全面的视角，有助于构建更公平的生成系统。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 838, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1777, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 594, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1039, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1520, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1657, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1385, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1769, \"height\": 1184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1778, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zc0zxjxixh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1585, \"height\": 2124, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zc0zxjxixh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1789, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zc0zxjxixh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1652, \"height\": 277, \"label\": \"Table\"}]"
motivation: FID得分在评估不同群体时引入非预期偏差。
method: 提出DQA分数量化指标可靠性，并缓解质量差异。
result: 有效评估并改善了跨群体的生成质量公平性。
conclusion: 为生成模型公平性评估提供了新工具。
---

## Abstract
Discrepancies in generation quality across demographic groups pose a substantial and critical challenge in image generative models. However, the Fréchet Inception Distance (FID) score, which is widely used as an image quality evaluation metric for generative models, introduces unintended bias when assessing quality across sensitive attributes. This undermines the reliability of the evaluation procedure. This paper addresses this limitation by introducing the Difference in Quality Assessment (DQA) score, a novel approach that quantifies the reliability of existing evaluation metrics, e.g. FID. DQA assesses discrepancies in evaluated quality across demographic groups under strictly controlled conditions to effectively gauge metric reliability. Our findings reveal that traditional quality evaluation metrics can yield biased assessments across groups due to inappropriate reference set selection and inherent biases in image encoder in FID. Furthermore, we propose DQA-Guidance within diffusion model sampling to reduce quality disparities across groups. Experimental results demonstrate the utility of the DQA score in identifying biased evaluation metrics and present effective strategies to mitigate these biases. This work contributes to the development of reliable and fair evaluation metrics for generative models and provides actionable methods to address quality disparities in image generation across groups.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式、用中文对给定的论文《Reliable Image Quality Evaluation and Mitigation of Quality Bias in Generative Models》进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机**：
    *   图像生成模型（如扩散模型）在不同人口统计群体（如性别、种族）之间存在生成**质量差异**，例如生成“女护士”图像的质量可能普遍高于“男护士”，这是一个关键但研究不足的公平性问题。
    *   这种质量偏差会负面影响下游任务，例如在用生成图像做数据增强时，会加剧分类器在不同群体间的性能不公平性。
*   **核心问题**：
    *   广泛用于评估生成图像质量的 **FID（Fréchet Inception Distance）指标**在评估这种偏差时**不可靠**。其不可靠性来源于两方面：
        1.  **参考集选择不当**：使用合并的参考集（所有群体混合）而非特定群体的参考集会掩盖或放大偏差。
        2.  **图像编码器固有偏差**：FID 使用的 InceptionV3 等编码器会不均匀地处理不同群体的图像特征，即使质量相似，其嵌入表示和距离度量也会产生不一致。
*   **研究目标**：
    1.  （**Q1**）如何量化评估指标在衡量质量偏差时的可靠性？
    2.  （**Q2**）如何有效缓解生成模型的质量偏差？

### 2. 论文提出的方法论

*   **核心方法：差异质量评估 (Difference in Quality Assessment, DQA) 分数**
    *   **思想**：DQA 是一个**可靠性分数**，用于量化一个图像编码器在特定评价指标（如 MMD, FD）下，对不同群体进行质量评估时产生的偏差程度。DQA 值越低，代表该编码器越可靠、越公平。
    *   **公式与流程**：
        1.  **可控数据集构建**：通过调整扩散模型采样参数（如减少步数、增强噪声），生成同一图像种子下从“高质量”到“低质量”的**六种受控退化版本**。
        2.  **群体特定测量**：为解决 FID 参考集选择不当的问题，公式采用**群体特定**的距离度量。即，群体 A 的生成集质量 = 距离(编码器(A_gen), 编码器(A_ref))。
        3.  **DQA 公式**：
            DQA = | 距离(A_gen, A_ref) - 距离(B_gen, B_ref) | / 距离(I_gen, I_ref)
            其中 I_gen 和 I_ref 是合并的生成集和参考集。
            *   **分子**：衡量两个群体生成质量的**绝对差异**，直接反应评估偏见。
            *   **分母**：衡量**整体生成质量**，用于归一化，使 DQA 能跨不同退化水平比较。
        4.  **多属性扩展 (AvgDQA)**：对于不止两个群体（如多种族），计算所有群体对 DQA 的平均值。
*   **应用 I：寻找可靠编码器**
    *   使用构建的可控数据集，计算不同预训练图像编码器的 DQA 分数，以识别出最公平、最可靠的编码器。实验发现，*自监督学习 + ResNet-50 架构*（如 DINO-RN50）效果最佳。
*   **应用 II：DQA 引导的扩散模型采样 (DQA-Guidance)**
    *   **思想**：将 DQA 作为一个**能量函数**，将其梯度整合到扩散模型的采样过程中，引导模型生成质量更公平的图像，**无需重新训练**。
    *   **技术与公式**：
        *   在每个去噪时间步 `t`，修改噪声预测 `ε_θ(z_t)`，加入 DQA 的梯度项：
            `ε̃_θ(z_t) = ε_θ(z_t) + σ_t * ∇z_t [ λ1 * DQA(A, B) + λ2 * 距离(I_gen, I_ref) ]`
        *   `λ1` 控制**公平性引导**的强度，该项旨在缩小不同群体间的质量差距。
        *   `λ2` 控制**质量正则化**的强度，该项通过最小化生成集与参考集间的整体距离来**维持或提升图像保真度**，防止因过度追求公平而牺牲质量。
        *   `z_t = [z^A_t; z^B_t]` 是时间步 `t` 时两个群体的联合潜在变量。

### 3. 实验设计

*   **DQA 评估数据集与场景**：
    *   **基准/参考集（T1）**：使用 Stable Diffusion XL (SDXL) 按推荐设置生成的高质量图像。
    *   **退化生成集（T2-T6）**：通过调整 SDXL 的文本引导强度、扩散步数、噪声强度和是否使用细化器等参数，模拟五种不同严重程度的图像质量退化场景。
    *   **数据规模**：包含 10 种职业、2 种性别、4 种种族的组合，每种组合、每种场景下生成 250 张图像，共计 20,000 张/场景。
*   **验证 DQA 有效性的下游任务**：
    *   **任务**：胸部 X 光片 (ChestX-ray14) 的多标签分类任务。
    *   **模型**：使用 ResNet-50 作为分类器。
    *   **数据增强对比**：
        *   **Baseline**：不使用任何生成图像增强。
        *   **全量增强**：使用所有生成的医学图像进行增强。
        *   **公平子集增强**：使用由可靠编码器（低 DQA）筛选出的质量公平的生成图像子集（算法 1 基于影响力函数采样）。
        *   **不公平子集增强**：使用由可靠编码器（高 DQA）筛选出的质量不公平的生成图像子集。
    *   **评估指标**：整体 AUC，以及不同性别间的 AUC 平均差异 (Avg(ΔAUC)) 和最大差异 (max(ΔAUC))，以衡量分类公平性。
*   **缓解质量偏差实验 (DQA-Guidance)**：
    *   **模型**：Stable Diffusion 和 ImageGen（用于医学图像）。
    *   **对比基线**：无引导的原始扩散模型采样 (`λ1=0`)。
    *   **消融实验**：
        *   变化 `λ1` 观察对质量公平性和整体质量的影响。
        *   变化 `λ2` 观察其对维持整体质量的贡献。
    *   **评估指标**：使用可靠的编码器（如 DINO-RN50）测量到的各群体生成质量（MMD），及其平均和最大质量差距。

### 4. 资源与算力

*   **论文中未明确说明**所使用的 GPU 型号、数量及具体训练时长。文中提及的模型（如 SDXL, Stable Diffusion, ImageGen）和编码器均为引用或使用现有预训练模型。提出的 DQA-Guidance 是一种免训练的采样方法，因此其计算开销主要体现在扩散模型的正常采样过程加上梯度计算，但文中未进行具体算力分析。

### 5. 实验数量与充分性

*   **实验数量充足且多样**，主要分为以下几组：
    1.  **DQA 编码器可靠性分析**：对比了不同架构 (CNN, ViT)、不同预训练方案 (监督、自监督如 DINO、MoCo, CLIP)、不同数据集 (ImageNet-1K, 21K) 的 10 余种编码器在多种退化类型下的 DQA 分数，分析透彻。
    2.  **DQA 有效性验证**：通过医疗影像分类的下游任务，对比了 Baseline、全量增强、DQA 公平/不公平子集增强等 4 种策略，证明了 DQA 能有效筛选出提升公平性的数据。
    3.  **DQA-Guidance 有效性验证**：在人类图像 (Stable Diffusion) 和医学图像 (ImageGen) 两个域上进行了实验，并对关键超参数 `λ1` 和 `λ2` 进行了消融研究。
    4.  **DQA 框架延展性验证**：将 DQA 的概念成功应用于其他类型的质量评估方法，如 VQA 模型 (BLIP, PaliGemma) 和 IQA 模型 (TOPIQ)。
*   **实验设计客观且公平**：
    *   **控制变量**：通过完全控制生成图像的退化过程来构建评估集，排除了非质量因素的干扰。
    *   **纠正 FID 偏差**：通过理论和合成数据，明确指出并纠正了先前工作中使用合并参考集导致的评估错误。
    *   **多维度评估**：不仅使用距离度量（MMD），还结合了下游分类任务的真实性能来交叉验证。
    *   **对比全面**：涵盖了从基础编码器选择到最终生成效果的全链路对比。

### 6. 论文的主要结论与发现

1.  **FID 不可靠**：传统的 FID 指标因不恰当的参考集选择和编码器偏差，无法可靠评估生成模型在不同群体间的质量公平性。
2.  **DQA 有效**：提出的 DQA 分数能够有效量化评估指标的可靠性。低 DQA 值对应更公平的编码器。
3.  **可靠编码器特征**：基于自监督学习（特别是 DINO）训练、且使用 ResNet-50 架构的编码器，在跨群体的质量评估中表现出最低的偏差和最高的可靠性。更大的训练数据集（如 IN-21K）和 CLIP 对比学习不一定保证更好的公平性。
4.  **DQA 的下游价值**：通过 DQA 筛选出的公平生成数据进行数据增强，能在不引入任何显式公平性约束的情况下，有效提升下游分类器的公平性。
5.  **DQA-Guidance 有效**：作为一种免训练的方法，DQA-Guidance 在扩散模型采样阶段能够同时**减少质量差距**（`λ1` 的作用）并**提升或维持整体生成质量**（`λ2` 的作用），实现了更公平、更高质的图像生成。

### 7. 优点

*   **问题洞察深刻**：深刻揭示了被广泛使用的 FID 指标在公平性评估场景下的根本缺陷，将质量评估的可靠性问题提升到了方法论层面。
*   **创新性与完整性**：提出了一个从**评估（DQA）到缓解（DQA-Guidance）** 的完整、统一框架，逻辑链条清晰。
*   **方法普适性强**：
    *   DQA 作为元评估指标，可以评估任何基于分布距离的图像质量评估管线和编码器。
    *   DQA 的框架被成功拓展到 VQA 和 IQA 领域，证明了其思想的通用性。
    *   DQA-Guidance 是一种**免训练**即插即用的方法，实用性强。
*   **实验扎实，说服力强**：
    *   使用**严格受控**的图像退化环境来验证编码器偏见，排除了混淆变量，实验设计精巧。
    *   结合下游任务的真实表现来验证 DQA 的效用，评估维度全面，结果具有实践指导意义。

### 8. 不足与局限

*   **DQA 对参考集质量的依赖**：DQA 的计算依赖于一个“高质量”的群体特定参考集 `A_ref`。如果参考集本身存在未被发现的偏差，DQA 的可靠性评估将受到影响。论文虽未强调，但这是一个潜在风险。
*   **群体划分的简化**：实验中将人口统计属性（如性别、种族）视为独立且明确的二分类或多分类变量。然而，现实世界中的人是这些属性的交叉体，论文未深入探讨**交叉性偏差**（如黑人女性 vs 白人男性）。
*   **DQA-Guidance 的计算开销**：尽管免训练，但在采样每一步都需要计算 DQA 及其梯度，特别是当群体和样本数量增加时，这会显著增加推理时间和计算成本。论文没有将此开销与原始采样过程进行量化对比。
*   **引导强度的权衡**：实验表明，增大 `λ1` 虽然促进公平，但过大会引入噪声、降低质量，需要小心调参。这个超参数的鲁棒性和在不同模型、数据上的通用性有待进一步检验。
*   **质量偏差的定义**：论文主要从分布距离的角度定义质量，而未充分考虑人类感知层面的质量偏差（如对某群体生成不自然的面部细节，但分布差异不大）。拓展的 VQA 和 IQA 评估部分回应了这个问题，但其本身仍依赖于这些模型的公平性。

（完）
