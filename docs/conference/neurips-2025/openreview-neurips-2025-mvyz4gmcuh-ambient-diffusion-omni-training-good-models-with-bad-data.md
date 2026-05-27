---
title: "Ambient Diffusion Omni: Training Good Models with Bad Data"
title_zh: 环境扩散全能：用坏数据训练好模型
authors: "Giannis Daras, Adrian Rodriguez-Munoz, Adam Klivans, Antonio Torralba, Constantinos Costis Daskalakis"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MVYz4GmcUH"
tags: ["query:real-ir"]
score: 9.0
evidence: 用低质量图像训练扩散模型
tldr: 针对扩散模型依赖高质量训练数据的局限，提出Ambient Diffusion Omni框架，利用自然图像的频谱幂律衰减和局部性，能够从任意低质量图像中提取信号进行训练。在合成模糊、JPEG压缩等退化图像上验证有效，降低了数据筛选成本。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1154, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 728, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 441, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 125, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 666, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 726, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 663, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1437, \"height\": 1491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1449, \"height\": 1436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1450, \"height\": 1435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1422, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1238, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1415, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1237, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1415, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 652, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 428, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 429, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 653, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 428, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1391, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 640, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 639, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 633, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 634, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 662, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 663, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1453, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 664, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 664, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 663, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 661, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 663, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 663, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvyz4gmcuh/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1291, \"height\": 770, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 706, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 703, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 647, \"height\": 123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 766, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1139, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 577, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 781, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 439, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 714, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 998, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 674, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvyz4gmcuh/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1452, \"height\": 527, \"label\": \"Table\"}]"
motivation: 扩散模型通常需要精心筛选的高质量数据，低质量图像往往被丢弃，但其中蕴含大量可用信号。
method: 利用自然图像的频谱幂律衰减和局部性两个特性，设计了一种无需数据筛选的扩散模型训练框架，可直接从任意低质量图像中学习。
result: 在合成高斯模糊、JPEG压缩、运动模糊等退化图像上成功训练了扩散模型。
conclusion: 证明了低质量图像在扩散模型训练中的价值，降低了数据准备成本。
---

## Abstract
We show how to use low-quality, synthetic, and out-of-distribution images to improve the quality of a diffusion model. Typically, diffusion models are trained on curated datasets that emerge from highly filtered data pools from the Web and other sources. We show that there is immense value in the lower-quality images that are often discarded. We present Ambient Diffusion Omni, a simple, principled framework to train diffusion models that can extract signal from arbitrarily images during training. Our framework exploits two properties of natural images -- spectral power law decay and locality. We first validate our framework by successfully training diffusion models with images synthetically corrupted by Gaussian blur, JPEG compression, and motion blur. We use our framework to achieve state-of-the-art ImageNet FID and we show significant improvements in both image quality and diversity for text-to-image generative modeling. The core insight is that noise dampens the initial skew between the desired high-quality distribution and the mixed distribution we actually observe. We provide rigorous theoretical justification for our approach by analyzing the trade-off between learning from biased data versus limited unbiased data across diffusion times.

---

## 论文详细总结（自动生成）

### 论文中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：扩散模型的训练通常依赖大规模、高质量、经过严格筛选的数据集，而低质量、合成或分布外的图像往往被直接丢弃。这导致了高昂的筛选成本和数据浪费。论文旨在回答：能否利用这些“坏数据”训练出高质量的扩散模型？
- **动机**：现实场景中数据质量参差不齐，且退化类型复杂（如模糊、JPEG压缩、传感器噪声），缺乏统一的解析描述。现有方法（如Ambient Diffusion）需要已知退化模型，通用性不足。作者希望提出一个无需预先知晓退化类型、能直接从“坏数据”中提取信号的训练框架。
- **整体含义**：通过利用自然图像的两个固有属性（频谱幂律衰减与局部性），论文证明了低质量、分布外图像在扩散模型训练中具有显著价值，能够在不牺牲多样性的前提下提升生成质量，从而降低对大规模数据筛选的依赖。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：
  - **噪声压缩分布距离**：在高扩散时间（高噪声水平），目标分布与退化分布的加噪版本会趋近（Theorem 4.2），从而允许使用低质量数据学习高分噪部分的去噪器。
  - **局部性**：低扩散时间（低噪声）下最优去噪仅需局部感受野，若分布外图像与目标图像在局部作物上的边际分布一致，则可替代使用。
- **关键技术细节**：
  - **时序分类器（noise classifier）**：训练噪声条件分类器 \(c^{\text{noise}}_\theta(x_t, t)\) 区分干净与退化图像的加噪版本，确定每个样本的安全噪声下限 \(t_{\min}^n\)（当分类器置信度低于阈值 \(\tau\)）。
  - **作物分类器（crops classifier）**：训练作物条件分类器 \(c^{\text{crops}}_\theta(A(t)(y))\) 判断图像作物属于目标分布还是分布外，确定作物大小对应的最大扩散时间 \(t_{\max}^n\)（同样基于阈值 \(\tau\)）。
  - **注释与训练**：基于分类器为每个样本分配个体化的扩散时间区间（对于低质量图像只用于 \(t \geq t_{\min}^i\)，对于分布外图像只用于 \(t \leq t_{\max}^i\)），形成所谓的“甜甜圈悖论”（中部时间样本减少）。再使用扩展的Ambient损失函数（公式2.2的变体）训练扩散模型。
- **公式/算法流程**：
  - 损失函数：  
    \[
    J_{\text{ambient-o}}(\theta) = \mathbb{E}_{t\sim U[0,T]} \sum_{i: t_{\min}^i < t} \mathbb{E}_{x_t|x_{t_{\min}^i}^{(i)}} \left\| \alpha(t, t_{\min}^i) h_\theta(x_t, t) + (1-\alpha(t, t_{\min}^i)) x_t - x_{t_{\min}^i}^{(i)} \right\|^2
    \]  
    其中 \(\alpha(t, t_{\min}^i) = \frac{\sigma^2(t) - \sigma^2(t_{\min}^i)}{\sigma^2(t)}\)。
  - 理论偏置-方差权衡：定理4.2表明加噪后TV距离以 \(D/(2\sigma)\) 衰减；对比有限干净样本与大量混合样本的误差上界，证明高噪声下使用低质量数据更优。

#### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **数据集**：
  - 合成退化：CIFAR-10、FFHQ（高斯模糊、JPEG压缩、运动模糊）。
  - 分布外/作物：AFHQ（猫/狗/野生动物）、程序生成图像（Shaders）。
  - 真实退化：ImageNet（用CLIP-IQA划分高质量top 10%与低质量90%）、文本到图像（CC12M、SA1B、JourneyDB、DiffusionDB）。
- **Benchmark**：FID、CLIP-FD、CLIP得分、GenEval、DrawBench、PartiPrompts、GPT-4o评估。
- **对比方法**：
  - 仅用干净子集（过滤策略）。
  - 所有数据等权（“no annotations”）。
  - 固定单一噪声注释（sample-independent）。
  - EDM-2（ImageNet baseline）、MicroDiffusion（text-to-image baseline）、以及论文提出的Ambient-o及其作物扩展版。

#### 4. 资源与算力
- **明确说明**：
  - CIFAR-10：单节点8×V100，约4.4小时/训练。
  - ImageNet XS模型（125M参数）：32×H200，约3天。
  - ImageNet XXL模型（1523M参数）：32×H200，约7天。
  - MicroDiffusion（1.1B参数）：8×H200，约2天。
  - 分类器训练时间显著短于扩散模型训练（未给出具体数值）。

#### 5. 实验数量与充分性
- **实验数量**：覆盖合成退化（3种+不同强度）、分布外（猫狗互换、程序生成）、真实退化（ImageNet、文本到图像）。消融实验包括：分类器阈值、预处理权重、缓冲策略、分类器训练样本平衡性、训练迭代次数、注释方式（样本依赖 vs 固定）、干净数据比例（1%-50%）、作物大小对FID的影响等。
- **充分性评价**：实验全面，消融细致，且在不同规模模型（从50M到1.5B参数）上验证。但作者也指出部分实验结果（如分类器阈值）可能有调参空间，且样本依赖注释可能引入类别偏差，需要进一步研究。

#### 6. 论文的主要结论与发现
- **主要结论**：通过Ambient-o框架，低质量、合成、分布外图像可以显著提升扩散模型的生成质量和多样性，且不需要预先知道退化类型。
- **具体发现**：
  - 合成退化实验中，仅用10%干净数据时，Ambient-o将FID从45.32（全数据等权）降低至6.16（高斯模糊σB=1.0），远优于仅用干净数据（8.79）。
  - ImageNet上，Ambient-o XXL+crops达到测试FID 2.53，优于EDM-2 XXL的2.73，同时提升CLIP-IQA质量。
  - 文本到图像：COCO FID从12.37降至10.61，且相比微调策略（只在高质量子集上fine-tune）显著提升多样性（DINO Vendi得分+13%）。
  - 理论证明高噪声下使用有偏数据可降低估计方差，偏置项随噪声衰减。

#### 7. 优点
- **方法优雅原则性强**：基于自然图像频谱和局部性的普适性质，无需假设退化模型，扩展了Ambient Diffusion的适用场景。
- **理论支撑充分**：提供了偏置-方差权衡的正式上界，并给出了噪声收缩距离的定理（Theorem 4.2）。
- **实用性强**：在图像生成和文本到图像生成两大任务上均取得SOTA或显著改进，且代码开源。
- **保留数据多样性**：相比过滤策略，Ambient-o利用所有数据，避免了模式坍塌（图6验证）。
- **实验设计全面**：覆盖合成退化、分布外、真实退化，消融系统。

#### 8. 不足与局限
- **理论限制**：高噪声下分布仅近似收敛，始终存在偏置（除非噪声无限大）。
- **对退化类型敏感**：对高频退化（如模糊）效果佳，但对低频退化（如掩膜、颜色偏移）需要极高噪声，几乎退化为过滤。
- **样本依赖注释可能引入类别偏差**：当退化分布中类别不均衡时，可能会偏向某些类别生成（作者已提醒）。
- **计算开销**：需要额外训练两个分类器（噪声和作物），增加训练流程复杂度。
- **质量标准依赖**：对真实数据集（如ImageNet）的高/低质量划分依赖CLIP-IQA这一启发式指标，可能不鲁棒。
- **“甜甜圈悖论”**：扩散轨迹中部时间数据利用率低，目前未提出优化方案。

（完）
