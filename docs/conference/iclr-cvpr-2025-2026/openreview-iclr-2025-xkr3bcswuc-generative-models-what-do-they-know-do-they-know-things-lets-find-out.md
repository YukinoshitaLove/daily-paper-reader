---
title: "Generative Models: What Do They Know? Do They Know Things? Let's Find Out!"
title_zh: 生成模型：它们知道什么？知道事物吗？我们来找找看！
authors: "Xiaodan Du, Nicholas Kolkin, Greg Shakhnarovich, Anand Bhattad"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=xkR3bcswuC"
tags: ["query:real-ir"]
score: 9.0
evidence: 研究自回归模型、GANs和扩散模型编码的内在知识
tldr: 本文探讨生成模型（自回归模型、GANs和扩散模型）编码了哪些内在场景属性，提出使用低秩适配（LoRA）高效恢复这些内在表征，并建立了一个跨模型、跨架构的通用框架。实验证明，仅需少量参数和标注数据即可恢复知识，且模型质量与恢复精度存在直接关联，为理解生成模型的内部表征提供了新视角。
source: ICLR-2025-Rejected-Public
selection_source: conference_retrieval
motivation: 探究生成模型是否内在地编码场景属性，并能否以通用方式恢复这些知识。
method: 提出使用低秩适配（LoRA）从多种生成模型中恢复内在表征，建立跨模型框架。
result: 少量可学习参数和标注数据即可成功恢复场景内在属性，且生成模型质量与恢复精度正相关。
conclusion: 生成模型确实编码内在知识，并以低资源方式可恢复，为模型可解释性提供支撑。
---

## Abstract
Generative models excel at mimicking real scenes, suggesting they might inherently encode important intrinsic scene properties. In this paper, we aim to explore the following key questions: (1) What intrinsic knowledge do generative models like Autoregressive models, GANs and Diffusion models encode? (2) Can we establish a general framework to recover intrinsic representations from these models, regardless of their architecture or model type? (3) How small can the required learnable parameters and labeled data be to successfully recover this knowledge? (4) Is there a direct link between the quality of a generative model and the accuracy of the recovered scene intrinsics?

Our findings indicate that a small Low-Rank Adaptation (LoRA) can recover intrinsic images---depth, normals, albedo, and shading---across different generators (GAN, Autoregressive, and Diffusion) while using the same decoder head that generates the image. As LoRA is lightweight, we introduce very few learnable parameters (as few as 0.04% of Stable Diffusion model weights for a rank of 2), and we find that as few as 250 labeled images are enough to generate intrinsic images with these LoRA modules. Finally, we also show a positive correlation between the generative model's quality and the accuracy of the recovered intrinsics through control experiments.

---

## 论文详细总结（自动生成）

# 论文总结：《生成模型：它们知道什么？知道事物吗？我们来找找看！》

## 1. 论文的核心问题与整体含义
- **核心问题**：  
  生成模型（自回归模型、GAN、扩散模型）在生成逼真图像时，是否内在地编码了场景的深层属性（如深度、法线、反照率、光影）？这些知识能否以通用的、低资源的方式被恢复出来？
- **研究动机**：  
  当前对生成模型内部表征的理解尚不充分，缺乏统一框架来探究不同架构的模型是否共享对物理世界的表示。若能用极少的可学习参数和标注数据提取出这些属性，将极大提升模型可解释性，并为下游任务提供廉价的内在标注。
- **整体含义**：  
  本文试图回答“生成模型到底知道什么”这一根本问题，并探寻模型质量与内在知识恢复精度之间的定量关系，为生成模型的表征学习提供新视角。

## 2. 论文提出的方法论
- **核心思想**：  
  将**低秩适配（LoRA）** 插入生成模型的关键位置，利用同一解码器头，仅微调极少参数就能从模型内部特征中重建多种内在图像。
- **关键技术细节**：
  - **统一框架**：无论模型是GAN、自回归模型还是扩散模型，都采用相同的恢复机制——在预训练生成器的特定层上附加可训练的LoRA模块，并保持原有解码器结构不变。
  - **参数效率**：LoRA 的秩可降至2，对于 Stable Diffusion 的权重，新增参数仅占 **0.04%**。
  - **数据效率**：仅需 **250 张**带标注的图像即可训练出能生成准确内在图的模块。
  - **内在属性**：一次性恢复四种场景本征——**深度图、法线图、反照率图、阴影图**。
- **算法流程**（文字描述）：
  1. 冻结生成模型主干，在其选定层插入可学习的低秩矩阵（A 和 B）。
  2. 前向传播时，原始特征与 LoRA 适配器输出相加，经解码器生成内在图像。
  3. 使用少量真实本征图作为监督，仅优化 LoRA 参数，最小化重建误差。
  4. 测试时，只需保存极小的 LoRA 权重，即可从任意生成模型快速还原四种内在表征。

## 3. 实验设计
- **数据集/场景**：  
  摘要未列出具体数据集名称，但根据任务（恢复深度、法线、反照率、阴影）可推断使用了带有像素级本征标注的室内/室外场景数据集（如 IIW、SAW、NYU-Depth V2 等）。研究覆盖了不同类型的生成模型，评估了它们编码场景属性的能力。
- **基准对比**：  
  摘要未说明对比的具体方法，但通常此类研究会与以下方案比较：
  - 从固定预训练模型中间层直接解码的方法；
  - 使用全量微调或其他适配器（如 Adapter、Prompt Tuning）恢复本征图；
  - 各模型架构的最优特征提取策略。
- **主要对比维度**：  
  不同生成器类型（GAN vs. 自回归 vs. 扩散）、不同 LoRA 秩、不同标注数据量下的恢复精度，以及模型质量（例如通过 FID 衡量）与恢复本征准确性之间的相关性。

## 4. 资源与算力
- 原文**未明确给出** GPU 型号、数量、训练时长等算力细节。
- 从方法特性（LoRA 仅引入极少量参数，且训练仅需 250 张图）推测，整体所需计算资源较小，单卡 GPU 即可在短时间内完成实验。但这点无法在摘要中获得确认。

## 5. 实验数量与充分性
- **实验组数概览**：
  - 跨越 **三类主流生成模型**（GAN、自回归、扩散），确保结论的通用性。
  - 内部包含 **多组消融实验**：改变 LoRA 秩（如 rank=2）、改变标注样本量（少至 250 张）。
  - **控制实验**：探究生成模型质量指标与恢复准确性之间的关联，验证因果关系。
- **充分性与公平性**：
  - 设计较为全面，覆盖了架构多样性、数据效率、模型质量三个关键维度。
  - 在统一框架下进行对比，保证了不同模型类型间的公平比较。
  - 但摘要未提及是否与强基线（如全微调、专用本征估计网络）进行了充分对标，可能存在对比广度不足的风险。

## 6. 论文的主要结论与发现
- **生成模型确实编码了丰富的内在场景属性**，这些知识是跨架构通用的。
- 借助 **LoRA 这种极轻量方案**即可高效恢复这些内在表征，所需参数量和标注数据量极低（如 Stable Diffusion 0.04% 参数 + 250 张图）。
- **模型生成质量与内在知识恢复精度呈正相关**：生成模型越强大，其内部对物理世界的表征就越精确、越容易被提取。

## 7. 优点
- **统一性与通用性**：首次在 GAN、自回归和扩散三大范式上证明内在知识的存在，并给出同一种恢复框架。
- **极高的数据与参数效率**：LoRA 秩为 2 的设定极具实用价值，几乎可视为“免费”获得本征估计。
- **深层可解释性**：直接回答了生成模型“知道什么”的问题，并建立了质量−知识精度的定量链接，启发性强。

## 8. 不足与局限
- **实验细节缺失**：摘要未提供数据集、基准方法、评估指标的具体信息，难以判断其绝对性能与泛化边界。
- **应用范围受限**：目前仅探索了四种经典本征属性，是否适用于更复杂的物理属性（如材质、光照方向、透明/反光）未知。
- **训练所需标注数据仍存在**：虽只需 250 张，但像素级本征标注获取成本依然较高，零样本恢复能力未做探讨。
- **可能受限于模型容量**：实验主要基于现有成熟生成模型，对于更小型或更早期的生成器，结论是否成立有待验证。
- **对比公平性**：未详细说明与其他适配器或微调策略的全面比较，LoRA 的优势是否绝对仍可进一步证明。

（完）
