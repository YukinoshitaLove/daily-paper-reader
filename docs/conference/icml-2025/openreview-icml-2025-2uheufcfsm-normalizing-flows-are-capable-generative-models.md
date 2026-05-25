---
title: Normalizing Flows are Capable Generative Models
title_zh: 归一化流是强大的生成模型
authors: "Shuangfei Zhai, Ruixiang ZHANG, Preetum Nakkiran, David Berthelot, Jiatao Gu, Huangjie Zheng, Tianrong Chen, Miguel Ángel Bautista, Navdeep Jaitly, Joshua M. Susskind"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2uheUFcFsM"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出TarFlow，一种用于图像的强大归一化流生成模型
tldr: 针对归一化流近年受关注较少的问题，提出TarFlow：基于Transformer的掩码自回归流架构，通过交替自回归方向与多项训练技术，直接在像素上建模与生成。实验表明NFs在图像生成上具有竞争力，重新确立了归一化流作为先进生成模型的地位。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 898, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1746, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 687, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1790, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 893, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 892, \"height\": 936, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 892, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 894, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 892, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 893, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 893, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 891, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 893, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 892, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 892, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 889, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 890, \"height\": 927, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 738, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1629, \"height\": 242, \"label\": \"Table\"}]"
motivation: 归一化流在图像生成上长期未获足够关注与突破。
method: 提出TarFlow，结合Transformer自回归块与交替方向及三项关键技术。
result: 在图像生成任务上取得可比拟扩散模型的性能。
conclusion: TarFlow证明了归一化流依然具有强大生成潜力。
---

## Abstract
Normalizing Flows (NFs) are likelihood-based models for continuous inputs. They have demonstrated promising results on both density estimation and generative modeling tasks, but have received relatively little attention in recent years. In this work, we demonstrate that NFs are more powerful than previously believed. We present TarFlow: a simple and scalable architecture that enables highly performant NF models. TarFlow can be thought of as a Transformer-based variant of Masked Autoregressive Flows (MAFs): it consists of a stack of autoregressive Transformer blocks on image patches, alternating the autoregression direction between layers. TarFlow is straightforward to train end-to-end, and capable of directly modeling and generating pixels. We also propose three key techniques to improve sample quality: Gaussian noise augmentation during training, a post training denoising procedure, and an effective guidance method for both class-conditional and unconditional settings. Putting these together, TarFlow sets new state-of-the-art results on likelihood estimation for images, beating the previous best methods by a large margin, and generates samples with quality and diversity comparable to diffusion models, for the first time with a stand-alone NF model. We make our code available at https://github.com/apple/ml-tarflow.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 归一化流（Normalizing Flows, NFs）是经典的基于似然的生成模型，能够精确计算密度并天然支持可逆变换。
- 近年来，扩散模型、自回归模型等大幅挤压了NFs的研究与应用空间，NFs在生成质量、似然估计等方面已明显落后，学术界产生“NFs是否本质上能力受限”的疑问。
- 本文试图打破这种成见，证明**归一化流本身仍是强大的生成建模范式**，问题只是过去缺少合适的架构与训练技巧。  
- 整体含义：通过设计可扩展的架构并引入少量关键技术，NFs可以在图像似然估计和生成质量上达到甚至超越当前最佳方法，重新激活该方向的研究价值。

### 2. 论文提出的方法论：核心思想、关键技术细节
#### 2.1 整体模型结构：TarFlow
- 思想：将Masked Autoregressive Flows（MAF）推广到“块”级别，使用**Transformer**实现自回归变换，交替方向堆叠多层。
- 图像处理：输入图像划分为patches，得到序列 $x \in \mathbb{R}^{N \times D}$（$N$为patch数，$D$为每块维度）。
- 每个flow block：
  1. 固定排列操作（交替反向），体积保持。
  2. 因果（causal）Transformer：序列方向上只允许前向依赖，输出两个头 $\mu_t^i$ 和 $\alpha_t^i$。
  3. 仿射变换更新：$z^{t+1}_i = (\tilde z^t_i - \mu_t^i(\tilde z^t_{<i})) \odot \exp(-\alpha_t^i(\tilde z^t_{<i}))$（$i>0$），第一块保持恒等。
- 总变换 $f = f^{T-1} \circ \dots \circ f^0$，堆叠 $T$ 个block，交替排列方向实现“深度可逆残差”。
- 对数行列式简单求和 $-\sum_{t,i,j} \alpha_t^i(\tilde z^t_{<i})_j$，训练损失为 $0.5\|z^T\|_2^2 + \sum_{t,i,j} \alpha_t^i(\tilde z^t_{<i})_j$（先验为标准高斯）。

#### 2.2 三项关键训练与推理技术
1. **高斯噪声增强训练**  
   - 训练时对输入加高斯噪声 $\mathcal{N}(0,\sigma^2 I)$，$\sigma\approx0.05$（远大于传统dequantization均匀噪声的0.002）。  
   - 目的：扩大训练分布支持集，改善逆映射 $f^{-1}$ 的泛化；高斯噪声使密度在数据点处模态集中，有利采样。
2. **基于分数的后处理去噪**  
   - 利用Tweedie公式 $E[x|y] = y + \sigma^2 \nabla_y \log q(y)$，用模型自身密度 $p_{\text{model}}$ 替代 $q$，从噪声样本 $y$ 恢复干净 $\hat x$。  
   - 无需额外网络，仅依赖自身模型的score。
3. **引导（Guidance）**  
   - **条件引导**（类似Classifier-Free Guidance）：将条件和无条件预测组合，  
     $\tilde\mu = (1+w)\mu(c) - w\mu(\emptyset)$，$\tilde\alpha = (1+w)\alpha(c) - w\alpha(\emptyset)$。  
   - **无条件模型引导**：通过改变注意力温度 $\tau$ 制造弱预测，再用同样公式将标准预测外推远离弱预测。  
   - 还可对位置或层调整引导权重，简单线性增长能改善FID。

### 3. 实验设计
- **数据集与场景**：
  - 无条件和条件 ImageNet 64×64（似然估计及生成）
  - 条件 ImageNet 128×128
  - AFHQ 256×256（无条件/条件皆可）
- **评价指标**：
  - 似然：bits per dimension (BPD)
  - 生成质量：Fréchet Inception Distance (FID)
- **对比方法**：
  - 似然：Very Deep VAE, Glow, Flow++, PixelCNN, SPN, Sparse Transformer, Routing Transformer, Improved DDPM, VDM, Flow Matching, NFDM 等。
  - 生成：EDM, ADM, BigGAN, IC-GAN, consistency models, simple diffusion, CDM, RIN 等。

### 4. 资源与算力
- 实验全部在 **A100 GPU** 上进行。
- 最大规模训练：条件 ImageNet 64×64 和 128×128 使用 **32 块 A100**，分别训练 320 epochs（batch size 768）。
- 无条件 64×64 生成任务用 **8 块 A100** 训练 200 epochs。
- 似然估计任务用 **32 块 A100** 训练 60 epochs。
- AFHQ 256×256 用 **8 块 A100** 训练 4000 epochs（数据集较小）。
- 每项实验均在 **14 天内**完成，但未报告总 GPU/时。默认使用 bfloat16 混合精度，仅似然任务保留 float32。
- 推理采样时间：32 张引导样本约 2 分钟（A100 单卡），去噪步骤需缓存激活，内存消耗较大。

### 5. 实验数量与充分性
- 主要实验覆盖 4 个数据集/任务组合，提供似然和生成两大类指标。
- 对比了大量来自不同范式的强基线（自回归、扩散、GAN、VAE 等），较为全面。
- 消融实验：
  - 噪声水平 $\sigma$ 对 FID 的影响（含去噪前后对比）
  - 引导权重 $w$ 对条件、无条件模型的影响
  - 条件与温度在无条件引导中的组合
  - 模型深度配置 $T \times K$ 对损失和 FID 的影响
  - 体积保持（VP）与通道耦合变体的性能对比
- 实验设计清晰，多维度验证了方法的有效性，具有较好的充分性和客观性。

### 6. 论文的主要结论与发现
- **TarFlow 在图像似然估计上达到新 SOTA**，首次将 ImageNet 64×64 BPD 降至 2.99。
- **生成样本质量可与扩散模型相比**，首次证明纯归一化流模型能生成高质量、多样性的自然图像。
- **三项技术创新高度协同**：高斯噪声增强 → 提升逆映射泛化；基于分数的去噪 → 去除噪声痕迹；引导 → 大幅改善样本真实度与模式覆盖。
- 归一化流并非有根本性弱点，**只要架构可扩展、训练得当，完全可以成为顶级生成模型**。

### 7. 优点：方法或实验设计上的亮点
- **架构极简**：纯粹由堆叠的因果 Transformer 构成，无复杂耦合层、无 1×1 卷积，易于实现和扩展。
- **训练稳定**：残差结构与 Transformer 训练范式融合，损失曲线平滑，与生成质量正相关。
- **最大似然直接训练**：无需像扩散模型那样依赖多步噪声扰动和繁琐调度，仅最大化似然就得到强大生成器。
- **技巧优雅且即插即用**：噪声增强、去噪、引导均围绕模型自身能力，未引入辅助网络。
- **实验坚实**：覆盖似然与生成，对比全面，消融充分，有力支持主张。

### 8. 不足与局限
- **推理速度慢**：采样过程是逐块自回归的反向传播，尽管有 KV-cache 加速，但本质上仍是顺序执行，生成高分辨率图像耗时较长；去噪步骤需反向传播，内存开销大。
- **未与其他范式在更大规模任务上对比**：如文本到图像生成、超大规模数据集上，TAR FLOW 的竞争力尚待检验。
- **引导调度设计粗浅**：仅尝试了线性递增的权重，更优的引导策略未深入探索。
- **去噪依赖自身模型质量**：若密度估计欠佳，去噪效果会受影响，产生偏差。
- **算力需求较高**：达到 SOTA 需要多卡并行训练，虽然比部分大模型可能小，但仍需要可观资源。

（完）
