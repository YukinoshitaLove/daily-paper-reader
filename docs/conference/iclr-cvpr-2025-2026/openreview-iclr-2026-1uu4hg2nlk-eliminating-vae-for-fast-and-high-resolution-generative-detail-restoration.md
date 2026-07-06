---
title: Eliminating VAE for Fast and High-Resolution Generative Detail Restoration
title_zh: 消除VAE以实现快速高分辨率生成式细节修复
authors: "Yan Wang, Shijie Zhao, Junlin Li, Li zhang"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=1uu4Hg2Nlk"
tags: ["query:real-ir"]
score: 10.0
evidence: 移除扩散超分辨率中的VAE以加速高分辨率修复。
tldr: 针对扩散模型在真实世界超分辨率中推理慢、显存消耗大的问题，发现VAE是主要瓶颈，通过像素混洗操作消除VAE，将潜在空间模型转换为像素空间模型GenDR-Pix，实现免分块的高分辨率细节修复，显著提升速度并降低内存需求。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 扩散超分辨率中VAE导致高延迟和内存瓶颈，限制高分辨率处理。
method: 利用像素混洗操作移除VAE，将潜在空间模型转化为像素空间模型GenDR-Pix。
result: 实现了免分块的高分辨率快速修复，显存占用大幅降低。
conclusion: 为实时高分辨率扩散超分辨率提供了高效解决方案。
---

## Abstract
Diffusion models have attained remarkable breakthroughs in the real-world super-resolution (SR) task, albeit at slow inference and high demand on devices. To accelerate inference, recent works like GenDR adopt step distillation to minimize the step number to one. However, the memory boundary still restricts the maximum processing size, necessitating tile-by-tile restoration of high-resolution images. Through profiling the pipeline, we pinpoint that the variational auto-encoder (VAE) is the bottleneck of latency and memory. To completely solve the problem, we leverage pixel-(un)shuffle operations to eliminate the VAE, reversing the latent-based GenDR to pixel-space GenDR-Pix. However, upscale with 
$\times$8 pixelshuffle may induce artifacts of repeated patterns. To alleviate the distortion, we propose a multi-stage adversarial distillation to progressively remove the encoder and decoder. Specifically, we utilize generative features from the previous stage models to guide adversarial discrimination. Moreover, we propose random padding to augment generative features and avoid discriminator collapse. We also introduce a masked Fourier space loss to penalize the outliers of amplitude. To improve inference performance, we empirically integrate a padding-based self-ensemble with classifier-free guidance to improve inference scaling. Experimental results show that GenDR-Pix performs 2.8$\times$  acceleration and 60% memory-saving compared to GenDR with negligible visual degradation, surpassing other one-step diffusion SR. Against all odds, GenDR-Pix can restore 4K image in only 1 second and 6 GB.

---

## 论文详细总结（自动生成）

# 论文核心问题与整体含义
- **研究动机**：扩散模型在真实世界超分辨率（SR）中取得突破，但推理速度慢、显存占用高，严重限制高分辨率图像处理。近期工作如GenDR通过步长蒸馏将采样步数压缩至1步以加速，然而显存瓶颈依然存在，高分辨率图像仍需分块（tile-by-tile）修复，无法端到端处理整图。
- **核心瓶颈定位**：通过对推理管线进行性能分析，作者发现**变分自编码器（VAE）**是延迟和显存的主要瓶颈。去除VAE可以彻底解决分块处理的限制。
- **整体含义**：本文提出**GenDR-Pix**，将原本基于潜在空间的GenDR模型转换为像素空间模型，从而消除VAE，实现极速、低内存的高分辨率生成式细节修复，使单张4K图像恢复仅需约1秒、6 GB显存，具备实时应用潜力。

---

# 方法论
## 总体思想
- **去除VAE**：利用**像素混洗（pixel-(un)shuffle）操作**替代VAE的编码器-解码器，将扩散过程直接从潜在空间迁移到像素空间，形成GenDR-Pix模型。
- **缓解像素混洗引入的失真**：直接进行×8的像素混洗可能产生重复纹理等伪影，为此提出**多阶段对抗蒸馏**策略，逐步移除编码器和解码器，并借助前阶段模型的生成特征指导对抗判别。

## 关键技术细节
- **多阶段对抗蒸馏**：
  - 逐步蒸馏编码器和解码器，不一次性跳跃到目标空间。
  - 利用**前一阶段模型生成的中间特征**对对抗判别进行指导，稳定蒸馏过程。
- **随机填充（Random Padding）**：
  - 对生成特征进行随机填充增广，避免判别器坍塌，提升对抗训练的鲁棒性。
- **掩码傅里叶空间损失（Masked Fourier Space Loss）**：
  - 在频域中对振幅的异常值进行惩罚，进一步抑制伪影和高频失真。
- **推理增强策略**：
  - 结合**基于填充的自集成（padding-based self-ensemble）**与**无分类器引导（classifier-free guidance）**，改善推理时的缩放性能，提升图像质量。

## 公式/算法流程（文字描述）
- 原始潜在扩散流程：输入图像 → VAE编码 → 潜在空间去噪（GenDR单步蒸馏）→ VAE解码 → 输出图像。
- 改进流程：输入图像 → 像素混洗下采样 → 像素空间去噪（GenDR-Pix蒸馏模型）→ 像素混洗上采样 → 输出图像。
- 训练流程：
  1. 构建像素空间数据对（HR与像素混洗后的LR）。
  2. 多阶段蒸馏：阶段一保留部分VAE组件，阶段二逐步替换为纯像素操作，并用前一阶段模型的生成特征辅助判别。
  3. 加入随机填充和掩码傅里叶损失进行对抗训练。
- 推理流程：单步去噪，可选择采用自集成与引导以提升细节。

---

# 实验设计
- **数据集与场景**：摘要未具体列出训练和测试数据集，但提及“真实世界超分辨率”任务，推测使用常用真实世界SR数据集（如RealSR、DRealSR等）。
- **Benchmark与对比方法**：
  - 主要对比基线为**GenDR**（潜在空间一步蒸馏扩散模型）。
  - 声称**超越其他一步扩散超分辨率方法**，但未列举具体方法名称。
- **评估指标**：摘要强调速度提升（2.8倍加速）、内存节省（60%）、4K图像恢复仅需1秒/6 GB，同时视觉质量劣化可忽略。具体定量指标（PSNR/SSIM/LPIPS等）未直接给出，但应包含在主论文中。

---

# 资源与算力
- 摘要**未明确说明**使用的GPU型号、数量及训练时长。
- 仅给出推理阶段的资源消耗：GenDR-Pix恢复4K图像仅需**6 GB显存**，**1秒**完成，间接反映模型在消费级显卡上的可行性，但训练阶段的算力需求未知。

---

# 实验数量与充分性
- **实验数量**：摘要中仅提及性能对比（加速、省内存）与消融概念（多阶段蒸馏、随机填充、掩码傅里叶损失等），未给出具体实验组数或表格数据。
- **充分性评估**：
  - 从摘要看，消融设计覆盖了主要创新点（渐进蒸馏、数据增广、频域损失），且声称“超越其他一步模型”，体现了一定完备性。
  - 然而，缺乏**数据集多样性**、**多种评价指标**、**与更多类方法的对比**（如非扩散模型、GAN方法）的明确报告，其充分性在原摘要中无法完全判断，需阅读全文。
- **客观性与公平性**：摘要中声称“negligible visual degradation”，若配合用户研究或定量指标则更可信。目前仅摘要层面，对比基线以GenDR为主，对其他方法的覆盖未知。

---

# 主要结论与发现
- VAE是扩散超分辨率的**真正瓶颈**，去除VAE可将潜在空间模型逆转为像素空间模型，实现高分辨率细节修复。
- 提出的GenDR-Pix在**速度（2.8倍加速）**和**内存（节省60%）**上显著优于GenDR，同时视觉质量几乎无损失。
- 首次实现**4K图像端到端单步扩散超分**，仅需1秒和6 GB显存，为实时高分辨率应用铺平道路。

---

# 优点
- **方法论贡献清晰**：直接定位VAE为瓶颈，通过像素混洗消除潜在空间依赖，思路简洁且有效。
- **工程实用性极强**：极大降低延迟和显存消耗，使扩散超分在消费级硬件上处理4K图像成为可能。
- **抗伪影设计**：多阶段蒸馏、随机填充、频域损失等多重设计针对消除像素混洗带来的重复纹理，方法体系完整。
- **推理增强**：引入自集成与引导策略，进一步提升单步输出质量。

---

# 不足与局限
- **摘要信息有限**：未披露训练数据、具体对比方法、详细量化指标，难以精确评估其泛化能力和相对优势。
- **像素混洗局限性**：×8混洗引入的伪影虽经缓解，但在强纹理区域仍可能残留失真，摘要未给出失败案例。
- **训练成本未知**：多阶段对抗蒸馏的训练复杂度、收敛时间未说明，可能抵消部分推理加速的优势。
- **适用范围**：论文聚焦于真实世界细节修复，对极端退化（严重模糊、噪声）或大倍率（>4×）的鲁棒性未讨论。
- **对比公平性**：仅与基于潜在空间的GenDR对比，可能未能充分体现与同期像素空间生成式超分方法的优劣。

---

（完）
