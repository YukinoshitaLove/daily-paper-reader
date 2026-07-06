---
title: "FaithDiff: Unleashing Diffusion Priors for Faithful Image Super-resolution"
title_zh: FaithDiff：释放扩散先验以实现忠实图像超分辨率
authors: "Chen, Junyang, Pan, Jinshan, Dong, Jiangxin"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_FaithDiff_Unleashing_Diffusion_Priors_for_Faithful_Image_Super-resolution_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 提出一种基于扩散的忠实图像超分辨率方法，释放扩散先验
tldr: 针对可靠超分辨率中对真实性和结构一致性的要求，提出FaithDiff方法，充分释放潜在扩散模型的先验。不同于冻结预训练模型，它利用扩散先验识别有用信息并恢复忠实结构，并通过缩小退化输入与噪声潜变量间的特征差距，有效提升了超分辨率结果的保真度，为扩散模型在忠实图像复原中的应用提供了新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1787, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1788, \"height\": 1403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1812, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1816, \"height\": 793, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1814, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1809, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 111, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 869, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-faithdiff-unleashing-diffusion-priors-for-faithful-image-super-resolution-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 176, \"label\": \"Table\"}]"
motivation: 现有扩散超分方法冻结模型导致保真度不足，需充分利用扩散先验实现忠实结构恢复。
method: 提出FaithDiff，释放扩散先验识别有用信息，并弥合退化输入与噪声潜变量的特征差距。
result: 在超分辨率中有效恢复忠实结构，平衡真实感和输入一致性，优于冻结扩散先验的方法。
conclusion: 扩散先验可被有效释放用于忠实超分辨率，该简单方法显著提升保真度。
---

## Abstract
Faithful image super-resolution (SR) not only needs to recover images that appear realistic, similar to image generation tasks, but also requires that the restored images maintain fidelity and structural consistency with the input. To this end, we propose a simple and effective method, named FaithDiff, to fully harness the impressive power of latent diffusion models (LDMs) for faithful image SR. In contrast to existing diffusion-based SR methods that freeze the diffusion model pre-trained on high-quality images, we propose to unleash the diffusion prior to identify useful information and recover faithful structures. As there exists a significant gap between the features of degraded inputs and the noisy latent from the diffusion model, we then develop an effective alignment module to explore useful features from degraded inputs to align well with the diffusion process. Considering the indispensable roles and interplay of the encoder and diffusion model in LDMs, we jointly fine-tune them in a unified optimization framework, facilitating the encoder to extract useful features that coincide with diffusion process. Extensive experimental results demonstrate that FaithDiff outperforms state-of-the-art methods, providing high-quality and faithful SR results.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **核心问题**：真实世界图像超分辨率（SR）不仅需要生成视觉逼真的纹理，还要求恢复的图像与低质量（LQ）输入保持结构一致性（即“忠实性”）。现有的基于潜在扩散模型（LDM）的方法虽然具有强大的生成能力，但通常冻结在高质量图像上预训练的扩散模型，仅仅利用编码器提取退化鲁棒特征去引导扩散过程。
- **主要痛点**：冻结扩散模型使其难以主动识别 LQ 输入中的有用信息，而编码器提取的错误结构信息易被扩散模型误认为真实结构，导致产生令人不满意的虚假纹理或结构错误。
- **整体含义**：为打破这一瓶颈，论文提出 **FaithDiff**，核心思想是“释放”（unleash）并微调扩散模型的先验能力，使其能够主动从退化输入中挖掘有用信息，并通过联合优化编码器和对齐模块，实现高保真、高忠实度的超分辨率。

## 2. 方法论
FaithDiff 的主要设计分为三个关键部分：

### 2.1 LQ 特征提取
- 使用预训练 VAE 编码器提取 LQ 图像的特征，但不同于多数方法只取最后一层（通道数极少），**取倒数第二层输出**（512 通道），以保留更丰富的结构与退化信息。

### 2.2 对齐模块（Alignment Module）
- **动机**：LQ 特征（恒定）与扩散过程逐渐变得清晰的噪声潜变量直接相加会引入持续的退化干扰。
- **结构**：  
  - 分别用卷积处理 LQ 特征 `f_LQ` 和当前时间步的噪声潜变量 `x_t`，然后拼接。  
  - 经过两层 Transformer 块促进两者交互，再通过残差连接与线性映射得到对齐特征 `f_a`。
- **作用**：自适应地从 LQ 特征中提取与当前扩散阶段相匹配的信息，使扩散模型能更好地接收并利用。

### 2.3 统一特征优化（Unified Feature Optimization）
- 将 **VAE 编码器**、**对齐模块**、**扩散模型** 联合微调，而保持 VAE 解码器和文本编码器冻结。
- **训练策略**：先固定编码器和扩散模型，仅预训练对齐模块（6000 次迭代），再进行端到端联合微调（40000 次迭代）。
- **损失函数**：基于噪声预测的 L1 损失：  
  `L = ||ϵ - ϵ̂_θ(√(ᾱ_t) x0 + √(1 - ᾱ_t)ϵ, f_LQ, c, t)||₁`
- **推理时**采用 20 步 Euler 采样，结合无分类器引导（CFG），无需额外适配器（如 ControlNet）。

## 3. 实验设计
### 3.1 数据集与基准
- **训练数据**：LSDIR、DIV2K、Flickr2K、DIV8K 以及 FFHQ（1 万张人脸），合成退化方式与现有工作一致，并利用 LLAVA 生成每张图像的文本描述。
- **合成测试集**：DIV2K-Val 和 LSDIR-Val，使用三种退化级别（Level I: 轻微，Level II: 中等，Level III: 严重）。
- **真实世界测试集**：RealPhoto60（来自 SUPIR）以及自收集的 **RealDeg** 数据集（含老照片、经典电影帧、社交媒体图像，共 238 张）。
- **OCR 识别测试**：ICDAR 2024 Occluded RoadText 数据集，生成严重退化图像以检验结构忠实度。

### 3.2 对比方法
涵盖 GAN 类与扩散类前沿方法：  
Real-ESRGAN、BSRGAN、StableSR、DiffBIR、PASD、SeeSR、DreamClear、CCSR、OSEDiff、ResShift、SUPIR。

### 3.3 评价指标
- **保真度**：PSNR、SSIM
- **感知质量**：LPIPS、MUSIQ、CLIPIQA+、PaQ-2-PiQ、NIQE、MANIQA
- **效率**：扩散推理时间
- **结构保真性**：OCR 识别准确率（Precision/Recall）

## 4. 资源与算力
- **训练硬件**：2 块 A800 GPU
- **批大小**：256（512×512 裁剪块）
- **训练步骤**：预训练对齐模块 6k 次迭代；端到端微调 40k 次迭代。
- **学习率**：对齐模块 5×10⁻⁵，微调阶段编码器 5×10⁻⁶，其他 5×10⁻⁵；使用余弦退火调度器。
- **推理测试**：在单张 A800 GPU 上测量 10 张 1024×1024 图像的扩散过程耗时。

## 5. 实验数量与充分性
实验设计较为完备，包含以下主要类别：

- **合成数据评估**：2 个数据集 × 3 个退化级别，与 11 种方法对比（表1）。
- **真实世界评估**：RealPhoto60 和 RealDeg 两个真实数据集，与多个主流方法对比（表2、图4）。
- **OCR 验证**：专门检验结构恢复能力（表3）。
- **运行时间对比**：6 种扩散方法的推理速度（表4）。
- **消融实验**：
  - 对齐模块有效性（有无对齐模块、有无预训练、倒数第二层特征 vs 最后一层特征）（表5）
  - 统一优化策略有效性（冻结扩散模型、冻结编码器、分别微调、联合微调）（表6）
- **可视化分析**：DAAM 注意力图对比（图5）、典型结果视觉比较（图1、3、4、6）。

实验对比方法多，指标全面，消融实验覆盖关键设计，客观性和公平性较高。

## 6. 论文的主要结论与发现
- **释放扩散先验**比冻结模型更有效：微调扩散模型能主动从退化输入中识别有用信息，抑制重建错误，恢复忠实结构。
- **对齐模块**有效地弥合了 LQ 固定特征与扩散动态潜变量的差距，使信息传输更合理。
- **联合优化编码器与扩散模型**能够利用二者的相互作用，使编码器提取的特征更契合扩散过程，扩散模型进一步修复特征，最终实现高保真恢复。
- 在合成与真实基准上，FaithDiff 在多项感知质量指标和结构保真度上均超越现有方法，且推理速度显著更快（2.55 秒 vs 7~11 秒）。

## 7. 优点
- **设计简洁**：无需额外的 ControlNet 或复杂的特征注入模块，对齐模块轻量且有效。
- **充分利用扩散先验**：不再将扩散模型视为固定的“恢复器”，而是可学习的结构识别器。
- **联合训练策略**：先预训练对齐，再端到端微调，训练稳定且有效促进协同。
- **全面且严谨的实验**：覆盖多种退化、真实场景、高效性、结构保真度，甚至 OCR 验证，多维度证明方法优势。
- **效率优越**：在取得更高质量的同时，推理时间缩短至现有方法的 1/3 左右。

## 8. 不足与局限
- **对预训练模型的依赖**：方法基于 SDXL 等大型文本到图像扩散模型，训练和部署仍需较高计算资源，未探讨在更小模型上的可行性。
- **训练数据规模与多样性**：虽融合多个数据集，但真实退化情况仍难以完全覆盖，在极端未见退化下的泛化能力未作专项分析。
- **潜在偏差风险**：利用 LLAVA 生成文本描述，生成的文本质量可能影响辅助信息的有效性，且文本描述偏差可能引入生成偏差。
- **真实场景有限**：尽管收集了 RealDeg 数据集，但规模较小（238 张），且未涉及更多典型的真实低质图像类型（如监控、医学影像等）。
- **未讨论推理时峰值内存**：虽展示了时间效率，但未给出 GPU 显存占用等资源细节。

（完）
