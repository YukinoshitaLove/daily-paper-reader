---
title: Noise Conditional Variational Score Distillation
title_zh: 噪声条件变分分数蒸馏
authors: "Xinyu Peng, Ziyang Zheng, Yaoming Wang, Han Li, Nuowen Kan, Wenrui Dai, Chenglin Li, Junni Zou, Hongkai Xiong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UYUqCPCZCw"
tags: ["query:real-ir"]
score: 9.0
evidence: 将预训练扩散模型蒸馏为快速生成式去噪器
tldr: 针对扩散模型采样速度慢的问题，提出噪声条件变分分数蒸馏（NCVSD）方法，将预训练扩散模型蒸馏为生成式去噪器。通过揭示无条件评分函数隐含表征后验去噪分布，在变分分数蒸馏框架下实现可扩展学习。所得去噪器支持快速单步生成，同时保留迭代细化的优势，为扩散模型的高效部署提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1750, \"height\": 1287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 2154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 2161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1703, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1776, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uyuqcpczcw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 2036, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 1400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 879, \"height\": 1373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 1352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1717, \"height\": 705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uyuqcpczcw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 424, \"label\": \"Table\"}]"
motivation: 扩散模型生成速度慢，需要多步采样。
method: 提出NCVSD，利用无条件评分函数与后验分布的关系，蒸馏扩散模型为单步生成去噪器。
result: 实现快速生成，同时保持迭代细化的效果。
conclusion: NCVSD为扩散模型的加速和生成能力保留提供了新途径。
---

## Abstract
We propose Noise Conditional Variational Score Distillation (NCVSD), a novel method for distilling pretrained diffusion models into generative denoisers. We achieve this by revealing that the unconditional score function implicitly characterizes the score function of denoising posterior distributions. By integrating this insight into the Variational Score Distillation (VSD) framework, we enable scalable learning of generative denoisers capable of approximating samples from the denoising posterior distribution across a wide range of noise levels. The proposed generative denoisers exhibit desirable properties that allow fast generation while preserve the benefit of iterative refinement: (1) fast one-step generation through sampling from pure Gaussian noise at high noise levels; (2) improved sample quality by scaling the test-time compute with multi-step sampling; and (3) zero-shot probabilistic inference for flexible and controllable sampling. 
We evaluate NCVSD through extensive experiments, including class-conditional image generation and inverse problem solving. By scaling the test-time compute, our method outperforms teacher diffusion models and is on par with consistency models of larger sizes. Additionally, with significantly fewer NFEs than diffusion-based methods, we achieve record-breaking LPIPS on inverse problems.

---

## 论文详细总结（自动生成）

# 论文总结：噪声条件变分分数蒸馏 (Noise Conditional Variational Score Distillation)

## 1. 核心问题与整体含义

- **研究动机**：扩散模型作为当前主流的生成模型，其迭代采样机制虽然提供了高质量的样本和灵活的推理控制，但速度慢，限制了其在实时应用中的部署。
- **核心问题**：现有的扩散模型蒸馏方法（如一致性模型、对抗蒸馏）虽然加快了生成速度，但在追求少步甚至单步生成时，往往牺牲了迭代细化的能力（即通过增加算力提升样本质量）和零样本可控推理的灵活性。
- **整体含义**：本文旨在提出一种新型的模型蒸馏框架，能从预训练扩散模型中蒸馏出**生成式去噪器**。这种新型生成模型既能实现极快的单步生成，又天然支持多步采样和零样本概率推理，在效率和灵活性之间取得了更好的平衡。

## 2. 方法论

- **核心思想**：论文揭示了一个关键理论联系：**无条件评分函数可以隐式地表征去噪后验分布的评分函数**。基于此，作者将变分分数蒸馏（VSD）框架扩展到带有噪声条件的形式，即噪声条件变分分数蒸馏（NCVSD）。
- **关键技术细节**：
    - **噪声条件VSD目标**：学习一个条件生成模型 $\mu_\theta(x_0|y_\sigma)$，该模型能在广泛的噪声水平 $\sigma$ 下，从噪声数据 $y_\sigma$ 中重构出干净数据 $x_0$。其优化目标是最小化扩散后模型分布与数据分布之间的反向 KL 散度。
    - **噪声条件评分估计器**：核心贡献之一。论文提出，条件评分函数 $\nabla_{x_t} \log q(x_t|y_\sigma)$ 可以通过一个预训练的无条件评分模型 $D_0$ 和一个闭式解来精确估计，公式如下：
        $$ \nabla_{x_t} \log q(x_t|y_\sigma) \approx t^{-2}\left[D_0\left(\frac{\sigma^{-2}y_\sigma + t^{-2}x_t}{\sigma^{-2} + t^{-2}}, (\sigma^{-2} + t^{-2})^{-\frac{1}{2}}\right) - x_t\right] $$
        这个估计器将噪声数据 $y_\sigma$ 和扩散过程中的数据 $x_t$ 融合，计算出有效的噪声水平，从而驱动蒸馏学习。
    - **辅助对抗损失**：为弥补教师模型不完美和模型评分估计不准确的问题，引入一个基于 Jensen-Shannon 散度的对抗损失，通过训练一个判别器来区分真实数据和生成数据在扩散空间中的分布。
    - **多步采样机制**：基于 DDIM 的思想，构建了一个边缘分布保持的多步采样链，允许在推理时通过增加采样步数来提升样本质量。
    - **即插即用概率推理 (PnP-GD)**：基于分裂吉布斯采样（SGS）框架，将训练好的生成式去噪器作为“先验步骤”的高效采样器，用于解决各类贝叶斯后验推断问题（如逆问题）。

## 3. 实验设计

- **数据集与场景**：
    - **类别条件图像生成**：在 **ImageNet-64×64** 和 **ImageNet-512×512** 数据集上进行评估。
    - **逆问题求解**：在 **FFHQ-256×256** 数据集上测试零样本概率推理能力，包括5个任务：**盒状修复、高斯去模糊、运动去模糊、超分辨率（4×）和相位恢复**。
- **基准与对比方法**：
    - **图像生成**：与教师模型 **EDM2** 和一致性模型的最新变体 **sCM, ECM** 等进行对比，指标为 FID。
    - **逆问题求解**：与多种基于扩散模型的零样本求解器对比，包括 **DDRM, DPS, DiffPIR, ΠGDM, DWT-Var, DAPS, 和 PnP-DM**。指标为 LPIPS 和 PSNR。

## 4. 资源与算力

- **硬件**：论文使用了 **NVIDIA A100 GPU**。
- **训练时长与配置**：
    - **ImageNet 64x64**：不同规模模型 (S/M/L) 的单 GPU 批大小分别为 64/32/16，训练总时长分别为 **650/1100/1450 GPU小时**。
    - **ImageNet 512x512**：训练总时长分别为 **650/1100/1450 GPU小时**。
    - **FFHQ 256x256**：使用 XS 规模模型，单 GPU 批大小为 8，训练总时长为约为 **300 GPU小时**。

## 5. 实验数量与充分性

- **实验组数**：论文进行了多组实验，包括：
    - **主要对比实验**：在两个 ImageNet 数据集上，用三种模型规模（S/M/L）与教师模型和多种一致性模型学生进行性能（FID）和计算成本（NFE）对比。
    - **消融实验（变参数实验）**：在逆问题去模糊任务中，详细分析了 PnP-GD 中 **EMA 衰减率** 对 LPIPS 和 PSNR 的影响，展示了该参数在感知-失真权衡中的作用。
- **充分性与公平性**：
    - **非常充分**。实验覆盖了不同模型规模、不同数据分辨率、有条件和无条件的各类任务。
    - **对比公平**。与当前最先进的蒸馏方法（sCM, ECM）进行了同级别尺寸和多步数下的对比，并明确标注了各自的训练迭代次数。在逆问题中，与多种零样本方法进行了全面比较，并考虑了计算效率（NFE）。

## 6. 主要结论与发现

- **性能优越性**：NCVSD 蒸馏的生成式去噪器在**同等尺寸**下，其单步和多步生成的 FID **优于**一致性模型（sCM/ECM），并且所需的训练迭代次数**显著更少**。
- **算力可扩展性**：通过增加推理时的计算量（多步采样），NCVSD 模型可以**匹配甚至超越更大尺寸**的一致性模型。例如，4步的 NCVSD-L 在 ImageNet-512 上 FID（1.76）超越了 2步 sCD-XXL（1.88）和教师模型 EDM2-XXL（1.81）。
- **高效灵活的推理**：提出的 PnP-GD 推理框架，在多个线性与非线性逆问题上，仅需**50 次函数计算（NFE）**，就取得了**最优或次优的 LPIPS 分数**，相比扩散模型方法（通常需 1k NFE）加速约 20 倍，展示了其在保持感知质量的同时大幅提升效率的潜力。

## 7. 优点与亮点

- **理论创新**：揭示了无条件评分函数与条件评分函数之间的理论联系，为蒸馏和逆问题求解提供了新思路。
- **方法统一**：生成的“生成式去噪器”是一个统一的模型，能同时实现快速单步生成、多步质量提升和零样本概率推理，功能强大。
- **效率与性能俱佳**：在图像生成上，以更少的训练开销达到甚至超越最先进水平；在逆问题上，以数量级减少的计算量取得突破性的感知质量（LPIPS）。
- **实践贡献**：对模型参数化（如幅度保持求和）、对抗损失动态平衡等技术细节进行了精心设计，并验证了其有效性，具有很强的实用价值。

## 8. 不足与局限

- **依赖预训练模型**：该方法不能从头训练，依赖于一个预训练好的扩散模型作为教师，限制了其独立性。
- **训练稳定性**：需要引入对抗训练，这通常需要仔细的手动调参以确保收敛，可能会影响方法的易用性和在不同数据上的泛化能力。
- **规模验证受限**：作者承认由于算力限制，未能在更大型的模型或数据集上验证 NCVSD 的效果。
- **PSNR 表现不最优**：在逆问题求解中，该方法倾向于产生高频细节丰富的“感知质量”好的样本（LPIPS 更优），但其 PSNR 值有时不如其他方法。这体现了感知-失真权衡，可能不适用于对像素级保真度要求极高的场景。

（完）
