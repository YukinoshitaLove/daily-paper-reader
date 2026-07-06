---
title: Reconciling Stochastic and Deterministic Strategies for Zero-shot Image Restoration using Diffusion Model in Dual
title_zh: 双域使用扩散模型调和零样本图像恢复中的随机与确定性策略
authors: "Wang, Chong, Guo, Lanqing, Fu, Zixuan, Yang, Siyuan, Cheng, Hao, Kot, Alex C., Wen, Bihan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_Reconciling_Stochastic_and_Deterministic_Strategies_for_Zero-shot_Image_Restoration_using_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 零样本图像恢复结合扩散模型与即插即用策略
tldr: 针对扩散模型零样本图像恢复中感知质量与数据保真度失衡的问题，提出一种融合扩散随机采样与确定性即插即用策略的方法，在保持细节的同时提升数据一致性，实验结果表明其优于纯扩散或纯PnP方法。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1763, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 779, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1792, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 542, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1800, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1799, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-reconciling-stochastic-and-deterministic-strategies-for-zero-shot-image-restoration-using-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 298, \"label\": \"Table\"}]"
motivation: 扩散模型恢复图像感知质量好但牺牲保真度，PnP保真度高但细节不足。
method: 提出双域调和策略，将扩散随机采样与确定性PnP统一于图像恢复。
result: 在零样本恢复任务上实现感知质量与数据保真度的平衡，优于单一策略。
conclusion: 该方法为扩散模型在图像恢复中的实际应用提供了更优的质量-保真度权衡。
---

## Abstract
Plug-and-play (PnP) methods offer an iterative strategy for solving image restoration (IR) problems in a zero-shot manner, using a learned discriminative denoiser as the implicit prior. More recently, a sampling-based variant of this approach, which utilizes a pre-trained generative diffusion model, has gained great popularity for solving IR problems through stochastic sampling. The IR results using PnP with a pre-trained diffusion model demonstrate distinct advantages compared to those using discriminative denoisers, i.e., improved perceptual quality while sacrificing the data fidelity. The unsatisfactory results are due to the lack of integration of these strategies in the IR tasks. In this work, we propose a novel zero-shot IR scheme, dubbed Reconciling Diffusion Model in Dual (RDMD), which leverages only a single pre-trained diffusion model to construct two complementary regularizers. Specifically, the diffusion model in RDMD will iteratively perform deterministic denoising and stochastic sampling, aiming to achieve high-fidelity image restoration with appealing perceptual quality.RDMD also allows users to customize the distortion-perception tradeoff with a single hyperparameter, enhancing the adaptability of the restoration process in different practical scenarios. Extensive experiments on several IR tasks demonstrate that our proposed method could achieve superior results compared to existing approaches on both the FFHQ and ImageNet datasets.

---

## 论文详细总结（自动生成）

# Reconciling Stochastic and Deterministic Strategies for Zero-shot Image Restoration using Diffusion Model in Dual 论文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：零样本图像恢复（IR）存在两种主流策略，各有不足：
  - **确定性回归**（PnP with discriminative denoiser）：数据保真度高，但恢复结果常有过度平滑或涂抹伪影，感知质量差。
  - **随机采样**（Diffusion-based sampling）：感知质量好，但容易牺牲对原始图像的保真度，产生与输入不一致的虚假细节。
- **核心问题**：如何在同一框架内整合确定性回归与随机采样的优势，使零样本IR既能保持高数据一致性，又具有逼真的感知质量，并支持用户灵活调节失真-感知权衡。
- **整体含义**：本文提出**RDMD**，利用**单个预训练扩散模型**同时构建两个互补的正则化器，在一个迭代过程中交替进行确定性去噪与随机采样，首次实现了零样本IR中两种策略的统一与调和。

## 2. 论文提出的方法论
- **核心思想**：通过改进的变量分裂算法，将扩散模型既当作判别式高斯去噪器（确定性），又当作生成式先验（随机），由权重参数 `τ` 控制两者贡献。
- **问题建模**：在目标函数中同时引入对辅助变量 `z` 和原变量 `x` 的正则化，并赋予不同策略：
  - **随机采样分支（更新x）**：将扩散模型的反向过程视为“去噪+重加噪”的随机采样步骤，近似求解对应的高斯去噪子问题。
  - **确定性回归分支（更新z）**：基于RED（Regularization by Denoising）公式，将扩散模型的去噪函数作为确定性先验，用梯度下降法迭代更新，对抗退化并保持数据一致性。
- **关键技术细节**：
  - 扩散模型提供去噪预测 `x0|t`（随机分支）与确定性估计 `fθ(zt; t')`（确定性分支）。
  - 数据一致性项采用梯度下降而非闭合解，提升框架通用性。
  - 引入重参数化噪声与可调节的随机性参数 `ζ`。
- **算法流程**（Algorithm 1）：从纯噪声开始，循环执行：
  1. 基于当前 `zt` 计算确定性估计 `fθ`。
  2. 融合数据一致性梯度与两个正则化梯度更新 `zt-1`。
  3. 利用更新后的 `zt-1` 进行重噪，生成下一个随机状态 `xt-1`。
- **可定制性**：通过单一超参数 `τ`（0到1）实现**失真-感知权衡**：`τ=0` 完全确定性，`τ=1` 完全随机，中间值灵活平衡。

## 3. 实验设计
- **数据集与场景**：
  - FFHQ 256×256 和 ImageNet 256×256。
  - 任务：高斯去模糊、运动去模糊、超分辨率（2×、4×、8×），所有退化均附加高斯噪声（σₙ=0.05）。
- **Benchmark 对比方法**：
  - 基于扩散模型的零样本方法：MCG, DPS, DiffPIR, Resample, BIRD。
  - 经典PnP/RED方法：RED（作为确定性基准），DiffPIR（作为随机基准，即本文τ=1的特例）。
- **评价指标**：PSNR / SSIM（失真度）与 LPIPS（感知质量）。

## 4. 资源与算力
- 文中仅提及实现使用 PyTorch 与 **NVIDIA RTX A5000** GPU，未说明使用数量、训练时长或具体算力消耗。
- 由于采用**预训练扩散模型**（来自先前工作，无额外训练），主要算力消耗在于推理迭代，未给出详细成本。

## 5. 实验数量与充分性
- **主要定量实验**：2个数据集 × 5种任务，共产生两组完整对比表格，覆盖FFHQ和ImageNet上的主要退化类型。
- **定性实验**：多任务恢复结果的可视化对比。
- **消融实验**：
  - 迭代步数 `T` 的影响（T=20/50/100/200）。
  - 关键超参数 `λ` 与 `τ` 的组合分析（图6）。
  - 与使用额外判别式网络（DRUNet, SwinIR）的双先验方案对比（表3）。
- **充分性与公平性**：实验覆盖主流零样本IR方法，所有方法使用相同预训练权重或公开模型，迭代步数等关键设置保持一致，比较公平。消融实验验证了核心设计选择的有效性与参数灵敏度。

## 6. 论文的主要结论与发现
- **统一框架有效**：单个扩散模型可同时扮演确定性去噪器和随机生成器，成功调和两种策略。
- **性能取长补短**：RDMD在多种IR任务上同时获得高于纯确定性的PSNR和优于纯随机的LPIPS，例如FFHQ 8× SR PSNR提升2.23dB，同时保持低LPIPS。
- **灵活权衡**：用户可通过调整 `τ` 在失真和感知之间取得理想折中，无需重新训练网络，增强实用性。

## 7. 优点
- **方法创新**：首次在零样本框架下统一扩散模型的确定性与随机性，无需额外模型。
- **即插即用**：仅依赖单一预训练扩散模型，部署简便。
- **性能优越**：在两大标准数据集上全面超过或媲美现有最优零样本方法。
- **强可解释性与可控性**：超参数 `τ` 直接控制恢复结果的风格偏向，便于实际应用。

## 8. 不足与局限
- **测试场景有限**：实验仅针对固定噪声水平0.05和256×256分辨率，对更高噪声、盲复原或高分辨率图像的泛化能力未验证。
- **计算效率**：迭代步数T=100优于原始DDPM但高于部分加速方法（如BIRD仅10步但需要额外优化），实时性或移动端应用可能受限。
- **依赖预训练先验**：性能上限受限于所使用的扩散模型质量，若换用其他模型需重新适配噪声调度。
- **参数灵敏度**：λ和τ需按任务调节，文中未给出自动化选择方案，可能增加使用门槛。
- **约束较强**：数据一致性采用简单梯度下降，在某些极端退化下可能不够鲁棒。

（完）
