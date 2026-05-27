---
title: "Precise Diffusion Inversion: Towards Novel Samples and Few-Step Models"
title_zh: 精确扩散反演：迈向新颖样本与少步模型
authors: "Jing Zuo, Luoping Cui, Chuang Zhu, Yonggang Qi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2sMk2ShRdP"
tags: ["query:real-ir"]
score: 8.0
evidence: 用于保真图像编辑的扩散反演
tldr: 扩散反演是实现图像编辑的关键但计算昂贵。本文提出PreciseInv，将反演重构为学习问题，采用动态规划策略在两步内实现精确反演。实验证明了其在少步扩散模型和新型样本上的高效性与保真性，为实时编辑提供了可能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1427, \"height\": 1977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 1979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1424, \"height\": 1983, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1424, \"height\": 2077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1418, \"height\": 2063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1418, \"height\": 2077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1423, \"height\": 2069, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1419, \"height\": 2066, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1448, \"height\": 2144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1453, \"height\": 2185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1417, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1429, \"height\": 1233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1449, \"height\": 1488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2smk2shrdp/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1447, \"height\": 1568, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2smk2shrdp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2smk2shrdp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1154, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2smk2shrdp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1430, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2smk2shrdp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1200, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2smk2shrdp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1218, \"height\": 980, \"label\": \"Table\"}]"
motivation: 解决现有扩散反演方法在精度与效率之间的平衡问题。
method: 将反演转化为学习问题，采用动态规划递归估计参数。
result: 在两步推断内实现快速且保真的反演。
conclusion: 为扩散模型的高效保真编辑奠定了基础。
---

## Abstract
The diffusion inversion problem seeks to recover the latent generative trajectory of a diffusion model given a real image. Faithful inversion is critical for ensuring consistency in diffusion-based image editing. Prior works formulate this task as a fixed-point problem and solve it using numerical methods. However, achieving both accuracy and efficiency remains challenging, especially for few-step models and novel samples. In this paper, we propose ***PreciseInv***, a general-purpose test-time optimization framework that enables fast and faithful inversion in as few as two inference steps. Unlike root-finding methods, we reformulate inversion as a learning problem and introduce a dynamic programming-inspired strategy to recursively estimate a parameterized sequence of noise embeddings. This design leverages the smoothness of the diffusion latent space for accurate gradient-based optimization and ensures memory efficiency via recursive subproblem construction. We further provide a theoretical analysis of ***PreciseInv***'s convergence and derive a provable upper bound on its reconstruction error. Extensive experiments on COCO 2017, DarkFace, and a stylized cartoon dataset show that ***PreciseInv*** achieves state-of-the-art performance in both reconstruction quality and inference speed. Improvements are especially notable for few-step models and under distribution shifts. Moreover, precise inversion yields substantial gains in editing consistency for text-driven image manipulation tasks. Code is available at: https://github.com/panda7777777/PreciseInv

---

## 论文详细总结（自动生成）

# 论文《Precise Diffusion Inversion: Towards Novel Samples and Few-Step Models》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：扩散模型反转（diffusion inversion）旨在给定真实图像后，恢复其在预训练扩散模型中的潜在生成轨迹。精确的反转是确保基于扩散的图像编辑一致性的关键。
- **现有不足**：先前工作将反转视为固定点问题并用数值方法求解（如Anderson加速、ReNoise等），但在少步模型（2、4步）和在分布外的新颖样本上，难以同时达到高精度和高效率。
- **本文目标**：提出一个通用测试时优化框架 **PreciseInv**，在仅需两步推理的情况下实现快速且保真的反转，并提升后续文本驱动图像编辑的连贯性与可控性。

## 2. 方法论

### 核心思想
- 将扩散反转变为**学习问题**，而非数值求解固定点方程。
- 利用扩散潜在空间的**平滑性**进行梯度优化，并通过**动态规划**策略递归估计参数化的噪声嵌入序列。

### 关键技术细节
1. **子问题分解**：基于扩散过程的马尔可夫性质，将整体反转问题分解为 T 个重叠子问题 `P(t)`，每个子问题学习一个局部噪声嵌入 `ε_t^*`，使得从该噪声潜变量经DDIM采样后重构的图像与真实图像 x0 的误差最小。
2. **最优子结构与重叠子问题**：相邻子问题共享重构目标，且存在递推关系：`P(t)` 的解可基于 `P(t-1)` 的解递归求得。
3. **自底向上计算**：从 t=1 到 T 依次求解，每次只对当前 timestep 进行反向传播，内存消耗恒定（SD v1.4 仅需 3.43 GB），与推理步数无关。
4. **算法流程**（Algorithm 1）：
   - 初始化噪声嵌入 `ε_t^*`（随机或DDIM一步初始化）。
   - 对于每个 t，计算当前潜变量 `x_t^* = √α̅_t x0 + √(1-α̅_t) ε_t^*`。
   - 定义重建损失 `L_rec = ‖μ(x_t^*) - x_{t-1}^*‖`，其中 μ 为DDIM采样函数。
   - 通过梯度下降迭代优化 `ε_t^*`，直到损失低于收敛阈值 η。
   - 循环到 t=T 得到最终反转潜变量 `x_T^*`。

### 理论分析
- 假设扩散模型 Lipschitz 连续且损失函数梯度 Lipschitz 连续，证明了梯度下降在每个子问题上单调收敛到驻点，且整体重构误差有几何上界 `δ/(1-L_m)`。

## 3. 实验设计

### 数据集
- **COCO 2017 验证集**：5,000 张自然图像，接近训练分布。
- **DarkFace 验证集**：6,089 张夜间低光照图像，分布偏移。
- **卡通数据集**（自收集）：722 张风格化图像，显著偏离训练分布。

### Benchmark 与对比方法
- **前向优化方法**：DDIM Inversion、ReNoise、EasyInv。
- **可逆采样器**：EDICT、BDIA、BELM。
- 均使用 SD v1.4 作为基础模型（除非指定其他模型）。

### 评价指标
- **LPIPS↓、SSIM↑、PSNR↑**：衡量重构质量。
- **平均推理时间（秒）**：衡量效率。

### 额外实验
- 使用 **LCM-SD v1.5** 和 **SDXL** 验证通用性。
- 少步推理设置（T=2, 4）。
- 与不同采样器（DDPM、Euler）结合实验。
- 收敛阈值 η 与推理步数 T 的消融研究。
- 文本驱动图像编辑任务定性比较。
- 潜空间插值实验分析潜在表示连续性。

## 4. 资源与算力

- **硬件**：所有实验在单张 **RTX 4090 24GB GPU** 上运行（SD3 除外，使用 **A100 40GB** GPU）。
- **软件**：PyTorch + Hugging Face Diffusers；混合精度（float16 / bfloat16）。
- **优化参数**：AdamW 优化器，学习率 0.1（SD v1.4）/ 0.05（LCM / SDXL）/ 0.025（SD3），权重衰减 0.01。
- 论文未明确报告总训练时长，但给出了每张图像的推理时间（如 PreciseInv 在 COCO 上 η=10⁻² 时 5.33s / 图，η=10⁻⁵ 时 23.29s / 图）。

## 5. 实验数量与充分性

### 实验组数
- **重构实验**：表1（三个数据集 × 多种方法）、表2（两种新模型）、表3（少步设置）、表4（额外模型/采样器组合）、表5（η与T的消融，5×6=30种组合）。
- **编辑实验**：图3-4定性比较。
- **插值实验**：图5定性分析。
- **附加附录**：更多定性结果（图6-19）。

### 充分性判断
- **充分**：覆盖多种数据域、多种扩散模型（SD v1.4, LCM, SDXL, SD3）、多种采样器（DDIM, DDPM, Euler）、多种推理步数（2~1000）。
- **公平**：超参数严格调优，空文本提示且无分类器引导（CFG=0），基线方法使用默认配置或 sweep 最佳参数。
- **结论可靠**：多个消融实验验证了收敛阈值、步数对质量-速度权衡的影响，且理论分析与实验结果一致。

## 6. 主要结论与发现

1. **重构性能**：PreciseInv 在 LPIPS、SSIM、PSNR 上全面超越所有对比方法，尤其在卡通数据集上提升显著（LPIPS 降低 0.127，PSNR 提升 7.92 dB）。
2. **效率优势**：在 η=10⁻² 时推理仅需 5.33s，仍比大多数基线质量更好；两步推理（T=2）即可达到高保真重构。
3. **少步模型与新颖样本**：对 LCM、SDXL 同样适用，在 T=2,4 时重构质量远超其他方法。
4. **编辑一致性**：精确反转使潜空间更平滑（插值实验），从而在文本驱动编辑中更好地保留无关细节，提升忠实度。
5. **理论保证**：证明了收敛性和误差上界，为方法提供了坚实基础。

## 7. 优点

- **方法创新性**：将固定点求解转化为学习问题，利用动态规划实现内存高效、收敛精确的反转。
- **通用性**：适用于多种扩散模型（DDIM / DDPM / Rectified Flow）和多种步数设置。
- **理论支撑**：给出收敛证明和误差上界，增强可信度。
- **实验全面**：多数据集、多模型、多指标、多消融，充分验证有效性。
- **实用价值**：在极低推理步数下仍保持高质量，适合实时编辑应用。

## 8. 不足与局限

- **SD3 效率较低**：在 SD3 上推理时间达 403s，主要因为缺乏有效初始化和模型规模大，论文建议未来采用逐步递减时间步优化策略。
- **编辑任务非专用**：PreciseInv 是通用反转方法，未针对编辑做专门设计（如注意力修改、掩码等），因此与高级编辑流水线相比，在编辑精度上可能仍有差距。论文指出集成是未来方向。
- **实验偏差风险**：仅依赖 LPIPS、SSIM、PSNR 等指标，未涉及用户研究或更细粒度的编辑可控性评估。
- **理论假设强度**：Lipschitz 连续性假设在扩散模型中通常成立，但极端非线性区域可能轻微违反，不过实验已验证实际效果。
- **计算资源**：尽管内存高效，但对于超大规模模型（如 SD3）仍需 A100 GPU，可能限制普及。

（完）
