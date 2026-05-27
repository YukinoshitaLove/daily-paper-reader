---
title: "Proper Hölder-Kullback Dirichlet Diffusion: A Framework for High Dimensional Generative Modeling"
title_zh: Proper Hölder-Kullback Dirichlet扩散：高维生成建模框架
authors: "Wanpeng Zhang, Yuhao Fang, Xihang Qiu, Jiarong Cheng, Jialong Hong, Bin Zhai, Qing Zhou, Yao Lu, Ye Zhang, Chun Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=G3r4nJXcpU"
tags: ["query:real-ir"]
score: 8.0
evidence: 提出基于Hölder-Kullback散度的新扩散框架
tldr: 扩散模型长期依赖高斯先验，本文提出了Proper Hölder-Kullback Dirichlet扩散框架，使用新的散度替代传统ELBO，在无条件CIFAR-10上达到FID 2.78，证明了非高斯先验在高维生成建模中的潜力，为扩散模型先验设计开辟了新方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 1440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 1444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 1441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3r4njxcpu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 1440, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1391, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1400, \"height\": 604, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1399, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1396, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1385, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3r4njxcpu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 182, \"label\": \"Table\"}]"
motivation: 扩散模型过度依赖高斯先验，缺乏对其他分布探索。
method: 提出利用时变乘法变换定义Dirichlet扩散过程，并引入Proper Hölder和PHK散度进行优化。
result: 在CIFAR-10无条件生成上取得FID 2.78。
conclusion: 非高斯先验在扩散模型中具有潜力，新散度框架可提升生成质量。
---

## Abstract
Diffusion-based generative models have long depended on Gaussian priors, with little exploration of alternative distributions. We introduce a Proper Hölder-Kullback Dirichlet framework that uses time-varying multiplicative transformations to define both forward and reverse diffusion processes. Moving beyond conventional reweighted evidence lower bounds (ELBO) or Kullback–Leibler upper bounds (KLUB), we propose two novel divergence measures: the Proper Hölder Divergence (PHD) and the Proper Hölder–Kullback (PHK) divergence, the latter designed to restore symmetry missing in existing formulations. When optimizing our Dirichlet diffusion model with PHK, we achieve a Fréchet Inception Distance (FID) of 2.78 on unconditional CIFAR-10. Comprehensive experiments on natural-image datasets validate the generative strengths of model and confirm PHK’s effectiveness in model training. These contributions expand the diffusion-model family with principled non-Gaussian processes and effective optimization tools, offering new avenues for versatile, high-fidelity generative modeling.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：扩散模型长期依赖高斯先验，对非高斯分布的探索十分有限，限制了模型的表达能力和适用范围。
- **背景**：已有的非高斯扩散模型（如 Beta 扩散）只能独立处理一维坐标，无法捕捉高维单纯形（simplex）中各维度之间的依赖关系；传统的 KL 散度存在不对称性和高计算复杂度的问题。
- **整体含义**：该论文旨在突破高斯先验的局限，提出一种基于 Dirichlet 分布和新型散度的扩散框架，以更自然地建模单纯形结构的数据（如归一化图像、成分数据），从而提升生成模型的保真度和多样性。

## 2. 论文提出的方法论

- **核心思想**：利用时变乘法变换定义 **前向** 和 **反向** Dirichlet 扩散过程，取代传统的加性高斯噪声；并引入 **Proper Hölder Divergence (PHD)** 和 **Proper Hölder–Kullback (PHK) 散度** 作为训练目标，替代传统的 ELBO 或 KLUB。
- **关键技术细节**：
  - 将 Beta 扩散推广到 **K 维 Dirichlet 扩散**，使得每个噪声步都保持单纯形结构。
  - 前向过程：\( \mathbf{z}_t | \mathbf{x}_0 \sim \text{Dir}(\eta \alpha_t \mathbf{x}_0, \ldots, \eta \frac{1}{K-1}(1 - \alpha_t \mathbf{x}_0)) \)。
  - 反向过程：通过学习预测 \( \hat{\mathbf{x}}_0 \) 的神经网络 \( f_\theta(\mathbf{z}_t, t) \) 来近似 \( \mathbb{E}[\mathbf{x}_0 | \mathbf{z}_t] \)。
  - 损失函数：PHD 具有闭式解且是严格 proper 的，PHK 是 PHD 与 KLUB 的加权组合，用于恢复对称性并提高训练稳定性。
  - 理论证明：PHD 的梯度方差比 HPD（Hölder 统计伪散度）更低，从而提升训练效率。
- **算法流程**（文字说明）：
  - **训练**：从数据集中采样 mini-batch，随机选取时间步 \( t \)，计算前向 Dirichlet 噪声样本 \( \mathbf{z}_t \)，通过网络预测 \( \hat{\mathbf{x}}_0 \)，计算 PHD/PHK 损失并反向传播更新参数。
  - **采样**：从均匀先验（初始化为期望值）开始，迭代应用反向更新规则：\( \mathbf{z}_{t_{j-1}} = \mathbf{z}_{t_j} + (1 - \mathbf{z}_{t_j}) \mathbf{p}_{(t_{j-1} \leftarrow t_j)} \)，其中 \( \mathbf{p} \) 由预测的 \( \hat{\mathbf{x}}_0 \) 和 Dirichlet 参数计算得到。

## 3. 实验设计

- **使用数据集**：CIFAR-10（32×32, 无条件生成）、FFHQ（64×64）、AFHQ（64×64）、CVUSA（街景到卫星图像）等。
- **Benchmark 与对比方法**：
  - 对比方法包括传统 **Gaussian 扩散**（DDPM、NCSNv2、VDM、Improved DDPM、TDPM+ 等）、**确定性扩散**（Cold Diffusion、Inverse Heat Dispersion）、**分类扩散**（D3PM）、**泊松扩散**（JUMP）、**Beta 扩散**等。
  - 主要评价指标：Fréchet Inception Distance (FID)，越低越好。
- 实验结果：所提方法在 **无条件 CIFAR-10** 上取得 **FID 2.78**，超越所有先前非高斯扩散模型，并超过大部分高斯基线。

## 4. 资源与算力

- **明确说明**：训练使用 **4 块 Nvidia L40S GPU**。
- 训练规模：处理 2 亿张 CIFAR-10 图像，batch size=512 时约需 **64 小时**（PHK 损失），PHD 约 61 小时，KLUB 约 70 小时。
- 采样时间：NFE=2000 时 4 块 GPU 约需 6 小时 9 分钟。
- 补充细节：附录 Table 7-9 给出了不同 batch size 和 NFE 下的详细训练及采样时间。

## 5. 实验数量与充分性

- **实验数量**：
  - 主对比实验（Table 1）：在 CIFAR-10 上与 16 种方法对比。
  - 消融实验（Table 2）：测试不同损失（−ELBO、KLUB、PHD、PHK）在不同 NFE（20~2000）和 batch size（512/288）下的 FID。
  - 额外参数分析（Table 5-6）：不同浓度参数 \( \eta \)、权重系数 \( \delta,\epsilon \) 对性能的影响。
  - 多种数据集（FFHQ、AFHQ、CVUSA）的定性结果展示及定量对比（CVUSA 的 FID/LPIPS，Table 4）。
- **充分性与客观性**：
  - 对比基线覆盖面广（高斯与非高斯），且均采用相同或官方设置。
  - 实验设计系统，考虑了不同 NFE、batch size、超参数组合。
  - **局限性**：作者明确指出，受限于计算资源，未对所有超参数进行全面网格搜索；且未在更大尺度数据集（如 ImageNet）上验证，因此最优性能可能未充分挖掘。

## 6. 论文的主要结论与发现

- **主要结论**：提出的 Proper Hölder-Kullback Dirichlet Diffusion（PHK-Dirichlet）在无条件 CIFAR-10 上达到 **FID 2.78**，创下非高斯扩散模型的新纪录，且优于多数高斯基线。
- **重要发现**：
  - PHD 由于是严格 proper 的散度，训练梯度方差更低，训练更稳定。
  - PHK（PHD 与 KLUB 的组合）进一步提升了性能，并节约约 **9% 的训练时间** 相比纯 KLUB。
  - 可视化表明，Dirichlet 扩散过程同时执行噪声和掩码操作，与高斯扩散有本质区别。

## 7. 优点

- **理论创新**：首次将 Dirichlet 分布引入扩散模型，并设计严格 proper 的 Hölder 散度，提供了可靠的优化信号。
- **梯度方差分析**：严格证明了 PHD 比 HPD 梯度方差更低，确保了训练稳定性。
- **闭式损失函数**：对于 Dirichlet 分布，PHD 和 PHK 均有解析表达式，无需蒙特卡洛采样。
- **实验结果优秀**：在非高斯框架下达到 SOTA，且说明非高斯先验在高维生成中的巨大潜力。
- 代码已开源，便于复现和扩展。

## 8. 不足与局限

- **超参数敏感**：模型对 \( \eta \)、Shift、Scale 等参数敏感，现有实验未覆盖所有可能的组合。
- **训练成本高**：处理 2 亿 CIFAR-10 图像需约 64 小时（4 × L40S），大规模超参数调优负担重。
- **数据集规模有限**：仅测试了中小型数据集（CIFAR-10 / FFHQ / AFHQ / CVUSA），未在 ImageNet 等高分辨率、大规模数据集上验证。
- **彻底性不足**：作者承认未针对 Dirichlet 扩散专门优化网络架构，性能可能仍有提升空间。
- **统计显著性**：未报告误差棒或置信区间，无法评估结果的稳定性。

（完）
