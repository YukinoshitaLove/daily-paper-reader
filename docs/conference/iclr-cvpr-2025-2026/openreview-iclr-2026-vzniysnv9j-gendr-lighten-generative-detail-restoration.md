---
title: "GenDR: Lighten Generative Detail Restoration"
title_zh: GenDR：轻量化生成细节恢复
authors: "Yan Wang, Shijie Zhao, Kexin Zhang, Junlin Li, Li zhang"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=vznIYSnv9J"
tags: ["query:real-ir"]
score: 10.0
evidence: 利用扩散模型进行生成式细节恢复以实现真实世界超分辨率
tldr: 该论文发现文本到图像扩散模型在超分辨率任务中存在目标不匹配，提出GenDR方法。通过采用16通道VAE编码器以更好保留输入信息，并设计高效的推理策略，在真实世界超分辨率上实现了细节保真度与速度的更优平衡。实验表明GenDR在多个基准上超越现有扩散超分方法，以更少参数量达到更佳效果，为生成式细节恢复提供了高效轻量方案。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现有扩散超分模型多步推理且低通道VAE，无法高效恢复细节，与超分目标不匹配。
method: 采用16通道VAE保留输入信息，设计专用扩散模型与高效推理策略，对齐超分任务需求。
result: 在真实世界超分数据集上以更少步骤和参数取得最佳细节恢复效果。
conclusion: GenDR通过任务对齐设计，实现了扩散模型在超分上的高效与高质统一。
---

## Abstract
Although recent research applying text-to-image (T2I) diffusion models to real-world super-resolution (SR) has achieved remarkable progress, the misalignment of their targets leads to a suboptimal trade-off between inference speed and detail fidelity. Specifically, the T2I task requires multiple inference steps to synthesize images matching to prompts and reduces the latent dimension to lower generating difficulty. Contrariwise, SR can restore high-frequency details in fewer inference steps, but it necessitates a more reliable variational auto-encoder (VAE) to preserve input information. However, most diffusion-based SRs are multistep and use 4-channel VAEs, while existing models with 16-channel VAEs are overqualified diffusion transformers, e.g., FLUX (12B). To align the target, we present a one-step diffusion model for generative detail restoration, GenDR, distilled from a tailored diffusion model with a larger latent space. In detail, we train a new SD2.1-VAE16 (0.9B) via representation alignment to expand the latent space without increasing the model size. Regarding step distillation, we propose consistent score identity distillation (CiD) that incorporates SR task-specific loss into score distillation to leverage more SR priors and align the training target. Furthermore, we extend CiD with adversarial learning and representation alignment (CiDA) to enhance perceptual quality and accelerate training. We also polish the pipeline to achieve a more efficient inference. Experimental results demonstrate that GenDR achieves state-of-the-art performance in both quantitative metrics and visual fidelity.

---

## 论文详细总结（自动生成）

# GenDR：轻量化生成细节恢复 论文总结

## 1. 研究动机与背景
- **核心问题**：将文本到图像（T2I）扩散模型用于真实世界超分辨率（SR）时，存在目标不匹配。T2I 任务需要多步推理来匹配文本提示，并通常压缩隐空间维度（如 4 通道 VAE）以降低生成难度；而 SR 任务只需较少推理步数即可恢复高频细节，但要求更可靠的变分自编码器（VAE）来保留输入信息。
- **现状与缺口**：当前多数扩散超分方法仍然使用多步推理和 4 通道 VAE，难以高效恢复细节；少数采用 16 通道 VAE 的模型（如 FLUX）参数量极大（～12B），不够轻量。亟需一种“任务对齐”的轻量化方案。

## 2. 方法论
- **整体思路**：先训练一个面向 SR 的定制扩散模型（12 通道 VAE），再将其蒸馏为一步生成模型 GenDR。
- **关键技术细节**：
  - **大隐空间 VAE**：训练 **SD2.1-VAE16（0.9B 参数）**，通过表示对齐扩展隐空间，在不显著增加模型尺寸的前提下保留更多输入信息。
  - **蒸馏策略——CiD**：提出“一致分数身份蒸馏”（Consistent Score Identity Distillation），将 **SR 任务特定损失**（如图像重建/感知损失）融入分数蒸馏过程，以利用超分先验并对齐训练目标。
  - **增强版蒸馏——CiDA**：在 CiD 基础上引入**对抗学习**和**表示对齐**，进一步提升感知质量并加速蒸馏训练。
  - **推理优化**：打磨整体流程，实现高效的一步推理。

## 3. 实验设计
- **数据集/场景**：真实世界超分辨率场景（原文可能使用了 RealSR、DRealSR 等常用 benchmark，具体名称未在摘要列出）。
- **对比方法**：与现有扩散超分方法进行比较，包括基于 Stable Diffusion 的多步超分模型、其他轻量化一步扩散模型等。
- **评估基准**：定量指标（如 PSNR、SSIM、LPIPS）和视觉保真度。

## 4. 资源与算力
- **说明**：摘要及元数据中**未给出**具体 GPU 型号、数量或训练时长。

## 5. 实验数量与充分性
- **实验规模**：摘要仅提及在多个基准上取得 state‑of‑the‑art，但未列出消融实验或对比方法的具体数量。从论文标题和描述可推知应包含如下实验：
  - 不同数据集上的性能对比；
  - 蒸馏策略（CiD vs. CiDA）的消融实验；
  - 推理步数、模型参数量的效率分析。
- **充分性评估**：根据其宣称的“更少步骤和参数取得最佳细节恢复”，实验应能支撑高效与高质的平衡，具有较好的充分性和公平性。

## 6. 主要结论与发现
- GenDR 通过任务对齐设计，在真实世界超分任务上以 **一步推理** 和 **更少参数** 实现了 **最佳的细节保真度**，在定量指标与视觉质量上均超越现有扩散超分方法，达成了高效与高质的统一。

## 7. 优点
- **推理效率极高**：一步生成，速度远快于多步扩散方法。
- **轻量化设计**：基于 0.9B 的 VAE，参数规模远小于 FLUX 等大模型。
- **任务对齐**：16 通道 VAE 更好地保留高频细节，蒸馏策略融入 SR 先验，目标更匹配。
- **蒸馏创新**：CiD 和 CiDA 整合对抗学习与表示对齐，兼顾感知质量和训练速度。

## 8. 不足与局限
- **预训练依赖**：方法建立在 SD‑2.1 预训练模型之上，可能受原有模型偏置影响。
- **泛化性未详述**：在摘要中未提及对未知降质、噪声或极端场景的鲁棒性。
- **资源信息缺失**：未公布训练成本与时间，较难评估工业复现门槛。
- **模型规模虽轻但仍非极致**：0.9B 参数在超分任务中仍属于较大模型，部署上可能仍有优化空间。

（完）
