---
title: "TSD-SR: One-Step Diffusion with Target Score Distillation for Real-World Image Super-Resolution"
title_zh: TSD-SR：基于目标得分蒸馏的一步扩散真实世界图像超分辨率
authors: "Dong, Linwei, Fan, Qingnan, Guo, Yihong, Wang, Zhonghao, Zhang, Qi, Chen, Jinwei, Luo, Yawei, Zou, Changqing"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Dong_TSD-SR_One-Step_Diffusion_with_Target_Score_Distillation_for_Real-World_Image_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 基于目标得分蒸馏的一步扩散真实世界图像超分辨率
tldr: 提出目标得分蒸馏（TSD）策略，利用扩散模型先验和真实图像参考，将多步扩散模型蒸馏为单步，实现高质量实时超分辨率，在恢复真实细节和效率上均优于现有方法。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 769, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1811, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 873, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 877, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1801, \"height\": 1032, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 869, \"height\": 286, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1813, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1815, \"height\": 1025, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1804, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dong-tsd-sr-one-step-diffusion-with-target-score-distillation-for-real-world-image-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 280, \"label\": \"Table\"}]"
motivation: 现有一阶扩散方法在图像恢复和细节重建方面效果不佳，多步推理则慢。
method: 设计目标得分蒸馏策略，利用扩散模型先验和真实图像参考，蒸馏出高效的单步超分模型。
result: 在真实世界超分辨率数据集上取得领先性能，同时保持低推理延迟。
conclusion: 证明目标得分蒸馏是构建兼具效率与质量的一步扩散超分模型的有效途径。
---

## Abstract
Pre-trained text-to-image diffusion models are increasingly applied to real-world image super-resolution (Real-ISR) task. Given the iterative refinement nature of diffusion models, most existing approaches are computationally expensive. While methods such as SinSR and OSEDiff have emerged to condense inference steps via distillation, their performance in image restoration or details recovery is not satisfied. To address this, we propose TSD-SR, a novel distillation framework specifically designed for real-world image super-resolution, aiming to construct an efficient and effective one-step model. We first introduce the Target Score Distillation, which leverages the priors of diffusion models and real image references to achieve more realistic image restoration. Secondly, we propose a Distribution-Aware Sampling Module to make detail-oriented gradients more readily accessible, addressing the challenge of recovering fine details. Extensive experiments demonstrate that our TSD-SR has superior restoration results (most of the metrics perform the best) and the fastest inference speed (e.g. 40 times faster than SeeSR) compared to the past Real-ISR approaches based on pre-trained diffusion priors.

---

## 论文详细总结（自动生成）

# TSD-SR：基于目标得分蒸馏的一步扩散真实世界图像超分辨率

## 1. 研究动机与核心问题
- **背景与问题**：预训练文本到图像扩散模型在真实世界图像超分辨率（Real‑ISR）中展现出强大的细节生成能力，但多步迭代去噪导致推理速度极慢（如 SeeSR 需 50 步），难以实用。
- **现有一步蒸馏方法的不足**：
  - 基于 VSD 损失的 OSEDiff 等虽将多步蒸馏为单步，但面临 **梯度方向不可靠**（低质量合成样本上教师模型预测不准）和 **细节恢复不充分**（不同时间步的误差差异大，均匀采样忽略细节优化）两大难题。
  - SinSR、AddSR 等一步模型在图像保真或细节上仍不理想。
- **整体目标**：构建一个兼具高质量恢复和极致推理速度的单步 Real‑ISR 模型。

## 2. 方法论
### 2.1 核心思路
将预训练 T2I 扩散模型（SD3）蒸馏为单步学生模型 \(G_\theta\)，联合教师模型 \(\epsilon_\psi\) 和可训练 LoRA 模型 \(\epsilon_\phi\)，通过 **目标得分蒸馏（TSD）** 和 **分布感知采样模块（DASM）** 解决 VSD 的梯度偏差与细节不足。

### 2.2 目标得分蒸馏（Target Score Distillation, TSD）
- **问题**：VSD 仅用教师‑LoRA 预测残差作为梯度，当学生输出质量差时，教师对合成潜变量 \(\hat{z}_t\) 的预测方向偏离真实方向（余弦相似度仅 0.17）。
- **目标得分匹配（TSM）**：引入真实 HQ 潜变量 \(z_t\)，强制教师对合成样本 \(\hat{z}_t\) 和真实样本 \(z_t\) 的预测一致，公式为  
  \[
  \nabla_\theta \mathcal{L}_{\text{TSM}} = \mathbb{E}_{t,\epsilon} \left[ w(t) \big( \epsilon_\psi(\hat{z}_t; t, c_y) - \epsilon_\psi(z_t; t, c_y) \big) \frac{\partial \hat{z}}{\partial \theta} \right]
  \]
- **融合损失**：将 TSM 与 VSD 加权结合，形成 TSD 损失，权重 \(\lambda\) 和 \(1-\lambda\)，既获得真实分布的先验，又避免 VSD 误导。
  \[
  \nabla_\theta \mathcal{L}_{\text{TSD}} = \mathbb{E}_{t,\epsilon} \left[ w(t) \big( \epsilon_\psi(\hat{z}_t) - \epsilon_\psi(z_t) + \lambda(\epsilon_\psi(z_t) - \epsilon_\phi(\hat{z}_t)) \big) \frac{\partial \hat{z}}{\partial \theta} \right]
  \]
- 借鉴 VSD 的交替训练策略：学生模型最小化重建损失（LPIPS） + TSD 正则化，LoRA 模型则用扩散损失更新。

### 2.3 分布感知采样模块（Distribution‑Aware Sampling Module, DASM）
- **动机**：VSD 在不同时间步上的预测误差不均衡——早期时间步（低噪声阶段）误差大，后期误差小（图 5）。传统均匀采样 \(t\) 无法聚焦细节恢复所需的关键时间步。
- **方法**：在单次迭代中，沿扩散采样轨迹向早期时间步移动，累积多个低噪声样本的梯度。具体地，利用 LoRA 模型从当前噪声样本 \(\hat{z}_t\) 去噪得到 \(\hat{z}_{t-1}\)，同理获得 \(z_{t-1}\)，将这些样本均输入到后续网络进行梯度回传，从而增强细节优化。

### 2.4 训练总损失
- **学生模型**：\(\mathcal{L}_{\text{Stu}} = \mathcal{L}_{\text{LPIPS}}(G_\theta(x_L), x_H) + \gamma \mathcal{L}_{\text{TSD}}\)。
- **LoRA 模型**：\(\mathcal{L}_{\text{Diff}} = \mathbb{E}_{t,\epsilon} \left[ \|\epsilon_\phi(\hat{z}_t; t, c_y) - \epsilon' \|^2 \right]\)，\(\epsilon'\) 为扩散训练目标（噪声或流向 HQ 的梯度）。

## 3. 实验设计
- **训练数据**：DIV2K + Flickr2K + LSDIR + 前 10K 张 FFHQ 人脸，采用 Real‑ESRGAN 的降质管线合成 LR‑HR 对。
- **测试基准**：
  - 合成数据：DIV2K‑Val。
  - 真实世界数据：RealSR、DRealSR（128→512 像素）。
- **评估指标**：
  - 全参考：PSNR、SSIM、LPIPS、DISTS、FID。
  - 无参考：NIQE、MUSIQ、MANIQA、CLIPIQA。
- **对比方法**：
  - 单步扩散模型：SinSR、AddSR‑1s、OSEDiff‑1s。
  - 多步扩散模型：StableSR（200 步）、ResShift（15 步）、PASD（20 步）、DiffBIR（50 步）、SeeSR（50 步）、SUPIR（50 步）、AddSR‑4s。
- **用户研究**：50 名参与者从人脸、建筑、动物、植物、文字五类图像中评选最佳恢复效果，以偏好率衡量。

## 4. 资源与算力
- **硬件**：8 块 NVIDIA V100 GPU。
- **训练时长**：约 120 小时。
- **批大小**：16。
- **优化器与学习率**：AdamW，学生模型 \(5\times10^{-6}\)，LoRA 模型 \(1\times10^{-6}\)；LoRA 秩设为 64。
- **推理速度**：在 A100 GPU 上，输入 512×512 图像，仅需 **0.1362 秒**（不含模型加载），比 SeeSR 快 40 倍以上，比 SUPIR 快 120 倍以上。

## 5. 实验数量与充分性
- **定量对比**：
  - 单步模型在三个数据集上的全面指标表（Tab.1）。
  - 多步模型在相同数据集上的指标表（Tab.2）。
  - 计算复杂度对比表（Tab.3，推理时间）。
- **消融实验**：分别去掉 TSM 和 DASM，在两个数据集上报告 DISTS、MUSIQ、MANIQA、CLIPIQA，验证各模块有效性（Tab.4）。
- **定性分析**：多张可视化对比图（图 7）和用户偏好雷达图/饼图（图 8）。
- **公平性**：所有模型均在同一退化流程下评估，指标覆盖保真度、感知质量、无参考质量；单步/多步模型均取自公开文献，推理时间在同一 A100 上测量。实验设计充分且对比客观。

## 6. 主要结论与发现
- TSD‑SR 在所有单步模型中取得最优的 LPIPS、DISTS、NIQE、FID、MUSIQ、CLIPIQA 等指标，并在多数指标上超越多步模型。
- 推理速度远快于所有对比方法，仅需单步（0.136 s），实现 Real‑ISR 的效率飞跃。
- TSM 有效修复了 VSD 的梯度不可靠问题，避免伪影；DASM 进一步提升了细节恢复。
- 用户研究中，TSD‑SR 获得 69.2% 的偏好率，在所有类别中均占优。

## 7. 优点与方法亮点
- **创新损失设计**：首次融合真实样本得分匹配与变分得分蒸馏，既稳定优化又保持感知真实性。
- **训练采样策略**：DASM 沿扩散轨迹积累梯度，显式增强了高频细节的优化。
- **极致效率**：真正实现了一步到位的扩散 Real‑ISR，推理速度比同期最快的多步模型还快一个数量级。
- **实验扎实**：覆盖合成与真实数据集、多种指标、单步与多步对比、消融分析和用户研究，结论可信。

## 8. 不足与局限
- **模型参数仍较大**：相比于传统 GAN 或非扩散方法，蒸馏后的模型依然保有大量参数，未来需通过剪枝、量化等手段进一步轻量化。
- **训练数据与退化覆盖**：仅用 Real‑ESRGAN 合成的降质数据训练，面对完全未知的真实复杂退化（如极端噪声、混叠、非均匀模糊）时性能可能下降。
- **PSNR/SSIM 较低**：论文也承认生成更丰富细节会牺牲这类保真度指标，但未深入探讨如何在感知‑失真权衡中取得更好平衡。
- **未进行跨域或跨尺度的泛化测试**：实验限于 4× 超分，未见针对更高倍率或不同下采样方式的评测。

（完）
