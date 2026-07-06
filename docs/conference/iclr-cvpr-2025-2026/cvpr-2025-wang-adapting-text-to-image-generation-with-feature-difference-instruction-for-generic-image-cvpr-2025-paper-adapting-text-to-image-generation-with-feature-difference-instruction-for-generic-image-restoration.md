---
title: Adapting Text-to-Image Generation with Feature Difference Instruction for Generic Image Restoration
title_zh: 利用特征差异指令适配文本到图像生成以实现通用图像修复
authors: "Wang, Chao, Fan, Hehe, Yang, Huichen, Karimi, Sarvnaz, Yao, Lina, Yang, Yi"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_Adapting_Text-to-Image_Generation_with_Feature_Difference_Instruction_for_Generic_Image_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出基于视觉语言模型的特征差异指令，引导扩散文本到图像模型进行通用图像修复
tldr: 针对现有扩散模型图像修复训练复杂和提示设计困难的问题，提出从预训练视觉语言模型中提取特征差异指令(FDI)，通过多尺度FDI适配器注入文本到图像模型，以分离的退化与内容表示提供更好的退化引导，从而提升图像修复性能，为通用图像修复提供了新视角。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1805, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1749, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 879, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 911, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1756, \"height\": 1065, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-adapting-text-to-image-generation-with-feature-difference-instruction-for-generic-image-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 873, \"height\": 342, \"label\": \"Table\"}]"
motivation: 简化扩散模型图像修复的训练与提示设计，利用预训练视觉语言模型知识。
method: 从BLIP-2的参考图像对中通过Q-Former减法提取特征差异指令，并用多尺度适配器注入T2I模型。
result: 实验表明退化与内容表示可线性分离，所提方法提供了有效的退化引导。
conclusion: 注入视觉语言模型知识显著提升了扩散模型的自主退化处理能力。
---

## Abstract
Diffusion-based Text-to-Image (T2I) models have demonstrated significant potential in image restoration. However, existing models continue to grapple with challenges such as complex training and prompt design. We introduce a new perspective for improving image restoration by injecting knowledge from pretrained vision-language models into current T2I models. We empirically show that the degradation and content representations in BLIP-2 can be linearly separated, providing promising degradation guidance for image restoration. Specifically, the Feature Difference Instruction (FDI) is first extracted by Q-Formers through a simple subtraction operation based on reference image pairs. Then, we propose a multi-scale FDI adapter to decouple the degradation style and corrupted artifacts, and inject the styleflow exclusively into specific blocks through adapter-tuning, thereby preventing noise interference and eschewing the need for cumbersome weight retraining. In this way, we can train various task-specific adapters according to different degradations, achieving rich detail enhancement in the restoration results. Furthermore, the proposed FDI adapters have attractive properties of practical value, such as composability and generalization ability for all-in-one and mixed-degradation restoration. Extensive experiments under various settings demonstrate that our method has promising repairing quality over 10 image restoration tasks and a wide range of other applications.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：基于扩散的文本到图像（T2I）模型在图像修复中展现了巨大潜力，但现有方法仍面临训练流程复杂、提示设计困难，以及内容与退化信息在视觉嵌入中相互干扰等挑战。
- **整体含义**：本文提出一种全新视角——通过将预训练视觉–语言理解模型（如 BLIP-2）中的知识注入到预训练 T2I 模型（如 Stable Diffusion）中，来更高效、鲁棒地完成通用图像修复。其本质是利用**参考图像对的特征差**作为退化感知的修复指令，绕开繁琐的提示工程和全模型重训。

### 2. 论文提出的方法论

- **核心思想**  
  作者实证发现 BLIP-2 中，干净图像与退化图像的 Q-Former 输出特征在较大程度上是线性可分的。由此，可以直接用两者相减得到的 **特征差异指令（FDI）** 作为修复引导条件。

- **关键技术细节**
  - **FDI 提取**：给定退化图像集 \(S_{noisy}\) 和干净图像集 \(S_{clean}\)，通过冻结的 BLIP-2 计算  
    \[
    F = \text{Q-former}(\text{Encoder}(S_{noisy})) - \text{Q-former}(\text{Encoder}(S_{clean}))
    \]
  - **整体框架 DiffRes**：  
    - **反演重建**：利用 DDIM 反演将退化图像映射到潜在空间的噪声状态 \(z_T\)，保留内容结构。  
    - **FDI 适配器**：由噪声解耦、多级引导和视觉调制器三部分组成，所有可训练参数集中于此，不修改预训练扩散模型。  
      1. **噪声解耦**：将 FDI 作为 Query，与从输入图像提取的多尺度特征（Key, Value）做交叉注意力，强化退化相关部分，得到优化后的 \(\hat{F}_i^S\)。  
      2. **多级引导**：利用 \(\hat{F}_i^S\) 通过 SEBlock 生成通道注意力权重，与 U-Net 编码层的中间特征 \(E_i^S\) 直接相加，注入修复引导。  
      3. **视觉调制器**：在 U-Net 解码层，基于 \(\hat{F}_i^S\) 通过 AdaIN 进行特征正则化，鼓励输出分布接近干净图像。  
    - **退化分类器（可选）**：一个 MLP 多标签分类器，用于识别输入图像中的退化类型，支持**组合式**（多分支适配器加权融合）或**渐进式**（顺序应用适配器）混合退化恢复。

### 3. 实验设计

- **数据集与场景**  
  涵盖 10 种图像修复任务：去雨（Rain100H/L, Rain1400）、去雾（RESIDE-6K）、去雪（Snow100K）、雨滴去除（RainDrop）、低光增强（LOL-v1, MEF）、去噪（CBSD68, DIV2K）、运动去模糊（GoPro）、散焦去模糊（DPDD）、阴影去除（SRD）、JPEG 压缩伪影去除（LIVE1）。  
  混合退化实验使用 RainDS（雨滴+雨线）、NYU-Rain/OutDoor-Rain（雨线+雾+低光）及 BID 数据集。

- **Benchmark 与对比方法**  
  - **单任务对比**：MPRNet, MAXIM, IR-SDE, Restormer, DA-CLIP, PromptIR, DehazeFormer, Retinexformer 等各任务 SOTA 方法。  
  - **统一修复（all-in-one）对比**：DL, TransWeather, TAPE, AirNet, IDR, DA-CLIP, InstructIR-5D 等。  
  - **混合退化对比**：AirNet, TransWeather, PromptIR, Restormer, InstructIR-5D 等。

- **评估指标**：PSNR, SSIM, FID, LPIPS。

### 4. 资源与算力

- **环境**：实验在 4 块 NVIDIA A100 GPU 上进行。
- **训练配置**：总批次大小 32，使用 AdamW 优化器（\(\beta_1=0.9, \beta_2=0.99\)），学习率 \(1\times10^{-5}\)，训练 50 个 epoch。
- **效率**：训练一个 FDI 适配器约需 8 小时，适配器参数量 45M。推理时无需分类器（退化类型已知），可灵活选择复合或渐进策略。

### 5. 实验数量与充分性

- **实验组数**  
  - 9 个单任务定量对比表（表 1）。  
  - 5 任务 all-in-one 对比表（表 2）。  
  - 混合退化定量对比表（表 3）及额外的组合退化实验。  
  - 交叉数据集泛化分析（表 4、图 7）。  
  - 交叉任务兼容性观察。  
  - 渐进与复合恢复的消融对比（图 8）。  
  - 自身模块消融实验（表 5）：逐步添加噪声解耦、视觉调制器等，验证各组件贡献。  
  - 大量可视化对比（图 5、图 6）。

- **充分性与公平性**  
  实验覆盖了主流退化类型、单任务/多任务/混合退化、同域和跨域泛化，并与大量近年 SOTA 方法进行公平比较，使用了多维度指标。消融研究清晰展示了 FDI 适配器各部分的作用。实验设计全面、客观且充分。

### 6. 论文的主要结论与发现

- BLIP-2 中干净/退化图像的特征差具有线性可分性，可作为有效的修复指令（FDI），且能被 LLM 解释为文字退化描述。
- 提出的 FDI 适配器能够以低成本、插拔式的方式将退化感知引导注入冻结的预训练 T2I 模型，无需重训基座网络。
- DiffRes 在 10 个任务上取得了最优或次优性能，在 all-in-one 和混合退化恢复中均表现出色，验证了方法的有效性和通用性。
- FDI 适配器具备可组合性、跨任务兼容性和应用扩展潜力（如图像风格迁移）。

### 7. 优点

- **创新性强**：首次将预训练视觉–语言理解模型中线性可分的特征差作为退化指令，为图像修复提供了新的知识迁移范式。
- **高效轻量**：采用适配器微调，冻结基座模型，单适配器仅 45M 参数，训练仅需 8 小时，显著优于重训完整扩散模型的方法。
- **灵活且实用**：适配器可组合、可替换，支持复合与渐进混合退化恢复，并可“即插即用”，不影响原始 T2I 模型。
- **修复质量高**：结合 DDIM 反演的内容注入与 FDI 的退化引导，在去除噪声、补全遮挡区域等方面表现出色，视觉结果清晰。
- **鲁棒性**：通过噪声解耦和视觉调制器缓解了 FDI 中残留的无关联噪声和伪影，提升了稳定性。

### 8. 不足与局限

- **对参考数据集的依赖**：训练和测试时都需要根据相应任务准备干净–退化图像对来提取平均 FDI，对于退化未知的真实场景可能需要重新收集配对数据。
- **混合退化处理复杂度**：虽然实现了多退化处理，但需要额外训练退化分类器和多个适配器，渐进式策略的多次推理也会增加计算开销。
- **跨域泛化限制**：跨数据集 FDI 效果受数据集特性影响（如雨况模拟的真实性），泛化能力仍受限于训练源的分布覆盖。
- **严重退化的挑战**：当退化严重遮挡内容时，BLIP-2 特征差可能仍包含噪声，噪声解耦效果有上限。
- **任务偏向性**：方法更适合退化效应能显著改变语义的噪声类型（如恶劣天气），对于细微噪声（如低强度 JPEG 压缩）的优势不如其他类型明显。
- **未深入探讨的边界**：论文对超出 10 种任务之外的新型退化、极端低分辨率输入等场景的试验较少，可扩展性尚需进一步验证。

（完）
