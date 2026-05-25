---
title: Inverse Problem Sampling in Latent Space Using Sequential Monte Carlo
title_zh: 潜在空间中使用序列蒙特卡洛的逆问题采样
authors: "Idan Achituve, Hai Victor Habi, Amir Rosenfeld, Arnon Netzer, Idit Diamant, Ethan Fetaya"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mWKCajTUUu"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出在潜在空间中基于扩散模型的图像逆问题采样方法
tldr: 针对扩散模型在图像逆问题中条件采样困难且受自动编码器变换影响的问题，提出在潜在空间使用序列蒙特卡洛的新采样方法。该方法有效处理编码器-解码器带来的额外难度，为利用扩散模型解决图像复原等逆问题提供了稳定推理途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 820, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 752, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1216, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1174, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 815, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1352, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1501, \"height\": 1162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1531, \"height\": 1768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 708, \"height\": 1646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mwkcajtuuu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 708, \"height\": 1661, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1645, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1645, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1285, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1135, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1126, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1141, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1139, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1138, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1139, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1137, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1140, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1138, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mwkcajtuuu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1139, \"height\": 461, \"label\": \"Table\"}]"
motivation: 扩散模型在逆问题中条件采样复杂，潜在空间变换引入额外困难。
method: 提出基于序列蒙特卡洛的方法，在潜在空间进行逆问题采样。
result: 实现了在潜在空间稳定且有效的条件采样。
conclusion: 该方法为基于扩散模型的逆问题求解提供了新方案。
---

## Abstract
In image processing, solving inverse problems is the task of finding plausible reconstructions of an image that was corrupted by some (usually known) degradation operator. Commonly, this process is done using a generative image model that can guide the reconstruction towards solutions that appear natural. The success of diffusion models over the last few years has made them a leading candidate for this task. However, the sequential nature of diffusion models makes this conditional sampling process challenging. Furthermore, since diffusion models are often defined in the latent space of an autoencoder, the encoder-decoder transformations introduce additional difficulties. To address these challenges, we suggest a novel sampling method based on sequential Monte Carlo (SMC) in the latent space of diffusion models. We name our method LD-SMC. We define a generative model for the data using additional auxiliary observations and perform posterior inference with SMC sampling based on a backward diffusion process. Empirical evaluations on ImageNet and FFHQ show the benefits of LD-SMC over competing methods in various inverse problem tasks and especially in challenging inpainting tasks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：在图像处理中，逆问题（如去模糊、超分辨率、修复等）旨在从退化的观测 $y = \mathcal{A}(x) + \psi$ 中恢复出自然图像 $x$。由于逆问题通常是不适定的，需要结合先验分布 $p(x)$ 来获得合理的解。
- **核心挑战**：扩散模型作为强大的先验，采样过程是序贯的（$p(x_{t-1}|x_t)$），而条件观测仅在最终步（$p(y|x_0)$），直接采样 $p(x_0|y)$ 非常困难。此外，主流的高效模型通常运作在自编码器的潜在空间（Latent Diffusion Models, LDM），编解码器的非线性变换使得原有的近似或滤波方法失效。
- **研究动机**：已有基于序列蒙特卡洛（SMC）的方法或仅考虑线性模型，或依赖 $p(y|\mathbb{E}[x_0|x_t])$ 近似，无法兼顾全局语义与局部细节。本文提出一种结合辅助观测与SMC的新方法，在潜在空间中实现更准确的后验采样。

### 2. 方法论
#### 2.1 核心思想
- 建立一个生成模型：引入辅助观测序列 $y_{1:T}$，每个 $y_t$ 直接由扩散过程的中间隐变量 $z_t$ 通过解码器和退化算子生成，即 $y_t \sim \mathcal{N}(\mathcal{A}(\mathcal{D}(z_t)), \tau^2 I)$。
- 利用吉布斯采样交替更新 $(y_{1:T}, z_{0:T})$，其中对 $z_{0:T}$ 的采样通过 SMC 进行。

#### 2.2 关键技术细节
- **初始化**：通过优化 $\min_x \|y_0 - \mathcal{A}(x)\|^2$ 获得初始 $x_0$，编码后得到 $z_0$，再通过DDIM前向过程生成初始的 $z_{1:T}$。
- **SISR采样 (SMC)**：
    - **目标分布近似**：假设 $p_\theta(z_{t:T}|y_{0:T}) \approx p_\theta(z_{t:T}|y_{t:T}, y_0)$，并利用后验均值估计 $\bar{z}_0(z_t)$ 构造 $\bar{p}_\theta(y_0|z_t)$。
    - **权重递推**：
        - $t=T$：$w_T \propto \frac{p_\theta(y_T|z_T) \bar{p}_\theta(y_0|z_T) p_\theta(z_T)}{\pi_T(z_T)}$
        - $0<t<T$：$w_t \propto \frac{p_\theta(y_t|z_t) \bar{p}_\theta(y_0|z_t) p_\theta(z_t|z_{t+1})}{\bar{p}_\theta(y_0|z_{t+1}) \pi_t(z_t|z_{t+1})} w_{t+1}$
        - $t=0$：$w_0 \propto \frac{p_\theta(y_0|z_0) p_\theta(z_0|z_1)}{\bar{p}_\theta(y_0|z_1) \pi_0(z_0|z_1)} w_1$
    - **提议分布**：$\pi_t(z_t|z_{t+1}) = \mathcal{N}(m_t, S_t)$，其中 $S_t = \tilde{\sigma}_{t+1}^2 I$，均值 $m_t = \mu_\theta(z_{t+1}, t+1) - \gamma_t \nabla_{z_{t+1}} \log \bar{p}_\theta(y_0|z_{t+1}) - \lambda_t \nabla_{\mu} \log q_\theta(y_t|z_{t+1})$。通过超参数 $s$ 控制两个修正项的激活时机，前期主要靠 $y_0$ 指导全局结构，后期加入 $y_t$ 修正细节。
- **理论性质**：定理4.1表明，当粒子数 $N \to \infty$ 时，SMC的离散测度收敛于目标后验 $p_\theta(z_{0:T}|y_{0:T})$，且吉布斯采样的平稳分布即为 $p_\theta(z_0, y_{1:T}|y_0)$。

#### 2.3 算法流程
1. 通过最小化数据一致性误差获得初始 $z_0$。
2. 前向生成 $z_{1:T}$ 和 $y_{1:T}$。
3. 迭代执行：对 $y_{1:T}$ 重采样，然后通过SISR (筛选、提议、加权、重采样) 更新 $z_{0:T}$。

### 3. 实验设计
- **数据集**：ImageNet 256$\times$256 和 FFHQ 256$\times$256，均采用对应的潜在扩散模型（VQ-4/CIN256-V2）。
- **任务**：Box修复、自由形式修复、高斯去模糊、8$\times$超分辨率。
- **对比方法**：共7种基于扩散模型的逆问题求解方法：
    - LDPS：DPS在潜在空间的自适应版本。
    - LTDS：TDS (Twisted Diffusion Sampling) 的潜在空间版。
    - ReSample：引入中间优化与重采样。
    - PSLD：在DPS基础上增加编解码一致性项。
    - PFLD：基于PSLD更新的粒子滤波方法。
    - LatentDAPS：解耦潜变量路径的去噪退火方法。
    - LD-SMC (本文)：1粒子和5粒子版本。
- **评估指标**：FID（主要）、NIQE、LPIPS 作为感知质量指标；PSNR、SSIM作为失真指标（见附录）。

### 4. 资源与算力
- **硬件**：主要使用 NVIDIA A100（40GB或80GB显存）。
- **计算开销**：
    - 文中报告了各方法的平均单图采样时间和显存占用（表4），例如：
        - LDPS：~105.5秒，8.1GB
        - LD-SMC (1粒子)：~136.3秒，9.2GB
        - LD-SMC (5粒子)：~537.2秒，21.2GB
        - ReSample：~333.4秒，5.8GB
    - 成本随粒子数和吉布斯迭代线性增加，1粒子即可在耗时接近LDPS的情况下取得提升。
- **模型训练**：使用预训练模型，无额外训练过程。

### 5. 实验数量与充分性
- **任务覆盖**：2个数据集 × 4类逆问题任务，共计8种主要场景，每个场景测试1024张固定图像。
- **对比基线**：与7种近期强方法在同一框架下比较（均使用相同的预训练LDM，统一添加噪声标准差 $\tau=0.01$）。
- **消融与分析**：
    - 探究超参数 $s$（激活细节修正的时间）对FID/PSNR的权衡（图5a）。
    - 粒子数 $N$ 的影响（图5b）。
    - 吉布斯迭代次数对FID/PSNR的影响（图6）。
    - 不同提议分布（朴素先验、DPS式提议与LD-SMC提议）的比较（表5）。
    - 辅助变量 $y_t$ 在不同时间的演化可视化（图7）。
- **公平性**：所有方法均在统一潜在扩散模型上运行，超参数通过网格搜索调优至最佳FID。实验设计客观且对比充分。

### 6. 主要结论与发现
- LD-SMC在多项任务上，尤其是修复任务中，显著提升了感知质量（FID、NIQE、LPIPS），且能保持较好的失真指标。
- 在更具挑战性的ImageNet数据集上，LD-SMC对基线方法的优势更加明显（如 box 修复 FID 从 64.74 降至 50.67）。
- 通过引入辅助观测 $y_{1:T}$ 并结合两个修正项（全局与细节），LD-SMC在图像修复等需要外推的任务中达成了一致性和真实感的更好平衡。
- 即使仅使用1个粒子和1次吉布斯迭代，也能取得具有竞争力的结果，展示了方法的有效性和一定的效率。

### 7. 优点
- **新颖的融合思路**：首次将辅助观测序列与SMC结合用于潜在扩散模型的逆问题求解，有效结合了“后验均值近似”（TDS）与“观测增强”（FPS）两者的优势。
- **针对性强**：专门解决潜在空间中解码器非线性带来的困难，适用范围更广。
- **理论保证**：给出了在粒子数趋于极限时采样趋向真实后验的证明，增强了方法的理论基础。
- **实际改善显著**：在修复任务等多模态性强、需要外推的场景中，大幅超越DPS、PSLD等专门为LDM设计的方法。
- **控制平衡的手段**：通过时间开关参数 $s$ 可灵活调控全局语义与局部细节的贡献，且1粒子版本计算成本可控。

### 8. 不足与局限
- **计算开销**：虽1粒子成本尚可，但多粒子或多吉布斯步骤会显著增加采样时间与显存消耗（线性增长），距离实时应用尚有距离。
- **超参数敏感性**：方法涉及 $\kappa_1, \kappa_2, s, \rho$ 等多个超参数，需针对不同任务谨慎调节。
- **理论假设**：收敛性证明依赖于解码器和扩散模型梯度的有界性等条件，实践中可能不总能严格满足（如网络不光滑时）。
- **任务覆盖**：仅测试了高斯退化和4种经典任务，缺少泊松噪声、相位恢复等更复杂的非线性退化场景的评估。
- **对比方法限制**：STSL等更新方法因代码未公开未能直接比较；且所有对比使用固定的预训练LDM，未探索更强的扩散模型骨干。

（完）
