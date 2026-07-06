---
title: One-Step Residual Shifting Diffusion for Image Super-Resolution via Distillation
title_zh: 基于蒸馏的一步残差偏移扩散图像超分辨率方法
authors: "Daniil Selikhanovych, David Li, Aleksei Leonov, Nikita Gushchin, Sergey Kushneryuk, Alexander Filippov, Evgeny Burnaev, Iaroslav Sergeevich Koshelev, Alexander Korotin"
date: 2025-09-15
pdf: "https://openreview.net/pdf?id=ALgBKWHNRV"
tags: ["query:real-ir"]
score: 10.0
evidence: 基于扩散模型的图像超分辨率，通过蒸馏实现单步重建
tldr: 针对扩散模型超分辨率计算成本高的问题，提出RSD蒸馏方法，通过训练学生模型使生成的图像与教师模型保持一致，实现单步重建，显著提升感知质量并避免伪造结构，在多指标上超越现有加速方法。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 扩散超分辨率模型计算昂贵，现有加速方法细节失真或产生虚假结构。
method: 提出RSD，通过让学生生成图像训练一个伪造的ResShift模型并与教师对齐，实现蒸馏。
result: 单步重建在LPIPS、NIQE等感知指标上明显优于教师及SinSR、OSEDiff等方法。
conclusion: RSD在单步扩散超分辨率中实现了速度与质量的更好平衡，有效抑制了幻觉。
---

## Abstract
Diffusion models for super-resolution (SR) produce high-quality visual results but require expensive computational costs. Despite the development of several methods to accelerate diffusion-based SR models, some (e.g., SinSR) fail to produce realistic perceptual details, while others (e.g., OSEDiff) may hallucinate non-existent structures. To overcome these issues, we present **RSD**, a new distillation method for ResShift. Our method is based on training the student network to produce images such that a new fake ResShift model trained on them will coincide with the teacher model. RSD achieves single-step restoration and outperforms the teacher by a noticeable margin in various perceptual metrics (LPIPS, CLIPIQA, MUSIQ, DISTS, NIQE, MANIQA). We show that our distillation method can surpass the other distillation-based method for ResShift - SinSR - making it on par with state-of-the-art diffusion-based SR distillation methods  with low computational costs in terms of perceptual quality. Compared to SR methods based on pre-trained text-to-image models, RSD produces competitive perceptual quality and requires fewer parameters, GPU memory, and training cost. We provide experimental results on various real-world and synthetic datasets, including RealSR, RealSet65, DRealSR, ImageNet, DIV2K, RealLR200 and RealLQ250.

---

## 论文详细总结（自动生成）

# 基于蒸馏的一步残差偏移扩散图像超分辨率方法（RSD）详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：扩散模型在图像超分辨率（SR）中虽然能生成高质量的视觉效果，但计算成本高昂。现有的加速方法存在两难困境：
  - 某些方法（如SinSR）难以生成逼真的感知细节；
  - 另一些方法（如OSEDiff）容易产生虚假的伪结构（幻觉）。
- **研究动机**：需要一种新的蒸馏方法，在单步推理中同时实现高感知质量和结构真实性，避免夸张的伪造细节。
- **整体含义**：提出 **RSD**（One-Step Residual Shifting Diffusion），一种基于ResShift的蒸馏方法，通过让学生模型生成的图像去“模仿”教师模型的分布，达到一步还原并超越教师模型的感知质量，从而在速度与视觉可信度之间取得更好的平衡。

## 2. 论文提出的方法论
- **核心思想**：训练一个学生网络，使其生成的超分辨率图像经过一个“伪造的ResShift模型”（fake ResShift）进一步处理后，该伪造模型的行为与原始的教师ResShift模型完全一致。
- **技术细节与流程**（文字说明）：
  - 基座模型为 **ResShift**，一种用于超分辨率的扩散模型。
  - **蒸馏策略**：学生网络直接输出超分辨率图像。假设存在一个新的ResShift模型，它只在学生生成的图像上进行训练（即“伪造的ResShift”）。蒸馏的目标是让这个伪造模型在功能上与教师模型重合（coincide）。这等价于让学生输出的图像位于教师模型所定义的高质量图像流形中，且能保持对低分辨率输入的忠实性。
  - 该过程不依赖多步扩散采样，直接一步生成最终结果。
  - 训练时，学生模型可能通过某种对抗或分布匹配损失来模拟教师模型的隐式映射。
- **公式或算法**：摘要未给出明确公式，但从描述可知是一种基于分布对齐的蒸馏范式，避免直接模仿中间潜变量，而是关注最终输出的一致性。

## 3. 实验设计
- **数据集/场景**：
  - 真实世界超分辨率数据集：**RealSR、RealSet65、DRealSR、RealLR200、RealLQ250**
  - 合成（理想退化）数据集：**ImageNet、DIV2K**
  - 覆盖了多种退化类型，兼顾真实场景与经典基准。
- **Benchmark 与对比方法**：
  - 主要的加速扩散超分方法：**SinSR**（同为ResShift的蒸馏方法）、**OSEDiff** 等。
  - 还对比了基于预训练文本到图像模型（如Stable Diffusion等）的超分方法。
- **评估指标**：感知质量指标 **LPIPS、CLIPIQA、MUSIQ、DISTS、NIQE、MANIQA**，全面衡量细节保真度、自然度和图像质量。

## 4. 资源与算力
- 摘要及提供材料中**未明确说明**所使用的GPU型号、数量、训练时长或显存占用。
- 不过，文中提到“与基于预训练文本到图像模型的方法相比，RSD 需要更少的参数、GPU 内存和训练成本”，暗示其算力需求相对较低，但具体数值未知。

## 5. 实验数量与充分性
- **实验组数推测**：
  - 至少涉及 **7 个不同数据集**（RealSR、RealSet65、DRealSR、ImageNet、DIV2K、RealLR200、RealLQ250），每个数据集上对比了多种蒸馏方法和基线教师模型。
  - 另外进行了与文本到图像方法的横向比较，以及在不同感知指标上的评测。
- **充分性与公平性**：
  - 实验设计相当全面，涵盖真实与合成退化、多个感知指标，对比对象包括原版教师模型、同架构的蒸馏方法SinSR、其他加速方法以及完全不同的技术路线（T2I模型）。
  - 由于在不同退化类型和指标下均报告结果，具备较好的客观性与公平性。

## 6. 论文的主要结论与发现
- **主要结论**：
  - RSD可以实现**单步**超分辨率重建，在推理速度上远胜多步扩散的教师模型。
  - 在 **LPIPS、CLIPIQA、MUSIQ、DISTS、NIQE、MANIQA** 等感知指标上，RSD明显超越教师模型及SinSR，达到与当前最先进的扩散超分蒸馏方法相当的水平。
  - 与基于预训练T2I模型的方法相比，RSD在感知质量上具有竞争力，但参数量、GPU内存占用和训练成本更低。
  - RSD有效抑制了伪结构幻觉，产生的图像更真实、自然。

## 7. 优点
- **方法创新性**：独特的“伪造模型对齐”蒸馏思路，不从扩散中间步骤直接回归，而是关注生成图像的分布匹配，避免了常见的细节丢失和幻觉问题。
- **速度与质量平衡**：单步推理实现与教师模型可比甚至更优的感知质量，实用性高。
- **鲁棒性**：在真实世界和合成退化数据上均表现优异，泛化能力强。
- **资源友好**：相比大模型T2I方案，所需算力和存储更少，适合实际部署。
- **评价全面**：使用多种无参考和有参考感知指标，结论更具说服力。

## 8. 不足与局限
- **缺乏算力细节**：未披露训练成本的具体数据（GPU型号/小时），难以精确评估其效率优势。
- **仅限于ResShift架构**：方法特定于ResShift扩散模型，其蒸馏策略能否推广到其他扩散SR框架（如Stable Diffusion-based）尚不明确。
- **未提及局限性讨论**：供审阅的摘要中未指出方法的潜在缺点，例如极端退化下的鲁棒性、对训练数据的依赖程度或单步生成可能存在的平滑问题等。
- **可能缺少像素级保真度分析**：仅报告了感知指标，未提及PSNR/SSIM等保真度指标，无法判断是否存在过度锐化或纹理扭曲。
- **对比方法有限**：虽与SinSR和OSEDiff等比较，但未提及更广泛的单步GAN或流模型超分方法，基准的覆盖率可能仍有提升空间。

（完）
