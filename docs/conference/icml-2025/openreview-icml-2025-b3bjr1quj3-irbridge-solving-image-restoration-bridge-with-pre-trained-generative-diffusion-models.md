---
title: "IRBridge: Solving Image Restoration Bridge with Pre-trained Generative Diffusion Models"
title_zh: IRBridge：利用预训练生成扩散模型解决图像复原桥问题
authors: "Hanting Wang, Tao Jin, Wang Lin, Shulei Wang, Hai Huang, Shengpeng Ji, Zhou Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=b3bJR1quJ3"
tags: ["query:real-ir"]
score: 10.0
evidence: 利用预训练扩散模型无需按退化类型训练解决图像复原
tldr: 针对现有图像修复桥模型需为每种退化重新训练的问题，提出IRBridge方法，通过设计转移方程弥合预训练生成扩散模型与修复任务间的分布差异。该方法无需为特定退化训练全新模型，显著降低计算成本并保持高性能。实验表明，IRBridge可通用地解决多种图像复原任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 788, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 771, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1753, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 848, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1653, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1618, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 581, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 578, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 577, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 579, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 576, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 574, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1411, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1404, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1407, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1699, \"height\": 966, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1704, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1701, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1701, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1701, \"height\": 961, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-b3bjr1quj3/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1697, \"height\": 957, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1530, \"height\": 560, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1128, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1130, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1128, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1129, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1128, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1130, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 685, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-b3bjr1quj3/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 348, \"label\": \"Table\"}]"
motivation: 每种退化类型都需从头训练桥模型，成本高且性能受限。
method: 通过转移方程将预训练扩散模型先验有效融入图像复原桥。
result: 在多种图像复原任务上高效利用预训练模型，减少训练开销。
conclusion: IRBridge为复用生成先验进行图像复原提供了通用框架。
---

## Abstract
Bridge models in image restoration construct a diffusion process from degraded to clear images. However, existing methods typically require training a bridge model from scratch for each specific type of degradation, resulting in high computational costs and limited performance. This work aims to efficiently leverage pretrained generative priors within existing image restoration bridges to eliminate this requirement. The main challenge is that standard generative models are typically designed for a diffusion process that starts from pure noise, while restoration tasks begin with a low-quality image, resulting in a mismatch in the state distributions between the two processes. To address this challenge, we propose a transition equation that bridges two diffusion processes with the same endpoint distribution. Based on this, we introduce the **IRBridge** framework, which enables the direct utilization of generative models within image restoration bridges, offering a more flexible and adaptable approach to image restoration. Extensive experiments on six image restoration tasks demonstrate that IRBridge efficiently integrates generative priors, resulting in improved robustness and generalization performance. Code will be available at GitHub.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景**：图像复原旨在从受雨、雾、噪声等退化影响的低质量图像中重建高质量图像。近年来，基于扩散模型的桥模型（bridge models）通过直接建模从退化图像到清晰图像的随机过程，在理论上更贴合图像复原的物理本质。
- **核心问题**：现有的图像复原桥模型（如IR‑SDE、GOUB）需要为**每一种特定的退化类型**（如去雨、去雾、去雪等）**从头训练一个独立的模型**，导致极高的计算成本与有限的泛化能力。
- **整体含义**：本文提出 **IRBridge** 框架，目标是**高效复用预训练生成扩散模型中的强大先验**，从而避免为每一种退化重新训练桥模型，同时提升模型的鲁棒性和泛化性能。

## 2. 方法论

### 2.1 核心思想
- 生成扩散模型（如Stable Diffusion）和图像复原桥模型（如IR‑SDE）的扩散过程都从**清晰图像**开始，最终分布相同（相同终点分布），但中间状态的分布不同。
- 提出一个**转移方程（Transition Equation）**，能够在两个具有相同终点分布的扩散过程之间进行状态转换，从而让预训练生成模型直接处理复原桥中的中间状态。

### 2.2 关键技术细节
- **转移方程**：设两个过程的状态分别为 `x_i^∘` (复原桥) 和 `x_j^*` (生成扩散)，则在已知清晰样本 `x0` 的条件下，二者之间可以通过线性组合与噪声项进行转换：
  `x_j^* = α·x_i^∘ + β·x0 + γ + σϵ`
  其中系数 `α,β,γ` 可由两个过程的扩散参数确定，`σ` 为可控的噪声系数。
- **临界时间步**：存在一个特定的时间步 `t̃_i`，当 `j = t̃_i` 且噪声 `σ` 取最小允许值时，方程中对 `x0` 的依赖系数 `β=0`，从而无需事先知道 `x0` 即可完成转换。
- **前向转移**：选择 `j > t̃_i` 且取特定 `σ` 使 `β=0`，可以将复原桥的状态**直接转化为生成扩散的状态**，而不依赖 `x0`。
- **反向转移**：利用估计得到的 `ˆx0`，选择 `i-1 < t̃_j` 且取 `σ=0`，可以**无噪声地**将生成扩散的状态映射回合复原桥的下一个状态，支持迭代。
- **IRBridge 框架**：  
  1. 对每一步，先通过**前向转移**将当前复原桥状态 `x_i^∘` 转换为生成扩散的状态 `x_j^*`。  
  2. 将该状态输入预训练生成模型，估算 `ˆx0`。  
  3. 再利用**反向转移**将 `x_j^*` 与 `ˆx0` 转换为复原桥的下一个状态 `x_{i-1}^∘`。  
  4. 重复上述步骤直至完成复原。  
  实际实施中，采用 **ControlNet** 将退化图像作为条件引导生成模型，而不需要建模退化过程本身。

### 2.3 公式与流程说明（文字概括）
- 所有涉及的扩散过程均可参数化为 `x_t = f_t x_0 + b_t + σ_t ε`。
- 转移方程的核心在于利用两个过程的 `f_t`、`b_t`、`σ_t` 已知且终点分布相同这一条件，推导出状态间的线性变换。
- 通过合理选择前向转移的 `j` 和反向转移的 `i-1`，可以完全避免或最小化对未知 `x0` 的依赖，实现零样本桥接。

## 3. 实验设计

### 3.1 使用数据集
- 图像去雨：Rain100H (1800训练/100测试)
- 图像去雾：RESIDE (OTS训练，SOTS测试)
- 图像去雪：Snow100K (50K训练/50K测试)
- 雨滴去除：RainDrop (861训练/58测试)
- 低光增强：LOL (485训练/15测试)
- 图像修复：CelebA-HQ 256×256 (随机笔刷掩膜)
- 真实场景泛化测试：RealRain-1K、Snow100K真实子集、RTTS，使用无参考指标。

### 3.2 对比方法
- **桥模型**：ResShift、IR‑SDE、GOUB、RDDM、DiffUIR
- **回归/有监督方法**：WGWS‑Net、IR‑SDE CNN RM、PromptIR
- **其他利用生成扩散先验的方法**：TAO、GDP、DDRM
- 本文方法同时考察了基于 IR‑SDE 和 GOUB 两种桥过程的变体。

### 3.3 评估指标
- PSNR、SSIM（均在Y通道计算，并通过VAE解码消除公平性干扰）
- LPIPS（感知相似度）
- FID（分布距离，衡量整体真实感）

## 4. 资源与算力
- 预训练模型：Stable Diffusion v1‑5
- 训练ControlNet：使用 **1 张 Nvidia RTX 3090 GPU**，batch size = 12，训练 **10k 步**，约 **1 天**。
- 作为对比，从头训练 GOUB 在同等GPU上约需 2.5 天。
- 推理时间：虽非优势，但可灵活调整步数，100 步约 14.2 秒，25 步约 3.4 秒，性能下降不大。

## 5. 实验数量与充分性
- 涵盖 **6 类主流复原任务**，每类任务均与多种类型方法（桥模型、回归模型、其他生成先验方法）进行全面定量对比（如表1）。
- 提供了**丰富的定性可视化结果**，包括不同迭代步的中间预测。
- **多角度消融与讨论**：
  - 时间步调度策略对性能的影响（多种任务，多种预设调度方案的分析）
  - 条件引导的作用（有无条件的对比）
  - 扩散过程类型的影响（生成扩散从噪声出发 vs. 桥扩散从退化图像出发的PSNR/SSIM曲线比较）
  - 反向转移的替代方案讨论
  - 泛化能力实验（仅用面部数据训练的修复模型在室内外场景的表现）
- 实验**充分且公平**：预处理统一（512分辨率，VAE解码后计算指标），基线丰富，涵盖了训练成本、推理效率、真实世界退化等维度。

## 6. 主要结论与发现
- IRBridge 成功地**无需从头训练桥模型**，直接利用预训练生成扩散模型解决了多种图像复原桥问题。
- 在多数任务上，IRBridge 的定量指标**优于或可媲美**专门训练的桥模型（如 GOUB、IR‑SDE），在 FID 等真实感指标上优势尤为明显。
- 预训练生成先验带来了**更强的泛化能力**，使模型在面对训练时未见过的场景或真实退化时仍能保持良好性能。
- 从退化的低质量图像开始的桥扩散过程，相比从纯噪声开始的常规生成过程，能提供更稳定、与输入更一致的重建结果。

## 7. 优点
- **高效复用先验**：避免为每种退化重新训练，显著降低计算成本，同时受益于大规模预训练带来的强特征表示。
- **通用转移方程**：理论简洁，可扩展至任意具有相同终点分布的扩散过程（如DDPM、Rectified Flow等）。
- **灵活的解耦设计**：训练（仅ControlNet）与推理（桥过程、时间步）分离，允许针对不同任务定制推理超参数。
- **实验全面**：覆盖6类任务，对比主流方法，深入讨论时间步策略、条件依赖和泛化性，论证扎实。

## 8. 不足与局限
- **时间步选择依赖经验**：最优调度策略目前需手动试探，缺乏自动化方法，且文中指出现有的调度并非最优。
- **条件引导模块较粗糙**：仅简单使用了预训练的ControlNet，未针对复原任务特别优化；文本条件未被有效利用。
- **VAE带来的信息损失**：潜伏空间编码可能丢失高频细节，导致平滑效应。
- **推理效率**：迭代扩散过程依然耗时，虽然可通过减少步数缓解，但仍是实时应用的瓶颈。
- **反向转移非最优**：当前使用的反向转移并未最大化似然，迭代路径不是理论上的最优路径。

（完）
