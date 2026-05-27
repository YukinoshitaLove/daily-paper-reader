---
title: Simple Distillation for One-Step Diffusion Models
title_zh: 一步扩散模型的简单蒸馏方法
authors: "Huaisheng Zhu, Teng Xiao, Shijie Zhou, Zhimeng Guo, Hangfan Zhang, Siyuan Xu, Vasant G Honavar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NHw8muIAcL"
tags: ["query:real-ir"]
score: 8.0
evidence: 面向一步生成扩散模型的蒸馏方法
tldr: 现有扩散模型采样速度慢，本文提出对比能量蒸馏（CED）方法，通过对比学习将多步扩散模型蒸馏为高效的一步生成器。实验表明该方法在保持生成质量的同时显著加速采样，简化了训练流程，为加速扩散模型采样提供了新的有效途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 671, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1391, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 692, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhw8muiacl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 973, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhw8muiacl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1391, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhw8muiacl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 687, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhw8muiacl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 651, \"height\": 1059, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhw8muiacl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 800, \"height\": 1057, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhw8muiacl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 521, \"height\": 247, \"label\": \"Table\"}]"
motivation: 扩散模型迭代采样慢，现有蒸馏方法性能下降或训练复杂。
method: 提出对比能量蒸馏，利用对比学习将多步扩散模型蒸馏为一步生成器。
result: 在保持生成质量的同时，实现一步采样，大幅提升速度。
conclusion: CED是一种简单有效的加速扩散模型采样的蒸馏方法。
---

## Abstract
Diffusion models have established themselves as leading techniques for image generation. However, their reliance on an iterative denoising process results in slow sampling speeds, which limits their applicability to interactive and creative applications. An approach to overcoming this limitation involves distilling multistep diffusion models into efficient one-step generators. However, existing distillation methods typically suffer performance degradation or require complex iterative training procedures which increase their complexity and computational cost. In this paper, we propose Contrastive Energy Distillation (CED), a simple yet effective approach to distill multistep diffusion models into effective one-step generators. Our key innovation is the introduction of an unnormalized joint energy-based model (EBM) that represents the generator and an auxiliary score model. CED optimizes a Noise Contrastive Estimation (NCE) objective to efficiently transfers knowledge from a multistep teacher diffusion model without additional modules or iterative training complexity. We further show that CED implicitly optimizes the KL divergence between the distributions modeled by the multistep diffusion model and the one-step generator. We present results of experiments which demonstrate that CED achieves competitive performance with the representative baselines for distilling multistep diffusion models while maintaining excellent memory efficiency.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：扩散模型虽在图像生成中效果卓越，但依赖迭代去噪过程，导致采样速度极慢（通常需要数十甚至数百步），限制了其在交互式、创意等实时应用中的使用。
- **已有尝试**：现有加速方法分为两类——基于分数的蒸馏（需额外辅助模型和迭代训练，复杂度高、GPU开销大）和基于轨迹的蒸馏（虽然轻量但一步生成时性能下降明显）。
- **本文目标**：设计一种简单、高效且有效的蒸馏算法，将多步扩散模型转化为一步生成器，无需额外辅助模型和迭代训练，同时保持生成质量。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：提出对比能量蒸馏（Contrastive Energy Distillation，CED），利用未归一化的联合能量模型（Joint Energy-Based Model, EBM）同时建模生成器和一个辅助分数模型（fake score model）。通过噪声对比估计（Noise Contrastive Estimation, NCE）优化目标，从多步教师扩散模型高效蒸馏知识。
- **关键技术细节**：
  - 定义联合分布 \( p_{\theta,\phi}(x|z) \propto p_{\text{fake},\phi}(x|z) \exp(-E(x, G_\theta(z))) \)，其中 \( E \) 衡量生成样本与分数模型样本之间的差异（如 LPIPS-Huber 距离）。
  - 训练目标：使用 NCE 形式的对比损失，正样本来自教师模型 \( p_{\text{real}} \)，负样本来自上一轮生成器 \( G_{\theta'} \)。
  - 损失函数：\( L_{\text{CED}} = \mathbb{E}_{x\sim p_{\text{real}}}[\log(1+e^{E})] + \mathbb{E}_{x'\sim G_{\theta'}}[\log(1+e^{-E})] \)。
  - 理论证明：CED 隐式优化了 DMD 中的 KL 散度，简化了传统两阶段训练（奖励模型 + RL）的流程。
- **算法流程**（Algorithm 1）：
  1. 用教师模型初始化一步生成器 \( G_{\theta} \)。
  2. 从教师模型采样合成图像作为正样本。
  3. 热身训练：最小化能量函数得到中间生成器 \( G_{\theta'} \)，并用其生成负样本。
  4. 构建三元组 \( (x, x', z) \)，利用 \( L_{\text{CED}} \) 训练最终生成器。

## 3. 实验设计
- **数据集与场景**：
  - CIFAR-10（32×32）用于无条件生成。
  - ImageNet（64×64）用于条件生成。
- **基准模型**：使用 EDM（Karras et al.）作为教师扩散模型。
- **对比方法**：分为五类——原始扩散模型（DDPM、EDM）、GANs（BigGAN、StyleGAN2）、带教师和假分数模型的蒸馏（Diff-Instruct、DMD、SiD）、仅带教师模型的蒸馏（TRACT、CD、PD、RECTIFIED FLOW）、仅带学生模型的蒸馏（本文 CED 两个变体 CED-DRE 和 CED）。
- **评估指标**：FID（Frechet Inception Distance）、IS（Inception Score），以及 ImageNet 上的 Precision 和 Recall。
- **实验数量**：主实验在 CIFAR-10 和 ImageNet 上进行，结果显示在表 2 和表 3 中。此外，进行了消融实验（不同距离函数、不同损失函数）、训练步数分析（图 2）、生成图像质量案例研究（图 4）以及更多可视化（附录 C）。总共至少 4 组实验：主结果两组、消融两组、步数分析一组、定性分析一组。

## 4. 资源与算力
- 论文在附录 B.1 中说明：使用 2 块 NVIDIA A100 GPU，CIFAR-10 有效 batch size = 512，ImageNet 有效 batch size = 1024，学习率 3e-5，热身训练 10000 步。
- 未明确给出完整训练时长（具体小时数），但提及 CED 在 CIFAR-10 上 100k 步达到较好结果，ImageNet 上 40k 步达到较好结果，相比之下 CD 需要 800k/600k 步。

## 5. 实验数量与充分性
- **数量**：主实验覆盖两个代表性数据集，消融实验覆盖距离函数（L2、L1、Pseudo-Huber、LPIPS-Huber）和损失函数（Logistic、Hinge、Brier、Exponential），以及训练步数分析。实验设计相对全面。
- **充分性与公平性**：
  - 遵循了领域标准评估协议（生成 50k 样本计算 FID/IS）。
  - 对比方法分类清晰，包含了主流基线。
  - 但未报告多次运行的标准差或置信区间（论文中仅报告单次结果，未提及误差条），可能影响统计显著性。
  - 未在更大规模数据集（如 ImageNet 256×256 或文本到图像）上实验，范围有限。

## 6. 主要结论与发现
- CED 在 CIFAR-10 上达到 FID 2.96（变体 CED-DRE 为 2.95），在 ImageNet 64×64 上达到 FID 4.06（CED-DRE 为 3.88）。
- 超越仅使用教师模型的蒸馏方法（如 CD、PD、TRACT、RECTIFIED FLOW），在性能与内存效率之间取得更好平衡。
- 与需要三个模型同时加载的方法（DMD、SiD）相比，CED 仅需加载学生模型，内存减少约 66%，且无需迭代训练多个组件，训练简单。
- 消融实验表明：LPIPS-Huber 距离函数优于 L2/L1；Logistic 和 Hinge 损失函数效果最佳。

## 7. 优点
- **简单高效**：无需额外辅助模型或迭代训练，训练流程简化。
- **理论联系**：证明了 CED 隐式优化 KL 散度，与分布匹配蒸馏目标一致，具有理论基础。
- **内存友好**：训练时仅需加载学生模型，大幅降低 GPU 内存消耗（相比 DMD/SiD 节省 2/3）。
- **收敛快**：相比 CD 等需要数十万步的方法，CED 在 40k-100k 步内即达到竞争性能。
- **扩展性好**：自然支持多种损失函数和距离度量，可灵活适配。

## 8. 不足与局限
- **实验规模**：仅在 CIFAR-10 和 ImageNet 64×64 上验证，未在更大分辨率（如 256×256）或文本到图像模型上测试，泛化性有待验证。
- **性能上限**：在 ImageNet 上不如 SOTA 方法 SiD（FID 1.52），差距约 2.5 分，可能源于缺少迭代更新带来的分布匹配精度。
- **无统计显著性**：未报告多次实验的标准差，结果鲁棒性未明确。
- **应用限制**：当前仅聚焦图像生成，未扩展到音频、3D、分子设计等其他领域（在附录 D 中作为局限提及）。
- **假设依赖**：方法有效性依赖于能量函数的设计（如 LPIPS-Huber 距离），不同距离函数敏感度较高，需谨慎选择。

（完）
