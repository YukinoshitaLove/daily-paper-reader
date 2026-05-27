---
title: Towards Reliable Identification of Diffusion-based Image Manipulations
title_zh: 面向可靠识别基于扩散模型的图像操作
authors: "Alex Costanzino, Woody Bayliss, Juil Sock, Marc Gorriz Blanch, Danijela Horak, Ivan Laptev, Philip Torr, Fabio Pizzati"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ciEdnQ0bLn"
tags: ["query:real-ir"]
score: 6.0
evidence: 检测基于扩散模型的图像操作
tldr: 扩散模型图像编辑工具易被滥用，需可靠检测方法。本文提出RADAR，利用基础模型的多模态特征和辅助对比损失，精确识别被修复区域。实验结果表明该方法在多种编辑类型上显著提升检测准确率，保障图像真实性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1344, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1422, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1420, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1416, \"height\": 1659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1419, \"height\": 1656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 2207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ciednq0bln/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1427, \"height\": 1132, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 655, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 523, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1444, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1444, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ciednq0bln/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 722, \"height\": 457, \"label\": \"Table\"}]"
motivation: 应对扩散模型图像编辑工具被滥用的安全挑战。
method: 结合基础模型多模态特征与对比损失，识别被修复区域。
result: 显著提高图像编辑区域的检测精度。
conclusion: 为扩散模型编辑的图像伪造检测提供了有效方案。
---

## Abstract
Changing facial expressions, gestures, or background details may dramatically alter the meaning conveyed by an image. 
Notably, recent advances in diffusion models greatly improve the quality of image manipulation while also opening the door to misuse. 
Identifying changes made to authentic images, thus, becomes an important task, constantly challenged by new diffusion-based editing tools.
To this end, we propose a novel approach for ReliAble iDentification of inpainted AReas (RADAR).
RADAR builds on existing foundation models and combines features from different image modalities.
It also incorporates an auxiliary contrastive loss that helps to isolate manipulated image patches.
We demonstrate these techniques to significantly improve both the accuracy of our method and its generalisation to a large number of diffusion models.
To support realistic evaluation, we further introduce BBC-PAIR, a new comprehensive benchmark, with images tampered by 28 diffusion models. 
Our experiments show that RADAR achieves excellent results, outperforming the state-of-the-art in detecting and localising image edits made by both seen and unseen diffusion models. 
Further information about our code, data and models, including separate licensing terms, will be publicly available at https://alex-costanzino.github.io/radar/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：扩散模型（如 Stable Diffusion、FLUX 等）使图像编辑变得极其容易和逼真，但同时也被恶意利用进行虚假信息传播、证据篡改等。现有 Image Forgery Detection and Localisation (IFDL) 方法主要针对传统 Photoshop 类操作（如 copy-move、splicing），对扩散模型操作的泛化能力严重不足。尤其是当训练时仅使用单一扩散模型，在面对其他扩散模型生成的篡改图像时性能急剧下降。
- **论文目标**：提出一种专门针对扩散模型图像修补 (inpainting) 操作的可靠检测与定位方法，既要在已知模型上表现优异，也要能泛化到未见过的扩散模型。

## 2. 方法论
### 核心思想
- **RADAR（ReliAble iDentification of inpainted AReas）**：利用多个预训练基础模型提取互补的多模态特征（语义 + 几何），通过交叉注意力融合，再结合 patch 级对比学习增强跨扩散模型的泛化能力。

### 关键技术细节
1. **数据生成流水线**（图1）：
   - 对原始图像，使用 Kosmos-2 提取物体列表和场景描述；随机选择一个物体，用 Grounded SAM 生成精细掩膜；用多个扩散修补器（共 K 个）以原图、掩膜和场景描述为输入，生成篡改图像。
   - 同时随机生成多边形掩膜以减少语义偏差。
2. **多模态特征提取**（图2）：
   - **语义编码器 ES**：DINO-v2 ViT-B/14，提取语义丰富的 patch 特征。
   - **几何编码器 EG**：Depth Anything V2 ViT-B/14，提取结构/深度相关的 patch 特征。
   - 两个编码器共享 Transformer 架构，保持特征空间兼容性。
3. **融合模块（Fusion Block）**：
   - 使用对称交叉注意力：语义特征以几何特征的 Key 做注意力，几何特征以语义特征的 Key 做注意力，得到 f′S 和 f′G。
   - 每个 patch 对通过一个共享的 patch-wise MLP 融合得到最终多模态特征 fM。
4. **定位头**：由卷积 + sigmoid 组成，将多模态特征映射为像素级篡改概率图。
5. **Patch 级对比学习**（图3）：
   - 将 batch 内的 patch 分为三类：original（原始图像中的 patch）、tampered（篡改图像中与掩膜重叠的 patch）、affected（篡改图像中与掩膜不重叠的 patch）。
   - 通过投影头 γ 得到嵌入 z，施加 supervised contrastive loss (L_SCL)，使同一分布内的 patch 特征聚集，不同分布间远离。
   - 这种设计有助于模型关注跨扩散模型的共同特征，提升泛化性。
6. **训练损失**：总损失 L = L_SCL + Σ L_loc (BCE + Dice loss)，仅训练融合模块、投影头和定位头，冻结预训练编码器。
7. **推理**：只使用定位头输出概率图，通过 top-1% 均值 >0.5 判断是否篡改。

## 3. 实验设计
### 数据集/场景
- 提出 **BBC-PAIR** 基准，包含 28 种扩散修补器，分为三个子集：
  - **BBC-PAIR-ID**：10 种开源扩散模型（SD 1.4/1.5/2.1/3/3.5, SDXL, Kandinsky 2.2/3.1, FLUX.1 schnell/dev），训练集 150,000 张，测试集 1,000 张。
  - **BBC-PAIR-LoRA**：对 ID 中模型进行 LoRA 微调（10 种 LoRA），每类 500 张，测试对自定义模型的泛化。
  - **BBC-PAIR-OOD**：8 种商业修补器（ClipDrop, DALL-E 2, Adobe Firefly 等）750 张 + 现有基准 CocoGlide、SafireMS-Expert、SID-Set，共 500+ 张，测试完全未见模型泛化。
- 原始图像来自 OpenImages-v7（ID/LoRA）和 DIV2K（OOD）。

### 对比方法
- 7 种最新开源 IFDL 方法：HiFi-Net、TruFor、MIML、AdaIFL、Mesorch、SAFIRE、SIDA。
- 所有方法使用官方实现和推荐分辨率。
- 指标：检测（AUC、Acc）、定位（F1、IoU）。

## 4. 资源与算力
- **训练配置**：4 块 NVIDIA A100 80GB GPU，batch_size=16，训练 120 个 epoch，优化器 NAdam（lr=1e-4，weight_decay=1e-5），采用混合精度训练。
- 消融实验使用 10% 数据训练 70 epoch。
- 文中明确说明。

## 5. 实验数量与充分性
- **主实验**：三个 BBC-PAIR 场景的完整定量对比（表1），以及每个场景内细分的修补器级别结果（附录表11-14）。
- **定性分析**：多组可视化对比（图4、图6-10），显示 RADAR 更精确的定位和更低的误检。
- **属性分析**（图5）：
  - 多模态激活互补性（语义关注主体，几何关注结构）。
  - UMAP 显示 affected patch 作为中间分布。
  - 对 JPEG 压缩、缩放、模糊的鲁棒性测试。
- **消融实验**（表2）：融合策略（单编码器、concat、sum vs 交叉注意力）、对比损失组件（w/o L_SCL、w/o affected、Affect=Orig）、修补器数量（K=1,5,10）。
- **额外实验**：
  - 非修补数据集（COVERAGE, CASIA-v2, IMD2020, CMFD, AutoSplice, DSO）测试（表5）。
  - 掩膜大小影响（表3）。
  - 资源效率（推理时间、内存占用）（表9）。
  - 小模型变体（ViT-Small）（表10）。
  - OpenSDI 数据集比较（表15）。
- **充分性评价**：实验设计全面，覆盖了检测、定位、泛化、鲁棒性、消融、资源等多个维度。对比方法均使用官方实现，指标标准，结论可靠。

## 6. 主要结论与发现
- RADAR 在所有三个 BBC-PAIR 场景上显著优于所有基线，尤其在 **检测 AUC** 上提升巨大（ID: 0.945 vs 第二名0.625；LoRA: 0.901 vs 0.650；OOD: 0.805 vs 0.679）。
- **定位性能**：IoU 在 ID 上 0.600（第二名0.536），LoRA 上 0.521（第二名0.508），OOD 上 0.450（第二名0.447）。
- **核心贡献验证**：多模态融合和对比损失对泛化至关重要；增加训练修补器数量（K从1到10）显著提升性能。
- 对常见图像扰动（JPEG、缩放、模糊）具有良好的鲁棒性。
- **affected patch 的分离**是提升泛化的关键设计。

## 7. 优点
- **创新性**：首次在 IFDL 中系统利用语义+几何两个互补的基础模型，并设计对称交叉注意力融合；提出针对扩散模型特性的 patch 级三分类对比学习（original/tampered/affected），有效提升跨模型泛化。
- **实验充分性**：大规模基准 BBC-PAIR（28 个模型，三个场景）彻底评估了泛化能力；消融实验细致，验证了每个设计选择的有效性。
- **实用价值**：对商用和自定义模型均有效，且对常见web操作鲁棒，接近实际部署需求。
- **公开性**：代码、数据和模型将开源，有利于后续研究。

## 8. 不足与局限
- **仍存在错误率**：尤其对于完全未见的高质量商业修补器，检测 AUC 约 0.65-0.68，仍有提升空间。
- **定位保守**：倾向于高精度低召回，可能漏检部分篡改区域（适合高可信场景，不适合需要高敏感度的场景）。
- **可解释性不足**：内部推理过程不透明，注意力图分析只能提供部分直觉，缺乏自然语言解释。
- **非修补操作泛化差**：在传统剪贴/复制-移动数据集上检测性能下降（AUC 约0.5-0.6），虽然定位尚可，但检测不可靠。说明 RADAR 专门针对 inpainting 设计，对其他操作不通用。
- **评估标准不统一**：IFDL 领域缺乏标准化的局部化粒度和鲁棒性测试协议，论文虽提出了新基准，但仍需社区共同努力。
- **潜在的负面使用**：可能被攻击者用来校验其修补技术的可检测性，从而针对性改进规避方法。论文提出了C2PA元数据和哈希验证等保护措施。
- **计算资源需求**：使用 4 张 A100 训练，单次 inference 约228ms（896x896），比小型网络慢，但比其他基于基础模型的方法（如SAFIRE、SIDA）快很多。

（完）
