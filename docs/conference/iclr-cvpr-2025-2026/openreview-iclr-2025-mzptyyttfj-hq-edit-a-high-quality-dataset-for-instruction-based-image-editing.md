---
title: "HQ-Edit: A High-Quality Dataset for Instruction-based Image Editing"
title_zh: HQ-Edit：一个高质量的指令驱动图像编辑数据集
authors: "Mude Hui, Siwei Yang, Bingchen Zhao, Yichun Shi, Heng Wang, Peng Wang, Cihang Xie, Yuyin Zhou"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=mZptYYttFj"
tags: ["query:real-ir"]
score: 9.0
evidence: 利用GPT-4V和DALL-E3构建20万编辑对的高质量指令图像编辑数据集
tldr: 针对指令图像编辑数据质量低的问题，构建了含约20万编辑对的高质量数据集HQ-Edit，通过可扩展的自动流水线利用GPT-4V和DALL-E3生成多样化、高分辨率编辑示例。并提出基于GPT-4V的对齐度和连贯性指标，为指令编辑模型的训练与评测提供了坚实基础。
source: ICLR-2025-Accepted
selection_source: conference_retrieval
motivation: 现有指令编辑数据集依赖属性引导或人工反馈，质量受限，需高质量数据。
method: 利用大模型设计自动收集流水线，在线收集、扩充并生成输入输出图片和指令。
result: 构建了高分辨率且细节丰富的编辑数据集，并培育出高效的评价指标。
conclusion: 该数据集和指标显著提升了指令驱动图像编辑任务的数据质量和评测标准。
---

## Abstract
This study introduces HQ-Edit, a high-quality instruction-based image editing dataset with around 200,000 edits. Unlike prior approaches relying on attribute guidance or human feedback on building datasets, we devise a scalable data collection pipeline leveraging advanced foundation models, namely GPT-4V and DALL-E 3. To ensure its high quality, diverse examples are first collected online, expanded, and then used to create high-quality diptychs featuring input and output images with detailed text prompts, followed by precise alignment ensured through post-processing. In addition, we propose two evaluation metrics, Alignment and Coherence, to quantitatively assess the quality of image edit pairs using GPT-4V. HQ-Edits high-resolution images, rich in detail and accompanied by comprehensive editing prompts, substantially enhance the capabilities of existing image editing models. For example, an HQ-Edit finetuned InstructPix2Pix can attain state-of-the-art image editing performance, even surpassing those models fine-tuned with human-annotated data.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景**：指令驱动的图像编辑任务当前面临一个关键瓶颈——高质量、大规模且配对良好的编辑数据稀缺。现有数据集在构建时往往依赖属性引导或人工反馈，导致图像质量、指令多样性与编辑精度受限，从而阻碍了编辑模型的性能提升。
- **核心问题**：如何以可扩展的方式自动构建一个兼具高分辨率、丰富细节和精确对齐指令的图像编辑数据集，从而从根本上改善指令编辑模型的训练与评测基础。
- **整体含义**：该工作指出，通过利用先进的基础模型（GPT‑4V 与 DALL‑E 3）构建自动化数据生产流水线，可以系统性地克服人工标注成本高、质量参差不齐的问题，为指令图像编辑领域提供一个高水平的公开基准，并催生出更有效的自动评价指标。

## 2. 论文提出的方法论

- **核心思想**：将大规模预训练模型（视觉语言模型与图像生成模型）作为“数据工厂”，自动生成输入‑输出图像对及对应的编辑指令，并通过后处理保证对齐质量。
- **关键技术流程**（以文字描述）：
  1. **在线示例收集与扩充**：首先从互联网等渠道收集多样化的编辑示例，然后利用生成模型对示例进行扩充，覆盖更丰富的编辑类型与场景。
  2. **成对图像生成与文本提示构建**：基于收集或扩充的示例，使用 GPT‑4V 和 DALL‑E 3 生成成对的输入图像与编辑后的输出图像（diptychs），同时为每一对图像配以详细的文本编辑指令。
  3. **后处理对齐保障**：通过专门设计的后处理步骤进一步校准图像对与指令，确保编辑意图与实际图像变化之间高度一致。
  4. **数据集构成**：最终得到包含约 20 万次编辑操作的高分辨率数据集 **HQ-Edit**，每个样本包括高细节的输入‑输出图像及全面的编辑提示。
- **新评价指标**：同时提出两项基于 GPT‑4V 的定量评估指标——
  - **Alignment（对齐度）**：衡量编辑指令与图像变化之间的匹配程度。
  - **Coherence（连贯性）**：评估编辑后图像的自然度与视觉一致性。
  这两项指标为自动化评测编辑质量提供了新颖且可扩展的方案。

## 3. 实验设计

- **所用数据与场景**：摘要中并未列出具体的基准数据集名称，但实验逻辑围绕 HQ‑Edit 数据集展开。典型的评测场景可能包括常见指令编辑任务，如物体替换、属性修改、风格迁移等。
- **基准对比方法**：
  - **微调 InstructPix2Pix**：使用 HQ‑Edit 数据集对 InstructPix2Pix 模型进行微调，验证数据质量对模型性能的增益。
  - **人类标注数据微调模型**：将上述微调结果与基于人工标注数据训练的模型进行直接比较，以此凸显自动化数据集的有效性。
- **评估方式**：使用所提出的 Alignment 与 Coherence 指标，并很可能辅以人工评估或现有自动指标（如 CLIP 分数等），但具体细节在提供的摘要中未展开。

## 4. 资源与算力

- 论文摘要及元数据中**未明确提及**所使用的 GPU 型号、数量、训练时长或总计算消耗。
- 考虑到数据生成过程涉及调用 GPT‑4V 和 DALL‑E 3（通常为云端 API），实际算力消耗集中于模型微调，但这一部分同样缺乏数字说明。因此无法给出具体资源配置。

## 5. 实验数量与充分性

- 根据现有摘要，可以推断至少包含以下几组实验：
  - 基于 HQ‑Edit 微调 InstructPix2Pix 的主实验。
  - 与人类标注数据微调版本的对比实验。
- 其他可能包含但未在摘要中列出的实验：
  - 消融实验（如验证后处理、指标有效性）可能存在于原文，但显式信息不足。
- **充分性评价**：虽然摘要所述的对比逻辑清晰且直接针对核心问题（自动数据 vs. 人工数据），但受限于摘要信息，无法全面判定实验的多样性与覆盖度。从已公开的结论（“超越人类标注微调模型”）来看，主要实验具有较强的说服力，但仍需详阅正文以评估偏倚风险与泛化性。

## 6. 论文的主要结论与发现

- **HQ‑Edit 数据集**：成功构建了一个包含约 20 万次编辑指令的高质量、高分辨率数据集，显著丰富了指令编辑领域的数据支撑。
- **模型性能提升**：使用 HQ‑Edit 微调的 InstructPix2Pix 模型**达到了最先进的图像编辑性能**，甚至**超越了在人工标注数据上微调的同类模型**。
- **评价指标有效**：所提出的 Alignment 和 Coherence 指标能够通过 GPT‑4V 实现自动化且可靠的编辑质量评估，为后续研究提供了实用的评测工具。
- 总体而言，该工作证明了以大模型驱动的数据生产流水线可以替代昂贵的人工标注，同时推动指令编辑模型与评测体系的共同进步。

## 7. 优点

- **可扩展的自动化流程**：利用 GPT‑4V 和 DALL‑E 3 构建数据生成管道，大幅减少人工成本，易于扩展数据规模与多样性。
- **高数据质量**：生成图像为高分辨率且富含细节，编辑指令详尽、对齐精准，明显优于传统属性引导或粗粒度标注。
- **双重贡献**：不仅提供了一个高质量数据集，还附带两个基于 GPT‑4V 的自动评测指标，实现了数据与评测的共同提升。
- **实证效果显著**：仅通过微调现有模型即可取得超越人工数据的性能，验证了所提数据流水线的实际价值。
- **易复现与推广**：方法依托公开可用的大模型，流水线设计清晰，便于其他任务借鉴。

## 8. 不足与局限

- **对基础模型的依赖**：数据质量完全受限于 GPT‑4V 和 DALL‑E 3 的能力与内在偏差，可能引入系统性错误或创意局限。
- **真实场景覆盖度未知**：自动化生成的数据未必能完美模拟真实世界编辑需求的分布，存在领域偏差风险。
- **实验对比范围不详**：摘要仅提及与人工标注数据的对比，缺乏与其他数据集构建方法或更多基线模型的横向比较，验证广度存疑。
- **算力与成本透明性缺失**：未说明生成数据及模型训练的具体资源开销，难以评估其经济性。
- **指标局限性**：Alignment 和 Coherence 来源于同一个大模型（GPT‑4V），可能形成自我验证循环，其与人类评判的一致性尚需外部实证。
- **延伸应用受限**：微调实验仅展示在 InstructPix2Pix 上的结果，对其它编辑架构的通用增益未做验证。

（完）
