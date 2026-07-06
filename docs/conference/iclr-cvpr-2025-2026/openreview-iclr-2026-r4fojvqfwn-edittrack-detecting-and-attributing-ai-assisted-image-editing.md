---
title: "EditTrack: Detecting and Attributing AI-assisted Image Editing"
title_zh: EditTrack：AI辅助图像编辑的检测与归因
authors: "Zhengyuan Jiang, Yuyang Zhang, Moyang Guo, Neil Zhenqiang Gong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=R4FoJvqfWN"
tags: ["query:real-ir"]
score: 4.0
evidence: 图像编辑检测与归因
tldr: 该工作定义并研究了图像编辑检测与归因问题，提出EditTrack框架，判断合成图像是否源自特定原图并识别编辑模型，弥补了AI图像鉴伪领域的空白。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有AI生成图像检测方法无法判断一张图像是否从特定原图编辑而来。
method: 基于编辑过程的四个关键观察，提出EditTrack检测与归因框架。
result: 未在摘要中详述，但预期能有效检测和归因编辑。
conclusion: EditTrack为图像编辑取证提供了首个检测与归因方法。
---

## Abstract
In this work, we formulate and study the problem of image-editing detection and attribution: given a base image and a suspicious image, detection seeks to determine whether the suspicious image was derived from the base image using an AI editing model, while attribution further identifies the specific editing model responsible. Existing methods for detecting and attributing AI-generated images are insufficient for this problem, as they focus on determining whether an image was AI-generated/edited rather than whether it was edited from a particular base image. To bridge this gap, we propose EditTrack, the first framework for this image-editing detection and attribution problem. Building on four key observations about the editing process, EditTrack introduces a novel re-editing strategy and leverages carefully designed similarity metrics to determine whether a suspicious image originates from a base image and, if so, by which model. We evaluate EditTrack on five state-of-the-art editing models across six datasets, demonstrating that it consistently achieves accurate detection and attribution, significantly outperforming five baselines.

---

## 论文详细总结（自动生成）

根据您提供的论文元数据及摘要，以下是详细的中文总结。需要说明的是，所提供的PDF提取文本仅为验证页面，并未包含论文正文内容，因此本总结主要基于元数据中的摘要及常规学术推断。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：图像编辑检测与归因。具体而言，给定一张原始图像和一张可疑图像，要求判断后者是否由前者经AI编辑模型修改而来（检测），并进一步识别出具体使用的编辑模型（归因）。
- **研究动机**：现有的AI生成图像检测方法仅能判断图像是否由AI生成或编辑过，无法回答“该编辑是否源自某一特定原图”这一更加精细的取证问题。论文旨在填补这一空白。
- **整体含义**：为图像取证提供了更深入、更精细的分析能力，有助于追踪AI编辑图像的来源，对抗深度伪造或未经授权的图像修改。

### 2. 论文提出的方法论
- **核心思想**：基于编辑过程的四个关键观察，设计了一种新颖的“重新编辑（re‑editing）”策略，并结合精心设计的相似性度量，实现检测与归因。
- **关键技术细节**：
  - 输入：一张基准图像（原图）和一张可疑图像。
  - 重新编辑策略：对待测的可疑图像进行再次编辑（或利用某种编辑模型重演），比较重新编辑结果与原始编辑结果之间的特征，从而推断可疑图像是否由该基准图像通过某个AI编辑模型生成。
  - 相似度度量：设计了专门的相似性指标，用以量化重新编辑结果与可疑图像之间的一致性，进而判定是否源于特定原图并归属到具体编辑模型。
- **算法流程**（推测）：对每个候选编辑模型，以原图为输入，生成参考编辑图像；将可疑图像与参考编辑图像输入相似度网络，得到分数；根据分数做二分类检测和多分类归因。

### 3. 实验设计
- **使用的数据集/场景**：评估涵盖6个数据集（具体名称未提供，可能包含各类图像编辑基准）。
- **编辑模型**：测试了5种最先进的编辑模型（摘要中未列出名称）。
- **对比方法（benchmark）**：与5种基线方法进行比较（摘要未指明具体是哪些方法，可能是现有的AI生成图像检测器或图像溯源方法），结果显示EditTrack显著超越它们。

### 4. 资源与算力
- 所提供的摘要及元数据中**未提及**任何关于GPU型号、数量、训练时长等算力信息。需要查看论文正文才能确认。

### 5. 实验数量与充分性
- **实验数量**：涉及6个数据集 × 5个编辑模型，加上5个基线的对比，以及可能包含消融研究。按照摘要的描述，至少进行了大量的模型与数据集组合实验。
- **充分性与公平性**：在多种编辑模型和多个数据集上验证，并与多个基线对比，实验设计较为全面；显著优于基线，表明结果具有一定鲁棒性。但由于缺乏详细实验数据，无法判断是否存在特定的数据偏差或测试设定不公。

### 6. 论文的主要结论与发现
- EditTrack能够稳定、准确地实现图像编辑检测与归因，大幅优于现有基线方法。
- 该工作是第一个解决图像编辑检测与归因问题的框架，为AI辅助图像编辑的取证提供了新工具。

### 7. 优点
- **新颖的问题定义**：首次明确提出并研究图像编辑检测与归因问题，拓展了AI生成图像取证的范围。
- **创新的方法论**：基于编辑过程的观察提出重编辑策略和相似度度量，针对性强。
- **实验验证全面**：涵盖多个编辑模型和数据集，结果一致优秀，显示出方法的泛化能力。
- **实际应用价值高**：可应用于版权保护、假新闻检测、图像真实性验证等场景。

### 8. 不足与局限
- **实验细节未知**：由于缺少正文，无法评估模型复杂性、计算开销、对未见过编辑模型的泛化能力。
- **可能依赖已知编辑模型**：归因任务假设候选模型池已知，可能无法处理未知或新型编辑模型。
- **对非AI编辑方法的泛化性未知**：仅针对AI辅助编辑，传统图像处理软件（如Photoshop手动作）是否适用未提及。
- **真实场景鲁棒性**：未提及处理后图像经过压缩、裁剪、再编辑等二次操作的鲁棒性评价。
- **偏差风险**：如果训练数据中编辑模型类型有限，可能对某些编辑风格存在偏向。

（完）
