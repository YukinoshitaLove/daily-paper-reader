---
title: "SIR-DIFF: Sparse Image Sets Restoration with Multi-View Diffusion Model"
title_zh: SIR-DIFF：基于多视图扩散模型的稀疏图像集恢复
authors: "Mao, Yucheng, Wang, Boyang, Kulkarni, Nilesh, Park, Jeong Joon"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Mao_SIR-DIFF_Sparse_Image_Sets_Restoration_with_Multi-View_Diffusion_Model_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 基于多视图扩散模型的图像恢复
tldr: 提出SIR-DIFF，利用多视图扩散模型联合恢复共享场景的多张降质图像，通过多视图关系补充信息，有效约束病态恢复问题，在多视图联合恢复中显著优于单图甚至视频恢复方法。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1634, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1794, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1801, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1801, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 846, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 507, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1753, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 601, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mao-sir-diff-sparse-image-sets-restoration-with-multi-view-diffusion-model-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 227, \"label\": \"Table\"}]"
motivation: 单张降质图像恢复是病态问题，多张图像包含互补信息可改善重建。
method: 设计多视图扩散模型，同时生成无失真视图，从多视图关系中提取丰富信息。
result: 多视图联合恢复效果显著优于单图甚至视频恢复方法。
conclusion: 展示了多视图扩散模型在图像恢复任务上的潜力，为利用多图像信息提供了新思路。
---

## Abstract
The computer vision community has developed numerous techniques for digitally restoring true scene information from single-view degraded photographs, an important yet extremely ill-posed task. In this work, we tackle image restoration from a different perspective by jointly denoising multiple photographs of the same scene. Our core hypothesis is that degraded images capturing a shared scene contain complementary information that, when combined, better constrains the restoration problem. To this end, we implement a powerful multi-view diffusion model that jointly generates uncorrupted views by extracting rich information from multi-view relationships. Our experiments show that our multi-view approach outperforms existing single-view image and even video-based methods on image deblurring and super-resolution tasks. Critically, our model is trained to output 3D consistent images, making it a promising tool for applications requiring robust multi-view integration, such as 3D reconstruction or pose estimation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：单张降质图像（如模糊、低分辨率）的恢复是一个严重病态的问题。实际中，我们常对同一场景拍摄多张照片，这些多视图图像包含互补信息，但现有单图恢复方法孤立处理，会破坏视图间的一致性，影响后续三维重建等任务。
- **整体含义**：提出将图像恢复重新定义为一个多视图协同恢复任务，利用多张降质图像间的互补信息联合生成干净、一致的高质量视图，从而更好地约束病态问题，并直接为三维视觉应用（如3D重建、位姿估计）提供三维一致的恢复结果。

### 2. 论文提出的方法论
- **核心思想**：基于潜在扩散模型（Latent Diffusion Model）设计一个多视图扩散模型 SIR‑Diff，在去噪过程中让多个视图的潜在表示相互关注，从而产生三维一致的干净图像。
- **关键技术细节**：
  - **统一编码器**：使用预训练的 Stable Diffusion 2.1 的 VAE 编码器将降质图像和带噪图像映射到潜在空间，冻结编码器/解码器。
  - **混合 2D‑3D 卷积 ResNet**：在 UNet 的 ResNet 块中同时使用 2D 卷积（继承自图像扩散模型）和 3D 卷积（继承自视频扩散模型 SVD），通过可学习混合权重 `σ` 融合输出：`O_ResNet = σ(α) × O_2D + σ(1‑α) × O_3D`。2D 卷积初始化为 SD2.1 权重，3D 卷积初始化为 SVD 权重。
  - **3D 自注意力 Transformer**：在低分辨率层将所有视图的令牌展平，执行全局自注意力，使每个空间令牌都能访问到其他视图的对应信息，从而显式建模多视图关系。为降低计算量，仅在低分辨率层插入，并完全移除原始扩散模型中的交叉注意力模块。
  - **训练目标**：标准噪声预测损失 `L = E||ϵ − ˆϵ||^2`，其中 `ˆϵ = s_θ(x_k, φ({I_c}^N_{i=1}), k)`，`x_k` 为噪声潜在，`φ({I_c})` 为条件降质图像的潜在。
- **总体流程**：输入 N 个降质图像的潜在级联带噪潜在，经过空间‑3D UNet 去噪，最后用冻结的解码器生成干净图像。

### 3. 实验设计
- **数据集与场景**：
  - 训练集：合成数据集 Hypersim 和 TartanAir，分辨率 640×480。
  - 零样本评估集（跨域）：ScanNet++（室内真实场景）、ETH3D（室内/室外 LiDAR 场景）、CO3Dv2（物体中心数据集），全部采用零样本设定以保证公平。
- **任务与基准**：
  - **运动去模糊**：人工合成运动模糊核（均值 85px），评估方法恢复清晰图像的能力。对比方法包括单图方法 Restormer、PromptIR，视频方法 VRT，以及 SIR‑Diff 的单帧版本。
  - **4× 超分辨率**：对高分辨率图像下采样再用双三次上采样模拟低分辨率输入。对比方法包括单图扩散模型 SAM‑DiffSR、OSEDiff，视频扩散模型 Upscale‑A‑Video，以及 SIR‑Diff 的单帧版本。
  - **下游应用**：对应点匹配（LoFTR）、3D 重建（BAD‑Gaussians、InstantSplat）、深度估计（DepthAnythingV2、DepthCrafter、Marigold），验证恢复图像对三维任务的提升。
- **评价指标**：
  - 图像质量：FID、LPIPS（去模糊和 SR），PSNR、SSIM（SR）
  - 视图一致性：新提出的 VConsis（视觉一致性）及 GConsis（几何一致性）用于深度任务。

### 4. 资源与算力
- 文中提到“This work partially used NCSA Delta GPU at the University of Illinois”，但**未明确说明**使用的 GPU 型号、数量、训练时长、批大小等具体算力消耗。可能详细配置在补充材料中，主论文未给出具体数值。

### 5. 实验数量与充分性
- **实验数量较多**：
  - 两大核心任务（去模糊、超分辨率）在三个真实数据集上评估，共 6 个主结果表。
  - 下游应用包含三项（特征匹配、3D 重建、深度估计），各有定量表格和定性展示。
  - 消融研究提到在补充材料中（主文未展示，但表示已做），如单帧 vs 多帧、不同架构变体。
- **充分性与客观性**：
  - 对比方法覆盖单图、视频、扩散模型等前沿基线，均为各自任务的最先进或代表性方法。
  - 采用零样本跨域评估，避免训练/测试域重叠，较为公平。
  - 定量指标综合了像素、感知、三维一致性，下游任务也采用标准指标，实验较为全面。
  - 可能不足：消融实验未在主文展示，难以判断对不同组件的具体贡献；只在合成数据训练，现实退化泛化性未验证。

### 6. 论文的主要结论与发现
- SIR‑Diff 在所有多视图去模糊和超分辨率任务中，在图像质量（FID、LPIPS、PSNR、SSIM）和视觉一致性（VConsis）上均显著优于现有单视图和视频方法。
- 模型生成的三维一致图像能有效提升下游应用性能：增加 LoFTR 的匹配点数、提升 BAD‑GS 和 InstantSplat 的 3D 重建质量、改善多视图深度估计的几何一致性。
- 多视图联合去噪能有效利用不同视图的互补信息，尤其在退化严重时，单图方法失效，而 SIR‑Diff 仍能稳定恢复。

### 7. 优点
- **新颖的视角**：将图像恢复从单图扩展为多视图协同恢复，利用多视图互补信息。
- **高效的架构设计**：
  - 混合 2D‑3D 卷积巧妙融合图像与视频扩散模型的先验，无需从零训练。
  - 3D 自注意力实现多视图信息交互，且仅用于低分辨率层降低开销。
  - 完全移除交叉注意力以加速训练和收敛。
- **零样本泛化**：在合成数据训练后，直接应用于真实场景（ScanNet++ 等）表现优异，说明强泛化能力。
- **三维一致性**：显式考虑视图间一致性，对 3D 下游任务非常友好。
- **多任务扩展性**：不仅去模糊和超分辨率，还展示在深度估计上的潜力，说明架构可适用于其他多视图恢复任务。
- **新评价指标**：引入视觉一致性度量，有助于评估多视图恢复的几何一致性。

### 8. 不足与局限
- **算力细节缺失**：未报告具体使用的 GPU 型号、训练时间、显存消耗等，难以复现或评估实用效率。
- **训练数据受限**：仅在合成室内数据集上训练，对复杂退化（如真实离焦模糊、高噪声）和室外变光照场景的泛化能力未充分验证。
- **多视图依赖**：需要若干张重叠视图作为输入，若视图极少（如2张）或内容重合度低，性能可能下降，且未讨论最低视图数要求。
- **计算开销**：全局 3D 自注意力在视图数增多时计算量增长快（与 N² 相关），尽管已在低分辨率层使用，仍有扩展瓶颈。
- **消融不透明**：消融实验未在主文展示，难以评估各组件（混合卷积、自注意力位置、去除交叉注意力）的具体贡献。
- **真实退化模拟**：模糊和低分辨率均采用简单合成手段（运动模糊核、双三次下采样），无法覆盖真实世界中复杂而未知的退化过程。
- **推理速度**：未提供推理时间，扩散模型多步采样可能影响实时性应用。

（完）
