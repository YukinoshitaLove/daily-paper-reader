---
title: Stochastic Deep Restoration Priors for Imaging Inverse Problems
title_zh: 随机深度恢复先验用于成像逆问题
authors: "Yuyang Hu, Albert Peng, Weijie Gan, Peyman Milanfar, Mauricio Delbracio, Ulugbek S. Kamilov"
date: 2024-09-17
pdf: "https://openreview.net/pdf?id=O2aioX2Z2v"
tags: ["query:real-ir"]
score: 6.0
evidence: 用于成像逆问题的深度恢复先验
tldr: 针对高斯去噪先验在逆问题中的不足，提出随机深度恢复先验（ShaRP），通过集成多个预训练恢复模型构建更强大的先验，并证明其对应于最小均方误差恢复的分数函数，从而在缺乏全采样数据时也能自监督训练，有效抑制结构化伪影，为成像逆问题提供了新的正则化框架。
source: ICLR-2025-Rejected-Public
selection_source: conference_retrieval
motivation: 高斯去噪先验不足以应对结构化伪影，需要更通用的恢复先验。
method: 提出ShaRP，集成多种恢复模型构建随机先验，并推导其与分数函数的联系。
result: 在处理结构化伪影和自监督学习方面优于高斯去噪先验方法。
conclusion: 通用深度恢复先验比单一高斯先验更能有效正则化逆问题。
---

## Abstract
Deep neural networks trained as image denoisers are widely used as priors for solving imaging inverse problems. While Gaussian denoising is thought sufficient for learning image priors, we show that priors from deep models pre-trained as more general restoration operators can perform better. We introduce Stochastic deep Restoration Priors (ShaRP), a novel method that leverages an ensemble of such restoration models to regularize inverse problems. ShaRP improves upon methods using Gaussian denoiser priors by better handling structured artifacts and enabling self-supervised training even without fully sampled data. We prove ShaRP minimizes an objective function involving a regularizer derived from the score functions of minimum mean square error (MMSE) restoration operators, and theoretically analyze its convergence. Empirically, ShaRP achieves state-of-the-art performance on tasks such as magnetic resonance imaging reconstruction and single-image super-resolution,  surpassing both denoiser- and diffusion-model-based methods without requiring retraining.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 成像逆问题（如磁共振成像重建、超分辨率等）通常通过正则化方法求解，其中深度去噪器常被用作图像先验。
- 现有的主流方法将“高斯去噪”视为学习通用图像先验的充分途径，但论文指出这种假设存在局限：高斯去噪先验难以有效处理具有复杂结构的伪影，并且在缺少全采样训练数据的场景下难以自监督训练。
- 论文提出一个核心观点：采用更通用的、预训练的深度恢复模型（不仅仅限于高斯去噪）作为先验，能够更强大地正则化逆问题，从而更好地抑制结构化伪影并实现无全采样数据的自监督学习。

### 2. 论文提出的方法论
- **核心思想**：提出**随机深度恢复先验 (Stochastic deep Restoration Priors, ShaRP)**。该方法将多个预训练的通用恢复模型（例如面向不同退化类型的恢复器）集成为一个随机先验，利用这个先验对逆问题的解空间进行正则化。
- **关键技术细节**：
  - 方法不依赖单一的高斯去噪模型，而是使用一个由**多种恢复模型构成的集合（ensemble）**。每个恢复模型可针对不同种类的退化（如去模糊、去噪、超分等）进行训练。
  - 论文从理论上证明，ShaRP 等价于优化一个目标函数，其正则项来源于**最小均方误差（MMSE）恢复算子的得分函数（score functions）**。这为使用通用恢复先验提供了理论依据。
  - 方法支持**自监督训练**：即使没有全采样的干净数据，也能利用欠采样或降质数据本身训练恢复模型，从而构建有效的先验。
- **公式/算法流程（文字描述）**：
  - 集成多个恢复算子，每个恢复算子对应一个特定的退化过程。
  - 在求解逆问题时，交替进行数据一致性更新和随机选择的恢复算子应用（或梯度更新），利用这些算子的得分函数引导解朝向更真实的图像分布。
  - 目标的优化包含一个类似于分数匹配的损失项，使得恢复算子能够近似真实数据分布的梯度。

### 3. 实验设计
- **数据集/场景**：
  - 磁共振成像（MRI）重建（可能使用如 fastMRI 等公开数据集）。
  - 单图像超分辨率（Single-image super-resolution, SISR）（可能涉及标准测试集如 Set5、Set14、BSD100 等）。
- **Benchmark 和对比方法**：
  - 与基于高斯去噪器的先验方法（例如利用 Denoising Score Matching 或 Plug-and-Play 框架的方法）进行对比。
  - 与基于扩散模型的方法（diffusion-model-based methods）进行对比。
  - 声称性能达到目前最优（state-of-the-art），且无需重新训练模型。

### 4. 资源与算力
- 提供的节选文本中**未具体说明**所使用的 GPU 型号、数量或训练时长。原文或完整论文可能包含这些细节，但基于现有摘要无法获得。

### 5. 实验数量与充分性
- 基于摘要可推测实验包含**至少两个主要任务**（MRI 重建和超分辨率），每个任务均有与多个方法的定量和定性对比。
- 实验还涉及**自监督训练的验证**，证明方法在无全采样数据下的有效性。
- 从“理论上分析其收敛性”可知，论文可能包含收敛性相关的实验或仿真。
- **充分性评估**：实验覆盖了代表性逆问题，且比较了当前主流的方法（去噪器先验和扩散模型），设计较为公平客观。但摘要未给出消融实验细节（如关于集成规模、不同恢复模型组合的影响），可能在全文中包含。

### 6. 论文的主要结论与发现
- 通用深度恢复模型作为先验（ShaRP）相比单一高斯去噪先验，在成像逆问题中能够**更有效地处理结构化伪影**，并取得更高的重建质量。
- ShaRP 可以在**无全采样数据的情况下进行自监督训练**，突破了高斯去噪先验对完整训练数据的要求。
- 在 MRI 重建和超分辨率任务上，ShaRP **超越了当前基于去噪器和扩散模型的方法**，且无需针对特定问题重新训练。

### 7. 优点
- **方法创新性强**：提出用集成通用恢复模型替代单一高斯去噪器，拓宽了先验学习的范式。
- **理论支撑扎实**：建立了 ShaRP 与 MMSE 恢复算子的得分函数之间的联系，并给出收敛性分析。
- **实用性好**：支持自监督训练，适用于难以获取全采样数据的应用场景；并且预训练模型可直接使用，无需重新训练。
- **性能突出**：在多个任务上取得最优结果，抑制伪影能力显著提升。

### 8. 不足与局限
- **实验覆盖可能有限**：摘要仅提及 MRI 重建和超分辨率，未涉及其他经典逆问题（如去模糊、CT 重建），泛化性有待更多验证。
- **计算开销未讨论**：集成多个恢复模型会带来更高的计算和存储成本，摘要未对比效率。
- **理论假设的局限性**：目标函数基于 MMSE 得分函数，对复杂或未知退化可能偏差较大，实际应用中可能需要仔细选择恢复模型库。
- **对比方法细节缺失**：未列出对比扩散模型的具体版本或结构，可能影响公平性判断。

（完）
