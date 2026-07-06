---
title: "VideoPhy: Evaluating Physical Commonsense for Video Generation"
title_zh: VideoPhy：评估视频生成的物理常识
authors: "Hritik Bansal, Zongyu Lin, Tianyi Xie, Zeshun Zong, Michal Yarom, Yonatan Bitton, Chenfanfu Jiang, Yizhou Sun, Kai-Wei Chang, Aditya Grover"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=9D2QvO1uWj"
tags: ["query:real-ir"]
score: 4.0
evidence: 评估文本转视频生成模型中的物理常识推理。
tldr: 针对文本转视频生成模型能否准确模拟物理世界的问题，本文提出VideoPhy基准，该基准通过设计涉及多种材质和物理交互的提示，系统地评估生成视频的物理常识遵循能力，实验揭示现有模型与真实物理模拟器之间存在明显差距，为视频生成模型的物理理解研究提供重要评测工具。
source: ICLR-2025-Accepted
selection_source: conference_retrieval
motivation: 现有视频生成模型能否作为物理世界模拟器尚不清楚。
method: 构建包含物理常识互动的提示数据集，评估生成视频的物理合理性。
result: 揭示了当前模型在物理常识遵循上的不足。
conclusion: 为视频生成模型的物理理解能力提供了评测工具。
---

## Abstract
Recent advances in internet-scale video data pretraining have led to the development of text-to-video generative models that can create high-quality videos across a broad range of visual concepts, synthesize realistic motions and render complex objects. Hence, these generative models have the potential to become general-purpose simulators of the physical world. However, it is unclear how far we are from this goal with the existing text-to-video generative models. To this end, we present VideoPhy, a benchmark designed to assess whether the generated videos follow physical commonsense for real-world activities (e.g. marbles will roll down when placed on a slanted surface). Specifically, we curate diverse prompts that involve interactions between various material types in the physical world (e.g., solid-solid, solid-fluid, fluid-fluid). We then generate videos conditioned on these captions from diverse state-of-the-art text-to-video generative models, including open models (e.g., CogVideoX) and closed models (e.g., Lumiere, Dream Machine). Our human evaluation reveals that the existing models severely lack the ability to generate videos adhering to the given text prompts, while also lack physical commonsense. Specifically, the best performing model, CogVideoX-5B, generates videos that adhere to the caption and physical laws for 39.6% of the instances. VideoPhy thus highlights that the video generative models are far from accurately simulating the physical world. Finally, we propose an auto-evaluator, VideoCon-Physics, to assess the performance reliably for the newly released models. The code is available here: https://github.com/Hritikbansal/videophy.

---

## 论文详细总结（自动生成）

# VideoPhy：评估视频生成的物理常识 论文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：当前基于海量网络视频数据预训练的文本到视频生成模型展现出强大的视觉合成能力，甚至被期许成为通用的“物理世界模拟器”。然而，这些模型在生成视频时是否真正理解并遵循物理常识（如物体在斜面上会滚落）尚未得到系统检验。
- **整体含义**：本文提出 **VideoPhy**，一个专为评估视频生成模型物理常识遵循能力而设计的基准测试，旨在量化现有模型与真正物理模拟之间的差距，并为该领域的未来研究提供评测工具。

## 2. 论文提出的方法论
- **核心思想**：通过构造一系列涉及物理交互的文本提示，驱动多种先进的文本转视频模型生成视频，再通过人工评估与自动评估器判断生成内容在物理层面的合理性。
- **关键环节**：
  - **提示数据集构建**：精心设计了覆盖不同材料类型交互的提示，如固体-固体、固体-流体、流体-流体等，确保场景包含明确的物理因果（如“弹珠放在倾斜表面会向下滚动”）。
  - **多模型视频生成**：选取开源（CogVideoX）与闭源（Lumiere, Dream Machine）等多个领先的文本转视频模型，在相同提示下生成视频。
  - **人类评估**：让人类评估者判断生成视频是否同时满足以下两点：①**语义一致性**（遵循文本描述）；②**物理合理性**（符合物理常识）。
  - **自动评估器 VideoCon-Physics**：为降低人工成本并加速新模型评估，提出一个自动化评判模型，以可信地评测未来发布模型的物理遵循能力。

## 3. 实验设计
- **评测数据集/场景**：VideoPhy 基准，包含大量基于不同材质组合与物理交互的文本提示，覆盖固体-固体、固体-流体、流体-流体等典型物理场景。
- **对比模型（基准）**：
  - 开源模型：CogVideoX-5B 等。
  - 闭源模型：Lumiere、Dream Machine 等。
- **评估指标**：
  - 人类评测的物理常识符合率（同时满足语义与物理定律的实例比例）。
  - 自动评估器 VideoCon-Physics 的评分。

## 4. 资源与算力
- 论文提供的摘要与元数据中**未明确说明**使用的 GPU 型号、数量、训练时长或推理所需的算力资源。若需确切信息，需参考论文正文。

## 5. 实验数量与充分性
- **实验规模**：
  - 在多个代表性文本转视频生成模型上进行了生成与评估。
  - 通过人类评估获得了各模型在提示集上的物理常识遵循率。
  - 额外设计了自动评估器 VideoCon-Physics，并可能包含消融实验或不同提示子集的分析（具体组数摘要未详述）。
- **充分性与客观性**：
  - 对比了开源与闭源多类模型，覆盖面较广。
  - 采用人工判断，并配套提出自动评估器以降低主观偏差，设计较为客观。
  - 由于仅依据摘要与元数据，无法确认是否包含系统性的消融实验、提示难度分级或跨领域泛化测试，但整体实验框架具备合理性。

## 6. 论文的主要结论与发现
- **模型物理常识严重不足**：当前最先进的文本转视频生成模型普遍无法可靠地模拟物理世界。表现最好的模型 **CogVideoX-5B** 仅能在 **39.6%** 的测试实例中生成既符合文本描述又遵循物理规律的视频。
- **现实与目标差距显著**：VideoPhy 清晰地揭示出：现有视频生成模型距离成为通用物理世界模拟器仍有巨大差距。
- **评估工具有效性**：所提出的自动评估器 VideoCon-Physics 可作为未来持续评测的有效手段，有助于追踪该领域的进展。

## 7. 优点
- **首创性**：首次系统性地构建面向视频生成物理常识评估的基准，填补了该领域的空白。
- **覆盖全面**：提示设计覆盖固体、流体等多种材料交互，物理场景多样。
- **实用性强**：提供自动评估器 VideoCon-Physics，降低了未来评测的人力成本，便于社区持续使用。
- **开源促进研究**：代码与基准公开，有助于复现与后续改进。

## 8. 不足与局限
- **物理现象覆盖有限**：仅涵盖部分材料组合与交互类型，可能遗漏更多复杂物理现象（如弹性碰撞、电磁、热力学等）。
- **人工评估主观性**：尽管严格设计，人类判断仍可能引入偏差，自动评估器的可靠性也需要进一步在大规模场景下检验。
- **未深入分析失败原因**：论文主要揭示差距，但对模型为何缺乏物理常识（训练数据、架构等）未做深入归因。
- **模型数量与版本**：对比的模型范围虽广，但可能未涵盖所有最新的视频生成模型；同时未提及推理效率等实际部署限制。

（完）
