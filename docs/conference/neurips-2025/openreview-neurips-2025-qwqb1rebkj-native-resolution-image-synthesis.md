---
title: Native-Resolution Image Synthesis
title_zh: 原生分辨率图像合成
authors: "ZiDong Wang, LEI BAI, Xiangyu Yue, Wanli Ouyang, Yiyuan Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QWQB1ReBkJ"
tags: ["query:real-ir"]
score: 8.0
evidence: 原生分辨率扩散图像合成
tldr: 标准图像生成受限于固定分辨率，NiT通过显式建模不同分辨率和宽高比的扩散过程，实现原生分辨率生成。在一个模型中同时取得ImageNet 256x256和512x512的SOTA，展示了从低分辨率到高分辨率的一致高质量生成能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 现有生成模型只能处理固定分辨率，无法适应任意分辨率和宽高比。
method: 提出NiT架构，在扩散过程中引入分辨率/宽高比条件，处理变长视觉token。
result: 单一模型在多个分辨率上均达SOTA，尤其512分辨率表现突出。
conclusion: NiT打破了分辨率限制，为灵活图像生成开辟了新方向。
---

## Abstract
We introduce native-resolution image synthesis, a novel paradigm in generative modeling capable of synthesizing images at arbitrary resolutions and aspect ratios. This approach overcomes the limitations of standard fixed-resolution, square-image methods by inherently handling variable-length visual tokens—a core challenge for conventional techniques. To this end, we propose the Native-resolution diffusion Transformer (NiT), an architecture that explicitly models varying resolutions and aspect ratios within its denoising process. Unconstrained by fixed formats, NiT learns intrinsic visual distributions from images encompassing a wide range of resolutions and aspect ratios. Notably, a single NiT model simultaneously achieves the state-of-the-art performance on both ImageNet-256x256 and 512x512 benchmarks. Surprisingly, akin to the robust zero-shot capabilities seen in advanced Large Language Models, NiT, pretrained solely on ImageNet, demonstrates excellent zero-shot generalization performance. It successfully generates high-fidelity images at previously unseen high resolutions (e.g., 1024x1024, 1536x1536) and diverse aspect ratios (e.g., 16:9,3:1, 4:3), as shown in Figure 1. These findings indicate the significant potential of native-resolution modeling as a bridge between visual generative modeling and advanced LLM methodologies.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
当前主流的图像生成扩散模型（如DiT、SiT）通常要求将输入图像统一调整为固定尺寸（如256×256或512×512），这会导致以下问题：
- **空间结构与语义退化**：缩放和裁剪操作丢失原始图像的细节、宽高比信息，影响生成质量。
- **分辨率泛化能力受限**：模型仅能生成训练时见过的固定分辨率图像，无法泛化到未见过的分辨率或宽高比。
- **数据利用效率低**：标准化处理抛弃了原始图像固有的尺度多样性，使得为不同分辨率需训练独立模型，累积计算成本高。

本文受大语言模型（LLM）处理变长文本的启发，提出**原生分辨率图像合成**（Native-Resolution Image Synthesis）范式，目标是让扩散模型能直接生成任意分辨率和宽高比的图像，从而突破固定尺寸的束缚，提升模型的灵活性和零样本泛化能力。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将图像生成视为变长视觉token序列的生成过程，依赖分辨率和宽高比信息。提出**Native-resolution diffusion Transformer（NiT）**，在去噪过程中显式建模不同分辨率和宽高比。
- **关键技术细节**：
  - **动态Token化**：原始分辨率图像经图像自动编码器（DC-AE，32×下采样，32维潜在空间）压缩为变长潜在序列，根据原始高度和宽度确定token数量，无需填充。
  - **变长序列处理**：采用**Packed Full-Attention**（基于FlashAttention-2）高效处理多个变长序列拼接成的打包序列，通过累积序列长度（CuSeqLens）限制注意力计算在各自实例内部。
  - **2D结构先验注入**：引入**轴向2D Rotary Positional Embedding（2D RoPE）**，解耦高度和宽度影响，通过相对位置编码为每个token提供二维位置感知，增强对不同分辨率和宽高比的适应能力。
  - **Packed Adaptive Layer Normalization**：对打包序列中的每个实例，利用其独有的条件嵌入（如类别标签）生成调制参数，广播作用于对应token子序列，确保条件控制一致。
  - **训练策略**：采用Flow Matching（线性路径）和Logit-Normal时间分布。使用**token budget**（如每迭代131,072个token）代替固定batch size，类似LLM训练方式。

### 3. 实验设计：数据集、Benchmark与对比方法
- **数据集**：主要用于ImageNet（1,000类）的class-guided图像生成；文本到图像生成实验使用SAM数据集（带有MiniCPM-V生成的字幕），并在COCO-val-2014上评估零样本性能。
- **基准测试**：
  - 标准基准：ImageNet 256×256和512×512。
  - 高分辨率泛化：768×768、1024×1024、1536×1536、2048×2048。
  - 宽高比泛化：1:3（320×960）、9:16（416×768）、3:4（480×640）、4:3（640×480）、16:9（768×416）、3:1（960×320）。
- **对比方法**：
  - 自回归模型：MaskGit、LlamaGen、VAR、ST-AR等。
  - 扩散模型：DiT、SiT、FlowDCN、FiTv2、SiT-REPA、EDM2、PixNerd等，其中大部分需要为不同分辨率训练独立模型。
- **评估指标**：FID、sFID、Inception Score、Precision、Recall（使用ADM评估套件）。

### 4. 资源与算力
论文未明确给出GPU型号和数量等信息。但在效率分析中提到：使用单张NVIDIA A100 GPU比较NiT-B和DiT-B，设置每迭代token数为65,536。NiT训练速度为1.28 iter/s，推理延迟0.246秒；DiT分别为1.08 iter/s和0.322秒。对于主要实验，NiT-XL模型训练了1000K步（对应131B token预算）。文本到图像模型训练400K步。总体训练代价相比多个独立模型累积更低。

### 5. 实验数量与充分性
- **实验数量**：非常充分。包括：
  - 标准基准对比（表1）
  - 分辨率泛化对比（表2）
  - 宽高比泛化对比（表3）
  - 6组消融实验：数据混合方式（a-f）对泛化的影响（表4-5）
  - 位置编码消融（表6）
  - 文本到图像生成结果（表7）
  - 大量可视化对比（附录D）
- **充分性评价**：实验设计全面，涵盖了多种分辨率、宽高比以及消融分析。对比方法均为当前SOTA，评估指标标准。消融实验揭示了原生分辨率训练的关键作用。实验公平、客观。

### 6. 论文的主要结论与发现
- NiT是首个单一模型同时在ImageNet 256×256和512×512基准上达到SOTA的扩散模型（512×512 FID=1.45，超越EDM2-XXL；256×256 FID=2.03）。
- 具有出色的零样本泛化能力：在未见过的1024×1024上FID=4.52，在9:16宽高比上FID=4.11，显著优于所有对比方法。
- 原生分辨率训练是泛化能力的关键，仅使用固定分辨率训练会严重削弱泛化；结合多种自然分辨率（尤其是原生分辨率）能获得最佳泛化。
- 2D RoPE比传统正弦-余弦位置编码更有利于跨分辨率建模。

### 7. 优点
- **创新性**：将变长序列处理与扩散Transformer结合，实现真正的原生分辨率生成，弥合了视觉生成与LLM灵活性之间的鸿沟。
- **高效性**：单一模型覆盖多分辨率，避免为每个分辨率训练独立模型，降低总训练成本。
- **泛化能力强**：在未见过的极高分辨率和极端宽高比上仍能生成高保真图像，远超现有方法。
- **技术细节完善**：Packed Full-Attention、2D RoPE、Packed AdaLN等设计既保证效率又保持结构先验。
- **实验充分**：提供了大量定量和定性结果，消融实验严谨，结论可信。

### 8. 不足与局限
- **极端情况性能不足**：论文本身承认在极高分辨率（2048×2048）和极端宽高比（如1:5）上的泛化还不理想（2048×2048 FID=24.76，仍较高）。
- **计算成本**：尽管比多个独立模型更高效，但训练NiT-XL仍需要大量算力（131B token），对资源有限的研究者可能不友好。
- **领域局限性**：实验仅基于ImageNet（类条件生成）和部分文本到图像数据，在更广泛领域（如视频生成、真实场景多分辨率数据集）未验证。
- **依赖于高性能图像编码器**：使用DC-AE（32×下采样），其质量和压缩率影响最终生成效果。
- **潜在偏差风险**：虽然避免了图像裁剪导致的偏差，但训练数据本身的分布（ImageNet中多为中等尺寸图像）仍可能影响泛化。

（完）
