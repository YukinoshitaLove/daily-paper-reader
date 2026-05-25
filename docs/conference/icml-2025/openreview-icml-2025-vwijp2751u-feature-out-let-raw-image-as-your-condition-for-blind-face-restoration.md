---
title: "Feature out! Let Raw Image as Your Condition for Blind Face Restoration"
title_zh: 特征出局！让原始图像成为盲人脸修复的条件
authors: "Xinmin Qiu, Chen Gege, Bonan Li, Congying Han, Tiande Guo, Zicheng Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vwIjp2751u"
tags: ["query:real-ir"]
score: 10.0
evidence: 通过伪哈希薛定谔桥进行盲人脸修复
tldr: P-I2SB 针对盲人脸修复中复杂未知退化的难题，提出伪哈希图像到图像薛定谔桥框架，将原始低质图像直接作为逆向扩散的起点，通过校正数据分布并学习分布间最优传输路径，理论上证明了其最优性。实验表明该方法在修复质量上达到新水平，为生成式图像修复提供了更优的理论路径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1731, \"height\": 996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1772, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1776, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1780, \"height\": 2086, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1780, \"height\": 1605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1779, \"height\": 1570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1780, \"height\": 1568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1779, \"height\": 1593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1778, \"height\": 1586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwijp2751u/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1779, \"height\": 1433, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 747, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 839, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwijp2751u/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1757, \"height\": 201, \"label\": \"Table\"}]"
motivation: 现有扩散方法使用特征提取器引导，未能充分利用低质图像本身的最优起始点性质。
method: 提出P-I2SB框架，结合伪哈希与薛定谔桥，校正分布并学习最优传输路径。
result: 在盲人脸修复任务上取得领先性能，验证了直接用原始图像作为条件的理论优势。
conclusion: P-I2SB 为生成式图像修复开辟了基于最优传输的新范式。
---

## Abstract
Blind face restoration (BFR), which involves converting low-quality (LQ) images into high-quality (HQ) images, remains challenging due to complex and unknown degradations. 
    While previous diffusion-based methods utilize feature extractors from LQ images as guidance, using raw LQ images directly as the starting point for the reverse diffusion process offers a theoretically optimal solution. 
    In this work, we propose Pseudo-Hashing Image-to-image Schrödinger Bridge (P-I2SB), a novel framework inspired by optimal mass transport problems, which enhances the restoration potential of Schrödinger Bridge (SB) by correcting data distributions and effectively learning the optimal transport path between any two data distributions.
    Notably, we theoretically explore and identify that existing methods are limited by the optimality and reversibility of solutions in SB, leading to suboptimal performance. 
    Our approach involves preprocessing HQ images during training by hashing them into pseudo-samples according to a rule related to LQ images, ensuring structural similarity in distribution.
    This guarantees optimal and reversible solutions in SB, enabling the inference process to learn effectively and allowing P-I2SB to achieve state-of-the-art results in BFR, with more natural textures and retained inference speed compared to previous methods.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究背景**：盲人脸修复（Blind Face Restoration, BFR）旨在将未知复杂退化下的低质量（LQ）人脸图像恢复为高质量（HQ）图像。现有扩散模型方法大多使用特征提取器从 LQ 图像中提取条件信息来引导生成，但这种方式没有将原始 LQ 图像本身作为逆向扩散的起点，理论上并非最优。
- **研究动机**：薛定谔桥（Schrödinger Bridge, SB）能够直接建立两个任意分布之间的最优传输路径。然而，在 BFR 等多对多的盲逆问题中，一个 HQ 图像可能对应多个 LQ 退化版本，破坏了 SB 解的最优性和可逆性，导致现有基于 SB 的方法（如 I2SB）在盲任务上表现不佳。
- **整体含义**：提出 Pseudo-Hashing Image-to-image Schrödinger Bridge (P-I2SB) 框架，通过简单的伪哈希预处理修正数据分布，使原始 LQ 图像可直接作为逆向过程的端点，从而在理论上保证 SB 解的最优和可逆，并在实践中大幅提升盲人脸修复的质量和效率。

## 2. 方法论
- **核心思想**：不依赖复杂的特征提取器，而是通过伪哈希策略将训练对 $(HQ, LQ)$ 转换为满足 SB 边界条件的新对 $(\hat{x}, y)$，然后直接使用 I2SB 学习两者之间的最优传输桥。
- **伪哈希模块（PHM, Pseudo-Hashing Module）**：
  - 训练时，给定 $x$（HQ）和其退化版本 $y$（LQ），利用某种可逆规则生成 $\hat{x} = H(x, y)$，使得 $\hat{x}$ 的分布结构与 $y$ 相似。
  - 提出三种具体策略：
    1. **Cat-I2SB**：通道拼接 $\hat{x} = x \oplus y$，对应 $y$ 变为 $y \oplus y$，形成 6 通道图像对。
    2. **Res-I2SB**：相对残差 $\hat{x} = y - x$，使两端的分布方向一致，保持空间几何关系。
    3. **Noise-I2SB**：轻量加噪 $\hat{x} = x + \sigma(y) \epsilon$，即对 HQ 图像加上与退化相关的噪声，而不损坏内容。
  - 推理时通过逆运算 $ \bar{x} = J(\hat{x}, y)$ 恢复 HQ 图像，如 Cat 取前 3 通道、Res 为 $y-\hat{x}$、Noise 采用 DDIM 去噪。
- **薛定谔桥模块（SBM, Schrödinger Bridge Module）**：
  - 沿用 I2SB 的前向/逆向 SDE 设计。前向过程 $q(X_t|X_0, X_1)$ 固定端点 $\hat{x}$ 和 $y$，学习一个可直接从 LQ 到 HQ 的扩散桥。
  - 损失函数为 $\mathcal{L} = \| \epsilon(X_t, t; \theta) - \frac{X_t - X_0}{\sigma_t} \|$，与 SGM 框架一致。
- **理论支撑**：
  - 定理 4.1 表明，若边界分布退化为 Dirac 分布，则桥的坐标过程服从相同的 SDE。
  - 推论 4.2 指出，多对一映射会导致无法建立统一的 SB，而伪哈希通过变换使每对 $(\hat{x}, y)$ 唯一化，从而满足 Dirac 边界条件，恢复可逆性和最优性。

## 3. 实验设计
- **数据集**：
  - 训练：FFHQ（70k 张 1024×1024 人脸，实验重置为 512×512），通过随机退化生成 LQ-HQ 配对。
  - 测试：合成数据集 CelebA-Test（3k 张）及真实世界数据集 Real-World LFW、CelebChild、WebPhoto-Test、Wider。
- **退化模型**：采用经典盲退化公式 $y = [(x \otimes k_\sigma) \downarrow_r + n_\delta]_{JPEG_q}$，参数范围与主流 BFR 方法一致。
- **对比方法**：包含 14 个 SOTA 方法，涵盖 GAN 类（GPEN、GFPGAN）、字典类（VQFR、CodeFormer、RestoreFormer）、扩散类（DifFace、DiffBIR、DR2、PGDiff）、流模型（PMRF、FlowIE）以及原始 I2SB。
- **评价指标**：像素级 SSIM/PSNR，无参考 NIQE，感知度量 FID、LPIPS。

## 4. 资源与算力
- **硬件**：8 块 32GB Tesla V100 GPU。
- **训练设置**：使用 UNet 作为预测网络，Adam 优化器，学习率 $1\times10^{-4}$，批量大小 64，训练 40,000 次迭代。
- **推理速度**：论文指出与先前方法相比保持了相当的推理速度，但未给出具体耗时数值。

## 5. 实验数量与充分性
- **主实验**：在 CelebA-Test 上全指标定量对比（表 1），在 4 个真实世界数据集上用 NIQE/FID 评估（表 2），提供大量定性可视化结果。
- **消融实验**：
  - 条件引导的作用：对比 Vanilla-I2SB、仅 LQ 条件、LQ+退化信息条件（表 3 a-c）。
  - 三种伪哈希策略对比（表 3 d-f）：Cat、Res、Noise 在 NIQE、FID、LPIPS 上均有显著提升。
- **额外分析**：MNIST 玩具实验验证伪哈希策略的有效性；数值实验展示反向过程中损失变化，证明伪哈希改善边界振荡。
- **评估客观性**：与大量最新方法对比，指标全面，训练/测试退化参数一致，消融设计清晰，实验较为充分、公平。

## 6. 主要结论与发现
- 传统基于桥的模型在盲复原中失效的根源在于多对一映射违背了桥的可逆最优条件。
- 提出的伪哈希策略简单有效，不增加复杂模块，仅通过预处理训练对即可使 SB 学习到最优传输路径。
- P-I2SB 在合成和真实场景下均取得 SOTA 性能，尤其在感知指标 FID、LPIPS 上优势明显，同时保持推理速度。

## 7. 优点
- **理论驱动**：从最优传输和 SB 解的唯一性出发，揭示了盲逆问题的固有冲突，并提出精确修正方法。
- **实现简洁**：无需额外的特征提取网络或复杂融合模块，仅通过通道拼接/残差/加噪等简易操作即大幅提升性能。
- **性能显著**：在多个基准上超越以复杂引导设计著称的扩散方法，纹理更自然，色彩保真度更高。
- **可解释性强**：伪哈希策略具备明确的空间几何或分布含义，推理过程可逆，便于理解。

## 8. 不足与局限
- **退化覆盖受限**：训练所用合成退化无法完全模拟真实世界的水印、极端姿态等复杂退化，导致部分真实样本残留伪影。
- **数据偏差**：训练数据以正面人脸为主，对极端侧脸或大角度姿态的修复鲁棒性不足。
- **框架通用性**：目前仅针对人脸修复验证，尚未拓展到其他盲恢复任务（如超分、去模糊）。
- **缺少用户研究**：评估完全依赖自动指标，缺乏人眼主观评价，真实感知质量的可信度仍有提升空间。

（完）
