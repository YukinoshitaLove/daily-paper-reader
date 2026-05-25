---
title: "EQ-VAE: Equivariance Regularized Latent Space for Improved Generative Image Modeling"
title_zh: EQ-VAE：通过等变性正则化改善生成式图像建模的潜空间
authors: "Theodoros Kouzelis, Ioannis Kakogeorgiou, Spyros Gidaris, Nikos Komodakis"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UWhW5YYLo6"
tags: ["query:real-ir"]
score: 9.0
evidence: 通过在自编码器潜空间施加等变性正则化改善生成图像建模
tldr: 该论文发现现有自编码器对缩放、旋转等变换缺乏等变性，导致潜空间复杂，影响生成模型性能。提出EQ-VAE，一种简单的正则化方法，通过微调强制潜空间等变性，在保持重建质量的同时提升多种主流生成模型的效果。该方法简单有效，为改善生成模型潜空间提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 811, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1577, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 637, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1006, \"height\": 1166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1414, \"height\": 1638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uwhw5yylo6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1174, \"height\": 2105, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 782, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 699, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 627, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 796, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 811, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 925, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 604, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1307, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1163, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1215, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 860, \"height\": 690, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uwhw5yylo6/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1412, \"height\": 321, \"label\": \"Table\"}]"
motivation: 自编码器缺乏等变性使潜空间复杂，阻碍生成性能。
method: 提出EQ-VAE，对预训练自编码器微调以施加等变性约束。
result: 在多种生成模型上提升了性能，不降低重建质量。
conclusion: 简单正则化即可有效简化潜空间，增强生成模型。
---

## Abstract
Latent generative models have emerged as a leading approach for high-quality image synthesis. These models rely on an autoencoder to compress images into a latent space, followed by a generative model to learn the latent distribution. We identify that existing autoencoders lack equivariance to semantic-preserving transformations like scaling and rotation, resulting in complex latent spaces that hinder generative performance. To address this, we propose EQ-VAE, a simple regularization approach that enforces equivariance in the latent space, reducing its complexity without degrading reconstruction quality. By finetuning pre-trained autoencoders with EQ-VAE, we enhance the performance of several state-of-the-art generative models, including DiT, SiT, REPA and MaskGIT, achieving a ×7 speedup on DiT-XL/2 with only five epochs of SD-VAE fine-tuning. EQ-VAE is compatible with both continuous and discrete autoencoders, thus offering a versatile enhancement for a wide range of latent generative models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：现有主流自编码器（如 SD‑VAE、VQ‑GAN）对缩放、旋转等语义保持的空间变换缺乏**等变性（equivariance）**，导致潜空间结构过于复杂、非线性程度高，从而显著拖慢生成模型（如扩散模型、掩码生成模型）的训练收敛并限制最终合成质量。
- **整体含义**：通过对自编码器施加轻量的等变性正则化，可以在不牺牲重建保真度的前提下，有效简化潜流形的几何结构，为下游生成模型提供“更易学习”的潜在分布，最终同时提升训练效率和生成效果。

### 2. 论文提出的方法论
- **核心思想**：让自编码器学习一个“变换相容”的潜空间，即对图像施加空间变换后编码，应当等价于先在图像空间变换再编码。显式约束该性质容易陷入平凡解，因此采用**隐式正则化**。
- **关键技术细节**：
  - **隐式对齐损失**：对输入 `x` 和随机采样变换 `τ`，要求解码器从变换后的潜在码 `τ◦E(x)` 重建出的图像与直接变换输入 `τ◦x` 保持一致。训练目标沿用 VAE 的标准重建、感知、对抗和 KL 项，仅将输入和重建目标同时进行对应变换。
  - **变换设计**：采用各向同性/各向异性缩放（缩放因子 0.25–1）与旋转变换（90° 整倍数）的组合，通过双三次插值实现下采样。
  - **训练方式**：以概率 `pα` 使用标准目标（恒等变换，保持原始重建能力），其余情况使用等变目标。对预训练自编码器仅需微调数个 epoch，无需重新训练架构。
  - **离散扩展**：对于 VQ‑GAN 等离散自编码器，在量化前对连续特征施加变换，流程与连续情形一致。
- **目标公式（文字概括）**：
  - 常规损失：`L_VAE(x) = L_rec(x, D(E(x))) + λ_gan L_gan + λ_reg L_reg`
  - 等变损失：`L_EQ-VAE(x,τ) = L_rec(τ◦x, D(τ◦E(x))) + λ_gan L_gan(D(τ◦E(x))) + λ_reg L_reg`
  - 混合训练：按概率 `pα` 切换上述两者。

### 3. 实验设计
- **数据集与场景**：
  - 自编码器微调：OpenImages（跟随 LDM 框架）。
  - 生成模型训练与评测：ImageNet 256×256（ADM 基准的评估协议）。
- **基准对比方法**：
  - **自编码器**：SD‑VAE、SD‑VAE‑FT‑EMA、SD‑VAE‑16、SDXL‑VAE、SD3‑VAE（连续）；VQ‑GAN（离散）。
  - **生成模型**：DiT‑B/XL、SiT‑B/XL、REPA（基于 SiT‑XL）、MaskGIT。
  - **消融基线**：额外训练但无等变性约束的 SD‑VAE（SD‑VAE†）、显式等变约束、仅旋转/仅缩放/各向异性缩放的组合。
- **评估指标**：生成指标（GFID、sFID、IS、Precision、Recall）、重建指标（RFID、PSNR、SSIM、LPIPS）、等变性误差、潜空间内在维度。

### 4. 资源与算力
- 文中**明确提到**用于评测的 **NVIDIA A100 GPU**。
- 生成模型的训练配置：DiT/SiT/REPA 在 ImageNet 上 batch size 256；MaskGIT batch size 256，训练最多 300 轮；自编码器微调仅 5 个 epoch，batch size 10。
- **未明确说明**的内容：微调自编码器及训练生成模型所消耗的 GPU 数量、总 GPU 小时或训练时长等具体算力量级。

### 5. 实验数量与充分性
- **实验覆盖**：
  - 5 种不同架构/尺寸的自编码器（包括连续与离散）均验证了等变正则化效果。
  - 4 种主流生成框架（DiT、SiT、REPA、MaskGIT）均获得性能提升。
  - 丰富的消融实验：变换类型（缩放/旋转/组合）、正则化强度 `pα`、微调轮数（1–5 轮）、隐式 vs. 显式正则化、额外训练对比、内在维度分析。
  - 与最先进的扩散模型在带引导的设置下对比（CFG 下 DiT‑XL/2、REPA 等）。
- **充分性与公平性**：
  - 实验设计全面，基本控制“额外训练时间”这一混淆因素（SD‑VAE† 额外训练无增益），比较公平。
  - 各模型遵从原论文的默认超参数与评估协议，结果可靠。

### 6. 论文的主要结论与发现
- **等变性缺乏被证实**：传统自编码器在潜空间直接施加变换后重建质量急剧下降，存在明显的等变性鸿沟。
- **EQ‑VAE 有效降低潜空间复杂度**：等变正则化使潜空间内在维度降低，且在前三维主成分可视化中表现出更平滑的结构。
- **生成模型显著受益**：
  - DiT‑XL/2 在 400K 迭代时 GFID 从 19.5 降至 14.5；1.5M 迭代时达到 8.8，超越未正则化模型 7M 迭代的结果。
  - REPA 达到同等性能的训练速度提升约 **4 倍**，SiT、MaskGIT 等均有类似加速。
  - 重建质量基本持平或轻微波动，未出现恶性退化。

### 7. 优点
- **方法简洁、即插即用**：仅微调自编码器几轮，无需改变架构，兼容现有预训练模型。
- **普适性强**：连续与离散潜空间均适用，提升多种生成范式（扩散、流匹配、掩码生成、自回归）的性能。
- **效率提升显著**：带来 **×7** 乃至更高的训练收敛加速，极大降低大规模生成模型的计算成本。
- **有效规避模式坍塌**：采用隐式正则化避免显式等变约束导致的潜在崩溃。

### 8. 不足与局限
- **变换类型受限**：仅考虑缩放和 90° 旋转，未覆盖更一般的仿射变换或高精度连续旋转，可能限制潜空间对复杂几何变化的建模能力。
- **各向异性缩放的副作用**：各向异性缩放虽进一步降低内在维度并提升生成指标，但轻微损害重建质量，依赖人工权衡。
- **重建‑生成权衡依旧存在**：尽管旨在“无损”提升，但极端正则化强度下重建指标有浮动，且论文未分析对超分辨率或多尺度生成等下游任务的影响。
- **实验偏差风险**：
  - 生成模型全在 ImageNet 256×256 上评测，缺乏文本到图像或多模态生成的验证。
  - 仅与 SD‑VAE 系列和 VQ‑GAN 比较，未对比更新的自编码器（如视频或高压缩率变体）。
  - 潜在空间复杂性度量（ID）在噪声影响下可能高估，需更稳健的几何分析手段。
- **算力与复现细节**：未报告具体 GPU 消耗和训练时长，难以精确评估资源开销。

（完）
