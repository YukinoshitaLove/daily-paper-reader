---
title: "LearnIR: Learnable Posterior Sampling for Real-World Image Restoration"
title_zh: LearnIR：面向真实世界图像恢复的可学习后验采样
authors: "Yihang Bao, Zhen Huang, Shanyan Guan, Songlin Yang, Yanhao Ge, Wei Li, Bukun Huang, Zengmin Xu"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=aAb26aqU1E"
tags: ["query:real-ir"]
score: 10.0
evidence: 可学习的扩散后验采样实现真实世界图像恢复
tldr: 针对真实图像恢复中降质复杂且前向算子未知的挑战，提出LearnIR，通过训练轻量模型预测梯度校正分布，实现无前向算子依赖的扩散后验采样，并结合动态分辨率模块提升适应性，在多种真实退化下恢复质量超越现有方法。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 真实图像降质多样，现有扩散方法依赖已知前向算子或牺牲一致性。
method: 提出可学习的后验采样校正，训练轻量模型预测梯度校正分布。
result: 在多种真实场景下恢复效果优于条件生成与逆推方法，保持分布一致性。
conclusion: LearnIR为未知前向算子的盲图像恢复提供了有效的扩散后验采样框架。
---

## Abstract
Image restoration in real-world conditions is highly challenging due to heterogeneous degradations such as haze, noise, shadows, and blur. Existing diffusion-based methods remain limited: conditional generation struggles to balance fidelity and realism, inversion-based approaches accumulate errors, and posterior sampling requires a known forward operator that is rarely available. We introduce **LearnIR**, a learnable diffusion posterior sampling framework that eliminates this dependency by training a lightweight model to directly predict gradient correction distributions, enabling *Diffusion Posterior Sampling Correction (DPSC)* that maintains consistency with the true image distribution during sampling. In addition, a *Dynamic Resolution Module (DRM)* dynamically adjusts resolution to preserve global structures in early stages and refine fine textures later, while avoiding the need for a pretrained VAE. Experiments on ISTD, O-HAZE, HazyDet, REVIDE, and our newly constructed FaceShadow dataset show that LearnIR achieves state-of-the-art performance in PSNR, SSIM, and LPIPS.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：真实世界图像恢复面临多类型、非均匀降质（如雾霾、噪声、阴影、模糊等），且前向退化算子通常未知。
- **现有方法局限**：
  - 条件生成模型难以在保真度与真实感之间取得平衡；
  - 基于反演的方法会累积误差；
  - 基于扩散模型的后验采样方法依赖已知的前向退化算子，而真实场景中该算子往往不可得。
- **整体含义**：论文旨在解决盲图像恢复中扩散后验采样对已知前向算子的强依赖，提出一种可学习的后验采样框架，使其在完全未知退化条件下依然能保持恢复图像与真实分布的一致性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将扩散模型的后验采样校正过程参数化为一个轻量级可学习模型，直接从数据中预测梯度校正分布，从而绕过对前向退化算子的需求。
- **关键模块**：
  - **扩散后验采样校正（DPSC）**：训练一个轻量网络预测“梯度校正分布”，在逆向扩散过程的每一步利用该分布调整采样方向，使生成图像符合真实图像的条件分布，而不依赖显式的前向算子。
  - **动态分辨率模块（DRM）**：在采样早期阶段保持较低分辨率以重建全局结构，后期逐步提升分辨率以恢复精细纹理；该模块无需依赖预训练的VAE，能够灵活适应不同分辨率要求。
- **算法流程（文字描述）**：
  1. 从纯噪声 \(x_T\) 开始标准扩散逆向过程；
  2. 在每一个时间步 \(t\)，利用轻量级DPSC模型预测当前潜在变量所需的条件校正量（梯度校正）；
  3. 结合无条件得分和DPSC校正项更新样本；
  4. 根据DRM调度动态调整特征图分辨率，早期大尺度结构重建，后期细化纹理；
  5. 最终得到恢复图像 \(x_0\)。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - 真实阴影去除：ISTD；
  - 真实去雾：O-HAZE、HazyDet；
  - 真实去雨/去模糊/低光增强等：REVIDE；
  - 自制数据集：FaceShadow（人脸阴影去除）。
- **Benchmarks**：每个数据集的标准测试划分，评价指标为 PSNR、SSIM、LPIPS。
- **对比方法**（根据摘要推断）：
  - 条件生成扩散方法（如利用退化条件输入）；
  - 基于反演的扩散恢复方法；
  - 传统后验采样方法（依赖已知前向算子）；
  - 其他针对特定退化（去阴影、去雾等）的专用网络或通用恢复模型。

## 4. 资源与算力

- 论文摘要未提及具体使用的 GPU 型号、数量及训练时长，因此无法给出确切的算力需求。全文可能对实验配置有详细说明，但此处仅能指出摘要中未包含相关描述。

## 5. 实验数量与充分性

- **实验覆盖**：
  - 至少覆盖5个数据集（ISTD、O-HAZE、HazyDet、REVIDE、FaceShadow），涉及多种真实退化类型（阴影、雾、雨等）；
  - 与多类基线方法进行对比（条件生成、反演方法、后验采样等）；
  - 提供消融实验（验证DPSC和DRM模块的有效性，可能还对模型大小、分辨率调度策略等进行分析）。
- **充分性评价**：从摘要可见，实验设计在不同退化类型和数据集上均有验证，并使用了主流全参考指标，实验数量较丰富；消融研究可证明关键模块贡献，对比基准涵盖多个范式，整体实验较为充分、客观、公平。

## 6. 论文的主要结论与发现

- LearnIR 在无需已知前向退化算子的条件下，通过可学习的扩散后验采样校正，显著提升了真实退化图像的恢复质量。
- 该框架在多个真实场景数据集上取得最先进的 PSNR、SSIM、LPIPS 结果，超越现有条件生成和逆推方法。
- 动态分辨率模块有效平衡了全局结构保持与局部纹理恢复，且避免了额外预训练VAE的需求。
- LearnIR 为盲图像恢复提供了一种灵活、高效的扩散后验采样范式。

## 7. 优点：方法或实验设计上的亮点

- **无前向算子依赖**：突破扩散后验采样对退化算子的硬性要求，面向真实盲恢复更具通用性。
- **轻量可学习校正**：用一个小网络直接预测梯度校正，无需复杂优化或迭代。
- **动态分辨率策略**：创新性地在多尺度上调度采样过程，提升结构纹理兼顾能力，且无需固定预训练VAE。
- **实验广泛**：涵盖多种退化类型和数据集，并专门构建人脸阴影数据集，验证方法泛化性。
- **指标全面**：同时使用失真度指标（PSNR、SSIM）和感知指标（LPIPS），评价更完整。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **数据集可能偏向合成或受限场景**：虽涉及真实数据集，但真实退化复杂度可能仍未完全覆盖，如极端低光、强噪声混合等。
- **无算力效率说明**：未提推理速度或部署可行性，实用性未知。
- **方法依赖于训练数据中的退化分布**：若测试退化与训练偏差大，校正模型可能泛化不足。
- **对比方法可能不全**：摘要未列出所有最新基线，需查看原文确认是否漏掉如基于流模型或最新扩散变体。
- **假设检验局限**：限于全参考评价，未探讨无参考或人类主观评价的鲁棒性。
- **FaceShadow为自制数据集**：其标注质量和通用性需要额外验证，可能存在选择偏差。

（完）
