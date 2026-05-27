---
title: Unleashing the Power of One-Step Diffusion based Image Super-Resolution via a Large-Scale Diffusion Discriminator
title_zh: 通过大规模扩散判别器释放一步扩散图像超分辨率的潜力
authors: "Jianze Li, Jiezhang Cao, Zichen Zou, Xiongfei Su, Xin Yuan, Yulun Zhang, Yong Guo, Xiaokang Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0M1gi4P4ka"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用大规模判别器的一步扩散模型进行真实图像超分辨率
tldr: 现有一步扩散超分辨率方法受限于教师模型能力。D3SR提出大规模扩散判别器，从任意时间步蒸馏噪声特征，实现高质量的一步超分辨率，在计算效率与性能上取得突破。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0m1gi4p4ka/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0m1gi4p4ka/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0m1gi4p4ka/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 782, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0m1gi4p4ka/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0m1gi4p4ka/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 1002, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0m1gi4p4ka/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0m1gi4p4ka/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 734, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0m1gi4p4ka/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0m1gi4p4ka/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 695, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0m1gi4p4ka/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 710, \"height\": 222, \"label\": \"Table\"}]"
motivation: 一步扩散超分辨率受限于教师模型能力。
method: 提出大规模扩散判别器从任意时间步蒸馏噪声特征。
result: 实现高质量的一步超分辨率，计算效率显著提升。
conclusion: 大规模扩散判别器可有效增强一步扩散模型的性能。
---

## Abstract
Diffusion models have demonstrated excellent performance for real-world image super-resolution (Real-ISR), albeit at high computational costs. Most existing methods are trying to derive one-step diffusion models from multi-step counterparts through knowledge distillation (KD) or variational score distillation (VSD). However, these methods are limited by the capabilities of the teacher model, especially if the teacher model itself is not sufficiently strong. To tackle these issues, we propose a new One-Step \textbf{D}iffusion model with a larger-scale \textbf{D}iffusion \textbf{D}iscriminator for SR, called D$^3$SR. Our discriminator is able to distill noisy features from any time step of diffusion models in the latent space. In this way, our diffusion discriminator breaks through the potential limitations imposed by the presence of a teacher model. Additionally, we improve the perceptual loss with edge-aware DISTS (EA-DISTS) to enhance the model's ability to generate fine details. Our experiments demonstrate that, compared with previous diffusion-based methods requiring dozens or even hundreds of steps, our D$^3$SR attains comparable or even superior results in both quantitative metrics and qualitative evaluations. Moreover, compared with other methods, D$^3$SR achieves at least $3\times$ faster inference speed and reduces parameters by at least 30\%.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

真实世界图像超分辨率（Real-ISR）旨在从低质量观测中恢复高质量图像，是一个具有挑战性的低级视觉任务。近年来，基于扩散模型的方法取得了优异性能，但通常需要数十到数百步采样，导致推理延迟大，限制了实际应用。为加速推理，研究者提出了多种一步扩散蒸馏方法（如知识蒸馏KD、变分分数蒸馏VSD），但这些方法严重依赖多步教师模型的能力上限。如果教师模型本身不够强，蒸馏后的学生模型性能便会受到制约。此外，VSD等蒸馏方法未利用真实高分辨率数据，仅依赖于预训练先验，可能导致生成图像缺乏真实感或产生伪纹理。**本文的核心动机是打破教师模型对一步扩散SR的性能限制，通过更强大的大规模扩散判别器来引导生成，同时提升图像细节质量。**

## 2. 论文提出的方法论

### 核心思想
- 抛弃传统的“多步教师+学生蒸馏”范式，转而使用**大规模预训练扩散模型（SDXL）作为判别器**，通过对抗训练从潜在空间任意时间步的噪声特征中学习真实数据分布。
- 生成器基于Stable Diffusion 2.1-base，通过LoRA轻量微调，保持参数量可控。
- 提出**边缘感知DISTS（EA-DISTS）感知损失**，结合Sobel边缘检测增强纹理细节重建。

### 关键技术细节
- **生成器**：将低分辨率图像通过VAE编码器得到潜在变量\(z_L\)，设置一个中间时间步\(T_L\)（非纯噪声），执行一步去噪得到预测\(\hat{z}_H\)，再通过解码器得到超分图像\(\hat{x}_H\)。公式：\(\hat{z}_H = \frac{z_L - \sqrt{1 - \bar{\alpha}_{T_L}} \epsilon_\theta(z_L; T_L)}{\sqrt{\bar{\alpha}_{T_L}}}\)。
- **扩散判别器**：使用SDXL的UNet（冻结大部分参数，仅微调下采样和中间块的LoRA），在其中间块后添加随机初始化的MLP，输出每个patch的真伪分数。输入为生成图像的潜在表示\(\hat{z}_H\)和真实图像潜在表示\(z_H\)经过前向扩散（加噪）后的特征。对抗损失：
  - 生成器损失：\(\mathcal{L}_G = -\mathbb{E}[\log D_\theta(F(\hat{z}_H, t))]\)
  - 判别器损失：\(\mathcal{L}_D = -\mathbb{E}[\log(1 - D_\theta(F(\hat{z}_H, t)))] - \mathbb{E}[\log D_\theta(F(z_H, t))]\)
  其中\(F(z,t) = \sqrt{\bar{\alpha}_t}z + \sqrt{1 - \bar{\alpha}_t}\epsilon\)为前向扩散函数。
- **EA-DISTS损失**：在原始DISTS损失基础上，额外计算超分图像和真实图像的Sobel边缘图的DISTS损失：\(\mathcal{L}_{\text{EA-DISTS}} = \mathcal{L}_{\text{DISTS}}(\hat{x}_H, x_H) + \mathcal{L}_{\text{DISTS}}(S(\hat{x}_H), S(x_H))\)，\(S\)为Sobel算子。
- **总训练损失**：生成器总损失 = \(\mathcal{L}_{\text{spatial}} + \lambda_1 \mathcal{L}_G\)，其中\(\mathcal{L}_{\text{spatial}} = \mathcal{L}_{\text{MSE}} + \lambda_2 \mathcal{L}_{\text{EA-DISTS}}\)。判别器仅使用对抗损失更新。

## 3. 实验设计

### 数据集
- **训练集**：LSDIR（大规模图像恢复数据集）+ FFHQ（前10k张人脸），总计95k张图像。随机裁剪512×512 patches，使用Real-ESRGAN退化流水线合成低分辨率图像。
- **测试集**：
  - **DIV2K-val**：合成退化，作为合成场景评估。
  - **RealSR**：真实世界超分辨率基准。
  - **RealSet65**：真实场景评估集。

### 对比方法
- **多步扩散模型**：StableSR（200步）、DiffBIR（50步）、SeeSR（50步）、ResShift（15步）、AddSR（4步）。
- **一步扩散模型**：SinSR、OSEDiff、AddSR（均为1步）。
- **其他方法**：GAN类（BSRGAN、Real-ESRGAN、RealSR-JPEG、LDL、FeMASR）、Transformer类（SwinIR）。

### 评估指标
- **全参考（FR）**：PSNR、SSIM（Y通道）、LPIPS、DISTS。
- **无参考（NR）**：NIQE、MUSIQ、ManIQA、CLIPIQA。

## 4. 资源与算力

- **GPU**：4块 NVIDIA A100-40GB。
- **训练配置**：batch size = 8，训练迭代**100K**次，优化器AdamW，学习率5e-5。
- **推断测试**：在单块A100 GPU上测试推理时间。
- 文中未明确说明训练总时长，但提供了推理时间对比（D3SR为0.11秒/图）。

## 5. 实验数量与充分性

论文进行了多组实验，较为充分且公平：
- **定量对比**：在3个测试集（DIV2K-val、RealSR、RealSet65）上，与11种以上主流方法进行对比，报告了8个指标（Table 1、Table 2）。
- **消融实验**（Table 4）：
  - 不同感知损失（MSE、LPIPS、EA-LPIPS、DISTS、EA-DISTS）的影响。
  - 不同判别器（无判别器、CNN判别器、Diffusion-GAN判别器、SD 2.1、SDXL）的影响。
- **复杂度分析**（Table 3）：对比了参数量、MACs、推理时间。
- **可视化对比**：图5展示了不同方法在RealSR上的视觉结果。
- **其他消融**：补充材料中还包含更多消融实验（文中提及但未详细列出）。

整体实验设计覆盖了合成与真实场景、全参考与无参考指标、多种基线方法，且严格控制了变量（如生成器架构不随判别器变化），结论可信。

## 6. 论文的主要结论与发现

- D3SR在所有无参考指标（NIQE、MUSIQ、ManIQA、CLIPIQA）上，在多个数据集上达到同类一步扩散方法中的最优或次优性能，甚至优于部分多步扩散方法。
- 推理速度显著领先：相比多步方法（如StableSR、DiffBIR）提速**7倍以上**，相比其他一步方法（如OSEDiff）提速**3倍**，参数量减少**至少30%**。
- 大规模扩散判别器（SDXL）比弱教师（SD 2.1）带来明显性能提升，证明打破教师上限的有效性。
- EA-DISTS感知损失在纹理细节和视觉质量上优于LPIPS、DISTS等基线。

## 7. 优点

1. **创新性**：首次使用大规模扩散模型作为判别器进行一步SR训练，克服了蒸馏方法的固有性能天花板。
2. **简洁高效**：生成器仅用LoRA微调，推断无需额外模块（CLIP、ControlNet等），参数少、速度快。
3. **损失设计**：EA-DISTS结合边缘信息，增强高频细节重建，视觉质量提升明显。
4. **缩放性**：可通过更换更强判别器（如SDXL）直接提升效果，无需修改生成器，具备良好迁移性。
5. **实验充分**：在多个数据集和指标上进行了系统对比和消融，验证了各组件的贡献。

## 8. 不足与局限

1. **合成退化依赖**：训练使用Real-ESRGAN退化流水线，真实场景中复杂未知退化（如运动模糊、噪声类型差异）的泛化性未充分验证。
2. **指标偏好**：PSNR/SSIM等保真度指标相对偏低，这在一众扩散方法中普遍存在，但可能限制在需要高保真度的应用场景。
3. **训练成本**：100K迭代需要4块A100 GPU，对计算资源要求较高，可能限制小规模团队复现。
4. **判别器冻结设计**：文中未详细讨论判别器冻结程度对训练稳定性的影响，LoRA微调范围（仅下采样和中间块）的选择依据可更明确。
5. **社会影响**：仅在补充材料中提及，但未深入讨论潜在滥用风险（如生成虚假图像）。
6. **对比方法覆盖**：虽然对比了多种扩散方法，但缺少与最新端到端非扩散一步SR模型的对比（如HAT、DAT等，不过这些通常为保真度导向）。

（完）
