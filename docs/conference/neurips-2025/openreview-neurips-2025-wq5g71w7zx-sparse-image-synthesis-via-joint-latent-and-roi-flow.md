---
title: Sparse Image Synthesis via Joint Latent and RoI Flow
title_zh: 基于联合潜变量和RoI流的稀疏图像合成
authors: "Ziteng Gao, Jay Zhangjie Wu, Mike Zheng Shou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wq5G71w7Zx"
tags: ["query:real-ir"]
score: 4.0
evidence: 使用稀疏潜变量表示的生成模型
tldr: 现有生成模型多依赖密集网格表示，忽视图像的空间稀疏性。本文提出一种基于稀疏非网格潜变量和RoI流的生成范式，通过稀疏自编码器将图像表示为少量带位置属性的潜变量，并联合训练流匹配Transformer。实验表明，该方法在保持生成质量的同时提高了效率，为视觉生成提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 577, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 793, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wq5g71w7zx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 791, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 451, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 273, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 565, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 901, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wq5g71w7zx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1164, \"height\": 430, \"label\": \"Table\"}]"
motivation: 自然图像具有内在稀疏结构，但现有生成模型使用密集网格表示，效率低。
method: 设计稀疏自编码器提取非网格潜变量，并联合RoI值训练流匹配Transformer。
result: 在图像合成任务中取得了有竞争力的结果，同时降低了计算开销。
conclusion: 利用稀疏表示可以提升生成模型的效率和表现力。
---

## Abstract
Natural images often exhibit underlying sparse structures, with information density varying significantly across different spatial locations. However, most generative models rely on dense grid-based pixels or latents, neglecting this inherent sparsity. In this paper, we explore modeling visual generation paradigm via sparse non-grid latent representations. Specifically, we design a sparse autoencoder that represents an image as a small number of latents with their positional properties (i.e., regions of interest, RoIs) with high reconstruction quality. We then explore training flow-matching transformers jointly on non-grid latents and RoI values. To the best knowledge, we are the first to address spatial sparsity using RoIs in generative process. Experimental results show that our sparse flow-based transformers have competitive performance compared with dense grid-based counterparts with significantly reduced lower compute, and reaches a competitive 2.76 FID with just 64 latents on class-conditional ImageNet $256\times 256$ generation.

---

## 论文详细总结（自动生成）

# 论文总结：基于联合潜变量和RoI流的稀疏图像合成

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：自然图像具有内在的稀疏结构，不同空间位置的信息密度差异很大（例如，天空背景像素多但信息量少，前景物体细节丰富）。然而，现有主流生成模型（如Stable Diffusion、DiT等）均采用均匀密集网格的潜表示，忽视了这一稀疏性，导致计算资源浪费且无法自适应分配。
- **研究动机**：探索一种新的视觉生成范式——使用非网格的稀疏潜表示（sparse non-grid latent representations），让模型能够根据图像内容动态分配潜变量数量，重点关注信息密集区域（如前景物体），从而在保持生成质量的同时大幅降低计算开销。
- **整体含义**：论文首次将区域兴趣（RoI）的概念引入生成式自编码器的潜空间，并联合建模潜变量和RoI的流（flow），验证了稀疏表示在图像生成中的可行性，为未来更高效的生成模型设计提供了新方向。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **整体框架**：遵循“自编码器 + 生成模型”的latent diffusion范式，但使用非网格表示。
  - **稀疏流自编码器（SF-VAE）**：将图像编码为少量潜变量（latents）及其对应的RoI（边界框格式 (x,y,h,w)）。编码器采用SparseFormer架构，无需边界框监督，通过可微分的局部特征提取逐步细化潜变量和RoI。解码器采用基于神经场的方法：每个潜变量对应一个神经场函数，将像素坐标通过2D余弦基变换（类似连续DCT）后送入条件化的MLP，输出下采样特征图，再经像素解码器上采样至原图。训练使用标准VAE损失（重构损失+感知损失+GAN损失+KL散度），仅对潜变量施加KL正则化。
  - **稀疏流变换器（SF-SiT）**：基于SiT（Scalable Interpolant Transformer），输入为带噪的潜变量和RoI，输出二者的速度（velocity）。关键设计：
    - **RoI位置编码**：将RoI的四个值（x,y,h,w）通过正弦位置编码加到对应token上，且该编码在推理过程中随RoI移动而变化。
    - **异步插值调度（Asynchronous interpolation schedule）**：对RoI使用比潜变量更快的插值策略（多项式调度，β=2），使模型在早期就能获得较清晰的RoI信息，辅助潜变量去噪。公式：σ_{r,t}=(1-t)^β，α_{r,t}=1-(1-t)^β；潜变量保持线性插值。
    - **RoI速度L1损失**：额外添加L1损失（权重0.2）约束RoI速度预测，提升RoI生成准确性。
- **推理**：使用ODE欧拉求解器（不采用SDE，因RoI分布非高斯），从标准高斯噪声逐步求解至目标潜变量和RoI，再通过SF-VAE解码得到图像。

## 3. 实验设计：数据集、Benchmark与对比方法
- **数据集**：ImageNet（class-conditional generation），主要进行256×256图像生成，部分实验扩展到512×512。
- **Benchmark**：使用FID（Fréchet Inception Distance）、IS（Inception Score）、Precision、Recall等标准指标，采用ADM评估流程（50K生成样本）。
- **对比方法**：
  - **自编码器重构**：对比SD-VAE-f8（32×32×4网格潜变量，参数量484M）、DC-AE（8×8×32网格潜变量，参数量323M）。
  - **生成模型**：对比DiT-B/2、DiT-XL/2、SiT-B/2、SiT-XL/2等网格基扩散/流变换器。特别注意使用相同训练步数（400K）和相同采样步数（NFE=250）进行公平比较。
- **消融实验**：针对异步插值调度的β值（1,2,4,min(2t,1),min(4t,1),decoupled）、RoI速度L1损失权重（0,0.2,0.5,1.0）进行超参数搜索。
- **长训练实验**：使用REPA（表示对齐）加速，训练SF-SiT-XL 1.4M步，报告带CFG和不带CFG的结果。

## 4. 资源与算力
- **SF-VAE训练**：32个epoch（320K迭代），batch size 128，学习率1e-4。未明确说明GPU型号和数量，但从训练时长可推测使用了多卡。
- **SF-SiT基础训练**：400K迭代，全局batch 256，Adam优化器，学习率1e-4。未明确GPU配置。
- **SF-SiT-XL长训练**：使用REPA，训练1.4M步，8张A100 GPU，耗时7天。
- **备注**：作者明确指出“Due to the lack of computational resources”，因此部分实验（如SF-SiT-XL的REPA训练）仅完成1.4M步，未达到标准7M步，限制了性能。计算资源分配相对有限。

## 5. 实验数量与充分性
- **实验组数**：约10组主要实验，包括：
  - 重构性能对比（表1）：不同方法在256×256和512×512上的rFID、PSNR、SSIM、LPIPS。
  - 潜变量数量影响（表2）：32、48、64、128 tokens下的重构rFID。
  - 生成性能对比（表5、表6）：短训练（400K）和长训练（1.4M）下SF-SiT与DiT/SiT的FID、IS等。
  - 消融实验（表3、表4）：异步调度类型、L1损失权重。
  - 可视化分析（图3、图5、图6）：重建图像、RoI分布、去噪过程。
- **充分性与公平性**：
  - **优点**：比较了多种基线，并努力对齐训练步数、采样步数、采样器类型（ODE Euler），结果表格清晰；消融实验探究关键超参数。
  - **不足**：
    - 长训练实验中仅用1.4M步对比原SiT的7M步，结论的普适性可能受限（作者自己也承认预期有更好结果但缺乏算力）。
    - 仅使用ImageNet单一数据集，未在更大规模文本-图像数据集（如LAION）上验证，泛化性存疑。
    - 缺少与最新非网格方法（如ElasticTok、Adaptive Length Tokenization）的直接对比。
    - 未报告多次运行的标准差或置信区间，实验可重复性受限于单次运行。

## 6. 论文的主要结论与发现
- **稀疏表示的有效性**：SF-VAE可用仅64个潜变量（2048维）达到接近SD-VAE-f8（4096维）的重构质量（rFID 0.70 vs 0.63），参数量和计算量更小。
- **生成质量**：SF-SiT-XL在400K步时与SiT-XL（ODE采样）性能相当（FID 18.6 vs 18.8）；长训练1.4M步后，在CFG下达到2.76 FID，略逊于SiT-XL的2.06但仅使用1/4的token数，计算量大幅降低（29.3G vs 114.4G FLOPs）。
- **异步插值和RoI L1损失**：β=2的异步调度与权重0.2的L1损失为最佳配置，单独线性调度或完全解耦调度效果显著变差。
- **局限**：RoI分布偏离高斯导致SDE采样不适用；当前模型收敛较慢，需要更多训练步数。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次提出将RoI作为潜变量的位置属性，并联合生成RoI和潜变量，实现了真正的空间自适应计算，突破了传统网格潜变量的限制。
- **高效性**：自编码器和生成模型均很轻量（SF-VAE仅133M参数，解码器153GFLOPs；SF-SiT-B仅5.9GFLOPs），且能以极少的token（64）达到有竞争力的性能。
- **设计精细**：针对RoI的异步插值调度和L1损失设计精巧，解决了RoI分布非标准高斯、位置信息时变等问题；RoI位置编码随t变化，增强了模型对RoI的动态感知。
- **实验严谨性**：在对比中努力对齐训练步数、采样器类型和NFE，并公开了代码和checkpoint的承诺，透明度较高。

## 8. 不足与局限
- **计算资源有限**：长训练仅1.4M步，远少于基线（7M步），导致最终FID仍有差距（2.76 vs 2.06），且无法充分展示大模型的潜力。
- **实验覆盖窄**：仅在ImageNet 256×256上验证，未涉及文本到图像、高分辨率（512×512以上）、视频、3D等领域，泛化性未知。
- **RoI分布建模困难**：RoI不符合高斯分布，导致SDE采样不适用，只能使用ODE采样，可能限制生成多样性。
- **安全性**：论文提到“it inherits safety risks regarding its generated content”，但未给出任何具体的安全措施或讨论，仅以ImageNet本身相对安全为由一笔带过，略显不足。
- **缺少与同类稀疏方法的直接对比**：如ElasticTok、Adaptive Length Tokenization等，使方法相对贡献的定位不够清晰。
- **超参数敏感性**：异步插值β和L1损失权重需手动调节，尚无理论指导选择。

（完）
