---
title: Solving Inverse Problems with FLAIR
title_zh: 使用FLAIR解决逆成像问题
authors: "Julius Erbach, Dominik Narnhofer, Andreas Robert Dombos, Bernt Schiele, Jan Eric Lenssen, Konrad Schindler"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=w9xETx7HT1"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于流的生成模型用于逆成像问题
tldr: 基于流的生成模型在逆成像问题中面临似然项难解、先验与观测冲突等障碍。FLAIR提出无需训练变分框架，将流模型作为先验，有效解决超分辨率、去模糊等问题，在保持先验质量的同时忠实于观测数据。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1360, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 1340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1139, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 1714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 1719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 1714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 1717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1438, \"height\": 1712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1437, \"height\": 1711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1450, \"height\": 2019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w9xetx7ht1/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1457, \"height\": 1450, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1032, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1308, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1019, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1273, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1272, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1275, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1272, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1271, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1273, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 669, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1272, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w9xetx7ht1/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1271, \"height\": 264, \"label\": \"Table\"}]"
motivation: 流生成模型作为逆问题先验时存在忠实度不足。
method: 提出无需训练的变分框架，利用流模型作为先验。
result: 在超分辨率等任务上实现高质量重建。
conclusion: 流模型可作为逆成像问题的强大先验。
---

## Abstract
Flow-based latent generative models such as Stable Diffusion 3 are able to generate images with remarkable quality, even enabling photorealistic text-to-image generation. Their impressive performance suggests that these models should also constitute powerful priors for inverse imaging problems, but that approach has not yet led to comparable fidelity.

There are several key obstacles: (i) the data likelihood term is usually intractable; (ii) learned generative models cannot be directly conditioned on the distorted observations, leading to conflicting objectives between data likelihood and prior; and (iii) the reconstructions can deviate from the observed data.
We present FLAIR, a novel, training-free variational framework that leverages flow-based generative models as prior for inverse problems. To that end, we introduce a variational objective for flow matching that is agnostic to the type of degradation, and combine it with deterministic trajectory adjustments to guide the prior towards regions which are more likely under the posterior. 
To enforce exact consistency with the observed data, we decouple the optimization of the data fidelity and regularization terms. Moreover, we introduce a time-dependent calibration scheme in which the strength of the regularization is modulated according to off-line accuracy estimates. 
Results on standard imaging benchmarks demonstrate that FLAIR consistently outperforms existing diffusion- and flow-based methods in terms of reconstruction quality and sample diversity. 
Source code is available at https://inverseflair.github.io/.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

逆成像问题（如超分辨率、去模糊、修复）旨在从退化观测中恢复高质量图像。基于流的生成模型（如 Stable Diffusion 3）虽能生成逼真图像，但作为先验用于逆问题面临三大障碍：

- 数据似然项通常难解（intractable）；
- 生成模型无法直接条件化于退化观测，导致先验与似然目标冲突；
- 重建容易偏离观测数据。

现有方法要么依赖软约束（如变分后验采样）导致忠实度不足，要么在潜在空间难以保持数据一致性。因此，作者提出 FLAIR（Flow-based Latent Adaptive Inference with deterministic Re-noising），一个无需训练（training-free）的变分框架，旨在同时保证高感知质量、严格数据一致性和样本多样性。

### 方法论

FLAIR 基于变分推断，用高斯分布 \( q(x_0|y) \) 近似真实后验 \( p(x_0|y) \)。其核心思想包括四个关键技术：

1. **流匹配变分目标**：将原分数匹配正则项替换为条件流匹配目标：
   \[
   \arg\min_{q} \left[ \frac{\|y - f(\mu_x)\|^2}{2\sigma_\nu^2} + \int_0^T \lambda_R(t) \mathbb{E}_{q(x_t|y)} \| v_\theta(x_t,t) - u_t(x_t|\epsilon) \|^2 dt \right]
   \]
   其中 \( v_\theta \) 是预训练流模型的预测速度场，\( u_t \) 是变分分布对应的目标速度场。

2. **确定性轨迹调整（Deterministic Trajectory Adjustment, DTA）**：重新参数化变分分布，使其均值线性插值后验均值 \( \mu_x \) 与模型预测的确定性端点 \( \hat{x}_1 \)：
   \[
   q(x_t|y) = \mathcal{N}\big((1-t)\mu_x + t\alpha\hat{x}_1,\; t^2(1-\alpha^2)I\big)
   \]
   这引导先验向更高密度的后验区域移动，避免低密度区域的不良梯度。

3. **硬数据一致性（Hard Data Consistency, HDC）**：解耦数据项与正则项的优化，交替执行正则器更新（基于流匹配梯度）和投影步骤：
   \[
   \mu_x \leftarrow \arg\min_{\mu_x} \|y - A(\mu_x)\|^2
   \]
   确保重建严格匹配观测。

4. **校准正则化权重（Calibrated Regularizer Weight, CRW）**：在验证集上离线计算每个时间步 \( t \) 的预期流匹配误差，取倒数作为权重 \( \lambda_R(t) \)，并在 \( t < 0.2 \) 时设为零（因 SD3 在低噪声区精度严重下降）。

**算法流程**（简化）：
- 初始化 \( \mu_x \) 为编码后的共轭初始化 \( E(A^\top y) \)。
- 从 \( t=1 \) 降至 0.2（步长 \( \Delta t \)）：
  1. 采样噪声 \( \epsilon \)，计算 \( x_t = (1-t)\mu_x + t\epsilon \)。
  2. 计算正则梯度 \( \nabla_{\mu_x} R = v_\theta(x_t,t) - u_t(x_t|\epsilon) \)。
  3. 更新 \( \mu_x \leftarrow \mu_x - \lambda_R \nabla_{\mu_x} R \)。
  4. 执行硬数据一致性投影。
  5. 预测单步无噪估计 \( \hat{x}_1 = x_t + (1-t)v_\theta(x_t,t) \)。
  6. 更新噪声估计 \( \hat{\epsilon} = \alpha \hat{x}_1 + \sqrt{1-\alpha^2} \epsilon \)（其中 \( \alpha = 1-t \)）。

### 实验设计

- **数据集**：
  - FFHQ（1024×1024，前 1000 张人脸图像）。
  - DIV2K（2K 分辨率，800 张自然图像）。
  - 像素空间实验：CelebA-HQ（256×256，流模型来自 Liu et al. 2022）。

- **任务与退化**：
  - 超分辨率（×8 和 ×12）：双三次下采样。
  - 运动去模糊（核大小 61）。
  - 框修复（约 1/3 区域遮挡）。
  - 加性高斯噪声（\( \sigma_\nu = 0.5\% \)）。

- **对比方法**：
  - 潜在空间：ReSample、FlowDPS、RSD、FlowChef（均使用 SD3.5-Medium 骨干）。
  - 像素空间：DDNM、DPS、Moment Matching、ΠGDM。

- **评价指标**：LPIPS、FID、SSIM、PSNR（但明确 PSNR 不适合评估后验采样质量）。所有方法均使用相同的 50 次函数评估（NFE）。

### 资源与算力

- GPU：单块 NVIDIA RTX 4090（24GB VRAM）。
- 论文未提供总训练时长（因为方法是 training-free，仅需推理），但附录表 A.6 列出了每种方法的运行时间与内存消耗。FLAIR（使用 tinyVAE 且数据项步数 ≤5）耗时约 22 秒/样本，内存约 5.96 GB；其他方法运行时间在 15–88 秒之间。

### 实验数量与充分性

实验数量丰富，覆盖多维度验证：

| 实验类型 | 数量与内容 |
|----------|------------|
| 主实验   | FFHQ 和 DIV2K 上 ×8/×12 超分辨率、运动去模糊、修复（共 8 个任务 × 2 数据集 = 16 组定量结果） |
| 消融实验 | 表 3：HDC、DTA、CRW 三项逐个开关，在 ×12 超分辨率上各 2 组（FFHQ/DIV2K），共 5 种组合 |
| 像素空间实验 | 表 5：CelebA-HQ 上修复和超分辨率各 1 组，对比 4 种方法 |
| 后验方差可视化 | 图 3：32 个样本方差图，对比 FlowDPS、RSD |
| 编辑演示 | 图 4：4 个编辑示例 |
| 正则权重消融 | 附录表 A.1：不同权重函数比较 |
| 文本提示影响 | 附录表 A.2：有/无 caption 对比 |
| 集成实验 | 附录表 A.7：8 次采样平均提升 PSNR |
| 统计显著性 | 附录表 A.16：配对 t 检验（p < 0.001） |
| 失败案例 | 附录图 10：两类典型失败 |

实验设计公平：所有基线使用相同骨干（SD3.5-Medium）、相同 NFE、相同退化参数，并公开了超参数设置。

### 主要结论与发现

1. FLAIR 在所有任务上显著优于现有基于扩散和流的方法，尤其是在感知质量指标（LPIPS、FID）上提升巨大（例如 FFHQ 上 inpainting 的 FID 从 42.5→8.7）。
2. 硬数据一致性（HDC）与确定性轨迹调整（DTA）是提升忠实度和感知质量的关键；去掉 DTA 会导致严重的模式塌陷。
3. 校准正则化权重（CRW）避免低噪声区不稳定的梯度，进一步改善纹理细节。
4. FLAIR 能生成多样化的后验样本，方差集中在高频纹理区域，表明其可靠地恢复了后验分布。
5. 在像素空间同样有效，说明框架可跨不同流模型迁移。

### 优点

- **无需训练**：直接利用预训练流模型，无额外微调，实用性强。
- **理论清晰**：将流匹配损失纳入变分目标，并给出完整的推导（附录 A.1–A.3）。
- **设计简洁有效**：三个关键组件（HDC、DTA、CRW）针对各自问题有明确动机，消融实验验证了各自贡献。
- **兼顾质量与多样性**：同时达到高感知质量、严格数据一致性和良好样本多样性，克服了感知-失真折衷。
- **实验充分且公平**：多数据集、多任务、多基线对比，显著性检验和详细超参数说明增强了可信度。

### 不足与局限

- **继承基础模型偏差**：FLAIR 继承 SD3 的训练数据偏差，对分布外场景（如罕见物体或风格）重建可能失真。
- **输出分辨率受限**：受 VAE 解码器限制，论文仅测试 768×768，未展示任意分辨率扩展。
- **额外超参数**：DTA 中的 α（论文设为 1-t）和正则权重 λ_R(t) 需手动设定或校准，引入额外调节成本。
- **计算开销**：硬数据一致性步骤涉及迭代优化，导致推理时间比部分基线长（约 172 秒/样本，使用 large VAE），但可通过 tinyVAE 和减少数据步数加速。
- **潜在伦理风险**：高质量图像修复可被用于伪造或篡改，论文已提及此点。
- **仅限线性/可微前向算子**：实验仅针对线性退化（下采样、模糊、掩码），对非线性退化（如传感器压缩）的适用性未验证。

（完）
