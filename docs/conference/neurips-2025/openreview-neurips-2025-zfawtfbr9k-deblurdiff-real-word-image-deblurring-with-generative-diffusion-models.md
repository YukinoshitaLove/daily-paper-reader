---
title: "DeblurDiff: Real-Word Image Deblurring with Generative Diffusion Models"
title_zh: DeblurDiff：使用生成扩散模型进行真实世界图像去模糊
authors: "Lingshun Kong, jiawei zhang, Dongqing Zou, Fu Lee Wang, Jimmy Ren, Xiaohe Wu, Jiangxin Dong, Jinshan Pan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ZfAwtFBR9K"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用扩散模型和潜在核预测进行真实图像去模糊
tldr: 直接使用扩散模型去模糊会阻碍结构提取或过度依赖去模糊网络。DeblurDiff提出潜在核预测网络，在潜空间中与条件扩散联合训练，学习空间变化核并通过逐元素自适应卷积实现鲁棒去模糊。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfawtfbr9k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 843, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfawtfbr9k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 972, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfawtfbr9k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 232, \"label\": \"Table\"}]"
motivation: 现有扩散去模糊方法在结构提取和依赖网络之间难以平衡。
method: 提出潜在核预测网络与条件扩散联合训练，学习空间变化核。
result: 在真实去模糊任务上取得鲁棒且高质量的结果。
conclusion: 潜在核预测可有效提升扩散模型的去模糊能力。
---

## Abstract
Diffusion models have achieved significant progress in image generation and the pre-trained Stable Diffusion (SD) models are helpful for image deblurring by providing clear image priors. However, directly using a blurry image or a pre-deblurred one as a conditional control for SD will either hinder accurate structure extraction or make the results overly dependent on the deblurring network. In this work, we propose a Latent Kernel Prediction Network (LKPN) to achieve robust real-world image deblurring. Specifically, we co-train the LKPN in the latent space with conditional diffusion. The LKPN learns a spatially variant kernel to guide the restoration of sharp images in the latent space. By applying element-wise adaptive convolution (EAC), the learned kernel is utilized to adaptively process the blurry feature, effectively preserving the information of the blurry input. This process thereby more effectively guides the generative process of SD, enhancing both the deblurring efficacy and the quality of detail reconstruction. Moreover, the results at each diffusion step are utilized to iteratively estimate the kernels in LKPN to better restore the sharp latent by EAC in the subsequent step. This iterative refinement enhances the accuracy and robustness of the deblurring process. Extensive experimental results demonstrate that the proposed method outperforms state-of-the-art image deblurring methods on both benchmark and real-world images.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
图像去模糊旨在从模糊观测中恢复清晰图像，是一项病态问题。近年来，扩散模型（如 Stable Diffusion）利用大规模预训练先验在生成高质量图像方面表现优异，因而被用于图像恢复。然而，现有方法存在两难：直接使用模糊图像作为扩散模型的条件输入，会因模糊区域缺乏有效结构信息而难以引导精确的结构提取；而先用一个额外的退化去除模型（如 FFTformer）进行预去模糊，再用其结果作为条件，又会导致最终结果过度依赖该预去模糊网络，一旦预去模糊结果不准确，就会产生伪影和错误结构。论文提出 DeblurDiff，旨在通过一种**潜在核预测网络（LKPN）** 在潜空间中联合训练扩散条件控制，实现鲁棒的真实世界图像去模糊，同时重建真实细节和纹理。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：在潜空间中联合训练一个**潜在核预测网络（LKPN）** 与条件扩散模型。LKPN 根据当前扩散步骤的潜变量和模糊潜变量，预测**空间变化的去模糊核**；然后通过**逐元素自适应卷积（EAC）** 将该核应用于模糊潜变量，得到更清晰的潜变量，作为条件引导扩散模型的生成过程。同时，扩散模型每一步输出的中间结果又被反馈回 LKPN 以迭代估计更精确的核，形成相互增强的闭环。
- **关键技术细节**：
  - LKPN：基于 U-Net 架构，输入为带噪声的清晰潜变量 \(z_t\)、模糊潜变量 \(z_{lq}\) 和时间步 \(t\)，输出空间变化核 \(k_t\)。
  - EAC：对每个像素位置预测特定卷积核，并对其邻域进行自适应卷积，从而保留模糊输入的信息，避免直接预测清晰图像带来的信息丢失。
  - 条件生成网络：采用 ControlNet 架构，将 LKPN 输出的清晰潜变量 \(z_s^t\) 与模糊潜变量 \(z_{lq}\) 拼接后作为条件，指导扩散模型的去噪过程。
- **公式/算法流程**：
  - 前向过程：\(z_t = \sqrt{\bar{\alpha}_t} z_0 + \sqrt{1-\bar{\alpha}_t} \epsilon\)
  - LKPN 核预测：\(k_t = \text{LKPN}(z_t, z_{lq}, t)\)
  - EAC 操作：\(z_s^t = \text{EAC}(z_{lq}, k_t)\)
  - 训练损失：包括扩散去噪损失 \(L_{\text{denoise}}\) 和 LKPN 的约束损失 \(L_{\text{LKPN}}\)（含潜空间和像素空间的 L2 损失）。
  - 推理采样：从随机噪声开始，LKPN 先预测初始核得到初始条件，扩散模型生成中间结果，再将其与模糊潜变量一起输入 LKPN 以更新核，如此迭代多步，逐步提升清晰度。

## 3. 实验设计
- **数据集**：
  - **训练集**：自建的约 50 万对大数据集，包含现有去模糊数据集（MC-Blur、RSBlur）、自拍高清视频片段（仿 REDS 策略合成）以及从高清图片合成运动模糊。
  - **测试集**：合成数据集（GoPro、DVD）、真实数据集（RealBlur、RWBI、Real Blurry Images）。
- **对比方法**：
  - 非扩散法：FFTformer、DBGAN。
  - 扩散法：HI-Diff、ResShift、ControlNet、PASD、DiffBIR（均为重新训练版本，*标记）。
- **评估指标**：
  - 参考指标：PSNR、SSIM、LPIPS、FID。
  - 无参考指标：NIQE、MUSIQ、MANIQA、CLIP-IQA。

## 4. 资源与算力
文中明确说明：训练使用 **8 台 NVIDIA 80G-A100 GPU**，batch size 为 128，学习率固定 \(5\times 10^{-5}\)，训练 **100,000 次迭代**。推理阶段的算力开销未详细报告，但指出目前是多步扩散过程，未来可加速至单步扩散。

## 5. 实验数量与充分性
- **定量实验**：在 3 个合成/真实基准（GoPro、DVD、RealBlur）和 2 个无 GT 数据集（RWBI、Real Images）上，与 7 种 SOTA 方法对比，报告 7 种指标（见表 1），数据全面。
- **消融实验**：
  - 验证 LKPN 与 EAC 的有效性（表 2）：对比 ControlNet（仅模糊输入）、w/o EAC（LKPN 直接预测清晰潜变量）、w/o SD for LKPN（LKPN 不使用扩散中间结果）。
  - 可视化分析：图 7、图 8 展示迭代过程中 LKPN 输出和扩散生成结果的变化。
- **公平性**：所有对比方法均使用相同的大规模训练集重新训练（标 *），并在相同条件下测试，保证对比公平。

## 6. 论文的主要结论与发现
- 提出的 DeblurDiff 在**无参考指标**（NIQE、MUSIQ、MANIQA、CLIP-IQA）上显著优于现有方法，尤其在真实场景中能恢复更清晰的纹理和结构，伪影更少。
- 在参考指标（PSNR、SSIM）上虽不如专门优化像素精度的 HI-Diff，但这是因为 HI-Diff 未使用预训练 SD 模型，侧重于像素逼真度；DeblurDiff 更侧重感知质量和细节重建。
- 消融实验表明：LKPN 结合 EAC 的动态核估计和迭代优化是关键；直接预测清晰潜变量或固定核均会导致平滑或伪影。

## 7. 优点
- **方法创新**：巧妙地将传统盲去模糊中的“核估计-图像恢复”迭代思路融入潜空间扩散过程，提出 LKPN 和 EAC，实现了自适应空间变化去模糊，无需额外预去模糊网络。
- **利用大规模预训练**：借助 Stable Diffusion 的先验，有效重建细节和纹理，同时在训练时只增量训练 LKPN 和 ControlNet，计算相对高效。
- **迭代细化**：扩散过程的中间结果反馈给 LKPN，形成相互增强，不断提升核估计精度和去模糊效果。
- **训练数据规模大**：自建 50 万对高清数据，弥补了现有去模糊数据集规模小的不足。

## 8. 不足与局限
- **实验覆盖**：仅使用了 SD2.1 版本，未验证在更新版本的 SD（如 SD3.5）上的表现，泛化性有待进一步检验。
- **推理速度**：多步扩散推理较慢，文中提及未来可尝试单步扩散优化，但当前未提供加速方案。
- **参考指标欠佳**：在 PSNR/SSIM 上不如某些非扩散方法（如 HI-Diff），说明在像素级保真度与感知质量之间存在权衡，可能不适用于对数值指标要求极高的应用场景。
- **潜在滥用风险**：虽然论文讨论了社会影响并提出水印、元数据等保护措施，但并未在模型发布时实现这些机制。
- **消融实验的指标覆盖**：消融实验仅使用 GoPro 数据集，未在所有数据集上验证组件的稳定性。

（完）
