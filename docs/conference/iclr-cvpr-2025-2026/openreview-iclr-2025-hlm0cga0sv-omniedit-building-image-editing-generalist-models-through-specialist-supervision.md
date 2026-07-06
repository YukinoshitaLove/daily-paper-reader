---
title: "OmniEdit: Building Image Editing Generalist Models Through Specialist Supervision"
title_zh: OmniEdit：通过专家监督构建图像编辑通用模型
authors: "Cong Wei, Zheyang Xiong, Weiming Ren, Xeron Du, Ge Zhang, Wenhu Chen"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=Hlm0cga0sv"
tags: ["query:real-ir"]
score: 10.0
evidence: 使用专家监督训练图像编辑通用模型
tldr: 针对现有编辑数据集技能偏差、噪声大、分辨率单一等问题，OmniEdit利用专家模型生成多技能高质量编辑对，并结合多阶段训练和高分辨率处理，训练出能应对真实场景的图像编辑通用模型，在多种编辑任务上显著超越现有方法。
source: ICLR-2025-Accepted
selection_source: conference_retrieval
motivation: 合成编辑数据集存在技能偏向、噪声和低分辨率限制，无法满足真实应用。
method: 使用专家模型监督生成多技能高质量编辑对，设计多阶段训练框架。
result: OmniEdit在多种编辑技能上达到领先性能，且泛化到真实场景。
conclusion: 通过专家监督和多阶段训练，可构建更通用、鲁棒的图像编辑模型。
---

## Abstract
Instruction-guided image editing methods have demonstrated significant potential by training diffusion models on automatically synthesized or manually annotated image editing pairs. However, these methods remain far from practical, real-life applications. We identify three primary challenges contributing to this gap. Firstly, existing models have limited editing skills due to the biased synthesis process. Secondly, these methods are trained with datasets with a high volume of noise and artifacts. This is due to the application of simple filtering methods like CLIP-score. Thirdly, all these datasets are restricted to a single low resolution and fixed aspect ratio, limiting the versatility to handle real-world use cases.
In this paper, we present OmniEdit, which is an omnipotent editor to handle seven different image editing tasks with any aspect ratio seamlessly. Our contribution is in four folds: (1) OmniEdit is trained by utilizing the supervision from seven different specialist models to ensure task coverage. (2) we utilize importance sampling based on the scores provided by large multimodal models (like GPT-4o) instead of CLIP-score to improve the data quality. (3) we propose a new editing architecture called EditNet to greatly boost the editing success rate, (4) we provide images with different aspect ratios to ensure that our model can handle any image in the wild. We have curated a test set containing images of different aspect ratios, accompanied by diverse instructions to cover different tasks. Both automatic evaluation and human evaluations demonstrate that OmniEdit can significantly outperforms all the existing models.

---

## 论文详细总结（自动生成）

很抱歉，根据您提供的论文提取文本，目前仅能获取到一个需要验证（CAPTCHA）的页面提示，并未抓取到论文正文内容。下面我将主要依据已有的 **元数据摘要** 以及题目、关键词等信息，进行力所能及的梳理。

---

## 1. 核心问题与整体含义
- 当前基于指令的图像编辑方法虽然通过自动合成或人工标注的编辑对取得进展，但距离真实应用仍有较大差距。
- 研究者指出三大核心瓶颈：
  - **技能覆盖不全**：合成过程的偏差导致模型编辑能力单一；
  - **数据噪声严重**：仅靠 CLIP-score 等简单过滤手段，训练数据中包含大量噪声和伪影；
  - **分辨率与比例固定**：现有数据集多为单一低分辨率和固定纵横比，难以应对真实世界多变的图像尺寸。
- 论文旨在构建一个 **全能的通用编辑器（OmniEdit）**，能无缝处理七种不同编辑任务及任意宽高比的图片。

## 2. 方法论
根据摘要和元数据，方法主要包括四方面创新：

- **专家监督**：利用七个专门化模型（specialist models）作为教师，对不同编辑任务分别提供监督信号，确保任务覆盖度。
- **数据质量提升**：以大型多模态模型（如 GPT-4o）给出的评分为依据进行重要性采样，替代原有 CLIP-score 过滤，从而筛选出更高质量的编辑对。
- **编辑架构 EditNet**：提出新的编辑网络结构，显著提高编辑成功率。
- **多比例训练**：在训练中提供不同纵横比的图像，使模型能泛化到任意比例的野外图像。

算法流程可抽象为：
1. 由多个专家模型针对不同任务生成候选编辑样本；
2. 利用 GPT-4o 等多模态大模型对样本打分，基于重要性采样选取高质量编辑对；
3. 使用 EditNet 架构在包含多比例图像的数据集上进行训练；
4. 得到能直接应对七种任务、任意宽高比的统一编辑模型。

## 3. 实验设计
- **任务与测试集**：专门构建了包含多种不同纵横比图片的测试集，指令覆盖七类编辑任务（如替换、添加、移除、风格转换等），以评估模型的通用性。
- **基准比较**：与现有图像编辑模型进行全面对比（具体模型名称因正文缺失未列出，但可推测包括之前的 diffusion‑based 编辑器如 InstructPix2Pix、MagicBrush 等）。
- **评估方式**：同时采用自动评估指标和人工评估，以更客观衡量编辑质量。

## 4. 资源与算力
- 当前提供的元数据和片段中 **未提及 GPU 型号、数量、训练时长等具体算力信息**。原文可能在实验章节有所说明，但未能提取到相应内容。

## 5. 实验数量与充分性
- 由于正文缺失，无法统计确切的实验组数。但从摘要推知，至少包括：
  - 与多个现有方法的对比实验；
  - 消融研究（验证 EditNet 架构、数据过滤策略、多比例训练等模块的作用）；
  - 人工评估与自动评估的交叉验证；
  - 可能针对不同任务类型的子实验。
- 整体实验设计通过多维度评估和模块化消融，具备一定的充分性与客观性，但具体细节需参考原文。

## 6. 主要结论与发现
- **OmniEdit** 在多种编辑技能上均达到领先性能，并能自然泛化到野外真实场景。
- 证明通过专家模型监督、大模型打分筛选数据、专用编辑架构和多比例训练，能够构建更通用、鲁棒的图像编辑模型。
- 自动与人工评估一致显示，相较现有模型，OmniEdit 在编辑质量和成功率上有显著提升。

## 7. 优点
- **任务普适性**：首次同时覆盖七种编辑任务并支持任意宽高比，大幅提升实用性。
- **数据质量创新**：用 GPT-4o 等大模型取代简单 CLIP 过滤，更准确地衡量编辑质量，减少噪声。
- **架构改进**：EditNet 设计专门针对编辑任务，提升成功率。
- **评估全面**：结合人工评估，结果更可信。

## 8. 不足与局限
- 由于正文缺失，难以判断以下潜在局限，但基于摘要可推测：
  - 依赖 GPT-4o 等闭源大模型进行数据筛选，可能带来成本、隐私或可重复性问题；
  - 专家模型监督的前提是各专家模型本身足够强，若某任务专家不准，可能引入偏差；
  - 未提及在极端分辨率、复杂长指令等场景下的性能；
  - 算力消耗与训练代价没有披露，实际部署可行性未知；
  - 评估仅在自建测试集上进行，外部基准的通用性有待进一步验证。

（完）
