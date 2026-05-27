---
title: "More Than Generation: Unifying Generation and Depth Estimation via Text-to-Image Diffusion Models"
title_zh: 超越生成：通过文本到图像扩散模型统一生成与深度估计
authors: "Hongkai Lin, Dingkang Liang, Mingyang Du, Xin Zhou, Xiang Bai"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ICgOzZc10r"
tags: ["query:real-ir"]
score: 4.0
evidence: 扩散模型统一生成与深度估计
tldr: 生成式深度估计方法需要微调扩散模型，但会破坏生成能力。本文提出MERGE，通过固定预训练文本到图像模型参数，引入即插即用框架实现生成与深度估计的无缝切换。实验表明该方法在保持生成质量的同时实现高精度深度估计。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 解决生成式深度估计中参数更新导致生成能力退化的问题。
method: 基于固定参数预训练模型，设计即插即用框架切换两种模式。
result: 同时保持图像生成能力和深度估计性能。
conclusion: 预训练扩散模型可扩展至多任务而无需灾难遗忘。
---

## Abstract
Generative depth estimation methods leverage the rich visual priors stored in pretrained text-to-image diffusion models, demonstrating astonishing zero-shot capability. However, parameter updates during training lead to catastrophic degradation in the image generation capability of the pretrained model. We introduce MERGE, a unified model for image generation and depth estimation, starting from a fixed-parameters pretrained text-to-image model. MERGE demonstrates that the pretrained text-to-image model can do more than image generation but also expand to depth estimation effortlessly. Specifically, MERGE introduces a plug-and-play framework that enables seamless switching between image generation and depth estimation modes through simple and pluggable converters. Meanwhile, we propose a Group Reuse Mechanism to encourage parameter reuse and improve the utilization of the additional learnable parameter. MERGE unleashes the powerful depth estimation capability of the pretrained text-to-image model while preserving its original image generation ability. Compared to other unified models for image generation and depth estimation, MERGE achieves state-of-the-art performance across multiple depth estimation benchmarks. The code and model will be made available.

---

## 论文详细总结（自动生成）

# 论文总结：More Than Generation: Unifying Generation and Depth Estimation via Text-to-Image Diffusion Models

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：预训练的文本到图像（T2I）扩散模型（如 Stable Diffusion、FLUX）在图像生成上表现优异，同时新兴的生成式深度估计方法（如 Marigold）发现这些模型中蕴含着丰富的视觉先验，可用于零样本深度估计。
- **核心问题**：现有生成式深度估计方法通常需要对整个预训练模型进行全参数微调（如 Marigold），这会不可逆地破坏模型原有的图像生成能力。其他统一生成与感知的方法（如 JointNet、UniCon）采用并行双模型架构，资源开销大；OneDiffusion 则从零训练需要海量多任务数据（100M），成本高昂。
- **研究目标**：能否在不牺牲 T2I 模型生成能力的前提下，高效地赋予其深度估计能力？论文提出 **MERGE**，基于**固定参数**的预训练 T2I 模型，通过极少的可学习参数实现生成与深度估计的统一，且两种模式可无缝切换。

## 2. 方法论

### 核心思想
- 固定整个预训练 T2I 扩散模型（以 DiT 为基础架构），不更新其任何参数。
- 在预训练 T2I 的每个 Transformer 层（称为 T2I block）之前插入可学习的“转换器”（converter），用于将原本面向图像生成的特征转变为适合深度估计的特征。
- 通过跳过或运行这些转换器，模型可立即在图像生成模式与深度估计模式间切换，即“即插即用”。

### 关键技术细节
1. **Play-and-Plug Framework**：
   - 在每个 T2I block 前复制一个相同的、可学习的 T2I block 作为 converter（初始化使用该 group 第一个 T2I block 的预训练权重）。
   - 深度估计推理时，启用 converter；图像生成时，跳过 converter，恢复原始 T2I 模型，故生成能力完全保留。

2. **Group Reuse Mechanism (GRE)**：
   - 观察到预训练 T2I 模型中相邻层的输出特征具有高余弦相似度，因此将连续的 T2I block 划分为若干组，同一组内共享同一个 converter。
   - 默认策略：均匀分组（如 28 层分为 14 组），大大减少参数量（仅约 12%），性能损失很小。

3. **Converter 简化（Empirical Investigation）**：
   - 原有 converter 包含 Self-Attention、Cross-Attention、FFN 等组件。实验发现，由于深度估计任务中文本提示通常为空，Cross-Attention 是冗余的，移除后不影响性能，节省约 25% 参数。
   - 进一步缩小 FFN 的扩展率（从 4 降至 1），可再节省约 36% 参数，且性能几乎不变。
   - 最终简化后的 converter 仅保留 Self-Attention 和缩放后的 FFN，称为 Converter B。

4. **训练方式**：
   - 仅训练 converter（及 patchify 层输入通道扩展部分），T2I 模型其他参数冻结。
   - 使用合成深度数据集（Hypersim 和 Virtual KITTI），总 74K 样本，采用与 Marigold 类似的去噪目标（LDM loss）。
   - 对 PixArt 和 FLUX 两种架构分别实现了 MERGE-B 和 MERGE-L。

## 3. 实验设计

### 数据集与评估基准
- **训练数据**：Hypersim（室内合成，+ Virtual KITTI（室外合成），共 74K 样本。
- **深度估计测试基准**：
  - NYUv2（室内真实场景）、ScanNet（室内真实场景）、DIODE（室内与室外混合）。
  - 评估指标：绝对相对误差（A.Rel ↓）、δ1 准确率（阈值 1.25，↑）。
- **法线估计测试基准**：NYUv2、ScanNet、iBims-1、Sintel，评估平均角度误差和 11.25° 以内像素比例。

### 对比方法
- **传统判别方法**：DPT、HDN、DepthAnything v1/v2。
- **仅深度估计的生成方法**：Marigold、GeoWizard、DepthFM、Lotus。
- **支持图像生成与深度估计的统一方法**：JointNet、UniCon、OneDiffusion。
- **高效微调方法**：LoRA、DoRA（同基座模型，参数量匹配）。
- **全参数微调对比**：自制 PixArt 版 Marigold（Marigold-P）。

### 实验充分性
- **主要结果（表1）**：在 NYUv2、ScanNet、DIODE 上与上述所有方法对比。
- **低秩微调对比（表2）**：与 LoRA、DoRA 在同基座模型上公平比较。
- **全参数微调对比（表3）**：与 Marigold-P 比较，展示保留生成能力的优势。
- **法线估计扩展（表4）**：在四个法线基准上对比其他生成法线方法。
- **消融实验（表5-9）**：
  - Converter 组成（SA/CA/FFN 不同组合）
  - Group Reuse 机制（不同分组数、有无 GRE）
  - Converter 数量（堆叠多个 vs 单一）
  - 初始化方式（随机 vs 预训练）
  - 不同文本提示（空、固定“depth map”、密集描述）
- 每个消融均报告 A.Rel 和 δ1，实验设计较全面。

## 4. 资源与算力
- **硬件**：8 张 NVIDIA H20 GPU。
- **训练配置**：
  - 训练迭代数：30K iterations
  - Batch size：32
  - 优化器：Adam
  - 学习率：PixArt 基座 1e-4，FLUX 基座 3e-4
  - 数据预处理：遵循 Marigold 默认设置
- **参数量**：额外可学习参数仅占原模型的 12%~18%（取决于基座），远少于全参数微调。
- **总训练时间**：论文未明确给出时长，但根据迭代数和硬件推测在数小时内。

## 5. 实验数量与充分性
- **实验数量**：主表 4 个（深度、法线、低秩对比、全参数对比），消融表 5 个，定性图 2 幅，覆盖核心验证。
- **充分性**：
  - 对比方法涵盖近年主流工作（2021-2025），包括判别与生成式、统一模型与仅深度模型。
  - 消融实验系统，从组件有效性到超参数选择均有分析。
  - 在室内（NYUv2, ScanNet）和室外（DIODE）场景均评估，泛化性好。
- **公平性**：
  - 与 LoRA/DoRA 对比时，调整 rank 使参数量与 MERGE-B 匹配，公平。
  - 与 Marigold-P 对比使用相同基座和训练数据，但 MERGE 参数量更少。
  - 训练数据规模远小于 OneDiffusion（74K vs 100M），但性能反超，凸显效率。

## 6. 主要结论与发现
- **MERGE 以极少的额外参数（~12%）实现了与全参数微调可比的深度估计性能，同时完整保留原 T2I 模型的图像生成能力**，这是以往工作无法兼顾的。
- **在 NYUv2 上，MERGE-L 的 A.Rel = 5.9, δ1 = 95.4%，超越 OneDiffusion（训练 100M 数据）**；在 DIODE 上 δ1 也领先。
- **Group Reuse 机制有效降低参数量，仅带来轻微性能损失**（14 组共享 vs 不共享：A.Rel 从 7.0 升至 7.5，但参数量减半）。
- **Converter 简化（移除 Cross-Attention、缩小 FFN 扩展率）完全可行**，不影响深度估计精度。
- **MERGE 可扩展到法线估计任务**，性能与专用方法相当。
- **预训练 T2I 模型本身已蕴含深度线索，只需轻量引导即可利用**，无需大规模多任务训练。

## 7. 优点
- **方法新颖且简洁**：即插即用框架，无需改动原始 T2I 模型参数，创新性高。
- **参数高效**：12% 额外参数即可实现高质量零样本深度估计，训练数据仅需 74K 合成样本。
- **模式切换零副作用**：图像生成能力完全保留，克服了全参数微调的根本缺陷。
- **通用性**：基于 DiT 架构（PixArt、FLUX）均有效，并扩展到法线估计。
- **消融充分**：对 converter 的每个组件、GRE 分组数、初始化等均做了细致分析，结论可信。
- **公平对比**：与多种基线在同一条件下比较，且公开代码。

## 8. 不足与局限
- **任务覆盖有限**：论文明确指出难以扩展到语义分割，因为现有方法（如 RGB 空间 ID 映射或 LDMSeg 位编码）与 VAE 不兼容或存在随机性问题。
- **性能差距**：在 DIODE 等室外复杂场景中，判别方法（如 DepthAnything v2）仍显著领先，生成式方法在户外泛化上弱于判别式。
- **架构依赖**：方法设计基于 DiT 架构（PixArt、FLUX），是否完全适用于 UNet 架构的 T2I 模型未验证（尽管理论上可迁移但需要适配）。
- **缺乏大规模多任务验证**：仅测试了深度和法线，未验证其他感知任务（如边缘、法线+深度联合等）。
- **数据来源单一**：训练仅使用两种合成数据集（室内+室外各一），尽管零样本泛化好，但域迁移风险仍存在（如真实低照度或特殊场景未覆盖）。
- **资源信息不全**：未报告训练总时长（小时数），仅在消融中提及迭代次数和 GPU 数量，影响复现精确性。

（完）
