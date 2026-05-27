---
title: Reliable Image Quality Evaluation and Mitigating Quality Bias in Generative Models
title_zh: 评估图像生成模型中的可靠质量和缓解质量偏差
authors: "Hoin Jung, Shenyu Lu, De Wang, Xiaoqian Wang"
date: 2025-05-06
pdf: "https://openreview.net/pdf?id=nFmq9z7Mdq"
tags: ["query:real-ir"]
score: 7.0
evidence: 评估并缓解图像生成模型中的质量偏差
tldr: 图像生成模型在人口统计分组间存在质量差异，但常用指标FID存在偏差。本文提出差异质量评估（DQA）分数，量化现有评估指标在不同组间的可靠性，并基于此提出缓解偏差的方法。实验证明DQA能有效检测指标偏差，并帮助提升生成模型的公平性。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 707, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 721, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1212, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1349, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1412, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1333, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1297, \"height\": 1708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1354, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1125, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1444, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfmq9z7mdq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1447, \"height\": 354, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1491, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 712, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nfmq9z7mdq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1463, \"height\": 265, \"label\": \"Table\"}]"
motivation: FID等图像质量评估指标在人口统计组间存在偏差，影响评估可靠性。
method: 提出DQA分数衡量评估指标在不同组间的一致性，并指导偏差缓解。
result: DQA能有效识别指标偏差，并在多个生成模型上改善质量公平性。
conclusion: 该工作提升了图像生成模型评估的可靠性，对公平生成有重要意义。
---

## Abstract
Discrepancies in generation quality across demographic groups pose a substantial and critical challenge in image generative models. However, the Fréchet Inception Distance (FID) score, which is widely used as an image quality evaluation metric for generative models, introduces unintended bias when assessing quality across sensitive attributes. This undermines the reliability of the evaluation procedure. This paper addresses this limitation by introducing the Difference in Quality Assessment (DQA) score, a novel approach that quantifies the reliability of existing evaluation metrics, e.g. FID. DQA assesses discrepancies in evaluated quality across demographic groups under strictly controlled conditions to effectively gauge metric reliability. Our findings reveal that traditional quality evaluation metrics can yield biased assessments across groups due to inappropriate reference set selection and inherent biases in image encoder in FID. Furthermore, we propose DQA-Guidance within diffusion model sampling to reduce quality disparities across groups. Experimental results demonstrate the utility of the DQA score in identifying biased evaluation metrics and present effective strategies to mitigate these biases. This work contributes to the development of reliable and fair evaluation metrics for generative models and provides actionable methods to address quality disparities in image generation across groups.

---

## 论文详细总结（自动生成）

# 论文《Reliable Image Quality Evaluation and Mitigating Quality Bias in Generative Models》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：图像生成模型（如GAN、扩散模型）在不同人口统计组（如性别、种族）之间生成图像的质量存在显著差异，这被称为“质量偏差”。然而，广泛使用的质量评估指标FID（Fréchet Inception Distance）在评估跨组质量时本身存在偏差，导致无法可靠地检测质量不公平问题。
- **研究动机**：现有工作多关注分布公平性（即生成样本数量均衡），但忽略了生成质量本身的公平性。质量偏差会负面影响下游任务（如医学图像分类中的公平性）。因此，需要可靠的工具来量化评估指标的偏差，并开发缓解质量偏差的策略。
- **核心贡献**：
  - 提出**Difference in Quality Assessment (DQA)** 分数，用于量化评估指标（如FID）在不同组间的可靠性。
  - 揭示传统指标偏差的两个来源：参考集选择不当和图像编码器内在偏差。
  - 提出**DQA-Guidance**，在扩散模型采样阶段通过梯度引导减少质量差异。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过构建严格受控的测试数据集（包含不同质量等级的生成图像），计算跨组评估结果差异相对于整体质量偏移的比值，从而隔离编码器偏差的影响。
- **关键技术细节**：
  - **DQA定义**：  
    \( \text{DQA} = \frac{D(f(A_{\text{gen}}), f(A_{\text{ref}})) - D(f(B_{\text{gen}}), f(B_{\text{ref}}))}{D(f(I_{\text{gen}}), f(I_{\text{ref}}))} \)  
    其中 \(D\) 为距离度量（如MMD），\(f\) 为图像编码器，\(A_{\text{gen}}, B_{\text{gen}}\) 为两组质量相近的生成图像，\(A_{\text{ref}}, B_{\text{ref}}\) 为对应的组内参考集。分子衡量组间质量差异，分母衡量整体质量偏移。低DQA表示编码器对两组公平；高DQA指示偏差。
  - **多组扩展**：AvgDQA通过两两配对DQA的平均值处理多个组。
  - **可控数据集构建**：使用Stable Diffusion XL生成6种质量退化场景（弱引导、少步数、强噪声、无精炼器、组合退化），共20,000张图像（10个职业×2性别×4种族），确保每组属性数量平衡。
  - **DQA-Guidance**：在扩散模型采样阶段，将DQA作为能量函数，计算其相对于潜变量 \(z_t\) 的梯度，结合整体质量项（分母），修正噪声预测：
    \[
    \tilde{\epsilon}_\theta(z_t) = \epsilon_\theta(z_t) + \sigma_t \nabla_{z_t} \left[ \lambda_1 \text{DQA} + \lambda_2 D(f^*(I_{\text{gen}}), f^*(I_{\text{ref}})) \right]
    \]
    其中 \(f^*\) 为可靠编码器（如DINO-RN50），\(\lambda_1, \lambda_2\) 为超参数。

## 3. 实验设计：数据集、场景、Benchmark、对比方法

- **数据集和场景**：
  - **人类图像生成**：使用SDXL生成10个职业、2性别、4种族的图像，构建6种质量退化场景（基线、弱引导、少步数、强噪声、无精炼器、组合）。
  - **医学图像**：使用ChestX-ray14数据集（NIH），并用Prompt2MedImage生成合成胸部X光图像。
- **Benchmark**：对比多种预训练编码器（InceptionV3, VGG, ResNet-50, ViT-B/16, Swin Transformer, CLIP, MoCo, MSN, DINO等）的DQA分数。
- **对比方法**：
  - 评估指标可靠性：对比不同编码器在DQA上的表现。
  - 质量偏差缓解：对比基线扩散模型（无引导）与DQA-Guidance生成图像的MMD和组间质量差距。
  - 下游任务验证：在ChestX-ray14分类任务中，对比使用全部生成增强、DQA选择的公平子集/不公平子集对分类公平性（AUC差距）的影响。

## 4. 资源与算力

- 论文在附录L中明确说明：
  - CPU: AMD EPYC 7313 16-Core Processor
  - GPU: NVIDIA RTX A5000
  - 未提供具体训练时长、GPU数量或总计算量。仅在附录中列出了计算资源类型，未详细量化。

## 5. 实验数量与充分性

- **实验数量**：
  - 编码器可靠性评估：对超过10种预训练模型、在6种退化场景下计算DQA，并分别针对性别和种族偏差。
  - 引导实验：在人类图像和医学图像两个领域，变化超参数 \(\lambda_1, \lambda_2\) 进行多组对比（表1、表3、图9、图11等）。
  - 下游任务验证：在ChestX-ray14分类任务中，比较基线、全部增强、公平子集、不公平子集共4种增强策略（表2）。另外测试了DQA-Guidance生成的样本对分类的影响（表3）。
  - 消融：对DQA-Guidance的 \(\lambda_1\) 和 \(\lambda_2\) 进行灵敏度分析。
  - 其他：对VQA和IQA模型进行了DQA扩展分析（附录I）。
- **充分性评价**：实验覆盖了人类图像和医学图像两个领域，编码器类型多样，退化场景模拟了实际质量问题。下游任务验证了DQA的实用性。消融实验充分。但缺失与现有公平性方法（如分布公平性方法）的对比，作者在局限性中提到缺乏对比基线。整体实验设计客观、公平，但样本量（每组250张）可能较小。

## 6. 主要结论与发现

- **FID等传统指标不可靠**：由于参考集选择不当和编码器偏差，FID会错误评估组间质量差异。
- **DQA能有效识别可靠编码器**：自监督模型（DINO-RN50、MoCo-RN50）在人类图像和医学图像上均表现出最低DQA，即最公平。
- **骨架网络影响**：CNN架构（如RN50）比Transformer更鲁棒；自监督训练比监督训练更公平；更大训练集（ImageNet-21K）并未提升公平性。
- **DQA-Guidance有效缓解质量偏差**：在扩散模型采样中应用DQA-Guidance，可同时降低组间质量差距和提升整体质量。
- **下游分类公平性提升**：使用DQA选择的公平子集进行数据增强，可降低分类AUC的性别差距；DQA-Guidance生成的样本也能改善分类公平性。

## 7. 优点：方法或实验设计亮点

- **创新性**：首次系统性地从质量公平性角度评估生成模型，提出DQA分数作为评估指标可靠性的工具。
- **方法有效**：DQA不仅能诊断编码器偏差，还能直接用于引导扩散模型采样，无需重训练。
- **实验设计严谨**：构建了受控退化数据集，确保不同组质量一致，从而隔离编码器偏差。
- **下游验证**：在医学图像分类任务中展示了质量偏差的实际影响及DQA的实用性。
- **多维度分析**：对比多种编码器架构、训练方式、数据集大小，结论全面。

## 8. 不足与局限

- **缺少对比基线**：DQA-Guidance未与现有公平性方法（如分布重采样、损失调整）对比，作者在5.4中承认这一点。
- **计算成本**：DQA-Guidance需要额外编码器和梯度计算，可能增加内存和耗时。
- **数据集限制**：受控数据集基于人工定义的质量退化，可能无法完全反映真实用户感知到的质量。
- **社会偏差风险**：虽然缓解了指标偏差，但若参考集本身存在偏差，DQA可能无法完全消除编码器偏差。
- **通用性验证不足**：主要实验基于Stable Diffusion系列和医学图像生成模型，未测试其他生成架构（如GAN）。
- **统计细节**：部分结果（如表1）未给出误差线或置信区间，尽管在分类任务中给出了误差条。
- **资源报告不完整**：仅说明GPU型号，未提供训练时长、能耗等。

（完）
