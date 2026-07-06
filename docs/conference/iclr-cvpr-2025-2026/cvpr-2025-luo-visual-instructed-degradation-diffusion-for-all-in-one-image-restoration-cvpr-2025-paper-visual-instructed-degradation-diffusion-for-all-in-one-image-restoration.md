---
title: Visual-Instructed Degradation Diffusion for All-in-One Image Restoration
title_zh: 视觉引导退化扩散用于全能图像恢复
authors: "Luo, Wenyang, Qin, Haina, Chen, Zewen, Wang, Libin, Zheng, Dandan, Li, Yuming, Liu, Yufan, Li, Bing, Hu, Weiming"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Luo_Visual-Instructed_Degradation_Diffusion_for_All-in-One_Image_Restoration_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 视觉引导退化扩散的全能图像恢复
tldr: 针对传统图像恢复需为每种退化单独建模、无法处理混合退化的问题，提出Defusion框架，通过将标准化视觉元素上的退化作为视觉指令，驱动扩散模型学习统一的恢复映射，消除了任务特定模型和模糊文本先验的需求，在去模糊、去噪、去雾等任务上表现优异，尤其在混合退化场景中展现出强大的泛化能力，为实现通用图像恢复提供了可行路径。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1800, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1816, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1816, \"height\": 653, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1817, \"height\": 1469, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1819, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 873, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-luo-visual-instructed-degradation-diffusion-for-all-in-one-image-restoration-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1813, \"height\": 315, \"label\": \"Table\"}]"
motivation: 现有方法需为每种退化单独训练模型，无法应对混合退化。
method: 提出Defusion，构建视觉指令对齐退化模式，利用扩散模型实现统一修复。
result: 在多种退化甚至混合场景下实现稳健的恢复效果。
conclusion: 视觉引导的退化扩散为通用图像恢复提供了新范式。
---

## Abstract
Image restoration tasks like deblurring, denoising, and dehazing usually need distinct models for each degradation type, restricting their generalization in real-world scenarios with mixed or unknown degradations. In this work, we propose Defusion, a novel all-in-one image restoration framework that utilizes visual instruction-guided degradation diffusion. Unlike existing methods that rely on task-specific models or ambiguous text-based priors, Defusion constructs explicit visual instructions that align with the visual degradation patterns. These instructions are grounded by applying degradations to standardized visual elements, capturing intrinsic degradation features while agnostic to image semantics. Defusion then uses these visual instructions to guide a diffusion-based model that operates directly in the degradation space, where it reconstructs high-quality images by denoising the degradation effects with enhanced stability and generalizability. Comprehensive experiments demonstrate that Defusion outperforms state-of-the-art methods across diverse image restoration tasks, including complex and real-world degradations.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- 图像恢复（去模糊、去噪、去雾等）的传统深度学习方法通常需要为每种退化类型单独训练一个模型，难以泛化到现实中常见的混合退化或未知退化场景。
- 近年来的“全能”（all-in-one）方法尝试统一处理多种退化，但大多依赖隐式先验（如学习型提示、任务特定子网络）或显式文本先验。文本先验存在语言歧义、与低级视觉结构对齐弱的问题，往往退化为简单的类别标签，无法准确描述退化的精细视觉效应。
- 因此，论文提出 **Defusion**，核心思想是**让“视觉”来描述“视觉”**：通过构建**视觉指令**，将退化效应以可视化的方式直接展示给模型，指导扩散模型在**退化空间**中进行去噪恢复，从而实现一个模型统一处理多种退化。

### 2. 论文提出的方法论
- **视觉指令构建**：
  - 定义**视觉底图**：从标准测试图（如 TE42）中按组随机选取基本视觉元素（同心纹理、随机纹理、自然纹理、颜色块）组合而成，与图像语义无关。
  - **退化接地**：对视觉底图施加与低质量输入图像相同的退化过程，生成含退化效应但语义纯净的视觉指令。
  - **退化标记化**：利用基于 VQ-VAE 的量化自编码器（编码器 E、码本 Z、解码器 D）将视觉指令压缩为离散退化编码。训练时同时优化重建损失（MSE + LPIPS 感知损失）与对抗损失，并在 10% 概率下用干净底图替换视觉指令。推理时，用编码器提取退化编码，并减去干净底图的编码作为残差输入，增强辨别力。
- **退化扩散模型**：
  - 定义**退化空间**：Degradation Space \(D_v = \{x_{LQ} - T_v(x_{LQ})\}\)，其中 \(T_v\) 是在视觉指令 v 引导下的恢复映射，理想情况下当 v 描述全部退化时即为高质量图像。
  - 扩散模型直接对退化空间中的差异向量进行前向加噪和反向去噪，条件为低质量图像 \(x_{LQ}\) 和视觉指令 v，训练目标为标准去噪得分匹配。
  - 推理时求解反向 SDE，得预测的退化分量 \(\hat{y}_0\)，再恢复 \(\hat{T}_v(x_{LQ}) = x_{LQ} - \hat{y}_0\)。
- **条件注入机制**：
  - **图像恢复桥接**：用轻量卷积网络将低质量图像编码为多分辨率特征，通过 AdaLN-Zero 注入 U-Net（而非在输入端拼接）。
  - **视觉指令适配器**：复制 U-Net 的交叉注意力层，Query 为 U-Net 特征图，Key/Value 为视觉指令的退化编码，类似 IP-Adapter 方式，同时保留预训练文本-图像模型的文本条件能力。

### 3. 实验设计
- **训练数据**：混合多个基准数据集，覆盖去雨（Rain1400、Outdoor-Rain、LHP）、去雾（RESIDE、Dense-Haze）、去雪（Snow100K、RealSnow）、雨滴去除（RainDrop、RainDS）、真实去噪（SIDD）、运动去模糊（GoPro、RealBlur）、散焦去模糊（DPDD）等。
- **评估数据集**：
  - 合成/基准任务：GoPro、DPDD、Snow100K-L、Dense-Haze、RainDrop、Rain1400、SIDD、LIVE1（JPEG 压缩伪影）。
  - 真实世界数据：NH-HAZE、LHP（真实去雨）、RealBlur、RealSnow。
  - 混合退化：WED 数据集上复合叠加（雨、雪、噪声的不同顺序）。
  - 水下退化：EUVP、TURBID 数据集。
- **对比方法**：大量任务特定模型（MPRNet、Restormer、DiffIR 等）以及全能模型（AirNet、PromptIR、TransWeather、MPerceiver、NAFNet*、Restormer*、DA-CLIP 等）。所有全能模型均使用统一的训练集重新训练（标 * 号）以保证公平对比。
- **评价指标**：PSNR、SSIM（失真度），LPIPS（感知质量）。

### 4. 资源与算力
- 训练使用 **8 块 NVIDIA A100 GPU**。
- 训练 **100 个 epoch**，图像分辨率 **256×256**，采用混合数据集和随机裁剪，数据增广包括水平、垂直翻转。
- 优化器为 Adam（学习率 1e−4 至 1e−6 余弦退火），扩散采样采用 DDIM，推理时仅 4 个时间步。

### 5. 实验数量与充分性
- **主对比实验**：在 8 个标准去退化任务上比较（表 1），覆盖去模糊、去雾、去雨、去噪等，对比众多 SOTA 特定和全能方法，均展示了定量领先。
- **真实世界泛化**：在 4 个真实数据集上评估（表 2），结果显著优于对比的全能方法。
- **混合退化**：构造 6 种不同顺序的雨、雪、噪声复合失真（表 3），体现处理复杂混合退化的能力。
- **水下场景**：在 EUVP 和 TURBID 数据集上测试（表 4），进一步验证对特殊环境中复合退化的效果。
- **消融研究**：对关键设计（退化扩散 vs 朴素扩散、视觉底图类型、视觉指令 vs 文本指令 vs 无指令）进行对比（表 5），证实各组件贡献。
- 整体而言，实验设计覆盖广泛任务和场景，对比公平（重新训练基线），消融分析严谨，实验充分性较高。

### 6. 论文的主要结论与发现
- 视觉引导的退化扩散框架能够在单一模型中统一处理多种图像退化，性能全面超越现有全能方法，甚至在多个任务上优于任务特定模型。
- 视觉指令相比文本指令能更准确、直观地表达退化视觉模式，显著提升恢复质量。
- 在退化空间中进行扩散建模，增强了训练的稳定性和模型的可控性（指令不匹配时模型不做改动），且易于适配预训练模型。
- 方法对混合退化、真实世界退化和未见于训练集的退化复合场景均表现出强泛化能力。

### 7. 优点
- **创新的视觉指令**：通过视觉底图与退化接地，构建语义无关、退化对齐的视觉提示，解决了文本先验与低级视觉脱节的问题。
- **退化空间扩散**：直接在退化差异上建模，而非在图像或隐空间，更稳定、高效，且自然继承图像恢复桥接的条件设计。
- **统一且可扩展**：单一模型处理多类退化，无需任务特定模块或提示选择，对新退化具有一定泛化性。
- **实验全面扎实**：覆盖 8 个常规任务、4 个真实世界数据集、混合退化及水下场景，并进行了充分的对比与消融。

### 8. 不足与局限
- 视觉底图的构建依赖人工选定的标准图（TE42），其元素组合未必能覆盖所有潜在退化形态的视觉细节，尤其对于高度非标准的或未预见退化，可能仍需特定设计。
- 退化标记化采用 VQ-VAE 离散码本，存在量化误差和信息瓶颈，可能丢失微妙的退化纹理。
- 论文未讨论计算代价与推理效率的详细分析（尽管推理仅用 4 步 DDIM，但整体模型仍为扩散模型，相比轻量前馈网络可能较重）。
- 训练依赖大量合成退化数据及明确的退化参数，而真实世界中退化往往未知且多源耦合，构建对应的视觉指令底图可能受限。
- 未系统分析在单一极端退化（如极低光照）下与极专模型的差距，以及超分辨率等空间分辨率提升任务的适用性。

（完）
