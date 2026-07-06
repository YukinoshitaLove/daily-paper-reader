---
title: "GIE-Bench: Towards Grounded Evaluation for Text-Guided Image Editing"
title_zh: GIE-Bench：面向文本引导图像编辑的接地评测基准
authors: "Yusu Qian, Jiasen Lu, Tsu-Jui Fu, Xinze Wang, Chen Chen, Yinfei Yang, Wenze Hu, Zhe Gan"
date: 2025-09-09
pdf: "https://openreview.net/pdf?id=BdzayGKKVc"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于功能正确性和内容保留的文本引导图像编辑接地评测基准
tldr: 针对文本引导图像编辑评测依赖CLIP精度不足的问题，提出GIE-Bench基准，从功能正确性和内容保留两个维度进行更接地的评价。功能正确性通过自动生成的选择题验证编辑目标是否实现；内容保留利用目标感知掩码确保未编辑区域视觉一致，为编辑模型提供了更细致的性能诊断。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有评测依赖CLIP不够精确，无法有效衡量编辑质量和内容保留。
method: 提出GIE-Bench，自动生成选择题评测功能正确性，并用目标感知掩码评测内容保留。
result: 能够更精确地评估编辑模型在实现指令变化和保持非目标区域一致性方面的表现。
conclusion: 为文本引导图像编辑提供了更接地气的标准评测工具，揭示模型优缺点。
---

## Abstract
Editing images using natural language instructions has become a natural and expressive way to modify visual content; yet, evaluating the performance of such models remains challenging. Existing evaluation approaches often rely on image-text similarity metrics like CLIP, which lack precision. In this work, we introduce a new benchmark designed to evaluate text-guided image editing models in a more grounded manner, along two critical dimensions: functional correctness, assessed via automatically generated multiple-choice questions that verify whether the intended change was successfully applied; and image content preservation, which ensures that non-targeted regions of the image remain visually consistent using an object-aware masking technique and preservation scoring. The benchmark includes over 1000 high-quality editing examples across 20 diverse content categories, each annotated with detailed editing instructions, evaluation questions, and spatial object masks. We note that our benchmark does not cover global editing tasks such as full style transfer, which remain important but are outside our current scope. We conduct a large-scale study comparing GPT-Image-, the latest flagship in the text-guided image editing space, against several state-of-the-art editing models, and validate our automatic metrics against human ratings. Results show that GPT-Image-1 leads in instruction-following accuracy, but often over-modifies irrelevant image regions, highlighting a key trade-off in the current model behavior. GIE-Bench provides a scalable, reproducible framework for advancing more accurate evaluation of text-guided image editing.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
*   **研究背景与动机**：文本引导的图像编辑模型发展迅速，但对其性能的评估仍严重依赖 CLIP 等图像-文本相似度指标，这些指标缺乏精确性，难以准确衡量编辑是否成功以及非编辑区域是否被破坏。
*   **核心问题**：如何设计一个更精确、更接地气的基准，来系统诊断文本引导图像编辑模型的两大关键能力——**功能性正确**（是否准确执行了指令）与**内容保真**（非目标区域是否保持一致）。
*   **整体含义**：论文提出 GIE-Bench，旨在为这一领域提供一个可扩展、可复现且能细致区分模型优缺点的标准化评测框架，从而推动更精准的模型研发与比较。

## 2. 论文提出的方法论
*   **核心思想**：绕开模糊的整体相似度，转而用两个模块化、可解释的维度对编辑模型进行“接地”评测。
*   **功能性正确性评测**：
    *   **方式**：对每一条编辑指令，自动生成一组**选择题**，用于验证预期修改是否实现。
    *   **机制**：通过检验模型是否能正确回答关于图像变更后状态的具体问题，来量化指令遵循的准确度，避免 CLIP 评分可能出现的虚高。
*   **图像内容保留评测**：
    *   **方式**：利用**目标感知掩码**技术，将图像划分为“待编辑区域”与“非编辑区域”。
    *   **保留评分**：专门计算非目标区域在编辑前后的视觉一致性，确保模型没有在无关区域引入不必要的修改或伪影。
*   **数据构建**：基准包含超过 **1000 个高质量编辑示例**，横跨 **20 个不同的内容类别**，每个样本均配备了详细的编辑指令、评测选择题及空间对象掩码。

## 3. 实验设计
*   **基准数据集**：所提出的 **GIE-Bench** 自身，规模为 1000+ 样本，覆盖 20 个类别。
*   **评测维度**：功能性正确性（基于选择题的指令遵循得分）和内容保留（目标感知掩码后的未编辑区域一致性得分）。
*   **对比方法**：将最新的旗舰级商业模型 **GPT-Image-1**，与多款当前最先进的（state-of-the-art）文本引导图像编辑模型进行了大规模横向比较。（论文摘要中未具体列出所有对比模型名称，但明确了对比对象的选取范围）
*   **指标验证**：将所提出的自动评测指标与人类主观评分进行了相关性校验，以证明其有效性。

## 4. 资源与算力
*   论文所提供的摘要及元数据中 **未明确提及** 具体的算力配置信息，例如 GPU 型号、数量、模型训练或大规模推理的时长等。由于 GIE-Bench 主要是一个评测基准，其算力消耗应主要集中在编辑模型的前向推理和自动指标的计算上，但具体资源细节未被披露。

## 5. 实验数量与充分性
*   **主要实验**：在 1000+ 样本、20 个类别的标准集上，对包括 GPT-Image-1 在内的多款 SOTA 模型进行了双维度（功能正确+内容保留）的系统评测。
*   **验证实验**：额外设计了将自动评测结果与人类评分进行对齐的验证环节，以证明评价标准的可靠性。
*   **充分性分析**：基准的设计涵盖了多样的场景和指令类型，且选择了具有代表性的商业与前沿模型进行对比。通过从两个互补且关键的角度拆解评测，同时辅以人工校验，实验设计在给定的基准范围内是客观且公平的，能够有效揭示不同模型的典型优缺点与行为模式。

## 6. 论文的主要结论与发现
*   **模型表现差异**：GPT-Image-1 在指令遵循功能性方面表现最突出，但其在内容保留维度上存在明显缺陷，经常**对无关的图像区域进行过度编辑**。
*   **核心权衡**：实验清晰地揭示了当前模型行为的一个关键权衡——**追求高度准确的指令执行，往往以牺牲非目标区域的内容一致性为代价**。
*   **框架价值**：GIE-Bench 提供了一个有效的、与人类判断相吻合的诊断工具，能识别出单纯依赖 CLIP 等指标无法发现的模型薄弱点，例如内容保留能力的不足。

## 7. 优点（方法与实验亮点）
*   **维度创新**：首次明确将评测解构为“功能正确性”和“内容保留”两个直观且关键的独立维度，诊断粒度极细。
*   **自动化与可扩展**：采用自动生成选择题和目标感知掩码的方法，使整个评测流程高度自动化、可复现，便于未来持续扩展更多样本。
*   **与人类对齐**：主动验证了自动指标与人类评分的一致性，大幅增强了基准的内部效度与说服力。
*   **揭示深层问题**：成功量化并暴露了顶级模型“指令遵循”与“非目标区域保真”之间的内部张力，为模型优化指明了具体方向。

## 8. 不足与局限
*   **任务覆盖面有限**：论文明确指出基准当前 **不涵盖全局编辑任务**，例如完整的风格迁移，这使得其评测范围主要限于局部或对象级编辑，无法全面评估模型的风格化能力。
*   **对比方法细节缺失**：摘要未列出除 GPT-Image-1 以外的具体对比模型信息，无法直接评估所选 SOTA 代表的全貌与时效性。
*   **内容类别偏差风险**：尽管已覆盖 20 个类别，但对于真实世界中极为多样化的编辑意图与对象类型，1000 余个样本可能仍存在覆盖度偏差，泛化性有待后续更大规模验证。
*   **应用限制**：作为基准，其本身不直接提升编辑模型性能，仅为工具；同时，其选择题生成和掩码技术的质量会直接影响评价的准确性，可能存在构建过程中的噪声。

（完）
