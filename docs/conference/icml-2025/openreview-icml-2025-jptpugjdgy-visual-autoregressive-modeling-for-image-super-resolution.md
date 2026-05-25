---
title: Visual Autoregressive Modeling for Image Super-Resolution
title_zh: 面向图像超分辨率的视觉自回归建模
authors: "Yunpeng Qu, Kun Yuan, Jinhua Hao, Kai Zhao, Qizhi Xie, Ming Sun, Chao Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JPTpUGJDGY"
tags: ["query:real-ir"]
score: 10.0
evidence: 使用扩散细化器的视觉自回归图像超分辨率模型
tldr: 该论文针对图像超分辨率中保真度与真实感的权衡及计算复杂度问题，提出VARSR框架，采用视觉自回归建模和下一尺度预测，通过前缀令牌整合条件，并引入尺度对齐旋转位置编码和扩散细化器，在超分辨率任务上取得优异表现。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1662, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 773, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 811, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1639, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 756, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 763, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 756, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 767, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1167, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1566, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1043, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1037, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1565, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1532, \"height\": 2284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1517, \"height\": 2280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1511, \"height\": 2276, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 845, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 658, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1569, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 807, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 708, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1469, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1644, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1066, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1317, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1781, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1788, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1547, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1027, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1102, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 949, \"height\": 313, \"label\": \"Table\"}]"
motivation: 现有超分模型存在保真度-真实感权衡和计算复杂性问题。
method: 提出VARSR，采用下一尺度预测的自回归模型，结合扩散细化器。
result: VARSR有效平衡保真度与真实感，且计算效率较高。
conclusion: 视觉自回归建模为图像超分辨率提供了新范式。
---

## Abstract
Image Super-Resolution (ISR) has seen significant progress with the introduction of remarkable generative models.
However, challenges such as the trade-off issues between fidelity and realism, as well as computational complexity, have also posed limitations on their application.
Building upon the tremendous success of autoregressive models in the language domain, we propose \textbf{VARSR}, a novel visual autoregressive modeling for ISR framework with the form of next-scale prediction.
To effectively integrate and preserve semantic information in low-resolution images, we propose using prefix tokens to incorporate the condition.
Scale-aligned Rotary Positional Encodings are introduced to capture spatial structures and the diffusion refiner is utilized for modeling quantization residual loss to achieve pixel-level fidelity.
Image-based Classifier-free Guidance is proposed to guide the generation of more realistic images.
Furthermore, we collect large-scale data and design a training process to obtain robust generative priors.
Quantitative and qualitative results show that VARSR is capable of generating high-fidelity and high-realism images with more efficiency than diffusion-based methods.
Our codes are released at \url{https://github.com/quyp2000/VARSR}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
图像超分辨率（ISR）长期面临**保真度与真实感难以兼顾**的问题，同时扩散模型的高计算复杂度限制了其应用。近期在语言领域成功的自回归（AR）模型，尤其是通过“下一尺度预测”进行视觉自回归建模的VAR范式，展现出粗到精生成、高效率等优势。然而，将VAR直接应用于ISR面临四个关键挑战：
- 如何高效整合低分辨率（LR）条件的语义信息；
- 如何保留图像的空间结构；
- 如何弥补离散量化带来的像素级细节损失；
- 如何在优化保真度的同时引导生成更逼真的纹理。

为此，本文提出 **VARSR**，一种针对ISR的视觉自回归框架，旨在利用下一尺度预测的生成特性，实现高保真、高真实感且高效率的图像超分辨率。

### 2. 方法论
VARSR框架分为三个阶段：条件控制生成、视觉自回归和扩散细化，并引入了四项核心技术以解决上述挑战。

- **前缀令牌（Prefix Tokens）作为条件控制**  
  将LR图像通过图像编码器映射为条件令牌 `rc`，并将其作为初始尺度放置在所有尺度令牌序列的开头 `(rc, r1, ..., rK)`。VAR在预测下一尺度时能够持续感知LR先验，有效整合条件信息且结构简单。

- **尺度对齐旋转位置编码（Scale-aligned RoPE）**  
  为克服标准绝对位置编码无法表达2D结构及跨尺度关系的问题，提出对多尺度令牌图进行2D旋转位置编码，并对高度和宽度维度进行归一化对齐，使不同尺度的空间位置关系得以保留。该编码同时应用于LR条件令牌，增强结构保真度。

- **扩散细化器（Diffusion Refiner）**  
  离散量化过程会丢失高频细节。VARSR引入一个轻量级MLP扩散细化器，它接收自回归Transformer最后一层的隐藏状态作为条件，通过扩散损失预测量化残差（连续令牌 `z`），将离散预测映射到连续空间，从而恢复精细纹理，提升像素级保真度。

- **基于图像的分类器自由引导（Image-based CFG）**  
  训练时为高质量和低质量图像分别分配正、负嵌入，使模型能感知低质量失真。推理时，通过引导公式 `eI = F(rc, cp) + λs(F(rc, cp) - F(rc, cn))` 调整概率分布，以引导尺度 `λs` 平衡多样性与真实感，促使生成更清晰、细节更丰富的图像，且无需额外训练。

- **大规模数据与训练流程**  
  收集了包含400万张高质量图像（覆盖超3000个类别）的数据集用于预训练，并从IQA/IAA数据集中选出5万张低质量图像作为负样本。训练分三步：**VQVAE训练**（加入尺度随机丢弃以增强早期尺度的语义）、**类别到图像（C2I）预训练**以获取生成先验、**ISR微调**（平衡交叉熵损失与扩散损失）。

### 3. 实验设计
- **数据集与场景**  
  - 合成验证集：从DIV2K验证集随机裁剪3000张512×512图像的DIV2K-VAL。  
  - 真实世界数据集：DrealSR和RealSR（均中心裁剪至512×512）。  
  - 真实无参考测试集：RealLR200（200张真实退化图像）。  
  LR图像分辨率为128×128，使用Real-ESRGAN退化管道生成。

- **对比方法**  
  与基于GAN的方法（BSRGAN, Real-ESRGAN, SwinIR-GAN, DASR）和基于扩散的方法（LDM, StableSR, DiffBIR, SinSR, PASD, SeeSR）进行全面比较。

- **评价指标**  
  - 全参考：PSNR、SSIM、LPIPS、DISTS、FID。  
  - 无参考感知质量：MANIQA、CLIPIQA、MUSIQ，以及额外的CNNIQA、HyperIQA、TOPIQ。

### 4. 资源与算力
论文明确提到所有实验在 **32块NVIDIA V100 GPU** 上完成。训练阶段分别为：VQVAE 10k次迭代，C2I预训练40k次迭代，ISR微调20k次迭代。优化器为AdamW，批量大小为128，推理时生成一张图像仅需 **0.59秒**，相比扩散方法有10倍以上的效率提升。

### 5. 实验数量与充分性
实验设计非常全面，包含：
- **主实验**：在3个基准数据集（DIV2K-VAL、RealSR、DrealSR）上与10种SOTA方法进行定量和定性比较，并辅以真实场景的用户研究（20名参与者，100张图像）。
- **消融实验**：针对LR条件模式（4种对比）、尺度对齐RoPE（3级）、扩散细化器、图像CFG、训练数据集规模、图像预处理策略、VQVAE尺度丢弃策略等7个以上关键组件进行消融。
- **扩展分析**：基础模型的C2I生成能力对比、在较小微调数据集上的结果、多组附加IQA指标评估、真实世界图像视觉对比。
各项消融均控制了单一变量，对比基线清晰，评估指标多样，实验非常充分、客观且公平。

### 6. 主要结论与发现
- VARSR能够生成**高保真且高真实感**的图像，在MANIQA、CLIPIQA、MUSIQ等无参考感知质量指标上大幅领先GAN和扩散模型对手，并在用户研究中获得最高偏好率（57.1%）。
- 在保真度指标（如PSNR、SSIM）上，VARSR与扩散方法相近，因生成更丰富纹理而略低于过度平滑的GAN方法，这符合保真度-真实感权衡理论。
- 推理效率极高，仅需0.59秒，**计算速度是扩散方法（如DiffBIR）的约10倍**。
- 所提的前缀令牌、尺度对齐RoPE、扩散细化器和图像CFG等模块均对性能有显著贡献。

### 7. 优点
- **范式创新**：首次成功将视觉自回归建模（下一尺度预测）应用于图像超分辨率，开辟了AR在ISR领域的新方向。
- **系统化设计**：针对ISR中条件集成、空间结构、量化损失和生成引导四大难题，设计了四个对应的有效模块，形成完整框架。
- **高效性**：利用AR模型尺度递进的特点和KV-cache等优化，推理步骤少、总计算量小，显著快于迭代采样的扩散模型。
- **数据与训练策略**：构建大规模高质量数据集并设计三阶段训练流程，为模型提供了强生成先验。
- **实验充分性**：涵盖合成和真实数据、多种评价维度、大量SOTA对比和详尽的消融研究，结论可靠。

### 8. 不足与局限
- **训练数据覆盖面**：尽管数据集包含400万张图像，但与Stable Diffusion等使用的数十亿级数据相比仍有差距，难以完美处理极端罕见场景（如论文中展示的蜘蛛侠、古代女子头饰复原不佳）。
- **全参考指标不占优**：由于生成更多纹理，在PSNR、SSIM等像素级保真度指标上相较于以平滑见长的GAN方法不占优势，这虽符合理论，但在某些对失真敏感的场合可能不被视为最优。
- **放大伪影风险**：基于图像的CFG若引导尺度 `λs` 过大，可能引入原图中不存在的细节或伪影，需谨慎调节。
- **模型规模**：基础自回归Transformer和VQVAE的参数量仍然较大（约1.1B），尽管推理速度快，存储和加载成本需考虑。

（完）
