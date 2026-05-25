---
title: "GaussMarker: Robust Dual-Domain Watermark for Diffusion Models"
title_zh: 高斯标记：面向扩散模型的鲁棒双域水印
authors: "Kecen Li, Zhicong Huang, Xinwen Hou, Cheng Hong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=m7Mx14cxv8"
tags: ["query:real-ir"]
score: 4.0
evidence: 在空间和频率域为扩散模型输出添加水印
tldr: 该论文针对扩散模型生成的图像提出双域水印方案，在空间域和频域同时嵌入水印，并引入可学习的高斯噪声恢复器增强检测鲁棒性，保护版权。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1557, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 821, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1695, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1660, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 842, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-m7mx14cxv8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 316, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 767, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 544, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1776, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 811, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-m7mx14cxv8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 896, \"height\": 249, \"label\": \"Table\"}]"
motivation: 扩散模型生成图像易被滥用，现有单域水印鲁棒性不足。
method: 流水线式注入器在空频双域嵌入水印，配合高斯噪声恢复器。
result: 实验显示双域水印对多种图像操作和攻击具有更高鲁棒性。
conclusion: 双域水印有效保护扩散模型生成图像的版权和完整性。
---

## Abstract
As Diffusion Models (DM) generate increasingly realistic images, related issues such as copyright and misuse have become a growing concern. Watermarking is one of the promising solutions. Existing methods inject the watermark into the *single-domain* of initial Gaussian noise for generation, which suffers from unsatisfactory robustness. 
This paper presents the first *dual-domain* DM watermarking approach using a pipelined injector to consistently embed watermarks in both the spatial and frequency domains. To further boost robustness against certain image manipulations and advanced attacks, we introduce a model-independent learnable Gaussian Noise Restorer (GNR) to refine Gaussian noise extracted from manipulated images and enhance detection robustness by integrating the detection scores of both watermarks.
GaussMarker efficiently achieves state-of-the-art performance under eight image distortions and four advanced attacks across three versions of Stable Diffusion with better recall and lower false positive rates, as preferred in real applications.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
随着扩散模型（Diffusion Models, DM）生成图像的逼真度日益提高，其带来的版权侵犯和恶意滥用问题也愈发突出。数字水印技术是一种有效的解决方案。然而，现有方法通常只在单一域（空间域或频率域）中向初始高斯噪声注入水印，导致鲁棒性不足，尤其在面对旋转、裁剪等简单图像编辑时，检测性能会急剧下降。例如，一些前沿方法在图像仅旋转3度时，检测准确率便从100%骤降至64%左右，极大地限制了其实际应用价值。因此，本文旨在提出一种更鲁棒、无需微调模型的水印方法，以提升对多种图像攻击的抵抗力。

### 论文提出的方法论
GaussMarker的核心思想是实现**双域水印注入**，并引入**可学习的高斯噪声恢复器**来增强检测鲁棒性。该方法包含注入和检测两个主要阶段。

*   **水印注入**：
    *   **空间域注入**：对一个`l`位的水印`ω`进行上采样和基于密钥`k`的置换，得到一个与水印高斯噪声`z_T`同维度的信号图`s`。然后，通过公式`z^s_T = abs(z_T) · (2s - 1)`，利用`s`来指导`z_T`的正负号，从而在空间域嵌入多位水印。
    *   **频率域注入**：对空间域水印处理后的`z^s_T`进行傅里叶变换，得到一个环形傅里叶特征图`ω_f`。然后，通过预定义的圆形掩码`M`，用公式`z^{s,f}_T = F^{-1}( F(z^s_T) · (1 - M) + ω_f · M )`将零位水印注入到`z^s_T`的频率域中，同时尽可能保留空间域的信号`s`。
*   **水印检测**：
    *   **初始噪声估算**：对于输入图像，先利用DDIM反演过程估算其对应的初始高斯噪声图`z_T`。
    *   **单域分数提取**：从估算的`z_T`中，通过注入的逆过程分别提取空间域检测分数`r_s`和频率域检测分数`r_f`。
    *   **高斯噪声恢复器**：为解决旋转和裁剪攻击下检测性能下降的问题，本文设计了一个可学习的、不依赖扩散模型训练的高斯噪声恢复器。它的核心目标是学习一种从被编辑图像估算出的高斯噪声信号图，恢复到原始水印信号图的映射。其优化目标是一个包含正负样本学习的二分类交叉熵损失函数，旨在让恢复器能精确还原带有水印的信号图，而对无水印的信号图则保持不变。GNR仅在检测阶段用于修正从空间域提取的信号，以提升`r_s`的准确性。
    *   **分数融合**：最后，使用一个两层的多层感知机模型，将空间域分数`r_s`和频率域分数`r_f`融合成一个最终的检测分数`r`，以实现更稳健的水印存在性判断。

### 实验设计
*   **数据集与场景**：实验在三个版本的Stable Diffusion模型（V1.4, V2.0, V2.1）上进行文本到图像的生成。使用`Stable-Diffusion-Prompts`数据集中的提示词进行生成，生成`512x512`像素的图像。水印容量设定为256位。
*   **Benchmark与对比方法**：作者全面对比了七种基线方法，涵盖多个类别：
    *   **免微调方法**：Tree-Ring， RingID， Gaussian Shading， PRC， LatentTracer。
    *   **需微调方法**：Stable Signature。
    *   **经典后处理方法**：DwtDctSvd（也是Stable Diffusion官方采用的方法）。
*   **评估指标**：
    *   **鲁棒性**：在1%假阳性率下的真阳性率（TPR@1%FPR）和位准确率（Bit Accuracy）。
    *   **保真度**：CLIP分数和FID（Fréchet Inception Distance）分数。
*   **攻击类型**：实验评估了**八种基本图像失真**（旋转、JPEG压缩、裁剪缩放、随机丢弃、模糊、椒盐噪声、高斯噪声、亮度调节）和**三种高级攻击**（VAE压缩、扩散模型再生成、视觉感知通用攻击UnMarker）。

### 资源与算力
论文明确提到了训练高斯噪声恢复器所需的资源：仅需**1张32G显存的V100 GPU**，训练时长约**72分钟**。这表明该方法的额外训练成本相对较低。在推理（检测）阶段，GNR和分数融合模块引入的时间开销几乎可以忽略不计（分别为0.0012秒和0.0001秒），主要耗时在于DDIM反演（约6.5秒）。

### 实验数量与充分性
实验设计全面且充分，客观性较强。
*   **超过千组实验**：作者生成了上千张水印和非水印图像进行评估。
*   **多模型跨版本验证**：在三个版本的Stable Diffusion上进行了测试。
*   **多维度鲁棒性测试**：覆盖了8种基本失真和4种高级攻击，并对其中一些攻击（如旋转、压缩）设置了不同强度进行深入分析。
*   **详尽的消融研究**：
    *   分别考察了仅空间域、仅频率域、双域(无GNR)、空间域+GNR和完整GaussMarker的性能。
    *   研究了GNR训练时采用的变换`T`的范围对鲁棒性的影响。
    *   分析了水印容量（20到212位）对位准确率的影响。
    *   测试了支持多用户（最多107个）时的身份识别准确率。
    *   探索了GNR模型大小、分数融合器（Fuser）类型、频率域掩码半径以及采样步数对性能的影响。

### 论文的主要结论与发现
1.  **性能最优**：GaussMarker在三个Stable Diffusion版本、八种图像失真下，平均TPR@1%FPR和位准确率均超过0.99，显著优于所有基线方法。
2.  **鲁棒性领先**：在面对先进的压缩攻击、扩散模型再生成攻击和视觉感知攻击时，GaussMarker同样展现了最强的鲁棒性。
3.  **双域与GNR是关键**：消融实验证实，空间域和频率域水印在对抗不同攻击时各有优势，融合二者分数至关重要。而GNR是针对旋转和裁剪攻击，将位准确率从50%左右提升至接近100%的核心组件。
4.  **良好的保真度**：在实现顶级鲁棒性的同时，GaussMarker生成的图像在CLIP分数和FID指标上保持了较高的质量，超越了鲁棒性最强的需微调基线方法Stable Signature。

### 优点
1.  **鲁棒性强**：首次将双域水印与可学习恢复器结合，极大地提升了对多种图像编辑和高级攻击的抵抗力。
2.  **无需微调**：方法不修改扩散模型参数，保留了模型的通用性，部署成本低。
3.  **模型无关的恢复器**：GNR的训练无需依赖任何扩散模型，仅需少量算力（一张V100，72分钟），且一个GNR可服务于多个水印，效率高。
4.  **高用户容量**：支持为多达10⁷个用户分配独立水印，并能保持高识别准确率。
5.  **实验详尽**：全面的对比、消融和压力测试，验证了方法的有效性和各模块的贡献，结论可信度高。

### 不足与局限
1.  **依赖DDIM反演**：与多数免微调方法一样，GaussMarker的检测依赖于基于ODE求解器的DDIM反演，可能不适用于其他类型的采样器。
2.  **不支持模型发布保护**：由于未修改模型参数，该方法不支持将水印直接嵌入模型权重，无法在模型本身被泄露时追溯来源。
3.  **保真度略有折损**：与部分保真度最优的免微调方法相比，GaussMarker在图像质量上存在微小损失，这可能是双域注入引入更多编辑所致。
4.  **对强噪声敏感**：虽然总体鲁棒性很强，但在高强度的高斯噪声攻击下，检测性能仍有明显下降。

（完）
