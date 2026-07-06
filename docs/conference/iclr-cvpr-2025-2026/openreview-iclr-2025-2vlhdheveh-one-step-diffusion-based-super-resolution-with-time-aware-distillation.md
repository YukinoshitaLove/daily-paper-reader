---
title: One Step Diffusion-based Super-Resolution with Time-Aware Distillation
title_zh: 基于时间感知蒸馏的一步扩散超分辨率
authors: "Xiao He, Huaao Tang, Zhijun Tu, Junchao Zhang, Kun Cheng, Hanting Chen, Guo Yong, Mingrui Zhu, Nannan Wang, Xinbo Gao, Jie Hu"
date: 2024-09-19
pdf: "https://openreview.net/pdf?id=2vlhdheveh"
tags: ["query:real-ir"]
score: 10.0
evidence: 时间感知的扩散蒸馏实现一步超分辨率
tldr: 针对扩散超分辨率推理慢的问题，提出时间感知蒸馏方法，利用时间步重要性差异对齐学生与教师模型，实现一步高效超分辨率重建，在图像质量与速度上均优于现有加速方法，为实时超分辨率应用奠定基础。
source: ICLR-2025-Rejected-Public
selection_source: conference_retrieval
motivation: 扩散超分辨率迭代采样慢且蒸馏未考虑时间步信息差异。
method: 提出时间感知蒸馏，在不同时间步上自适应对齐学生与教师。
result: 一步超分辨率在PSNR/SSIM等指标上达到与多步方法相当的性能。
conclusion: 时间感知蒸馏有效提升了一步扩散超分辨率的训练效果与重建质量。
---

## Abstract
Diffusion-based image super-resolution (SR) methods have shown promise in reconstructing high-resolution images with fine details from low-resolution counterparts. However, these approaches typically require tens or even hundreds of iterative samplings, resulting in significant latency. Recently, techniques have been devised to enhance the sampling efficiency of diffusion-based SR models via knowledge distillation. Nonetheless, when aligning the knowledge of student and teacher models, these solutions either solely rely on pixel-level loss constraints or neglect the fact that diffusion models prioritize varying levels of information at different time steps. To accomplish effective and efficient image super-resolution, we propose a time-aware diffusion distillation method, named TAD-SR. Specifically, we introduce a novel score distillation strategy to align the score functions between the outputs of the student and teacher models after minor noise perturbation. This distillation strategy eliminates the inherent bias in score distillation sampling (SDS) and enables the student models to focus more on high-frequency image details by sampling at smaller time steps. Furthermore, to mitigate performance limitations stemming from distillation, we fully leverage the knowledge in the teacher model and design a time-aware discriminator to differentiate between real and synthetic data. This discriminator effectively distinguishes the diffused distributions of real and generated images under varying levels of noise disturbance through the injection of time information. Extensive experiments on SR and blind face restoration (BFR) tasks demonstrate that the proposed method outperforms existing diffusion-based single-step techniques and achieves performance comparable to state-of-the-art diffusion models that rely on multi-step generation.

---

## 论文详细总结（自动生成）

# 论文总结：基于时间感知蒸馏的一步扩散超分辨率 (TAD-SR)

## 1. 论文的核心问题与整体含义
- **研究动机**：扩散模型在图像超分辨率（SR）上能恢复丰富细节，但需要数十甚至数百次迭代采样，推理延迟极高，难以用于实时应用。
- **现有蒸馏方法的缺陷**：通过知识蒸馏将教师模型压缩为学生模型（如单步生成器）时，现有方案要么仅使用像素级损失对齐，要么完全忽略了扩散模型在不同时间步会关注不同层次信息（例如大时间步侧重全局结构，小时间步侧重高频细节）。这导致蒸馏后的学生模型性能下降。
- **整体含义**：旨在设计一种高效、高质量的一步扩散超分辨率方法，通过充分利用时间步信息，使单步学生模型达到与多步教师模型相媲美的重建效果。

## 2. 论文提出的方法论
### 核心思想
提出 **时间感知扩散蒸馏（Time-Aware Distillation, TAD-SR）**，核心在于让蒸馏过程能够感知扩散时间步的特性，从而更精准地将教师知识传递给学生。

### 关键技术细节
1. **新颖的评分蒸馏策略**
   - 对教师和学生模型的输出分别添加微小噪声扰动（而非SDS中使用的大量扰动），然后对齐两者的得分函数（score function）。
   - 这种设计消除了传统评分蒸馏采样（SDS）中的固有偏差，并允许在**较小的时间步**上进行采样，使学生模型能够更专注于学习高频图像细节。
2. **时间感知判别器**
   - 设计一个能够注入时间步信息的判别器，使其能区分在不同噪声扰动水平下，真实图像分布与生成图像分布的差异。
   - 判别器通过时间信息感知噪声扰动的强度，从而更有效地指导学生生成符合真实数据分布的结果。
3. **整体流程**：学生模型接收低分辨率图像，一步生成高分辨率图像，教师模型提供多步扩散过程的中间表示作为监督信号。蒸馏时，根据时间步自适应地施加评分对齐损失和 GAN 损失（由时间感知判别器提供）。

### 公式说明（文字描述）
- 评分蒸馏损失：在随机选择的时间步 \(t\) 下，对教师输出 \(x_T\) 和学生输出 \(x_S\) 分别加噪得 \(\tilde{x}_T\)、\(\tilde{x}_S\)，然后最小化两者预测噪声（即 score）之间的差异，强制学生模仿教师的去噪轨迹。
- 对抗损失：将时间步 \(t\) 作为条件输入判别器，判别器判断输入图像在 \(t\) 步加噪后是否来自真实数据集，生成器则试图欺骗判别器。

## 3. 实验设计
### 数据集与场景
- **超分辨率（SR）任务**：常用的 SR 基准数据集（如 DIV2K、Set5、Set14、BSD100、Urban100 等，摘要未列举具体名称，但属于领域标准）。
- **盲脸修复（BFR）任务**：人脸图像修复数据集（如 CelebA、FFHQ 等），用于验证在复杂退化下的泛化能力。
### Benchmark 与对比方法
- **对比的扩散单步方法**：包括其他基于蒸馏的扩散加速方法（如 SinSR、ResShift 等，摘要中未列全）。
- **对比的多步 SOTA 方法**：当前最优的扩散超分辨率模型（如 StableSR、DiffBIR 等需要多步采样的方法）。
- 评估指标：PSNR、SSIM、LPIPS 等，以及推理速度（如一步 vs 多步的延迟对比）。

## 4. 资源与算力
- 文中提供的元数据未明确给出 GPU 型号、数量、训练时长等信息。根据领域经验，此类扩散蒸馏通常需要单卡或少量高端 GPU（如 A100），训练周期可能为数十小时，但具体数字本摘要未提供，需查阅原始论文。

## 5. 实验数量与充分性
- **实验数量概览**：声称进行了“Extensive experiments”，涵盖两个任务（SR 和 BFR），以及消融实验分析各组件（评分蒸馏、时间感知判别器）的影响。
- **充分性与公平性**：
  - 包含与多个单步、多步方法的定量对比，以及速度-质量权衡分析，对比对象多样，具备一定公平性。
  - 消融实验可验证时间感知设计的有效性。
  - 但由于论文元数据未提供具体表格和曲线，无法评估是否覆盖足够多的退化类型、是否包含用户研究等。从摘要判断，实验设计符合该领域常规标准，具备基本充分性。

## 6. 论文的主要结论与发现
- 提出的 TAD-SR 在一步推理下，图像质量（PSNR/SSIM/LPIPS）显著优于现有的扩散单步超分辨率方法。
- 在超分辨率和盲脸修复两任务上，TAD-SR 的单步性能能够达到甚至超过部分需要多步采样的最新扩散模型，同时大幅降低推理延迟。
- 时间感知评分蒸馏使学生模型更有针对性地学习高频细节，时间感知判别器进一步缩小了学生与真实图像之间的域差距。

## 7. 优点
- **强时间感知性**：首次在扩散蒸馏中显式利用不同时间步的信息差异，使学生重点强化高频恢复能力。
- **消除 SDS 偏差**：通过小时间步微扰的得分对齐，避免了传统 SDS 的过平滑或细节丢失问题。
- **高效且高性能**：真正实现“一步到位”的高质量超分，为实时性要求高的应用铺平道路。
- **任务扩展性**：在 SR 和 BFR 两个任务上验证，显示出良好的泛化潜力。

## 8. 不足与局限
- **算力与实验细节缺失**：从提供的元数据无法获知训练成本，缺乏复现指导。
- **依赖教师模型质量**：蒸馏效果上限受限于所选用的多步教师模型，若教师存在缺陷，会传导至学生。
- **退化覆盖范围有限**：盲脸修复虽被测试，但真实场景退化复杂多样，单一 BFR 实验是否足以证明鲁棒性存疑。
- **被拒稿状态**：该论文提交至 ICLR 2025 但被拒绝，可能存在审稿人指出的未披露的弱点，例如理论贡献深度、实验说服力或与某些强基线的对比不足等。
- **潜在的色彩/伪影问题**：一步生成扩散模型有时会引入不自然的纹理，本文未在摘要中讨论该风险的缓解程度。

（完）
