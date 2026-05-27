---
title: "Dimension-Reduction Attack! Video Generative Models are Experts on Controllable Image Synthesis"
title_zh: 降维攻击！视频生成模型是可控制的图像合成专家
authors: "Hengyuan Cao, Yutong Feng, Biao Gong, Yijing Tian, Yunhong Lu, Chuang Liu, Bin Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=L1m5124sNQ"
tags: ["query:real-ir"]
score: 7.0
evidence: 利用视频生成模型进行可控图像合成
tldr: 视频生成模型蕴含丰富的动态先验。本文提出降维攻击（DRA-Ctrl）范式，将视频模型知识压缩至可控图像生成任务，通过时空维度约简实现精确控制。实验证明该方法在图像编辑任务中表现优异，拓展了视频模型的应用边界。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1457, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 433, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 439, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1456, \"height\": 968, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1455, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1454, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1448, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1456, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1454, \"height\": 159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1451, \"height\": 164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1447, \"height\": 156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1449, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l1m5124snq/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 590, \"height\": 360, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1349, \"height\": 1089, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 906, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 635, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 662, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 704, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 781, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l1m5124snq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 793, \"height\": 306, \"label\": \"Table\"}]"
motivation: 探索视频生成模型在低维可控图像生成任务中的迁移潜力。
method: 提出视频到图像的知识压缩与任务自适应框架，实现降维控制。
result: 在可控图像合成任务中达到与专用模型相当的性能。
conclusion: 视频生成模型可作为可控图像合成的有效基础。
---

## Abstract
Video generative models can be regarded as world simulators due to their ability to capture dynamic, continuous changes inherent in real-world environments. These models integrate high-dimensional information across visual, temporal, spatial, and causal dimensions, enabling predictions of subjects in various status. A natural and valuable research direction is to explore whether a fully trained video generative model in high-dimensional space can effectively support lower-dimensional tasks such as controllable image generation. In this work, we propose a paradigm for video-to-image knowledge compression and task adaptation, termed \textit{Dimension-Reduction Attack} (\texttt{DRA-Ctrl}), which utilizes the strengths of video models, including long-range context modeling and flatten full-attention, to perform various generation tasks. Specially, to address the challenging gap between continuous video frames and discrete image generation, we introduce a mixup-based transition strategy that ensures smooth adaptation. Moreover, we redesign the attention structure with a tailored masking mechanism to better align text prompts with image-level control. Experiments across diverse image generation tasks, such as subject-driven and spatially conditioned generation, show that repurposed video models outperform those trained directly on images. These results highlight the untapped potential of large-scale video generators for broader visual applications. \texttt{DRA-Ctrl} provides new insights into reusing resource-intensive video models and lays foundation for future unified generative models across visual modalities. The project page is \url{https://dra-ctrl-2025.github.io/DRA-Ctrl/}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：视频生成模型（如 HunyuanVideo-I2V）具备丰富的时空、因果与动态先验，能够模拟连续世界变化。现有可控图像生成方法大多基于图像生成模型，受限于图像数据的静态性。本文旨在探索：**能否将视频生成模型的高维知识压缩并迁移至低维可控图像生成任务**，实现“降维攻击”（Dimension-Rduction Attack）。
- **核心问题**：视频帧是连续平滑变化的，而可控图像生成需要处理条件图像与目标图像之间的离散、突变转换，直接使用两帧视频方式会导致模型过约束（I2V）或缺乏一致性（T2V），性能不佳。
- **整体含义**：提出 DRA-Ctrl 框架，通过设计过渡策略和注意力机制，使视频模型能有效完成多种可控图像生成任务，且效果优于基于图像模型的专用方法，为复用昂贵视频生成模型开辟新路径。

## 2. 方法论
- **核心思想**：以视频模型（HunyuanVideo-I2V）为基础，将条件图像与目标图像作为“镜头转场”的起止帧，通过中间帧插值实现平滑过渡，再微调模型使之学会从条件帧生成目标帧。
- **关键技术细节**：
  - **Mixup-based Shot Transition**：构造过渡帧序列 $F_\alpha$，使用公式 $F_\alpha = ((1-\beta) F_{\alpha=0}^\gamma + \beta F_{\alpha=1}^\gamma)^{1/\gamma}$，其中 $\beta = \alpha^2(3-2\alpha)$，$\gamma=2.2$。条件帧 $F_{\alpha=0}$ 保持无噪声且不参与损失计算，中间帧和目标帧 $F_{0<\alpha \le 1}$ 加入噪声并计算损失。损失权重 $w(k)$ 根据目标图像占比自适应调整。
  - **Frame Skip Position Embedding (FSPE)**：在 RoPE 的时间维度引入跳变间隔 $\delta$，使得少量潜在帧（如4帧）能模拟大量像素帧（如37帧），大幅减少计算开销。
  - **Attention Masking Strategy**：设计注意力掩码阻止条件图像与目标图像提示之间的信息混合，同时增强目标图像令牌与目标提示之间的交互（添加偏移量 $\omega=0.6$ 的均值）。
- **算法流程**：训练时，将条件图像和 $K$ 个过渡帧及目标图像编码为潜在表示，输入 Transformer，采用统一全注意力机制。损失函数为 flow matching 损失，仅对目标图像和过渡帧计算梯度。推理时，条件帧令牌保持无噪声，其余为高斯噪声，逐步去噪后解码最后一个潜在帧得到输出。

## 3. 实验设计
- **数据集与场景**：
  - **空间对齐生成**：使用 Text-to-Image-2M 子集（约160K样本），测试集为 COCO2017 验证集（5000张图像，分辨率 512×512）。子任务：canny→图像、depth→图像、图像颜色化、图像去模糊、图像内/外补全。
  - **主体驱动生成**：使用 Subjects200K 高质量子集（约110K图像对），测试集为 DreamBench（30个主体，每个25个提示）。
  - **风格迁移**：用 GPT-4o 生成100对原图→Bitmoji 风格图像进行微调。
- **对比方法**：
  - 空间对齐：ControlNet (SD1.5/FLUX.1)、T2I-Adapter、Uni-ControlNet、OminiControl、EasyControl。
  - 主体驱动：Textual Inversion、DreamBooth、BLIP-Diffusion、ELITE、Re-Imagen、BootPIG、SSR-Encoder、OmniGen、OminiControl、FLUX.1 IP-Adapter、MS-Diffusion、UniReal、UNO 等。
- **评价指标**：
  - 可控性：canny 用 F1 分数，其他用 MSE。
  - 生成质量：FID、SSIM。
  - 主体一致性：DINO、CLIP-I。
  - 提示遵循性：CLIP-T、VL Score（基于 QWen2.5-VL 的0-4评分，综合主体一致性和提示遵循性）。

## 4. 资源与算力
- **硬件**：
  - 空间对齐任务：2×NVIDIA H800 GPU（80GB）。
  - 主体驱动任务：4×NVIDIA H800 GPU。
  - 风格迁移：1 NVIDIA H800 GPU。
- **训练配置**：使用 LoRA（rank=16），AdamW 优化器，有效 batch size 16（空间对齐）/ 经梯度累积后的配置（主体驱动未明确说明 batch size，但提到使用4卡，步数9000）。
- **训练步数**：空间对齐 6000 步；主体驱动 9000 步；风格迁移 2600 步。
- **推理**：50步采样，分辨率 512×512。

## 5. 实验数量与充分性
- **实验组数**：
  - 空间对齐：5个子任务（canny, depth, colorization, deblur, mask）。
  - 主体驱动：1个标准 benchmark（DreamBench），并使用新提出的 VL Score。
  - 风格迁移：1个验证。
  - 消融实验：包含 **4类**消融——
    1. T2V/I2V 基线对比。
    2. 不同过渡类型（fade-in-fade-out vs slide-away）。
    3. 过渡帧数（4, 8, 12）影响。
    4. 模块消融（去掉 loss reweighting、FSPE、mixup、attention masking）。
  - 效率分析：与 I2V 基线及直接视频生成对比。
- **充分性评价**：
  - 实验覆盖 **多种任务类型**（空间条件、主体驱动、风格迁移），对比方法全面。
  - 消融实验设计合理，验证了每个提出模块的有效性。
  - 引入 VL Score 弥补传统指标缺陷，评价更客观。
  - 不足之处：训练使用子数据集（160K/110K），规模相对较小；DreamBench 是标准但较老 benchmark；对更复杂场景（如多主体、高分辨率）未测试。

## 6. 主要结论与发现
- **核心结论**：视频生成模型通过合理的降维改编（过渡策略+注意力掩码）可以在可控图像生成任务上 **显著优于** 基于图像模型的专用方法，尤其在 **主体一致性和可控性** 指标上表现突出。
- **具体发现**：
  - 直接使用 T2V/I2V 基线会导致过一致或过变化，mixup 过渡能平衡两者。
  - FSPE 用少量帧模拟长距离变换，节省计算且保持效果。
  - 注意力掩码能有效分离不同来源的信息，增强提示遵循性。
  - 8帧转移效果最好，过多或过少均有害。
  - 生成效率：DRA-Ctrl 比直接生成145帧视频快90.4%，同时获得更高 VL Score。

## 7. 优点
- **方法创新性**：首次提出利用视频模型处理离散图像生成任务，提出“镜头转场”视角，设计 mixup 过渡桥接连续-离散差距。
- **技术细节精巧**：FSPE 以极低成本扩大时间跨度；注意力掩码精细设计防止信息混淆并增强目标提示控制。
- **实验全面性**：覆盖多个可控生成场景，消融实验完整，引入 VL Score 解决传统指标不足。
- **性能优势**：在主体一致性和空间可控性上取得 SOTA，且效率较高。
- **社会影响考量**：论文末讨论了正负面影响和 safeguards，体现负责任 AI 态度。

## 8. 不足与局限
- **图像质量指标略低**：在 FID、SSIM 上不如某些专用图像模型（如 FLUX.1 ControlNet），因为视频模型未针对图像生成优化。
- **CLIP-T 分数偏低**：由于基模型（HunyuanVideo-I2V）使用 LLaVA 进行文本理解，与纯文本 CLIP 不直接对齐，导致提示遵循性指标较低。
- **生成效率仍受过渡帧拖累**：尽管 FSPE 减少帧数，但相比直接图像模型仍需要多步去噪，推理速度慢（约24秒/图，表7）。
- **特定任务失败案例**：在图像到深度任务中偶尔产生彩色区域，因为视频模型擅长生成彩色数据。
- **训练数据规模有限**：空间对齐仅用160K样本，主体驱动110K样本，可能限制泛化能力。
- **未测试超分辨率等多个常见任务**：虽在附录中提到了超分辨率，但定量评估未包含。
- **伦理风险**：可控生成可能被用于生成虚假图像，论文虽提出 safeguards，但实际部署仍需更严格限制。

（完）
