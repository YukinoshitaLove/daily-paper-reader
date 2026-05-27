---
title: "CamEdit: Continuous Camera Parameter Control for Photorealistic Image Editing"
title_zh: CamEdit：用于逼真图像编辑的连续相机参数控制
authors: "Xinran Qin, Zhixin Wang, Fan Li, Haoyu Chen, Renjing Pei, Wenbo Li, Xiaochun Cao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2ncMTlR9nC"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于扩散模型的图像编辑，支持连续相机参数控制
tldr: 现有文本驱动图像编辑难以实现连续相机参数控制和平滑过渡。本文提出CamEdit框架，通过连续参数提示机制和参数感知调制模块，在扩散模型中实现光圈、快门速度等参数的连续、语义化操控，生成逼真的编辑效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1353, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 578, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1422, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 1328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ncmtlr9nc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 271, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ncmtlr9nc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ncmtlr9nc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ncmtlr9nc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 691, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ncmtlr9nc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 713, \"height\": 242, \"label\": \"Table\"}]"
motivation: 文本驱动的图像编辑缺乏对相机参数的连续控制。
method: 提出连续参数提示机制和参数感知调制模块，嵌入扩散模型。
result: 实现了对光圈、快门速度等参数的连续、逼真编辑。
conclusion: 该框架使扩散模型能够进行细粒度的相机参数编辑。
---

## Abstract
Recent advances in diffusion models have substantially improved text-driven image editing. However, existing frameworks based on discrete textual tokens struggle to support continuous control over camera parameters and smooth transitions in visual effects. These limitations hinder their applications to realistic, camera-aware, and fine-grained editing tasks. In this paper, we present CamEdit, a diffusion-based framework for photorealistic image editing that enables continuous and semantically meaningful manipulation of common camera parameters such as aperture and shutter speed. CamEdit incorporates a continuous parameter prompting mechanism and a parameter-aware modulation module that guides the model in smoothly adjusting focal plane, aperture, and shutter speed, reflecting the effects of varying camera settings within the diffusion process. To support supervised learning in this setting, we introduce CamEdit50K, a dataset specifically designed for photorealistic image editing with continuous camera parameter settings. It contains over 50k image pairs  combining real and synthetic data with dense camera parameter variations across diverse scenes. Extensive experiments demonstrate that CamEdit enables flexible, consistent, and high-fidelity image editing, achieving state-of-the-art performance in camera-aware visual manipulation and fine-grained photographic control.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有文本驱动的图像编辑方法（如基于扩散模型的 Prompt-to-Prompt、InstructPix2Pix 等）主要关注语义、风格或结构编辑，无法支持**连续相机参数**（如光圈、快门速度、焦平面）的精细操控。传统方法将相机参数编码为离散文本 Token，导致编辑效果不连续、物理不一致，难以满足真实感摄影编辑需求。
- **研究动机**：实际应用中（如摄影后期、虚拟现实、教育场景）需要能够通过文本指令直接、连续地调整光圈大小、景深位置和曝光时间，且输出图像需保持真实感。现有扩散模型虽然具备图像编辑能力，但缺乏对相机参数物理效应的显式建模。
- **整体含义**：本文提出 **CamEdit** 框架，首次在扩散模型中实现**连续的、物理可解释的相机参数控制**，并配套构建了高质量数据集 CamEdit50K，旨在弥合生成模型与真实摄影编辑之间的鸿沟。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
CamEdit 延续 InstructPix2Pix 的指令驱动编辑范式，以 Stable Diffusion 3 为骨干，通过两个关键模块实现连续参数编辑：
1. **连续参数提示（Continuous Parameter Prompting）**：在预训练文本编码器的嵌入空间中，通过插值锚点嵌入来合成任意连续参数对应的文本条件，无需修改编码器。
2. **参数感知调制（Parameter-Aware Modulation, PAM）**：在扩散 Transformer 的每个模块中，根据相机参数对空间特征和通道特征进行自适应调整，从而显式模拟光学效应。

### 2.2 关键技术细节

- **连续参数提示**：
  - 预定义一组离散锚点值（如光圈 f/2、f/2.8、...、f/10），每个锚点对应一个可学习的文本嵌入（通过 CLIP Tokenizer + 编码器得到）。
  - 对于任意连续参数值 \( p \)，其嵌入 \( e_p \) 由相邻锚点嵌入的线性组合加上一个位置相关的残差（由 MLP 预测）构成：
    \[
    e_p = \text{Linear}([e_i, e_{i+1}]) + \text{MLP}(\phi(p))
    \]
    其中 \( \phi(p) \) 是 \( p \) 在区间 \([p_i, p_{i+1}]\) 内的归一化位置。
  - 该嵌入替换提示中的占位符 `<P>`，与原始文本一起输入扩散模型，保持分布一致性。

- **参数感知调制模块**：
  - **几何感知空间调制**：基于输入特征图 \( \mathbf{F} \) 和参数 \( p \)，通过 MLP 预测一个位移场 \( \Delta G \in \mathbb{R}^{2 \times H \times W} \)，对特征坐标进行变形（grid_sample），模拟焦平面导致的景深空间变化。
  - **通道调制**：预测通道级的缩放因子 \( \gamma(p) \) 和偏置 \( \beta(p) \)，对变形后的特征进行调整，模拟快门速度等全局亮度变化：
    \[
    \mathbf{F}_p = \gamma(p) \cdot \mathbf{F}_g + \beta(p)
    \]
  - 调制放置在自注意力层之后，注入到每个 Transformer 块中。

- **训练细节**：
  - 骨干：Stable Diffusion 3，大部分权重冻结；仅更新文本嵌入层（锚点嵌入）和参数调制模块。
  - 使用 LoRA 对 Transformer 进行轻量微调。
  - 优化器：AdamW，学习率 1e-5，分辨率 512×512，batch size 32，训练 50 个 epoch。

## 3. 实验设计

- **数据集**：作者自行构建了 **CamEdit50K** 数据集，包含 50K+ 图像对（输入/目标），覆盖光圈、焦平面、快门速度三种参数的连续变化。数据集由真实照片（含 EXIF 元数据或通过物理估计方法恢复参数）和合成渲染图像（使用可微渲染管线生成，具有真实参数标签）组成，确保多样性、真实感和密集参数标注。
- **Benchmark 与评价指标**：
  - 感知质量：NIQE（越低越好）、MUSIQ（越高越好）。
  - 内容保持：DINO 相似度（越高越好）。
  - 参数控制精度：目标参数与生成图像中估计参数之间的 L1 误差（越低越好）。
- **对比方法**：
  - **扩散编辑模型**：SuperEdit、UltraEdit、In-Context Edit、PhotoGen（相机感知生成模型）；还将 UltraEdit 在 CamEdit50K 上重新训练得到 UltraEdit*。
  - **其他方法**（分任务对比）：
    - 光圈编辑：BokehMe、BRVIT、DrBokeh。
    - 焦平面编辑：BokehMe、MPIB、DrBokeh。
    - 快门速度编辑：SCI、CycleR2R、CLODE。
  - 此外使用 GPT-4o 进行打分，并组织了 15 位摄影专家的用户研究。

## 4. 资源与算力

论文中未明确说明使用的 GPU 型号、数量及总训练时长。仅提到训练在 512×512 分辨率、batch size 32 下进行 50 个 epoch，以及使用 AdamW 优化器。因此无法提供具体的算力开销细节。用户如需复现，需参考作者未来公开的代码和配置。

## 5. 实验数量与充分性

- **定量比较**：表 2(a) 展示了在光圈、焦平面、快门速度三个任务上，CamEdit 与 5 种扩散方法的对比（NIQE、DINO、Error）；表 2(b) 展示与其他非扩散方法的对比（增加了 MUSIQ）。
- **定性比较**：图 6、图 7 展示了多组视觉对比，说明连续性、细节保留和真实感。
- **消融实验**：表 3 对连续参数提示（ConPrompt）、参数感知调制（PAM）进行消融；表 4 对 CamEdit50K 中合成数据与真实数据比例进行消融。图 8 展示了训练稳定性和 T-SNE 可视化。
- **额外评估**：图 5 展示了 GPT-4o 评分和用户研究结果（0–10 分制）。
- **充分性评价**：实验覆盖了三个主要参数任务，对比了多种基线（包括重训练的变体），进行了组件消融和数据消融。但未提供误差棒或统计显著性检验，可能影响结论的稳定性。整体而言实验设计较为全面，结论可信。

## 6. 主要结论与发现

- CamEdit 在所有三项相机参数编辑任务上均显著优于现有扩散编辑模型和传统渲染方法，特别是在参数控制误差上降低 40% 以上（对比 UltraEdit*）。
- 连续参数提示机制相比直接学习参数嵌入，训练更稳定、嵌入语义更对齐，生成质量更高。
- 参数感知调制模块有效改善了深度敏感区域（如前景边缘）的过渡自然性，并提升了全局亮度调整的准确性。
- CamEdit50K 数据集的混合构成（真实 + 合成）对性能至关重要：合成数据提供密集参数标签，真实数据保证视觉真实感，两者互补。

## 7. 优点

- **创新性**：首次在扩散编辑框架中实现连续相机参数控制，提出无需修改文本编码器的连续参数提示方法，思路简洁高效。
- **物理一致性**：参数感知调制模块显式建模光学效应（景深空间变形、全局亮度缩放），使编辑结果符合物理规律。
- **数据集贡献**：CamEdit50K 是首个专为连续相机参数编辑设计的配对数据集，包含真实与合成数据，支持监督学习，可推动后续研究。
- **全面实验**：定量、定性、消融、用户研究多维度评估，对比方法涵盖扩散模型和传统渲染方法，验证了框架的有效性。

## 8. 不足与局限

- **参数覆盖不完整**：仅支持光圈、焦平面、快门速度三种参数，未涵盖 ISO、白平衡、焦距等其他常见相机参数。
- **无法恢复模糊区域的细节**：当输入图像本身存在散焦模糊时，CamEdit 无法“去模糊”恢复锐利细节（即无法从模糊中恢复焦点信息），这属于物理上的固有限制。
- **训练/推理效率**：使用 Stable Diffusion 3 骨干及多个额外模块，计算成本较高，论文未给出具体速度或显存消耗，对资源受限场景不友好。
- **实验统计信息缺失**：主要结果（表 2–4）未报告误差棒或置信区间，消融实验也仅展示单次结果，无法评估随机性带来的波动。
- **数据集依赖**：CamEdit50K 中真实数据的参数估计依赖于多种物理先验（深度估计、模糊测量、ISP 逆映射），这些估计可能存在误差，可能影响训练数据的标签质量。
- **泛化性**：仅在 512×512 分辨率下训练和测试，高分辨率场景（如 4K）的编辑效果和效率未知。

（完）
