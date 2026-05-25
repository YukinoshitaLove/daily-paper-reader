---
title: A Mixture-Based Framework for Guiding Diffusion Models
title_zh: 一种引导扩散模型的混合框架
authors: "Yazid Janati, Badr MOUFAD, Mehdi Abou El Qassime, Alain Oliviero Durmus, Eric Moulines, Jimmy Olsson"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=HIOA3bScFB"
tags: ["query:real-ir"]
score: 7.0
evidence: 扩散模型贝叶斯逆问题中的混合分布后验采样
tldr: 针对扩散模型在贝叶斯逆问题中后验采样存在难解似然的问题，提出一种基于混合分布的近似框架，并利用吉布斯采样实现可处理的推断。该方法可在不重新训练的情况下用于图像复原等逆问题，扩展了扩散模型的应用范围。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 801, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1752, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 317, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1520, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1318, \"height\": 1143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1724, \"height\": 2020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1730, \"height\": 2015, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1730, \"height\": 1349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1728, \"height\": 2016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1727, \"height\": 2014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1731, \"height\": 1348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1730, \"height\": 1347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1729, \"height\": 1347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1495, \"height\": 2360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1494, \"height\": 2348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1494, \"height\": 2357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1494, \"height\": 2347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1494, \"height\": 2363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1493, \"height\": 2349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1494, \"height\": 2361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1493, \"height\": 2348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1495, \"height\": 2358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1492, \"height\": 2353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1493, \"height\": 2346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1495, \"height\": 2366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1495, \"height\": 2362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hioa3bscfb/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1494, \"height\": 2366, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 807, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 511, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1057, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1681, \"height\": 1750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1681, \"height\": 1757, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1148, \"height\": 1738, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1661, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hioa3bscfb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1591, \"height\": 283, \"label\": \"Table\"}]"
motivation: 扩散模型用于逆问题时，后验分布难以处理。
method: 用混合分布近似中间后验，通过吉布斯采样进行梯度采样。
result: 在贝叶斯逆问题上验证了方法的有效性。
conclusion: 为扩散模型在通用逆问题中的应用提供了新的概率框架。
---

## Abstract
Denoising diffusion models have driven significant progress in the field of Bayesian inverse problems. Recent approaches use pre-trained diffusion models as priors to solve a wide range of such problems, only leveraging inference-time compute and thereby eliminating the need to retrain task-specific models on the same dataset. To approximate the posterior of a Bayesian inverse problem, a diffusion model samples from a sequence of intermediate posterior distributions, each with an intractable likelihood function. This work proposes a novel mixture approximation of these intermediate distributions. Since direct gradient-based sampling of these mixtures is infeasible due to intractable terms, we propose a practical method based on Gibbs sampling. We validate our approach through extensive experiments on image inverse problems, utilizing both pixel- and latent-space diffusion priors, as well as on source separation with an audio diffusion model. The code is available at \url{https://www.github.com/badr-moufad/mgdm}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：在贝叶斯逆问题（如图像复原、音源分离）中，利用预训练的去噪扩散模型（Denoising Diffusion Models, DDMs）作为先验进行后验采样时，存在一个关键瓶颈：扩散过程中的中间后验分布包含一个难以直接计算的似然项，其梯度无法解析获得，这导致必须使用启发式且不稳定的近似。
- **研究动机**：现有无需重新训练（training-free）的扩散模型引导方法（如DPS, PGDM等）通常采用粗糙的近似来估计该似然项，这常需要大量调参和启发式技巧（如重缩放）来保证稳定性和性能，尤其是在潜空间扩散模型中挑战更大。因此，亟需一种更严格、性能更优的方法来应对此难题。
- **整体含义**：本文旨在提出一个原则化的概率框架，以更准确地逼近这些中间后验分布，从而为利用扩散模型求解通用逆问题提供一种更可靠、性能可随计算资源扩展的采样策略。

### 2. 论文提出的方法论

- **核心思想**：摒弃以往直接且粗糙地近似中间时刻`t`的似然，而是提出一种**混合分布近似**策略。该策略观察到，对于时刻`t`的难解似然，可以利用任意更早时刻`s < t`的似然，通过前向扩散核`p_{s|t}`的期望形式，构造出`t-1`个不同的近似版本。将这些近似版本通过加权混合，构建对`t`时刻中间后验分布`\hat{\pi}_t^y`的近似。
- **关键技术细节与算法流程**：
    1.  **混合模型构建**：对每个中间时刻`t`，定义其后验分布的混合近似：`\hat{\pi}_t^y(x_t) := \sum_{s=1}^{t-1} \omega_s^t \hat{\pi}_s^t(x_t)`，其中`\hat{\pi}_s^t(x_t)`是基于`\hat{g}_s(y|x_s)`（`s`时刻的近似似然）和扩散正向核的加权范式定义的。
    2.  **数据增强与吉布斯采样（Gibbs Sampling）**：由于混合分量`\hat{\pi}_s^t`及其得分函数仍不可直接计算，论文提出一个聪明的数据增强策略。引入辅助变量`x_0`和`x_s`，构造一个联合分布`\pi^y_{0,s,t}(x_0, x_s, x_t)`，使得`\hat{\pi}_s^t`是其`x_t`的边际分布。
    3.  **可行的吉布斯更新**：该联合分布的三个完全条件分布具有简洁且可处理的形式：
        -   `\pi^y_{t|0,s}(x_t|x_0, x_s)`：即简单的正向加噪过程`q_{t|s}(x_t|x_s)`。
        -   `\pi^y_{0|s,t}(x_0|x_s, x_t)`：还原为原始先验扩散模型的后验`p_{0|s}(x_0|x_s)`，可用预训练模型精确或近似采样（去噪步骤）。
        -   `\pi^y_{s|0,t}(x_s|x_0, x_t)`：这是唯一涉及观测似然的项，正比于`\hat{g}_s(y|x_s) q_{s|0,t}(x_s|x_0,x_t)`。此分布虽非标准形式，但可通过变分推断，用一个高斯分布`\mathcal{N}(\mu, \text{diag}(e^\rho))`来近似，通过最小化KL散度，并用重参数化技巧估计梯度进行优化。
    4.  **算法步骤（MGDM算法）**：
        - 从纯噪声开始，循环处理一系列设定的时间步`t_i`。
        - 对每个`t_i`，从`{1, \dots, t_i-1}`中先采样一个混合索引`s`。
        - 执行`R`步吉布斯采样：交替地（a）通过优化的高斯变分近似采样`x_s`（融入观测信息）；（b）通过前向核采样`x_t`（加噪）；（c）通过预训练扩散模型的后向去噪步骤采样`x_0`。
        - 将最后更新的`x_0`作为当前迭代的输出，并传递给下一个时间步作为“运行估计”`\hat{X}_0^*`。

### 3. 实验设计

- **使用数据集与场景**：
    - **图像逆问题**：FFHQ (256x256)、ImageNet (256x256) 和 FFHQ的潜空间扩散模型（Latent Diffusion Model, LDM）。
    - 任务涵盖6个线性逆问题（如：4x/16x超分、中心/半图修补、高斯/运动去模糊）和4个非线性逆问题（如：JPEG去压缩、相位检索、非线性模糊、HDR重建）。
    - **音频源分离**：在Slakh2100测试集上，利用一个多乐器（贝斯、鼓、吉他、钢琴）音频扩散模型，从混合音轨中分离各个乐器声。
- **基准对比方法**：
    - 像素空间扩散：DPS, PGDM, DDNM, DiffPIR, RED-DIFF, DAPS, PNP-DM。
    - 潜空间扩散：PSLD, ReSample, DAPS, PNP-DM。
    - 音频分离：MSDM, ISDM, Demucs-512。
- **评估指标**：对图像任务，报告LPIPS（主要）、FID、PSNR和SSIM。对音频任务，报告SI-SDRi（尺度不变的信噪比改善）。

### 4. 资源与算力

- **说明**：论文在第19页（附录B.5）明确指出，所有实验均在**Nvidia Tesla V100 SXM2 GPU**上进行。但文中**未提及**具体使用的GPU**数量**，也未报告除推理时间外的任何**训练时长**信息（因为该方法本身是无训练的，仅需要预训练好的扩散模型）。推理时间的对比见附录B.7。

### 5. 实验数量与充分性

- **实验数量**：
    - **主实验**：在2个数据集（FFHQ像素、ImageNet）上测试了10个图像逆问题任务，并在1个潜空间数据集（FFHQ LDM）上测试了10个任务，共与7-8种方法进行了对比。
    - **扩展实验**：在Slakh2100上进行了1个音频源分离任务，与5种方法对比。还进行了高噪声（σ_y=0.3）和泊松噪声似然下的实验。
    - **消融与分析实验**：包含对吉布斯步数`R`的消融研究（在图像相位检索和音频分离任务上）、不同时间采样分布`μ`对性能影响的对比、以及单个参数（如吉布斯步数、梯度步数）影响的分析。还提供了大量视觉对比的样例画廊。
- **充分性与公平性**：
    - 实验覆盖广泛，从像素到潜空间，从图像到音频，从线性到非线性，从低噪到高噪，较为充分。
    - 对比方法均为领域内最新的代表性工作。
    - 关键的是，作者强调对MGDM的超参数是**按数据集而非按任务**进行调整的，且在公平的噪声设置下复现或细致调优了所有对比方法的超参数，这在很大程度上保证了对比的客观性与公平性。

### 6. 论文的主要结论与发现

- **性能卓越**：MGDM在绝大多数任务上（尤其是在最综合的感知指标LPIPS上）取得了第一或第二的最佳结果，是唯一在所有任务上都保持强劲竞争力的方法。
- **潜空间通用性**：该方法可无需任何修改地“即插即用”于潜空间扩散模型，并显著优于专门为潜空间设计的PSLD和ReSample等方法。
- **计算可扩展性**：算法性能可通过增加吉布斯采样步数`R`来单调提升，展示了一种有效的“推理时计算扩展（inference-time compute scaling）”特性，且此扩展比单纯增加梯度优化步数更高效。
- **定性优越**：生成的样本在保持多样性的同时，视觉上更连贯、清晰，相比在高PSNR/SSIM上占优的方法（如DDNM, DiffPIR），能在感知上更贴近真实图像。

### 7. 优点

- **方法论创新与原则性**：提出了一种新颖的混合分布视角和配套的吉布斯采样方案，为训练-自由引导提供了一个更优雅、更严格的概率框架。
- **性能优越且鲁棒**：在大量任务上实现了最优或次优性能，且性能随计算资源增加而提升的规律明确，没有在特定任务上表现不稳定。
- **极强的通用性**：方法无缝适配于像素空间和潜空间的扩散模型，以及图像和音频等不同数据模态，展示出作为通用逆问题求解器的潜力。
- **实现相对简洁**：核心算法（算法2）流程清晰，主要利用了预训练模型和标准优化/采样技术，没有引入过多复杂的重缩放启发式。
### 8. 不足与局限

- **计算与内存开销**：在像素空间运行时，MGDM相较于DPS等方法速度较慢（但在潜空间中更快），且因为需要计算向量-雅可比乘积，内存消耗高于无条件扩散，这是一个有待优化的问题。
- **超参数敏感性**：混合权重序列`ω`和时间步采样分布`μ`的选择对性能有显著影响，但当前的选择（如均匀采样）是基于经验观察，缺乏自适应的、以数据驱动的选择策略，是该框架的一个局限性。
- **采样器兼容性**：方法论基于SDE的随机微分方程采样（DDPM），不直接适用于基于常微分方程（ODE）的确定型采样器（如DDIM），这限制了其在更广泛生成范式中的应用。
- **理论分析**：论文主要以实证为主，对吉布斯采样链的混和速率、对混合近似的误差界等缺乏深入的理论分析。

（完）
