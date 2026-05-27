---
title: "Kernel Density Steering: Inference-Time Scaling via Mode Seeking for Image Restoration"
title_zh: 核密度引导：基于模式搜索的图像修复推断时缩放方法
authors: "Yuyang Hu, Kangfu Mei, Mojtaba Sahraee-Ardakan, Ulugbek S. Kamilov, Peyman Milanfar, Mauricio Delbracio"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=hDx3pFaYeH"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用扩散模型推断时方法进行图像修复
tldr: 现有扩散模型在图像修复中常出现保真度不一致和伪影问题。本文提出核密度引导（KDS）推断框架，通过N粒子集成和逐块核密度估计梯度，引导样本趋向共享高密度区域，避免陷入伪影。实验表明该方法在不增加训练的情况下显著提升修复质量，为扩散模型推断提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 900, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1418, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 976, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1363, \"height\": 1864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1366, \"height\": 1738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1368, \"height\": 1796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1346, \"height\": 2269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 1418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1439, \"height\": 1374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdx3pfayeh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1435, \"height\": 1418, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1469, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 672, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 657, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1366, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 735, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 737, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1362, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1189, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 982, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 956, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 925, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdx3pfayeh/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 905, \"height\": 238, \"label\": \"Table\"}]"
motivation: 扩散模型在图像修复中保真度不稳定且易产生伪影，亟需改进推断过程。
method: 采用N粒子集成，利用核密度估计梯度指导各粒子局部模式搜索。
result: 在多个基准上实现更鲁棒、高保真的修复输出，有效抑制伪影。
conclusion: 证明集体模式搜索可提升扩散模型图像修复的可靠性。
---

## Abstract
Diffusion models show promise for image restoration, but existing methods often struggle with inconsistent fidelity and undesirable artifacts. To address this, we introduce Kernel Density Steering (KDS), a novel inference-time framework promoting robust, high-fidelity outputs through explicit local mode-seeking. KDS employs an $N$-particle ensemble of diffusion samples, computing patch-wise kernel density estimation gradients from their collective outputs. These gradients steer patches in each particle towards shared, higher-density regions identified within the ensemble. This collective local mode-seeking mechanism, acting as "collective wisdom", steers samples away from spurious modes prone to artifacts, arising from independent sampling or model imperfections, and towards more robust, high-fidelity structures. This allows us to obtain better quality samples at the expense of higher compute by simultaneously sampling multiple particles. As a plug-and-play framework, KDS requires no retraining or external verifiers, seamlessly integrating with various diffusion samplers. Extensive numerical validations demonstrate KDS substantially improves both quantitative and qualitative performance on challenging real-world super-resolution and image inpainting tasks.

---

## 论文详细总结（自动生成）

好的，以下是对给定论文《核密度引导：基于模式搜索的图像修复推断时缩放方法》的结构化、深入、客观的中文总结。

## 论文总结：核密度引导（KDS）

### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：扩散模型在图像修复（如超分辨率和图像修复）中展现出巨大潜力，但现有方法常面临两个问题：
    - **保真度不稳定**：生成的图像虽然感知上清晰，但可能与真实图像存在较大结构偏差（高失真）。
    - **易产生伪影**：独立采样或模型缺陷导致样本落入“虚假模式”（spurious modes），产生不自然的纹理或颜色失真。
- **核心问题**：如何在保留扩散模型生成高感知质量图像能力的同时，提升修复结果的保真度和鲁棒性，避免伪影？
- **整体含义**：本文提出一种新的推断时框架，通过对多个并行采样的粒子进行集体模式搜索，引导它们趋向于共享的高密度区域，从而实现更鲁棒、更保真的图像修复。该方法无需重新训练模型或依赖外部验证器，是一种即插即用的增强方案。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用 $N$ 个独立采样的粒子（扩散样本）构成一个集成，通过核密度估计（KDE）隐式地估计当前样本集在潜在空间中的密度分布。然后计算密度梯度（即均值漂移向量），将每个粒子的预测结果向局部高密度区域（即多数粒子达成共识的区域）引导，从而抑制假性模式，提升输出的稳健性和保真度。
- **关键技术细节**：
    1.  **N粒子集成**：同时运行 $N$ 个扩散采样过程，每个过程从不同的初始噪声开始，最终得到 $N$ 个预测的干净隐变量 $\{\hat{\mathbf{z}}^{(i)}_0\}_{i=1}^N$。
    2.  **逐块核密度估计（Patch-wise KDE）**：
        - 直接对高维的完整隐变量进行KDE需要指数级增长的粒子数，不可行。因此，KDS 采用逐块策略：将每个预测的干净隐变量 $\hat{\mathbf{z}}^{(i)}_0$ 分解成不重叠的块（patch）。
        - 对于每个空间位置的块，从所有 $N$ 个粒子中提取对应的块组成一个局部块集成 $\mathcal{P}_j = \{\mathbf{p}_j^{(k)}\}_{k=1}^N$。
        - 在这个低维的局部块空间中进行KDE，并计算均值漂移向量，指向该块集成的局部密度模式。
    3.  **均值漂移向量计算**：对于粒子 $i$ 在位置 $j$ 的块 $\mathbf{p}^{(i)}_j$，其均值漂移向量为：
        \[
        \mathbf{m}(\mathbf{p}^{(i)}_j) = \frac{\sum_{k=1}^{N} G\left(\frac{\|\mathbf{p}^{(i)}_j - \mathbf{p}^{(k)}_j\|^2}{h^2}\right) \mathbf{p}^{(k)}_j}{\sum_{k=1}^{N} G\left(\frac{\|\mathbf{p}^{(i)}_j - \mathbf{p}^{(k)}_j\|^2}{h^2}\right)} - \mathbf{p}^{(i)}_j
        \]
        其中 $G$ 为高斯核函数，$h$ 为带宽。
    4.  **引导粒子更新**：用漂移向量更新当前块：
        \[
        \hat{\mathbf{p}}^{(i),\text{KDS}}_j \leftarrow \mathbf{p}^{(i)}_j + \delta_t \mathbf{m}(\mathbf{p}^{(i)}_j)
        \]
        其中 $\delta_t$ 是随时间步变化的引导强度（在早期噪声大时不进行引导，后期逐渐开启）。
    5.  **集成到扩散采样器**：在每一步去噪中，先得到预测的干净隐变量 $\hat{\mathbf{z}}^{(i)}_{0|t}$，然后应用上述KDS过程得到修正后的 $\hat{\mathbf{z}}^{(i),\text{KDS}}_{0|t}$。最后基于修正后的预测来计算下一步的隐状态。该过程可无缝集成到DDIM、DPM-Solver++等采样器中。
    6.  **最终粒子选择**：在推理结束后，从 $N$ 个KDS引导后的隐变量中，选择最接近所有样本平均值的一个，解码为最终图像。

- **算法流程（文字说明）**：
    1.  初始化 $N$ 个随机潜变量 $\mathbf{z}^{(i)}_T$。
    2.  对于时间步 $t = T$ 到 $1$：
        a. 得到 $N$ 个粒子的噪声预测。
        b. 计算每个粒子的预测干净潜变量 $\hat{\mathbf{z}}^{(i)}_{0|t}$。
        c.  应用逐块KDS：
            i. 将每个 $\hat{\mathbf{z}}^{(i)}_{0|t}$ 划分为不重叠的块。
            ii. 对于每个块位置，收集所有粒子的块组成集成。
            iii. 为每个粒子的块计算均值漂移向量，并应用引导更新。
            iv. 重组所有更新后的块，得到修正后的干净预测 $\hat{\mathbf{z}}^{(i),\text{KDS}}_{0|t}$。
        d. 基于 $\hat{\mathbf{z}}^{(i),\text{KDS}}_{0|t}$ 执行一步扩散采样（如DDIM步骤），得到下一时刻的 $\mathbf{z}^{(i)}_{t-1}$。
    3.  从 $N$ 个最终的 $\hat{\mathbf{z}}^{(i),\text{KDS}}_{0}$ 中选择最靠近平均值的那个，解码得最终图像。

### 3. 实验设计
- **任务**：真实世界图像超分辨率（4×）和中心区域图像修复。
- **数据集**：
    - **超分辨率**：DIV2K（合成低分辨率）、RealSR、DRealSR（真实世界低分辨率）、DF2K（更复杂的合成退化）。
    - **图像修复**：ImageNet 验证集（前1000张），中心遮罩30%区域。
- **骨干模型**：
    - 超分辨率：LDM-SR, DiffBIR, SeeSR。
    - 图像修复：基于Stable Diffusion v2微调的LDM inpainting模型。
- **对比方法**：
    - **基线**：不带KDS的标准DDIM/DPM-Solver++采样。
    - **同行方法**：High Density Sampling (HDS)、Density-Guided Sampling (DGS)、Best-of-N (BoN) 选择（使用LIQE、CLIPIQA作为选择标准）。
- **评价指标**：PSNR, SSIM, LPIPS, FID, NIMA, DISTS, MANIQA, CLIPIQA。

### 4. 资源与算力
- **明确说明**：论文在表格4中提及了计算时间和内存消耗（例如，对于DiffBIR，N=1时7.9秒/8.0GB；N=10时28.4秒/10.4GB），表明KDS的计算开销随粒子数线性增加。
- **未明确说明**：论文**没有**明确说明训练或测试所使用的具体GPU型号、数量以及总训练时长。实验中使用的预训练模型是公开的，KDS本身是推理时方法，不涉及额外训练。因此，资源报告主要围绕推理时间而非训练。

### 5. 实验数量与充分性
- **实验组数**：实验非常丰富。
    - **主实验**：在超分辨率（3个骨干 × 3个数据集）和图像修复（1个骨干 × 2个采样器）上均进行了对比，总计约10组定量表格。
    - **消融研究**：深入探究了粒子数 $N$、带宽 $h$、块大小、核函数、引导强度 $\delta_t$ 等超参数的影响，以及自动带宽选择的有效性。提供约5组消融表格。
    - **对比分析**：与HDS/DGS进行了详细超参扫描对比（1表格）；与Best-of-N方法进行对比（2表格）；分析了与无分类器引导（CFG）的交互（1表格）。
    - **鲁棒性分析**：展示了KDS对最差粒子的改善作用。
- **充分性与公平性**：
    - **充分性**：实验覆盖了多个任务、多个骨干网络、多种采样器，并进行了详尽的消融和对比，能够支撑论文的主要结论。定量和定性结果均提供。
    - **公平性**：实验均注明“使用相同的初始噪声”进行对比。消融实验系统地改变单一变量。统计显著性检验（$P<0.05$）在部分表格中标记。方法**没有**与InDI等方法在同一设置下（如相同骨干）进行完全公平比较（InDI需要特定训练），但在论文中进行了概念性讨论。总体而言，实验设计较为客观和严谨。

### 6. 主要结论与发现
- KDS作为一种无需重训练、即插即用的推断时框架，能**显著提升**扩散模型在图像修复中的**保真度**（PSNR、SSIM）和**感知质量**（LPIPS、FID），同时**减少伪影**。
- KDS的有效性在于其集体的局部模式搜索机制：通过将粒子引导向多粒子集成的共识区域，有效抑制了由独立采样引入的假性模式。
- KDS的逐块设计使其能够实用地应用于高维潜空间，且性能随粒子数 $N$ 增加而提升（存在收益递减点）。
- 与基于外部验证器的Best-of-N方法相比，KDS在同等计算成本下表现更优，证明其**从内部引导生成**的策略比**事后挑选**更有效。
- 带宽 $h$ 是关键的权衡超参数：较小 $h$ 可保持局部细节但可能不够鲁棒；较大 $h$ 能提升保真度但可能模糊感知细节。自动带宽选择（如中位数启发式）可达到接近手动调优的效果。

### 7. 优点
1.  **新颖且简洁的方法论**：将均值漂移和核密度估计与扩散模型采样过程有机结合，思想直观且理论动机清晰。
2.  **即插即用，无需训练**：KDS是纯推断时方法，可轻松应用于现有预训练模型和多种采样器，实用性强。
3.  **有效平衡感知-失真权衡**：在不牺牲感知质量的前提下，显著提升了修复结果的保真度，优于许多需要额外训练或外部模型的方法。
4.  **提升鲁棒性**：能有效压制伪影，使最差情况下的输出也得到改善，增强了扩散模型的可靠性。
5.  **实验充分、结果扎实**：在多个主流设置下进行了系统性的验证，并提供详尽的消融研究，结论可信度高。

### 8. 不足与局限
1.  **计算开销**：KDS需要同时采样 $N$ 个粒子，计算时间和内存消耗随 $N$ 线性增长。虽然 $N=10$ 已带来显著收益，但对于资源受限的场景仍有一定门槛。论文未探索轻量化变体（如自适应粒子数）。
2.  **超参数敏感性**：核心超参数——带宽 $h$、引导强度 $\delta_t$ 和块大小——需要调节。虽然自动带宽选择有效，但其他参数可能在不同任务或退化类型下需要重新调整，论文缺乏自动化的超参数搜索或域自适应探讨。
3.  **应用范围有限**：实验仅覆盖了超分辨率和图像修复。对于其他逆问题（如去模糊、去噪）或视频/3D图像修复的适用性尚未验证。论文虽在2D玩具例子上验证了概念，但缺乏更广泛的应用实证。
4.  **潜在偏差**：在最终粒子选择时，选择最靠近集成的平均值的样本，可能偏向于“保守”的估计，在某些极低分辨率或复杂纹理场景下可能会牺牲极端但有价值的细节。
5.  **与基线对比范围**：虽然与HDS/DGS等模式搜索方法进行了对比，但未与同样优化感知-失真权衡的其他推断时方法（如基于SMC的采样器、扩散后处理去噪）进行充分的定量比较，部分对比只是概念性讨论。

（完）
