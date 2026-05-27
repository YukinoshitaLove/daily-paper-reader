---
title: "When Worse is Better: Navigating the Compression Generation Trade-off In Visual Tokenization"
title_zh: 何时更差反而更好：视觉标记化中压缩与生成的权衡
authors: "Vivek Ramanujan, Kushal Tirumala, Armen Aghajanyan, Luke Zettlemoyer, Ali Farhadi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=o8hWyJIgAV"
tags: ["query:real-ir"]
score: 7.0
evidence: 视觉标记化中压缩与生成的权衡分析
tldr: 两阶段图像生成中，第一阶段压缩与第二阶段生成存在权衡。本文通过缩放定律研究离散自回归图像生成中的这一权衡，发现对于较小的第二阶段模型，更激进的压缩（即使重建变差）反而提升生成性能，提供了选择标记化方法的指导原则。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1306, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1314, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1321, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1299, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 574, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 584, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 1241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1449, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1302, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1449, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1448, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1448, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1449, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1448, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1448, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1449, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1447, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1447, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1448, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1449, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1448, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1449, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1448, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1437, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hwyjigav/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1356, \"height\": 475, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 805, \"height\": 889, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 593, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 592, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1008, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 988, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hwyjigav/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 569, \"height\": 179, \"label\": \"Table\"}]"
motivation: 两阶段图像生成中压缩与生成的权衡不明确。
method: 通过缩放定律分析不同压缩率下生成性能的变化。
result: 发现更激进压缩可提升小生成模型的最终性能。
conclusion: 为视觉标记化的设计提供了权衡指导。
---

## Abstract
Current image generation methods are based on a two-stage training approach. In stage 1, an auto-encoder is trained to compress an image into a latent space; in stage 2, a generative model is trained to learn a distribution over that latent space. This reveals a fundamental trade-off, do we compress more aggressively to make the latent distribution easier for the stage 2 model to learn even if it makes reconstruction worse? We study this problem in the context of discrete, auto-regressive image generation. Through the lens of scaling laws, we show that smaller stage 2 models can benefit from more compressed stage 1 latents even if reconstruction performance worsens, demonstrating that generation modeling capacity plays a role in this trade-off. Diving deeper, we rigorously study the connection between compute scaling and the stage 1 rate-distortion trade-off. Next, we introduce Causally Regularized Tokenization (CRT), which uses knowledge of the stage 2 generation modeling procedure to embed useful inductive biases in stage 1 latents. This regularization improves stage 2 generation performance better by making the tokens easier to model without affecting the stage 1 compression rate and marginally affecting distortion: we are able to improve compute efficiency 2-3$\times$ over baseline. Finally, we use CRT with further optimizations to the visual tokenizer setup to result in a generative pipeline that matches LlamaGen-3B generation performance (2.18 FID) with half the tokens per image (256 vs. 576) and a fourth the total model parameters (775M vs. 3.1B) while using the same architecture and inference procedure.

---

## 论文详细总结（自动生成）

# 论文《When Worse is Better: Navigating the Compression-Generation Trade-off for Visual Tokenization》中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：现代图像生成普遍采用两阶段训练：第一阶段（Stage 1）用自编码器（如VQGAN）将图像压缩到潜在空间（通常是离散 token 序列）；第二阶段（Stage 2）用生成模型（如自回归 transformer）学习该潜在空间上的分布。
- **核心问题**：存在一个根本的权衡——是更激进地压缩（使得 Stage 2 学习更容易但重建质量变差），还是保留更多信息（重建好但 Stage 2 学习更难）？本文系统研究了这种“压缩-生成”权衡，并探索如何通过缩放定律来量化最优压缩率。
- **整体含义**：传统方法孤立地优化 Stage 1（仅关注重建损失），但生成质量最终取决于 Stage 1 的重建能力和 Stage 2 的建模能力共同作用。本文揭示了更差的 Stage 1 重建有时反而能带来更好的 Stage 2 生成，关键在于 Stage 2 的容量和计算预算。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 引入**因果正则化标记化（Causally Regularized Tokenization, CRT）**：在 Stage 1 训练中，利用一个小的因果 transformer 对预量化前的连续潜在特征施加 ℓ2 下个 token 预测损失，并将该损失反向传播到编码器。这使得 Stage 1 的 tokens 更易于被自回归 Stage 2 建模，从而在几乎不改变压缩率且仅轻微影响重建失真的前提下，大幅提升 Stage 2 的生成效率。

### 关键技术细节
1. **基线框架**：VQGAN（ResNet 编码器+解码器，codebook 大小为 16k，输出 256 个 token）。
2. **CRT 损失**：  
   - 在编码器输出的连续潜在向量 \( \hat{X}_i \) 上，用一个 2 层因果 transformer 预测下一个位置的连续潜在向量，损失为 ℓ2 误差 \( \|\hat{X}_i - \text{pred}(\hat{X}_{<i})\|_2 \)。
   - 该损失与标准 VQGAN 损失（VQ、GAN、感知、ℓ2）加权联合训练，权重 λ=4.0（需预先从 0 退火）。
   - 关键设计：使用 ℓ2 损失而非交叉熵（CE），因为 CE 在离散 token 切换时会丢失相似性信息，而 ℓ2 在连续空间上更平滑。
3. **缩放定律分析**：采用 \( L(C) = L_{\min} + C^\alpha e^\lambda \) 形式拟合验证损失和 gFID 与训练 FLOPs 的关系，用于评估不同压缩策略下的计算最优前沿。
4. **Stage 2 模型**：Llama 架构的自回归 transformer，类条件生成，使用分类器无关引导（CFG）采样。

## 3. 实验设计：数据集、benchmark、对比方法

- **主要数据集**：ImageNet 256×256（128 万张图像，1000 类），用于类条件生成。
- **辅助数据集**：LSUN 的三个子集（猫、马、卧室），验证方法在更大规模数据上的普适性。
- **Benchmark 指标**：
  - 重建：rFID（FID on reconstruction）、PSNR、MS-SSIM。
  - 生成：gFID（生成图像与验证集的 FID）、Inception Score、Precision、Recall。
- **对比方法**：
  - 系统级对比：与 ADM（扩散）、LDM、DiT、MaskGIT、VAR、VQGAN、LlamaGen 等公开 SOTA 方法比较。
  - 计算控制对比：在 ImageNet 和 LSUN 上，同等计算/参数下与优化的 VQGAN 基线比较。
  - 消融实验：CRT 超参数（层数、损失权重）、损失形式（ℓ2 vs CE vs LARP）、codebook 大小、token 数量等。

## 4. 资源与算力

- 训练硬件：每个实验在 1 个节点（8 张 80GB A100 GPU）上运行。
- 训练时长：
  - Stage 1 VQGAN：约 3 天（400k 迭代，batch 128）。
  - Stage 2 最大模型（775M 参数）：约 3.5 天（375k 迭代，batch 256）。
- 计算量近似：作者未给出精确的总 FLOPs，但通过缩放定律图覆盖了约 10^15 至 10^18 FLOPs 的计算范围。
- 注：CRT 在 Stage 1 训练中引入约 5% 的额外 FLOPs（2 层 transformer），作者通过减少 5% 训练步数进行控制。

## 5. 实验数量与充分性

- 总体实验量非常大，主要分为三大类：
  - **缩放定律实验**：针对不同 codebook 大小（1k、16k、131k）和 token 数量（256、400、576），每个设置训练了 7 种模型规模（52M～775M 参数）× 9 种迭代步数（15k～2.25M），总计超过 200 个独立训练运行。
  - **CRT 对比实验**：在 ImageNet 上对 7 种模型规模、4 种计算预算进行系统对比，并重复于 LSUN 的 3 个类别、3 种规模。
  - **消融实验**：CRT 层数（0-12）、损失权重 λ（0-15）、损失形式（ℓ2 vs CE vs LARP）、codebook 大小、token 数量等，每组消融取多个 Stage 2 规模的平均 gFID 以增强统计性。
- 充分性评价：实验覆盖了 2～3 个数量级的模型参数和 5 个数量级的计算预算，对比了最相关的 SOTA 方法，并控制了计算公平性（如训练时减少 CRT 的额外开销）。但 FID 指标仅报告点数未给误差线，作者说明方差很低。总体实验设计严谨、全面，支持主要结论。

## 6. 论文的主要结论与发现

1. **压缩-生成权衡依赖于 Stage 2 模型容量**：小模型更喜欢更激进的压缩（低 token/低 codebook），大模型在高计算预算下需要更好的重建质量来逼近瓶颈。
2. **缩放定律分析一致**：在验证损失和 gFID 上都观察到 log-log 线性缩放；计算最优前沿符合统一函数形式。
3. **CRT 显著提升 Stage 2 效率**：在相同计算/参数下，CRT 将 gFID 降低 15-30%，计算效率提升 2-3×；在系统级对比中，CRT 以 775M 参数、256 tokens 达到 LlamaGen-3B（3.1B 参数、576 tokens）的性能（2.18 gFID），实现 4 倍参数节省和 8 倍推理计算节省。
4. **CRT 在 LSUN、文本-图像生成上也有效**：在更大规模、非 ImageNet 数据上同样带来一致改进。
5. **关键设计选择**：ℓ2 损失优于 CE，2 层因果 transformer 为最佳；CRT 通过降低 tokens 的条件熵来提升 Stage 2 建模（均匀降低所有位置的损失）。

## 7. 优点：方法或实验设计上的亮点

- **系统性缩放分析**：首次在大规模视觉 token 化中系统研究压缩率、计算预算和模型容量三者间的相互作用，提供了可指导设计的缩放定律。
- **简洁有效的 CRT 方法**：仅需在 Stage 1 训练时增加一个小的辅助损失，即可在几乎不改变 token 化结构的情况下显著提升生成效率，具备强通用性和易于集成性。
- **公平的计算控制**：所有对比均保持 Stage 2 计算量（FLOPs）一致，并通过减少训练步数抵消 CRT 引入的额外开销，确保比较的公正性。
- **全面消融与验证**：对关键超参数、损失形式、数据域进行了系统消融，并在多个数据集（ImageNet, LSUN, 文本-图像）上验证了方法的普适性。
- **清晰的实践指导**：结论直观——资源受限时选更压缩的 token 化，预算充足时需平衡重建质量；CRT 可进一步提升 Pareto 前沿。

## 8. 不足与局限

- **模型规模上限**：最大 Stage 2 模型为 775M 参数，未探索更大规模（如 1B+），作者指出受限于 ImageNet 数据集大小（数据瓶颈）。未来可在更大数据（如 text-to-image web-scale）上验证缩放趋势。
- **评估偏重 ImageNet**：主要实验在类条件 ImageNet 上进行，虽然增加了 LSUN 和文本-图像实验，但后者仅做了初步验证，且 LSUN 的 gFID 趋势不如 ImageNet 稳定（随参数增加改善不明显）。
- **无开源代码和数据**：由于公司政策，代码未公开，可复现性受一定影响（但附录提供了完整训练细节）。
- **CRT 轻微增加 Stage 1 训练成本**：虽然作者控制了总 FLOPs，但实际训练时间略有增加（约 5%）；在极大规模 tokenizer 训练中可能需要额外权衡。
- **依赖预定义扫描顺序**：CRT 的因果顺序基于固定的 raster-scan 顺序，未来工作可结合更灵活的 1D tokenizer 以释放更多增益。
- **未讨论负面的社会影响**：附录 C 简要提及 deepfake 和版权问题，但未深入分析。

（完）
