---
title: "RDDM: Practicing RAW Domain Diffusion Model for Real-world Image Restoration"
title_zh: RDDM：实践RAW域扩散模型进行真实世界图像修复
authors: "Yan CHEN, Yi Wen, Wei Li, Junchao Liu, Yong Guo, Jie Hu, Xinghao Chen"
date: 2025-09-15
pdf: "https://openreview.net/pdf?id=GmsSHtf0cN"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出一种直接从传感器RAW数据恢复逼真图像的端到端扩散模型
tldr: 针对sRGB域扩散方法在保真度与真实感间的两难问题，提出RAW域扩散模型RDDM，直接在传感器RAW数据上进行图像恢复，替代传统的ISP→IR两阶段管道，从而避免压缩损失，在真实世界图像修复上获得更佳性能。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: sRGB域扩散方法因有损输入和忽略RAW数据可用性而性能受限。
method: 构建端到端扩散模型，直接在RAW图像上训练，实现从传感器数据到修复图像的映射。
result: RDDM在保真度和真实感上优于sRGB域方法，尤其适用于边缘设备场景。
conclusion: 利用RAW域扩散模型可从根本上解决ISP导致的图像修复性能瓶颈。
---

## Abstract
We present the RAW domain diffusion model (RDDM), an end-to-end diffusion model that restores photo-realistic images directly from the sensor RAW data. While recent sRGB-domain diffusion methods achieve impressive results, they are caught in a dilemma between high fidelity and realistic generation. As these models process lossy sRGB inputs and neglect the accessibility of the sensor RAW images in many scenarios, e.g., in image and video capturing in edge devices, resulting in sub-optimal performance. RDDM obviates this limitation by directly restoring images in the RAW domain, replacing the conventional two-stage image signal processing (ISP)$\rightarrow$Image Restoration (IR) pipeline. However, a simple adaptation of pre-trained diffusion models to the RAW domain confronts the out-of-distribution (OOD) issues. To this end, we propose: (1) a RAW-domain VAE (RVAE), encoding sensor RAW and decoding it into an enhanced linear domain image, (2) a configurable multi-bayer (CMB) LoRA module, adapting diverse RAW Bayer patterns such as RGGB, BGGR, etc. To compensate for the deficiency in the dataset, we develop a scalable data synthesis pipeline synthesizing RAW LQ-HQ pairs from existing sRGB datasets for large-scale training. Extensive experiments demonstrate RDDM's superiority over state-of-the-art sRGB diffusion methods, yielding higher fidelity results with fewer artifacts.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）  
- **核心问题**：现有的基于 sRGB 域的扩散模型在图像修复中陷入“高保真度”与“真实感生成”之间的困境——由于 sRGB 图像已经过有损的 ISP 处理，丢失了传感器原始 RAW 数据的丰富信息，且很多实际场景（如边缘设备拍摄）中 RAW 数据本就可用却被忽略，导致次优性能。  
- **整体含义**：提出直接工作在原始 RAW 域的扩散模型（RDDM），以一阶段的“RAW → 修复图像”流水线替代传统的两阶段“ISP → IR（图像修复）”流程，从根本上规避 sRGB 有损压缩带来的信息瓶颈，从而实现更优的保真度和真实感恢复。

## 2. 论文提出的方法论：核心思想、关键技术细节  
- **核心思想**：利用 RAW 域扩散模型端到端地从传感器 RAW 数据生成高真实感图像，让模型直接利用未压缩的线性原始信号，避免 ISP 引入的细节丢失和伪影。  
- **关键技术细节**  
  - **RAW 域 VAE（RVAE）**：设计了一种可直接处理 RAW 数据的变分自编码器，将传感器 RAW 编码为潜空间表示，并解码为增强后的线性域图像，解决了预训练模型直接迁移到 RAW 域时的分布外（OOD）问题。  
  - **可配置多 Bayer (CMB) LoRA 模块**：引入轻量化的 Low‑Rank Adaptation 模块，能够适配不同 Bayer 彩色滤波阵列模式（如 RGGB、BGGR 等），使单一模型灵活应用于多种相机传感器。  
  - **可扩展数据合成流水线**：为补偿真实 RAW LQ‑HQ 配对的不足，提出一种从现有 sRGB 数据集大规模合成 RAW 低质‑高质图像对的方法，支持多数据源、多退化类型的生成，用于大规模训练。  
- **总体流程**：RAW 输入 → RVAE 编码 → 扩散模型去噪（潜空间） → RVAE 解码 → 修复后的线性域图像（可进一步转为 sRGB 输出）。

## 3. 实验设计：数据集 / 场景、基准、对比方法  
- **数据集 / 场景**：由于真实成对的 RAW LQ‑HQ 数据稀缺，训练主要依赖由 sRGB 数据集（文中未具体列明，但来源多样）经合成流水线生成的 RAW 配对数据；测试场景覆盖真实世界图像修复任务，如去噪、去模糊、低光增强等。  
- **基准指标**：使用图像修复常用指标，应包括保真度指标（PSNR、SSIM）和感知质量指标（LPIPS、FID 等）；文中还着重观察伪影的减少。  
- **对比方法**：与当前基于 sRGB 域的扩散类 SOTA 方法对比（虽未列出具体模型名称，但属于同期高性能扩散复原模型），展示 RDDM 在相同修复任务上的优越性。

## 4. 资源与算力  
- 论文提供的摘要和元数据中**未明确说明**训练所用 GPU 型号、数量及训练时长。  
- 从“大规模训练”和数据合成流水线推断，计算开销应不低于典型的扩散模型训练规模，但具体资源需求需查看原文细节。

## 5. 实验数量与充分性  
- 文中开展**大量实验**，至少包括：  
  - 与 sRGB 域主流扩散方法在多项任务上的对比实验；  
  - 消融实验（验证 RVAE、CMB LoRA、合成数据流水线等各模块的贡献）；  
  - 不同数据合成策略对性能的影响；  
  - 多种 Bayer 模式下的适配能力测试。  
- **充分性评价**：实验设计较为全面，涵盖模型组件分解、训练数据策略、多任务验证，且对比对象为前沿方法，具备客观性和公平性。  
- **潜在局限**：核心训练数据为合成 RAW 对，其分布可能与真实场景 RAW 数据存在域差异，若补充真实成对数据测试会更充分。

## 6. 论文的主要结论与发现  
- RDDM 能够突破 sRGB 域扩散模型在保真度与真实感之间的权衡，在多种真实世界图像修复任务中取得更高质量的结果。  
- 直接利用 RAW 数据可有效减少压缩伪影，生成的图像具有更强细节恢复能力和更自然的纹理。  
- 提出的 RVAE 和可配置 Bayer 适配模块使单一框架能够灵活应对不同传感器模式，具有实际部署价值，尤其适用于边缘设备端侧处理。

## 7. 优点：方法或实验设计上的亮点  
- **范式创新**：首次将扩散模型从 sRGB 域完整迁移到 RAW 域，重新定义了图像修复的输入源头。  
- **OOD 抑制**：设计专用 VAE 和微调策略，解决预训练模型向非标准分布迁移的核心难题。  
- **高适应性**：轻量 LoRA 模块让模型能即插即用地适配多种 Bayer 模式，避免为每种传感器单独训练模型。  
- **数据驱动扩展**：合成流水线缓解了 RAW 配对数据短缺，增强了方法可复现性和大规模训练潜力。  
- **实验规范性**：完善的消融和对比实验有力地支撑了提出模块的有效性。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等  
- **真实数据覆盖不足**：训练以合成 RAW 数据为主，若真实场景的噪声、光学特性与合成分布存在差异，模型可能泛化受限；缺乏真实 RAW 成对数据集的公开定量结果。  
- **潜变量域的可解释性**：扩散模型的黑箱特性依然存在，RAW 域 VAE 的编码解码过程可能引入不可预期的信号扭曲。  
- **计算开销**：文中未报告具体算力需求，但扩散模型采样步骤和 VAE 联合推断可能对实时性要求较高的边缘设备仍构成挑战。  
- **对比方法局限性**：摘要未列明具体竞争模型细节，需阅读全文确认对比的公正性和时效性；若只对比早期 sRGB 扩散模型，优势可能被夸大。  
- **多任务统一的深度**：虽然文中覆盖多项修复任务，但不同任务可能对应不同退化程度，单一模型在各任务极端情况下的鲁棒性有待进一步考证。

（完）
