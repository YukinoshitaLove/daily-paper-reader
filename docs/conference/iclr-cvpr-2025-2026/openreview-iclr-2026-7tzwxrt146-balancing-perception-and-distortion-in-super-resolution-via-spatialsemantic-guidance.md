---
title: Balancing Perception and Distortion in Super Resolution via Spatial–Semantic Guidance
title_zh: 通过空间-语义引导平衡超分辨率中的感知与失真
authors: "Dan Wang, Haiyan Sun, Shan Du, Z. Jane Wang, Zhaochong An, Serge Belongie, Xinrui Cui"
date: 2025-09-07
pdf: "https://openreview.net/pdf?id=7tzwXrT146"
tags: ["query:real-ir"]
score: 10.0
evidence: 扩散超分辨中利用空间-语义引导平衡感知与失真
tldr: 针对扩散模型超分中感知质量与保真度的矛盾，提出SpaSemSR框架，引入空间-语义双重引导。空间定位文本引导融合物体空间线索与语义提示，减少幻觉，提升结构一致性，实现了感知与失真的更好权衡，为高保真超分辨率提供了新路径。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 扩散超分虽提升感知但易幻觉，需平衡感知-失真权衡。
method: 提出SpaSemSR，利用空间定位文本引导与语义提示进行扩散模型引导。
result: 在超分辨率中有效减少幻觉，实现高感知质量同时保持内容保真度。
conclusion: 空间-语义引导为扩散超分提供了保真且感知自然的有效框架。
---

## Abstract
In image super-resolution (SR), perceptual quality and distortion form two competing objectives, bounded by the Perception-Distortion trade-off. GAN-based SR models reduce distortion but often fail to synthesize realistic fine-grained textures, while diffusion-based models generate perceptually plausible details but frequently hallucinate content, leading to fidelity loss. This raises a key challenge: how to harness the powerful generative priors of diffusion models without sacrificing fidelity. We introduce SpaSemSR, a Spatial-Semantic guided diffusion-based framework that addresses this challenge through two complementary guidance. First, spatial-grounded textual guidance integrates object-level spatial cues with semantic prompts, reducing distortion by aligning textual guidance with visual structure. Second, semantic-enhanced visual guidance unifies multimodal semantic priors via a multi-encoder design with semantic degradation constraints, improving perceptual realism under severe degradations. These complementary guidances are adaptively fused with diffusion priors via novel spatial-semantic attention mechanisms, curbing distortion and hallucination while preserving the strengths of generative diffusion models. Extensive experiments across multiple benchmarks demonstrate that SpaSemSR achieves a state-of-the-art balance between perception and distortion, producing both realistic and faithful restorations.

---

## 论文详细总结（自动生成）

# 论文总结：Balancing Perception and Distortion in Super Resolution via Spatial–Semantic Guidance

## 1. 核心问题与整体含义
- **研究背景**：在图像超分辨率（SR）中，感知质量（perceptual quality）与失真（distortion）是一对固有的矛盾体，受感知-失真权衡（Perception-Distortion trade-off）的约束。
- **动机**：基于GAN的SR模型能降低失真，但往往无法合成逼真的纹理细节；扩散模型（diffusion-based）能生成感知上可信的细节，却频繁产生“幻觉”（hallucinate content），导致内容保真度下降。
- **核心挑战**：如何在利用扩散模型强大的生成先验能力的同时，不牺牲保真度，即**平衡感知与失真**。

## 2. 方法论
- **整体框架**：提出 **SpaSemSR**，一种基于**空间-语义引导**（Spatial-Semantic Guidance）的扩散超分辨率框架。
- **两大互补引导机制**：
  1. **空间定位文本引导（Spatial-grounded Textual Guidance）**：整合物体级别的空间线索（object-level spatial cues）与语义提示（semantic prompts），通过将文本引导与视觉结构对齐来降低失真。
  2. **语义增强视觉引导（Semantic-enhanced Visual Guidance）**：采用多编码器设计（multi-encoder design）结合语义退化约束（semantic degradation constraints），统一多模态语义先验，从而在严重退化条件下提高感知逼真度。
- **融合机制**：设计新颖的**空间-语义注意力机制**（spatial-semantic attention），自适应地将上述两种引导与扩散先验融合，以抑制失真和幻觉，同时保留扩散模型的生成优势。

## 3. 实验设计
- **数据集/场景**：论文提及在**多个基准（multiple benchmarks）** 上进行了广泛实验，但摘要未列出具体数据集名称。
- **对比方法**：摘要未明确列出对比的基线方法，但暗示与基于GAN和基于扩散的SR模型进行了对比。
- **评估指标**：突出了对感知质量和失真（保真度）的双重兼顾，未具体说明指标名称（如LPIPS、PSNR等）。

## 4. 资源与算力
- **文中提及**：摘要未提供任何关于GPU型号、数量、训练时长等算力信息。**无法从摘要文本中获取此类细节**。

## 5. 实验数量与充分性
- **实验数量**：摘要只提到“extensive experiments across multiple benchmarks”，未说明具体实验组数（如消融实验、不同退化等级等）。
- **充分性与公正性**：基于摘要无法判断实验是否充分、客观。但声称达到SOTA平衡，暗示实验设计应为满足论文声明的结论提供了支撑，但详细评估需阅读全文。

## 6. 主要结论与发现
- **效果**：SpaSemSR在感知与失真之间实现了**最先进的平衡**（state-of-the-art balance），能生成既**逼真**又**忠实**（realistic and faithful）的恢复结果。
- **有效性**：通过空间和语义的双重引导，有效减少了扩散模型的幻觉，并在保持内容保真度的同时提升了感知质量。

## 7. 优点
- **创新点突出**：将空间线索与语义提示结合引导扩散模型，为解决感知-失真权衡提供了新视角。
- **互补设计**：文本引导降低失真，视觉引导提升逼真度，两者通过注意力机制巧妙融合。
- **目标明确**：精准定位扩散超分的幻觉痛点，提出针对性缓解方案。

## 8. 不足与局限
- **摘要信息有限**：未提及具体数据集、对比算法、量化结果、消融研究细节，难以深入判断局限性。
- **应用限制**：空间定位依赖物体空间线索的准确提取，对无显著物体或复杂场景的泛化性未论证。
- **计算开销**：多编码器和注意力融合可能增加推理成本，但摘要未讨论效率问题。
- **评估范围**：仅在超分辨率任务上验证，是否适用于其他恢复任务（如去模糊）未知。

（完）
