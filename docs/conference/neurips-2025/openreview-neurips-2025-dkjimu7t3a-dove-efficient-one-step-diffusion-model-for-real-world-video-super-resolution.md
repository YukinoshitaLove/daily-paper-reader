---
title: "DOVE: Efficient One-Step Diffusion Model for Real-World Video Super-Resolution"
title_zh: "DOVE: 高效一步扩散模型用于真实世界视频超分辨率"
authors: "Zheng Chen, Zichen Zou, Kewei Zhang, Xiongfei Su, Xin Yuan, Yong Guo, Yulun Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DkJImu7t3A"
tags: ["query:real-ir"]
score: 9.0
evidence: 一步扩散模型用于视频超分辨率
tldr: 扩散模型在视频超分中效果好但推理慢，DOVE通过潜在-像素两阶段训练策略，将预训练视频扩散模型微调为单步模型，大幅提升推理速度同时保持质量，解决了一步生成在高保真度要求下的挑战。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dkjimu7t3a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dkjimu7t3a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dkjimu7t3a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dkjimu7t3a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 670, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dkjimu7t3a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 601, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 588, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 714, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 1328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dkjimu7t3a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 750, \"height\": 234, \"label\": \"Table\"}]"
motivation: 扩散模型用于视频超分推理极慢，一步加速面临高保真度挑战。
method: 基于预训练视频扩散模型CogVideoX，提出潜在-像素两阶段训练策略，微调为单步模型。
result: 在真实视频超分数据集上实现快速推理且质量损失小。
conclusion: 一步扩散模型为视频超分实用化提供了可行方案。
---

## Abstract
Diffusion models have demonstrated promising performance in real-world video super-resolution (VSR). However, the dozens of sampling steps they require, make inference extremely slow. Sampling acceleration techniques, particularly single-step, provide a potential solution. Nonetheless, achieving one step in VSR remains challenging, due to the high training overhead on video data and stringent fidelity demands. To tackle the above issues, we propose DOVE, an efficient one-step diffusion model for real-world VSR. DOVE is obtained by fine-tuning a pretrained video diffusion model (*i.e.*, CogVideoX). To effectively train DOVE, we introduce the latent-pixel training strategy. The strategy employs a two-stage scheme to gradually adapt the model to the video super-resolution task. Meanwhile, we design a video processing pipeline to construct a high-quality dataset tailored for VSR, termed HQ-VSR. Fine-tuning on this dataset further enhances the restoration capability of DOVE. Extensive experiments show that DOVE exhibits comparable or superior performance to multi-step diffusion-based VSR methods. It also offers outstanding inference efficiency, achieving up to a **28$\times$** speed-up over existing methods such as MGLD-VSR. Code is available at: https://github.com/zhengchen1999/DOVE.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：DOVE: Efficient One-Step Diffusion Model for Real-World Video Super-Resolution

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：视频超分辨率（VSR）旨在从低分辨率视频重建高分辨率视频。真实世界中的视频退化复杂且未知，传统方法效果有限。扩散模型凭借强大的生成先验，在VSR中展现出优异性能，但需要数十步迭代采样，导致推理速度极慢（例如MGLD-VSR处理33帧720p视频需425秒）。
- **核心问题**：如何实现一步（单步）扩散模型用于VSR，同时满足高保真度要求和可接受的训练开销。直接迁移图像领域的单步加速方法（如蒸馏、对抗训练）在视频域面临两大困难：①视频多帧导致训练成本飙升；②对抗训练不稳定，易引入伪影，违背VSR的高保真需求。
- **整体含义**：论文提出DOVE，首个实现一步推理的扩散模型用于真实世界VSR，在不牺牲重建质量的前提下大幅提升效率，推动扩散模型在VSR任务中的实用化。

## 2. 论文提出的方法论

### 2.1 核心思想

- 基于强大的预训练文本到视频扩散模型CogVideoX，通过微调将其转换为单步VSR模型。
- 避免引入任何额外模块（如ControlNet、时序层、光流模块），仅微调Transformer部分，VAE编码器/解码器冻结。
- 设计两阶段“潜在-像素”训练策略，用回归损失替代蒸馏或对抗损失，实现高效微调。

### 2.2 关键技术细节

#### 整体框架

- 输入低分辨率视频 \( \mathbf{x}_{lr} \) → 双线性上采样到目标分辨率 → VAE编码器得到潜在 \( \mathbf{z}_{lr} \)。
- 以 \( \mathbf{z}_{lr} \) 作为扩散起始点（对应特定时间步 \( t \)），通过单步去噪得到“干净”潜在 \( \mathbf{z}_{sr} \)：
  \[
  \mathbf{z}_{sr} = \sqrt{\bar{\alpha}_t} \mathbf{z}_{lr} - \sqrt{1-\bar{\alpha}_t} v_\theta(\mathbf{z}_{lr}, c, t)
  \]
  其中 \( v_\theta \) 为Transformer去噪器，采用 \( v \)-预测公式。\( t \) 经验设置为399（而非总步数999），平衡结构保留与退化去除。
- \( \mathbf{z}_{sr} \) 经VAE解码器得到输出视频 \( \mathbf{x}_{sr} \)。

#### 两阶段训练策略（Latent-Pixel Training Strategy）

- **Stage-1（潜在空间适应）**：冻结VAE解码器，最小化预测潜在与真实HR潜在之间的MSE损失 \( \mathcal{L}_{s1} = \mathcal{L}_{mse}(\mathbf{z}_{sr}, \mathbf{z}_{hr}) \)。由于潜在空间计算效率高，可处理长帧序列视频。
- **Stage-2（像素空间精炼）**：进一步在像素空间微调。为降低内存，图像可视为单帧视频，采用混合图像/视频训练策略。
  - **图像分支**：最小化MSE损失和DISTS感知损失：\( \mathcal{L}_{s2-image} = \mathcal{L}_{mse} + \lambda_1 \mathcal{L}_{dists} \)。
  - **视频分支**：通过帧级VAE处理（逐帧编码/解码）避免多帧内存峰值，Transformer仍处理完整潜在。损失添加帧差损失以保证时序一致性：
    \[
    \mathcal{L}_{frame}(\mathbf{x}_{sr}, \mathbf{x}_{hr}) = \frac{1}{n-1} \sum_{t=2}^n \| \Delta \mathbf{x}^{(t)}_{sr} - \Delta \mathbf{x}^{(t)}_{hr} \|_1
    \]
    总损失 \( \mathcal{L}_{s2-video} = \mathcal{L}_{mse} + \lambda_1 \mathcal{L}_{dists} + \lambda_2 \mathcal{L}_{frame} \)。
  - 超参数 \( \varphi \) 控制训练批次中图像与视频的比例，最优为80%图像。

### 2.3 高质量数据集构建（Video Processing Pipeline → HQ-VSR）

- **动机**：现有VSR数据集要么数量少，要么缺乏针对VSR的筛选。
- **管道步骤**：
  1. **元数据过滤**：保留短边≥720像素、帧数≥50的视频。
  2. **场景过滤**：检测场景分割，丢弃少于50帧的片段，去除镜头切换。
  3. **质量过滤**：使用美学评分、CLIP-IQA、FasterVQA、DOVER等多指标综合评分，保留高质量视频。
  4. **运动处理**：估计光流，基于运动掩码检测运动区域并裁剪出动态部分，丢弃静态区域；确保裁剪后分辨率仍≥720p。
- **结果**：从OpenVid-1M中提取2055个高质量视频，形成HQ-VSR数据集。

## 3. 实验设计

### 3.1 数据集与场景

- **训练集**：
  - 视频：HQ-VSR（2055视频），采用RealBasicVSR退化管道合成LQ-HQ对。
  - 图像：DIV2K（900图像），采用Real-ESRGAN退化。
- **评估集**：
  - 合成数据集：UDM10、SPMCS、YouHQ40（使用与训练相同的退化）。
  - 真实数据集：RealVSR、MVSR4x（移动手机拍摄的LQ-HQ对）、VideoLQ（网络视频，无HQ参考）。
  - 所有实验在×4缩放因子下进行。

### 3.2 评估指标

- 图像质量：PSNR、SSIM（保真度）；LPIPS、DISTS、CLIP-IQA（感知质量）。
- 视频质量：FasterVQA、DOVER（整体视频质量）。
- 时序一致性：光流翘曲误差 \( E^*_{warp} \)。

### 3.3 对比方法

- 图像超分辨率：RealESRGAN、ResShift。
- 视频超分辨率：RealBasicVSR、Upscale-A-Video、MGLD-VSR、VEnhancer、STAR。

## 4. 资源与算力

- **训练硬件**：4张NVIDIA A800-80G GPU。
- **训练配置**：
  - Stage-1：总batch size 8，视频分辨率320×640，帧长25，训练10,000迭代，学习率2×10⁻⁵。
  - Stage-2：混合图像/视频，batch size 8，分辨率320×640，训练500迭代，学习率5×10⁻⁶。
  - 优化器：AdamW（β1=0.9, β2=0.95, β3=0.98）。
  - 损失权重：λ₁=1, λ₂=1。
- **推理时间测量**：单张A100 GPU，处理33帧720×1280视频。

## 5. 实验数量与充分性

- **主要定量对比**：在5个数据集（UDM10、SPMCS、YouHQ40、RealVSR、MVSR4x、VideoLQ）上与7种方法全面对比，指标涵盖保真度、感知、视频质量和时序一致性（Table 2）。
- **消融实验**（Table 1）：
  - 训练策略：对比Stage-1、Stage-2仅图像、Stage-2混合图像/视频。
  - 图像比例φ：从0%到100%搜索最优比例。
  - 训练集：对比YouHQ、OpenVid-1M、HQ-VSR。
  - 数据处理管道：对比原始、过滤后、再经运动处理的效果。
- **推理效率比较**（Table 3）：比较不同扩散方法的步数、运行时间和DOVER分数。
- **定性结果**：提供合成和真实视频的视觉对比（图4）及时序轮廓对比（图5）。
- **充分性分析**：实验覆盖了合成与真实场景，消融全面验证各组件贡献，对比方法均为公开SOTA，且采用统一评测设置。结论客观，实验设计公平。

## 6. 论文的主要结论与发现

- **性能**：DOVE在多个数据集上的保真度（PSNR/SSIM）和感知指标（LPIPS/DISTS/CLIP-IQA）均达到或超越多步扩散方法；在视频质量指标（FasterVQA/DOVER）上表现领先。
- **效率**：单步推理使DOVE比MGLD-VSR快约28倍，比最快的对比方法VEnhancer快8倍。
- **数据集有效性**：所构建的HQ-VSR数据集仅2055个视频即可显著提升性能，证明筛选质量的重要性。
- **训练策略有效性**：两阶段潜在-像素训练策略在仅10K+500次迭代内完成微调，高效且有效。

## 7. 优点

- **创新性**：首次将一步扩散模型成功应用于真实世界VSR，解决了视频域高训练成本和高保真需求的矛盾。
- **简洁高效**：不引入任何额外模块，直接微调预训练模型，架构简单，推理速度快。
- **训练策略精巧**：潜在空间适应降低计算负担，像素空间混合训练兼顾细节和时序一致性；采用回归损失避免了复杂蒸馏和对抗训练的不稳定性。
- **数据管道系统化**：提出四步视频处理管道，从大规模公开数据中筛选出高质量VSR专用数据集，有助于社区后续研究。
- **实验充分**：覆盖多场景、多指标，消融实验验证每个设计决策，结果可信。

## 8. 不足与局限

- **预训练模型依赖**：DOVE基于CogVideoX构建，若该模型未来更新或关闭，可能影响可复现性；泛化到其他预训练视频模型的能力未验证。
- **缩放因子单一**：仅评估×4倍率，×2或×8等其他倍率的性能未知。
- **视频数据集规模有限**：HQ-VSR仅含2055个视频，虽通过筛选提升了质量，但多样性可能不足，在极端场景（如剧烈运动、复杂光照）下的鲁棒性有待进一步验证。
- **真实世界退化模拟**：训练采用合成退化（RealBasicVSR/Real-ESRGAN），与真实退化存在差距，尽管在真实数据集上表现不错，但可能仍有域偏移。
- **时序一致性指标**：翘曲误差 \( E^*_{warp} \) 有一定局限性，对于快速运动或遮挡场景可能存在测量偏差。
- **缺失上/下游任务分析**：未讨论模型对后续任务（如目标检测、追踪）的影响，也未分析偏差或公平性问题。
- **补充材料中提及局限性**：原文在NeurIPS checklist中承诺讨论了局限性，但主文未包含，可能仅在补充材料中（未提供），此处基于现有信息推断。

（完）
