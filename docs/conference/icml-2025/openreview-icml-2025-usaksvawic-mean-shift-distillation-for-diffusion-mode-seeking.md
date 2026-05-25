---
title: Mean-Shift Distillation for Diffusion Mode Seeking
title_zh: 扩散模式搜索的均值偏移蒸馏
authors: "Vikas Thamizharasan, Nikitas Chatzis, Iliyan Georgiev, Matthew Fisher, Difan Liu, Nanxuan Zhao, Evangelos Kalogerakis, Michal Lukáč"
date: 2025-01-10
pdf: "https://openreview.net/pdf?id=USAKSVAwIc"
tags: ["query:real-ir"]
score: 6.0
evidence: 引入均值偏移蒸馏，一种改进模式搜索并可替代分数蒸馏采样的扩散蒸馏技术
tldr: 本文提出均值偏移蒸馏，一种新型扩散蒸馏技术，通过从均值偏移模式搜索中导出分布梯度，替代分数蒸馏采样（SDS），无需重新训练模型。在文本到图像和三维生成任务中，该方法展示了更优的模式对齐和收敛性，输出更逼真的结果，简化了扩散模型的应用。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1744, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1704, \"height\": 1027, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 756, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 815, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-usaksvawic/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1643, \"height\": 1633, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-usaksvawic/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-usaksvawic/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 340, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-usaksvawic/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 644, \"height\": 279, \"label\": \"Table\"}]"
motivation: 现有分数蒸馏采样存在模式对齐不佳和收敛慢的问题。
method: 提出均值偏移蒸馏，通过模式搜索导出梯度，作为SDS的直接替代。
result: 在文本到图像和三维生成中实现了更高的保真度和更快的收敛。
conclusion: 均值偏移蒸馏是一种有效的扩散蒸馏改进方法。
---

## Abstract
We present *mean-shift distillation*, a novel diffusion distillation technique that provides a provably good proxy for the gradient of the diffusion output distribution. This is derived directly from mean-shift mode seeking on the distribution, and we show that its extrema are aligned with the modes. We further derive an efficient product distribution sampling procedure to evaluate the gradient.

Our method is formulated as a drop-in replacement for score distillation sampling (SDS), requiring neither model retraining nor extensive modification of the sampling procedure. We show that it exhibits superior mode alignment as well as improved convergence in both synthetic and practical setups, yielding higher-fidelity results when applied to both text-to-image and text-to-3D applications with Stable Diffusion.

---

## 论文详细总结（自动生成）

### 1. 核心问题与研究动机
现有扩散蒸馏方法（如分数蒸馏采样 SDS）在利用预训练扩散模型优化图像生成时，存在明显的**梯度估计偏差**和**高方差**问题。具体表现为：
- SDS 的优化目标与真实数据分布的模式（modes）**不一致**，甚至在简单场景下会产生“虚假模式”。
- 收敛过程因梯度估计方差大而变得困难，容易导致结果模糊、细节丢失。
这些问题限制了蒸馏技术在文本到二维图像及文本到三维生成等任务中的表现。

### 2. 方法论：均值偏移蒸馏（Mean-Shift Distillation, MSD）
论文提出一种直接源自**均值偏移模式搜索**的扩散蒸馏方法，作为 SDS 的即插即用替代。

- **核心思想**：通过构建平滑密度的均值偏移向量，获得与真实分布梯度**方向一致**的代理，且该向量的极值点与分布模式重合。
- **梯度代理推导**：
  - 对数据密度 \( p \) 用高斯核 \( G_\lambda \) 卷积得到平滑密度 \( p^*_\lambda \)。
  - 令 \( \nabla_{\mathbf{x}} p^*_\lambda(\mathbf{x}) = 0 \)，导出均值偏移迭代公式
    \[
    \mathbf{x}' = \frac{\int \mathbf{y} G_\lambda(\mathbf{x}-\mathbf{y}) p(\mathbf{y}) d\mathbf{y}}{\int G_\lambda(\mathbf{x}-\mathbf{y}) p(\mathbf{y}) d\mathbf{y}}.
    \]
  - **均值偏移向量** \( \mathbf{m}(\mathbf{x}) = \mathbf{x}' - \mathbf{x} \propto p^*_\lambda(\mathbf{x}) \nabla p^*_\lambda(\mathbf{x}) \)，因此沿该向量移动即可提升似然。
- **乘积分布采样**：
  - 将均值偏移的积分视作对乘积分布 \( \dot{p}_\lambda(\mathbf{y}|\mathbf{x}) \propto p(\mathbf{y}) G_\lambda(\mathbf{x}-\mathbf{y}) \) 的期望。
  - 利用扩散模型采样时修改分数函数：
    \[
    \nabla_{\mathbf{z}_t} \log \dot{p}_\lambda(\mathbf{y}|\mathbf{x}) = \nabla_{\mathbf{z}_t} \log p(\mathbf{z}_t) - \frac{\mathbf{x} - \mathbf{z}_t}{\lambda^2}.
    \]
  - 实际中用单样本估计，得到更新方向 \( \mathbf{m}(\mathbf{x}) \approx \mathbf{y} - \mathbf{x} \)。
- **稳定化实现**：
  - 将核项的积分解耦为解析指数衰减项：
    \[
    \mathbf{z}_{t+\Delta t} = \mathbf{y} + (\mathbf{z}'_{t+\Delta t} - \mathbf{y}) e^{\Delta t / \lambda^2},
    \]
    以缓解显式积分器在分数幅度过大时的不稳定性。
  - 引入分类器自由制导（CFG）并与有限区间应用核项等启发式策略配合。

### 3. 实验设计
论文通过**合成数据**和**真实模型**两组实验验证方法，并与 SDS、SDI 等基线对比。

- **数据集/场景**：
  - 2D 合成数据：分形（Fractal）、螺旋（Spiral）、风车（Pinwheel）玩具分布，用于可视化模式对齐与梯度行为。
  - 文本到 2D：用 Stable Diffusion 优化坐标基 MLP 生成的图像，不采用像素直接表示，以保证与 DDIM 采样的公平比较。
  - 文本到 3D：用 NeRF 参数化体素，优化生成三维物体。
- **对比方法**：SDS、SDI（重参数化 DDIM 的改进版），以及 DDIM 直接采样作为上限参考。
- **评价指标**：
  - 2D 合成：负对数似然（NLL）、生成精度/召回率、最大均值差异（MMD）、梯度估计效率（归一化均方误差与代价之比）。
  - 文本到 2D：FID（以 DDIM 生成图像为参考）、CLIP 相似度（CLIP-SIM）。

### 4. 资源与算力
- **硬件**：实验在**单块 NVIDIA A100 GPU** 上完成。
- **框架**：使用 PyTorch 和 threestudio 框架实现。
- **优化参数**：Adam 优化器，学习率 0.01；文本到 2D 优化 400 步，文本到 3D 优化 7000 步。
- 文中未明确给出总训练时长或单次迭代耗时。

### 5. 实验数量与充分性
- **实验组数**：覆盖 **3 种 2D 玩具分布**（含理想去噪器和学习去噪器两种设定）以及 **2 种真实应用**（文本到 2D、文本到 3D），各应用下均与两个基线对比。
- **消融分析**：
  - 带宽 \(\lambda\) 对采样过程的影响分析（图 6）。
  - 稳定化策略（限制制导区间、噪声缩放）的定性消融（图 8）。
- **充分性评价**：2D 合成实验能系统性揭示梯度偏差和方差问题，但真实模型实验规模较小（主观测评居多，缺少大规模标准化基准）。整体设计对核心主张提供了足够支撑，但在泛化性验证上稍显不足。

### 6. 主要结论与发现
- 均值偏移蒸馏（MSD）的梯度代理在理论上**严格对齐**平滑密度的梯度，其极值点逼近真实分布模式。
- 相比于 SDS，MSD **模式对齐更优**，避免了虚假模式，且**梯度估计方差更低**。
- 在文本到图像和文本到三维任务中，MSD 生成结果的**保真度**（FID）和**图文一致性**（CLIP-SIM）均优于 SDS 和 SDI。
- 收敛过程可通过带宽 \(\lambda\) 的单调递减自然地实现，并形成清晰的**终止判据**。

### 7. 优点
- **理论扎实**：将均值偏移与扩散输出分布梯度建立直接联系，优化方向有明确保证。
- **即插即用**：完全兼容现有 SDS 流程，无需重新训练扩散模型或大幅修改代码。
- **估计效率高**：虽然单次估计需要更多评分函数调用，但效率（方向正确性/代价）远高于 SDS。
- **终止条件明确**：带宽衰减至低值时，优化结果趋于稳定，可自动停止。

### 8. 不足与局限
- **数值稳定性依赖启发式**：在高维真实模型中，核项和评分项幅度过大，必须借助有限区间制导、噪声缩放等技巧，增加了调参负担。
- **带宽调度敏感**：\(\lambda\) 的衰减方案对最终质量有重要影响，文中未提供自动选取方法。
- **实验验证规模有限**：真实模型部分仅使用了 Stable Diffusion 一种骨干，且文本提示数量较少（约 10 个）；3D 任务只有定性对比。
- **计算开销**：单步需要运行完整的 DDIM 逆过程，比 SDS 更耗时，尽管效率更高，但绝对速度未作优化。
- **理论与实践的差距**：从理想去噪器到学习去噪器的迁移中，部分理想性质有所折损（如模式召回率下降）。

（完）
