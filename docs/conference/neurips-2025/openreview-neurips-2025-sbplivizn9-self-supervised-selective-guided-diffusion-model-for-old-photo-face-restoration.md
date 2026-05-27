---
title: Self-Supervised Selective-Guided Diffusion Model for Old-Photo Face Restoration
title_zh: 自监督选择性引导扩散模型用于老照片人脸修复
authors: "Wenjie Li, Xiangyi Wang, Heng Guo, Guangwei Gao, Zhanyu Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sbPlIVIZN9"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于自监督选择性引导扩散模型的老照片人脸修复
tldr: 针对老照片人脸修复中复合退化（破损、褪色、模糊）和现有扩散方法依赖显式退化先验或全局统计引导的局限性，本文提出自监督选择性引导扩散模型（SSDiff）。该方法利用预训练扩散模型在弱引导下生成伪参考人脸，通过分阶段监督——在去噪全过程中施加结构引导，在后期步骤进行颜色细化——实现区域特定的恢复。实验表明，该方法在恢复细节和色彩方面优于现有方法，解决了局部伪影问题。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 660, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1422, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1421, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 800, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 945, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1427, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1426, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1438, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1434, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1339, \"height\": 2350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1340, \"height\": 2352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1341, \"height\": 2345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sbplivizn9/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1340, \"height\": 2343, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 916, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 634, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 635, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 564, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 512, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 490, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 396, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sbplivizn9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 790, \"height\": 122, \"label\": \"Table\"}]"
motivation: 老照片人脸退化复杂，现有扩散方法难以处理局部伪影和颜色问题。
method: 提出SSDiff，利用伪参考人脸进行分阶段的结构和颜色引导，无需显式退化先验。
result: 在多种退化老照片上实现了更自然、更精确的恢复效果。
conclusion: 自监督选择性引导有效提升了扩散模型在复杂退化图像修复中的性能。
---

## Abstract
Old-photo face restoration poses significant challenges due to compounded degradations such as breakage, fading, and severe blur. Existing pre-trained diffusion-guided methods either rely on explicit degradation priors or global statistical guidance, which struggle with localized artifacts or face color. We propose Self-Supervised Selective-Guided Diffusion (SSDiff), which leverages pseudo-reference faces generated by a pre-trained diffusion model under weak guidance. These pseudo-labels exhibit structurally aligned contours and natural colors, enabling region-specific restoration via staged supervision: structural guidance applied throughout the denoising process and color refinement in later steps, aligned with the coarse-to-fine nature of diffusion. By incorporating face parsing maps and scratch masks, our method selectively restores breakage regions while avoiding identity mismatch. We further construct VintageFace, a 300-image benchmark of real old face photos with varying degradation levels. SSDiff outperforms existing GAN-based and diffusion-based methods in perceptual quality, fidelity, and regional controllability. Code link: https://github.com/PRIS-CV/SSDiff.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：老照片人脸修复面临复合退化（破损、褪色、严重模糊），现有方法（如GAN-based和扩散方法）在处理这些复杂退化时存在局限：依赖显式退化先验或全局统计引导，难以处理局部伪影和不自然的肤色。
- **动机**：预训练扩散模型在弱引导下生成的人脸图像虽然偏离原身份，但具有相似的轮廓、自然的颜色和良好的破损区域修复能力。利用这些伪参考图像进行自监督引导，可以避免显式建模退化，同时实现区域选择性恢复。
- **意义**：提出一种无需训练的零样本方法，特别针对老照片人脸，能同时恢复结构、颜色和破损区域，并在真实老照片基准上取得领先性能。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：自监督选择性引导扩散（SSDiff）。利用预训练扩散模型在弱引导（小梯度尺度）下生成伪参考人脸，这些伪参考具有良好轮廓和自然色彩，但身份特征（如眼睛、嘴巴）与输入不一致。通过分阶段选择性地引导去噪过程：早期（前600步）施加结构恢复和破损区域平滑引导，后期（后400步）施加肤色颜色细化引导，避免干扰身份敏感区域。
- **关键技术细节**：
  - **弱引导生成伪标签**：对输入低质量图施加小梯度尺度 \(s_w=1e-3\)，获得伪参考 \(y_p\)。
  - **选择性恢复引导**：使用预训练的人脸解析网络和划痕检测网络获得掩码 \(M\) 和解析图 \(P\)。对非破损区域（\(y_c\)）施加L1损失 \(\|(1-M)\odot (y_c-\hat{x}_c)\|_2^2\)；对破损区域中的非敏感区域（背景、皮肤、头发）施加边缘梯度平滑损失L2，确保填充自然。
  - **选择性着色引导**：在后期阶段（t<T1），将伪参考的颜色通过风格迁移网络转移到当前中间结果，再对皮肤区域施加L3损失 \(\|y_s-\hat{x}_s\|_2^2\)，避免影响已稳定的身份特征。
  - **阶段划分**：T1=400步（总步数1000）。早期仅L1+L2，后期加入L3。
  - **强引导尺度**：恢复过程使用强梯度 \(s_s=3.5e-3\)。
- **算法流程**（文字说明）：
  1. 从输入图像提取人脸解析图P和刮痕掩码M。
  2. 使用弱引导生成伪标签 \(y_p\)，并从中提取非破损区域 \(y_c\)、破损指导区域 \(y_n\)、皮肤区域 \(\hat{y}_p\)。
  3. 从噪声开始反向扩散：
     - 每个时间步计算当前中间估计 \(\hat{x}_t\)。
     - 若 \(t > T1\)：计算 \(L = L1 + L2\)，利用梯度更新去噪步骤（结构恢复）。
     - 若 \(t \le T1\)：额外计算 \(\hat{x}_s\)（皮肤区域），对伪标签皮肤进行风格迁移得到 \(y_s\)，计算 \(L3\)，总损失 \(L = L1 + L2 + L3\)（加入颜色细化）。
     - 使用强梯度 \(s_s\) 和方差调整均值。
  4. 迭代T步得到最终高质人脸。

## 3. 实验设计
- **数据集/场景**：
  - **VintageFace**：作者自建的真实老照片基准，包含300张图像，按退化程度分为简单、中等、困难各100张。
  - **WebPhoto-Test**和**CelebA-Child**：两个经典的盲人脸修复基准，也包含部分老照片。
  - 还单独测试了无破损和大幅破损图像、不同姿势、戴眼镜等场景。
- **对比方法**：
  - GAN-based：BOPB（专门老照片）、CodeFormer、GPEN等。
  - 学习型扩散：DifFace、DiffBIR、ResShift等。
  - 零样本扩散：DDNM、PGDiff。
- **评估指标**：FID、BRISQUE、TOPIQ、MAN-IQA（无参考指标），以及CLIP身份距离（用于保真度）。
- **实验充分性**：在三个退化级别上定量对比所有方法；提供大量定性对比（多个图）；消融实验包括：自监督策略有无、三个损失项（L1/L2/L3）的贡献、阶段切换点T1、弱/强引导尺度影响、引导区域选择（皮肤 vs 全脸、颜色迁移 vs 引导）、对预训练网络鲁棒性测试（解析图、刮痕掩码、风格迁移扰动）、计算成本对比。整体实验覆盖全面，客观公平。

## 4. 资源与算力
- 论文明确：所有实验在PyTorch框架下，使用**单块NVIDIA RTX 4090 GPU**实现。
- 由于方法无需训练（training-free），未提及训练时长。单张图像平均推理延迟为95 ms（四个组件在线执行）或24 ms（预处理后），相比PGDiff的10s有显著优势。
- 参数量和FLOPs：SSDiff仅45.4M参数和120.7G FLOPs，远小于DiffBIR等。

## 5. 实验数量与充分性
- **实验组数**：定量对比（三个退化等级×7种方法）21组；额外两个公开基准（WebPhoto-Test、CelebA-Child）各7组；消融实验：自监督策略（2种）、三个损失项（4种）、T1选择（6种）、强弱引导尺度（多种组合）、指导区域比较（多组）、对预训练网络鲁棒性测试（3组扰动×3种网络）、计算成本对比（4种方法）。定性图大量（附录中约20张）。
- **充分性判断**：实验设计较为全面，涵盖了方法核心组件的验证、与SOTA的对比、泛化性测试、鲁棒性分析、效率分析。所有对比均使用相同预处理和评估协议，结果客观公平。但未提供用户研究（已声明使用无参考指标，因为真实老照片无GT），符合领域惯例。

## 6. 主要结论与发现
- SSDiff在所有三个退化级别上均优于现有GAN和扩散方法，尤其在FID、TOPIQ、MAN-IQA等感知质量指标上领先。
- 自监督伪参考引导策略显著提升恢复质量（移除后FID从128.3升至145.7）。
- 阶段划分和区域选择性引导至关重要：L1保证非破损区域保真，L2促进破损区域平滑，L3实现自然肤色；过早开始颜色引导会损害身份。
- 方法对预训练网络（解析、检测、风格迁移）的误差具有鲁棒性。
- 在无破损和大幅破损图像上均表现稳健，还可进行区域特定的风格化恢复（如改变唇色、发色）。
- 计算成本低，适合实际应用。

## 7. 优点
- **无需训练**：利用预训练扩散模型的生成能力，通过零样本引导适应新任务，无训练成本。
- **自监督伪参考**：巧妙利用弱引导生成的伪标签作为监督信号，避免手工设计退化模型或统计先验。
- **分阶段选择性引导**：匹配扩散模型“由粗到细”特性，早期恢复结构、后期优化颜色，且只引导非身份敏感区域（皮肤、非关键破损），避免身份畸变。
- **区域可控性**：通过解析图和掩码实现像素级选择性引导，支持局部风格化调整。
- **高效轻量**：额外组件少，推理速度快（仅增加少量延迟），参数量和FLOPs远小于对比方法。
- **构建真实基准**：VintageFace包含300张真实老照片并分级，弥补该领域缺乏公开测试集的不足。

## 8. 不足与局限
- **大面积污渍问题**：当图像中存在大片污渍（如墨水、斑点）且颜色与皮肤相近时，模型可能将污渍误解为面部皮肤或头发的一部分，导致恢复结果不自然（见图11）。这是扩散模型依赖周围上下文的特性所致，缺乏细粒度区域级标注作为约束。
- **对预训练网络依赖**：虽然鲁棒性实验表明影响有限，但解析图、刮痕检测和风格迁移网络的质量仍间接影响最终结果。若这些网络在极端退化下完全失效（如解析图IOU低于70%），性能可能下降。
- **仅针对人脸区域**：方法需配合外部图像修复模型处理非人脸区域（如背景），未实现全图统一恢复。
- **实验覆盖**：未在合成退化数据集上进行定量指标（如PSNR、SSIM、LPIPS）比较（因真实老照片无GT）。虽然符合惯例，但限制了对忠实度的精确评估。
- **应用限制**：仅适用于正面或接近正面的人脸图像（因解析网络和扩散模型训练数据多为正脸），侧脸或大角度可能效果不佳（但作者展示了几个侧脸示例尚可）。

（完）
