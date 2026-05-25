---
title: Is Noise Conditioning Necessary for Denoising Generative Models?
title_zh: 去噪生成模型是否需要噪声条件？
authors: "Qiao Sun, Zhicheng Jiang, Hanhong Zhao, Kaiming He"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pTSWi6RTtJ"
tags: ["query:real-ir"]
score: 9.0
evidence: 研究无条件噪声的去噪生成模型
tldr: 该论文挑战了去噪扩散模型中噪声条件不可缺的观点，受盲图像去噪启发，探究了多种无噪声条件的去噪生成模型，发现大多数模型性能退化平滑甚至更优。作者提出一种无噪声条件模型，在CIFAR-10上取得2.23的FID，显著缩小了与有噪声条件模型的差距，证明噪声条件并非绝对必要。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 651, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 973, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 741, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 805, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 741, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 791, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 796, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1778, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1778, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1779, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ptswi6rttj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1202, \"height\": 1329, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 884, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 790, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 533, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 582, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1340, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1521, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 711, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 953, \"height\": 813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 1148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ptswi6rttj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1821, \"height\": 289, \"label\": \"Table\"}]"
motivation: 质疑噪声条件在去噪生成模型中的必要性，探索盲去噪背景下的替代方案。
method: 移除噪声条件，设计无噪声条件模型并进行数学误差分析。
result: 无噪声条件模型在CIFAR-10上达到FID 2.23，接近领先的有噪声条件模型。
conclusion: 噪声条件不是必须的，为生成模型设计提供了新思路。
---

## Abstract
It is widely believed that noise conditioning is indispensable for denoising diffusion models to work successfully. This work challenges this belief. Motivated by research on blind image denoising, we investigate a variety of denoising-based generative models in the absence of noise conditioning. To our surprise, most models exhibit graceful degradation, and in some cases, they even perform better without noise conditioning. We provide a mathematical analysis of the error introduced by removing noise conditioning and demonstrate that our analysis aligns with empirical observations. We further introduce a noise-*unconditional* model that achieves a competitive FID of 2.23 on CIFAR-10, significantly narrowing the gap to leading noise-conditional models. We hope our findings will inspire the community to revisit the foundations and formulations of denoising generative models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
现代去噪生成模型（如扩散模型、流匹配等）几乎普遍采用**噪声条件输入**（将当前噪声水平作为额外信息馈入神经网络），业界普遍认为这是模型成功的关键。

**本文挑战了这一固有认知**。受盲图像去噪研究的启发，作者系统性地探究了在**完全移除噪声条件**的情况下，各类去噪生成模型的表现。研究发现，大多数模型并不会崩溃，而是出现“优雅退化”（graceful degradation），甚至在基于流的模型中，去除噪声条件后性能反而有所提升。整体含义是：噪声条件并非生成模型工作的**必要条件**，这为重新审视该领域的基础范式与理论提供了有力依据。

### 2. 论文提出的方法论
核心思想是将各种去噪生成模型统一到一个相同的理论框架下，并分析去除噪声条件后的误差传播。具体包括以下部分：

- **统一形式化**：将去噪生成模型的训练损失重写为 `L = E[ w(t) || NN(z|t) - r(x,ε,t) ||^2 ]` 的形式，其中 `r` 为回归目标，`w(t)` 为权重。采样过程统一为迭代式 `x_{i+1} = κ_i x_i + η_i NN(x_i|t_i) + ζ_i ε̃_i`。该框架可以覆盖 iDDPM、DDIM、EDM、Flow Matching 等主流模型。
- **有效回归目标分析**：在无噪声条件时，神经网络 `NN(z)` 的唯一有效目标是 `R(z) = E_{t|z}[ R(z|t) ]`，即对所有可能的 `t` 取期望。作者证明了后验分布 `p(t|z)` 在高维数据下呈高度集中的狄拉克函数形态，其方差约为 `t_0^2/(2d)`（`d` 为数据维度）。因此，`R(z)` 与 `R(z|t)` 之间的单步误差 `E(z)` 极小（约为 `O(1)`，而目标范数为 `O(d)`）。
- **累积误差上界**：在迭代采样过程中，无噪声条件采样器与有条件采样器之间的最终误差被证明存在上界 `Σ A_i B_i`，其中 `A_i` 与调度 `κ_i`、`η_i` 以及目标函数的利普希茨常数相关，`B_i` 与回归误差 `δ_i` 有关。该上界可**不经过网络训练**，仅依靠模型调度与数据集统计量进行计算，且与实验观测高度吻合。
- **噪声无条件模型 uEDM**：基于上述分析，作者设计了一个专门面对无噪声条件场景的模型。它改造自 EDM，核心修改是将输出缩放系数 `c_out(t)` 固定为常数 1，从而让网络无需学习依赖 `t` 的缩放，降低误差上界。该模型称为 uEDM。

### 3. 实验设计
- **数据集与场景**：
    - **主要基准**：CIFAR-10 无条件类生成（class-unconditional）。
    - **额外验证**：ImageNet 32×32 无条件类生成、FFHQ 64×64 无条件类生成、CIFAR-10 条件类生成。
    - **大尺寸及引导**：ImageNet 256×256 上使用 SiT 模型搭配无分类器引导（CFG）进行验证。
- **对比方法**：涵盖多种去噪生成模型家族，包括 iDDPM (x‑pred 与 ϵ‑pred)、DDIM、ADM、EDM、Rectified Flow (1‑RF，即一种 Flow Matching)、iCT、ECM 以及作者提出的 uEDM。
- **评估指标**：以 **FID** 为主要质量指标，同时报告**函数评估次数（NFE）**。
- **公平性控制**：所有实验均基于作者重新实现（JAX/TPU），每种方法在有噪声条件和无噪声条件下保持完全一致的实现与超参数，仅修改噪声条件输入。

### 4. 资源与算力
- **计算平台**：主代码基于 **Google TPU v2 和 v3** 运算核心，使用 JAX 框架实现。
- **GPU 实验**：FFHQ 64×64 上的 EDM 实验使用 **8 块 H100 GPU**。
- **训练时长**：论文未明确给出总训练时长，但提供了各实验的训练步数与批量大小（如 EDM 训练 2 亿张图像，批量 512）。

### 5. 实验数量与充分性
- **实验组数**：至少涉及 **7 种模型架构、4 种数据集/任务设置**的对比，外加**消融研究**（误差界分析、随机性水平对 DDIM 的影响、替代噪声条件架构等），实验规模相当庞大。
- **充分性与客观性**：
    - 作者重新实现了所有对比方法，确保实验条件完全可控，排除了实现差异带来的偏差。
    - 实验设计客观、系统：进行了从理论误差界到实际 FID 的关联分析，并通过多种替代方案（如显式训练噪声预测器、联合训练无监督噪声预测器）验证了结果的一致性。
    - 唯一的潜在偏差是没有对无噪声条件模型单独调参，这可能导致其性能被低估（但也使比较更严格）。
- 总体而言，实验**非常充分且公平**。

### 6. 论文的主要结论与发现
- **噪声条件并非不可或缺**：绝大多数去噪生成模型在移除噪声条件后仍能正常工作，性能仅出现适度下降（黄色区域），并未发生灾难性崩溃。
- **流匹配模型表现更优**：基于流的模型（1‑RF）在无条件情况下 FID 甚至有所**提升**，表现出对噪声条件的高度不敏感。
- **模型崩溃可被理论预测**：理论误差上界与实验结果强烈相关，例如 DDIM + ODE 采样器的极高误差上界准确预言了其灾难性失效（FID 从 3.99 飙升至 40.90），而 SDE 采样器因随机性带来的误差抵消机制则表现平稳。
- **新模型缩小差距**：专门设计的 uEDM 在 CIFAR-10 上获得 FID **2.23**，大幅缩小了与最强噪声条件模型 EDM（FID 1.97~1.99）的差距。
- **替代噪声条件方案效果相似**：无论是预训练噪声水平预测器，还是端到端联合学习噪声信息，其最终表现与完全无噪声条件模型接近，说明误差本质上来源于 `p(t|z)` 中的不确定性。

### 7. 优点
- **理论创新**：提供了严密且易计算的误差上界，将去噪生成模型的鲁棒性分析从“黑箱经验”推向“白盒可预测”，方法论价值高。
- **挑战常识**：颠覆了“噪声条件必不可少”的普遍认知，可能引发对该领域基础原理的重新思考。
- **统一视角**：所提出的统一框架同时覆盖扩散、流匹配、一致性模型等，便于横向比较和理论推导。
- **实验完备**：不仅展示了现象，还通过理论推导、多种替代架构、CFG 大模型实验等进行了多维度验证，结论说服力强。
- **开辟新方向**：指出无噪声条件模型更符合经典能量模型（EBM）的朗之万动力学设置，为物理启发的生成模型设计提供了可能性。

### 8. 不足与局限
- **实验规模限制**：尽管进行了 256×256 实验，但主要探索仍集中在 CIFAR-10 等较小数据集上的无条件生成。在更大、更复杂的数据集（如高分辨率文本到图像）上，无噪声条件模型是否依然有效需进一步验证。
- **理论假设的理想性**：误差上界的推导中假设了利普希茨连续性且为最坏情况累加，在实际数据上需要以高概率形式的近似，其绝对数值（10²~10⁶）远大于实际图像范数，更多起相对预测作用。
- **uEDM 仍存在差距**：尽管 FID 2.23 非常接近 EDM，但仍有约 0.25 的差距，且未达到 SOTA 水平，说明无噪声条件设计在最优性能上尚有提升空间。
- **未针对无条件调参**：实验中无噪声条件模型直接沿用了有条件模型的超参数，如果进行专属调优，可能会进一步缩小差距或改变部分结论。

（完）
