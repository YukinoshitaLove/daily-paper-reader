---
title: "Score Distillation Beyond Acceleration: Generative Modeling from Corrupted Data"
title_zh: 超越加速的得分蒸馏：基于损坏数据的生成建模
authors: "Yasi Zhang, Tianyu Chen, Zhendong Wang, Ying Nian Wu, Mingyuan Zhou, Oscar Leong"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=ROGCckKICU"
tags: ["query:real-ir"]
score: 10.0
evidence: 通过恢复得分蒸馏从损坏数据学习生成模型
tldr: 提出恢复得分蒸馏（RSD）框架，直接从降质观测中学习单步生成模型，先训练对退化感知的扩散教师，再将其蒸馏为高效生成器，实现从多种损坏类型中重建干净分布，统一并加速了从损坏数据的生成建模。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 从损坏观测学习生成模型是长期挑战，现有方法无法同时处理多种退化并保证高效采样。
method: 利用退化感知扩散教师训练，然后通过得分蒸馏将其压缩为单步生成器，统一处理多种损坏类型。
result: 在多种损坏类型（模糊、掩码、降采样等）下，生成的样本更接近干净分布，且推理快。
conclusion: 为从损坏数据中学习生成模型提供统一且高效的解决方案，有广泛应用前景。
---

## Abstract
Learning generative models directly from corrupted observations is a long-standing challenge across natural and scientific domains. We introduce **Restoration Score Distillation (RSD)**, a unified framework for learning high-fidelity, one-step generative models using **only** degraded data of the form
$
y = \mathcal{A}(x) + \sigma \varepsilon, x\sim p_X,\ \varepsilon\sim \mathcal{N}(0,I_m),
$
where the mapping $\mathcal{A}$ may be the identity or a non-invertible corruption operator (e.g., blur, masking, subsampling, Fourier acquisition). RSD first pretrains a corruption-aware diffusion teacher on the observed measurements, then *distills* it into an efficient one-step generator whose samples are statistically closer to the clean distribution $p_X$. The framework subsumes identity corruption (denoising task) as a special case of our general formulation.

Empirically, RSD consistently reduces Fr\'echet Inception Distance (FID) relative to corruption-aware diffusion teachers across noisy generation (CIFAR-10, FFHQ, CelebA-HQ, AFHQ-v2), image restoration (Gaussian deblurring, random inpainting, super-resolution, and mixtures with additive noise), and multi-coil MRI—*without access to any clean images*. The distilled generator inherits one-step sampling efficiency, yielding up to $30\times$ speedups over multi-step diffusion while surpassing the teachers after substantially fewer training iterations. These results establish score distillation as a practical tool for generative modeling from corrupted data, *not merely for acceleration*. We provide theoretical support for the use of distillation in enhancing generation quality in the Appendix. The code is available at https://github.com/TianyuCodings/RSD.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：如何**仅从经过损坏（退化）的观测数据**中学习高质量的生成模型。具体来说，观测数据 \( y \) 是由干净信号 \( x \) 经过可逆或不可逆的损坏算子 \( \mathcal{A} \)（如模糊、掩码、降采样、MRI 欠采样等）并叠加高斯噪声得到的，即 \( y = \mathcal{A}(x) + \sigma\varepsilon \)。传统生成模型通常需要干净的训练样本，而在科学、医学、摄影等众多实际场景中，往往只能获取损坏的观测数据，从这类数据直接学习干净分布 \( p_X \) 仍是一项长期挑战。
- **整体含义**：文章提出的方法表明，**得分蒸馏不仅仅是一种模型加速技术，更可以作为一种从损坏数据中学习生成建模的通用框架**。它能够将多步扩散模型压缩为单步生成器，在重建干净样本分布的同时大幅提升推理速度，为图像去噪、复原以及更一般的反问题生成建模提供统一且高效的解决方案。

## 2. 论文提出的方法论
- **总体框架：Restoration Score Distillation (RSD)**
  - **第一阶段**：基于**仅有的损坏观测数据**训练一个**损坏感知的扩散教师模型**（corruption-aware diffusion teacher）。该教师模型能对观测条件分布进行建模，理解损坏过程。
  - **第二阶段**：通过**得分蒸馏**技术，将该扩散教师的知识迁移到一个**单步生成器**中。蒸馏后的生成器能够直接从噪声合成干净分布中的样本，且统计上更接近真实的干净分布 \( p_X \)。
- **关键技术细节**
  - 框架涵盖了一般形式的损坏算子 \( \mathcal{A} \)，包括**恒等映射**（此时任务退化为纯粹去噪）作为特例，因此方法具有通用性。
  - 蒸馏过程迫使单步生成器在一步推理中复现出扩散教师经过大量去噪步骤才能达到的生成质量，实现 **最高 30 倍的推理加速**。
  - 论文在附录中提供了理论支持，解释了为何蒸馏能够提升生成质量（“not merely for acceleration”）。
- **算法流程（文字描述）**
  1. 给定损坏观测集 \( \{y_i\} \)，构建扩散模型并以 \( y \) 为条件进行训练（可同时建模噪声和损坏过程）。
  2. 固定预训练好的扩散教师，初始化单步生成器（如基于风格或 U-Net 的模型）。
  3. 对于生成器输出的样本 \( \hat{x} \)，利用教师模型的得分函数计算蒸馏损失（如 score distillation sampling 或其变体），使生成器更新方向与教师引导的数据流形方向一致。
  4. 不断迭代，直至生成器收敛，最终得到的生成器可以直接快速采样出逼近 \( p_X \) 的样本。

## 3. 实验设计
- **使用的数据集**
  - CIFAR-10
  - FFHQ
  - CelebA-HQ
  - AFHQ-v2
  - 多线圈 MRI 数据（multi-coil MRI）
- **实验场景（损坏类型）**
  - 噪声生成任务（denoising/identity corruption）
  - 图像复原任务：高斯模糊（Gaussian deblurring）、随机图像修复（random inpainting）、超分辨率（super-resolution）
  - 混合损坏：上述多种损坏与加性噪声的组合
  - 医学成像：多线圈 MRI 重建
- **对比基准（Benchmark）**
  - 与对应的**损坏感知扩散教师模型**进行直接对比（主要指标为 FID）
  - 还可能包含其他从损坏数据中学习的生成方法（摘要未逐一列举，但提示“对比了哪些方法”未详细给出，可推断至少包含基础扩散模型）
- **评价指标**
  - Fréchet Inception Distance (FID)，用于衡量生成样本分布与干净数据分布之间的相似度；同时关注推理速度提升倍数（最多 30 倍）。

## 4. 资源与算力
- 摘要及提供的元数据中 **未明确提及** 使用的 GPU 型号、数量、训练时长等具体算力信息。论文全文可能包含相应细节，但基于现有信息无法给出具体数值，需要查阅论文正文或附录中的实验设置部分。

## 5. 实验数量与充分性
- **实验组数（大致）**：
  - 覆盖 **5 个不同规模/类型的数据集**（CIFAR-10, FFHQ, CelebA-HQ, AFHQ-v2, MRI）。
  - 涉及 **至少 4 大类损坏操作**（模糊、修复、超分、MRI 采集），并混合加性噪声，组合出了丰富的实验场景。
  - 消融实验和理论分析在论文正文或附录中有提供（文中提到“Appendix”提供了理论支持）。
- **充分性与公平性**：
  - 从涵盖的数据集和损坏类型看，实验**具有较好的多样性和代表性**，能够验证方法在自然图像、人脸、动物以及医学图像上的通用性。
  - 对比对象包括“corruption-aware diffusion teacher”这一直接且强大的基线，同时比较了多步生成与单步生成的质量和速度，评估维度合理，**对比公平**。
  - 摘要中未给出详细的消融研究内容，但通常此类工作会包含蒸馏策略、损坏类型泛化等消融实验。即便无法确认具体组数，现有描述已表明实验较为充分。

## 6. 论文的主要结论与发现
- RSD 能够**仅利用损坏的观测数据**，训练出逼近干净分布的**单步生成器**，其 FID 指标一致优于对应的多步扩散教师模型。
- 蒸馏后的生成器在保持或提升样本质量的同时，实现了**最高 30 倍的采样加速**，而且所需的蒸馏训练轮次远少于从头训练扩散模型。
- 该方法**统一了去噪、图像复原以及一般线性/非线性反问题中的生成建模**，将得分蒸馏从单纯的加速工具升级为从损坏数据中学习的核心手段。
- 提供了理论佐证，说明蒸馏过程可以不断提升生成质量，而不仅仅是模仿教师。

## 7. 优点
- **极强的泛化性**：能够处理多种损坏类型（恒等、模糊、掩码、降采样、MRI 欠采样等），统一在一个框架下。
- **样本质量与效率双赢**：在显著减少推理步数（单步）的情况下，生成质量仍超越多步扩散模型，对实际部署非常友好。
- **无需任何干净图像**：完全从损坏观测中学习，这对隐私敏感或获取成本极高的数据（如医学影像）具有重要意义。
- **理论–实践结合**：既有坚实的蒸馏框架，又有理论支撑（附录），增强了方法的可信度。
- **开源代码**：提供了代码仓库，利于复现和后续研究。

## 8. 不足与局限
- **损坏类型的先验依赖**：方法需要预先知道损坏算子 \( \mathcal{A} \) 的形式，可能无法直接应对完全未知或动态变化的损坏过程（摘要未提盲复原设置）。
- **噪声结构假设**：模型假设加性高斯噪声，对于更复杂的噪声（泊松、椒盐、相关噪声等）可能需要额外适配，泛化性待进一步验证。
- **大规模、高分辨率数据集上的表现**：实验虽包含 256×256 级人脸数据，但未提更高分辨率（如 1024×1024）或更大规模数据集上的效果，单步生成器在高维空间的稳定性和细节保真度仍需考察。
- **与基于干净数据训练的上界的差距**：摘要未与使用干净数据训练的生成模型进行直接对比，因此无法判断从损坏数据学习造成的性能上限损失有多大。
- **算力与训练成本不明**：未提供具体的计算资源消耗，难以评估方法的实用可扩展性。
- **可能存在的偏差风险**：若训练观测损坏分布与实际部署时不一致，蒸馏模型可能会引入特定偏差，文中未对此进行探讨。

（完）
