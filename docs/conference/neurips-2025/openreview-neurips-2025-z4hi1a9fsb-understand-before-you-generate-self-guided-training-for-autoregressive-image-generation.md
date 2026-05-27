---
title: "Understand Before You Generate: Self-Guided Training for Autoregressive Image Generation"
title_zh: 先理解再生成：自回归图像生成的自引导训练
authors: "Xiaoyu Yue, ZiDong Wang, Yuqing Wang, Wenlong Zhang, Xihui Liu, Wanli Ouyang, LEI BAI, Luping Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Z4hi1a9FsB"
tags: ["query:real-ir"]
score: 8.0
evidence: 自引导训练的自回归图像生成
tldr: 自回归模型在图像生成中面临局部依赖、语义不一致和空间不变性不足等问题。本文首次系统研究下一词元预测在视觉领域的机制，识别关键障碍并提出自监督训练目标。实验证明该方法显著提升了生成图像的高层语义质量，推动自回归图像生成发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1228, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 447, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1429, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1412, \"height\": 638, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 997, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 927, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 482, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 440, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 470, \"height\": 225, \"label\": \"Table\"}]"
motivation: 自回归模型在图像生成中学习高层视觉语义存在困难，需要系统分析并改进。
method: 引入自监督目标增强模型对视觉语义的理解，解决局部依赖和语义不一致问题。
result: 在多个图像生成基准上，方法提升了生成质量，特别是语义一致性。
conclusion: 该工作揭示了自回归图像生成的机制瓶颈，并提出有效训练策略。
---

## Abstract
Recent studies have demonstrated the importance of high-quality visual representations in image generation and have highlighted the limitations of generative models in image understanding. As a generative paradigm originally designed for natural language, autoregressive models face similar challenges. In this work, we present the first systematic investigation into the mechanisms of applying the next-token prediction paradigm to the visual domain. We identify three key properties that hinder the learning of high-level visual semantics: local and conditional dependence, inter-step semantic inconsistency, and spatial invariance deficiency. We show that these issues can be effectively addressed by introducing self-supervised objectives during training, leading to a novel training framework, Self-guided Training for AutoRegressive models (ST-AR). Without relying on pre-trained representation models, ST-AR significantly enhances the image understanding ability of autoregressive models and leads to improved generation quality. Specifically, ST-AR brings approximately 42% FID improvement for LlamaGen-L and 49% FID improvement for LlamaGen-XL, while maintaining the same sampling strategy.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
自回归（AR）图像生成模型（如LlamaGen）在图像生成任务上取得了与扩散模型相当的性能，但其直接采用自然语言领域的“下一词元预测”范式，在视觉领域面临三大瓶颈：
- **局部与条件依赖**：模型注意力过度集中在局部邻近词元和条件令牌上，难以捕捉全局上下文。
- **跨步语义不一致**：随着生成步数推进，模型在不同时间步学习的语义表示出现退化，后期线性探测准确率下降。
- **空间不变性缺失**：视觉分词器（如VQ-GAN）对微小扰动敏感，同一物体不同视角的离散令牌差异大，导致语义冗余学习。

这些问题限制了AR模型学习高质量的视觉表示，进而影响生成质量。论文旨在通过引入自监督训练目标，在不依赖预训练表示模型的前提下，增强AR模型的图像理解能力，从而提升生成性能。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 核心思想
ST-AR（Self-guided Training for AutoRegressive models）将自监督学习（掩码图像建模MIM + 对比学习）集成到AR模型的下一代词元预测训练中，通过“自引导”方式增强视觉语义表示。

### 关键技术细节
- **掩码图像建模（MIM）损失**：为扩大感受野，不直接屏蔽输入令牌，而是在Transformer注意力图中随机屏蔽一定比例（r=0.25）的令牌（将相应位置设为负无穷）。学生网络与EMA教师网络的特征进行余弦距离对齐。
- **跨步对比损失（\( \mathcal{L}_{\text{step}} \)）**：从同一视图的不同时间步随机采样K个位置，在同一图像不同位置作为正样本，不同图像间为负样本，增强跨步语义一致性。
- **跨视图对比损失（\( \mathcal{L}_{\text{view}} \)）**：对同一图像使用两种数据增强，在不同视图的相同位置作为正样本，不同图像间为负样本，增强空间不变性。
- **EMA教师网络**：采用动量更新（decay=0.9999），为学生网络提供稳定的学习目标。
- **总损失**：\( \mathcal{L}_{\text{ST-AR}} = \mathcal{L}_{\text{AR}} + \alpha \mathcal{L}_{\text{MIM}} + \beta \cdot \frac{1}{2}(\mathcal{L}_{\text{step}} + \mathcal{L}_{\text{view}}) \)，其中α=1.0，β=0.5。

## 3. 实验设计
- **数据集**：ImageNet-256×256（类条件图像生成任务），使用与LlamaGen相同的VQGAN离散化。
- **评估基准**：图像理解采用线性探测（Linear Probing）Top-1准确率；图像生成采用FID、sFID、IS、Precision、Recall（ADM评估套件）。
- **对比方法**：
  - 基线：LlamaGen各尺寸（B/L/XL）及其不同训练轮次（50/300 epoch）。
  - 其他范式：BigGAN（GAN）、DiT/SiT/LDM-4（扩散）、MaskGIT（掩码AR）、VAR（并行AR）、VQGAN（因果AR）等。
- **训练设置**：与LlamaGen相同的超参数（lr=1e-4 per 256 batch, AdamW, weight decay=0.05, gradient clip=1.0），对比损失施加于中间层（如LlamaGen-B的第6层）。

## 4. 资源与算力
论文仅说明训练设置与LlamaGen一致（学习率、优化器、梯度裁剪等），**未明确提及使用的GPU型号、数量或训练时长**。因此，无法直接评估算力消耗。但提及ST-AR增加了训练成本（在第5节Limitations中指出）。

## 5. 实验数量与充分性
论文进行了较为充分的实验：
- **主对比实验**（表1、2）：覆盖LlamaGen B/L/XL的50和300 epoch，还与其他方法横向对比。
- **消融实验**（表3-6）：
  - 各损失组件贡献（MIM、step、view单独及组合）。
  - 掩码比例r（0.15~0.45）。
  - 对比损失施加的深度（1/4、1/2、3/4、全深度）。
  - 跨步采样数K（2、4、8、16）。
- **可视化**：注意力图对比（图5 vs 图2）、线性探测曲线（图4）、定性对比（图6）。
整体实验设计系统，消融全面，与基线使用相同代码框架和评估协议，保证了**客观性和公平性**。

## 6. 论文的主要结论与发现
- **三大瓶颈得到验证**：通过注意力图、线性探测、令牌扰动分析，确认了局部依赖、语义不一致、空间不变性缺失的问题。
- **ST-AR有效提升理解**：LlamaGen-B线性探测准确率从18.68%提升至45.27%，且后期不退化；注意力图覆盖更大语义区域。
- **显著改善生成质量**：
  - LlamaGen-XL（50 epoch）FID降低49%（19.42→9.81）。
  - LlamaGen-XL（300 epoch）FID达6.20，超过4倍参数量的LlamaGen-3B（9.38）。
  - 多种模型尺寸均有一致提升。
- **无需额外预训练表示模型**：仅通过自引导训练即可获得更好的视觉表示。

## 7. 优点
- **概念创新**：首次系统分析AR图像生成的内在机制，并对应设计自监督方案。
- **方法简洁有效**：仅增加训练时损失，不改变推理采样策略，保持与语言模型的兼容性。
- **广泛适用**：在多种模型规模（B/L/XL）和训练时长（50/300 epoch）上均有显著提升。
- **实验全面**：包含理解与生成两方面评估，消融实验覆盖核心超参数。

## 8. 不足与局限
- **训练成本增加**：额外自监督损失带来更高的计算开销，论文未提供具体时间/资源对比。
- **实验场景单一**：仅在ImageNet类条件生成上验证，未在文本条件、跨域或多模态场景测试。
- **依赖视觉分词器**：VQGAN的固有问题（如空间不变性）仍部分存在，ST-AR虽用对比学习缓解但未根本解决。
- **潜在应用风险**：生成质量提升可能被滥用于伪造图像，论文在Limitations中提及。

（完）
