---
title: "CompBench: Benchmarking Complex Instruction-guided Image Editing"
title_zh: CompBench：复杂指令引导图像编辑基准评测
authors: "Bohan Jia, Wenxuan Huang, Yuntian Tang, Junbo Qiao, Jincheng Liao, Shaosheng Cao, Fei zhao, Zhaopeng Feng, Zhouhong Gu, Zhenfei Yin, LEI BAI, Wanli Ouyang, Lin Chen, Fei Zhao, Zihan Wang, Yuan Xie, Shaohui Lin"
date: 2025-09-08
pdf: "https://openreview.net/pdf?id=Ky6vPLlzbV"
tags: ["query:real-ir"]
score: 9.0
evidence: 用于复杂指令引导图像编辑的基准，包含细粒度指令。
tldr: 针对现有图像编辑基准任务简单、指令粒度不足的问题，提出大规模基准CompBench，包含精细指令跟随、空间与上下文推理等复杂编辑场景，系统评估模型的精确操控能力，并提供指令解耦策略支持细粒度分析。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有基准常简化任务，缺乏对复杂指令的全面评估。
method: 构建包含细粒度指令和推理挑战的大规模编辑基准，采用MLLM-人协作框架。
result: 能够全面评测图像编辑模型的精确操控与推理能力。
conclusion: 为高级图像编辑模型的评估提供了重要平台。
---

## Abstract
While real-world applications increasingly demand intricate scene manipulation, existing instruction-guided image editing benchmarks often oversimplify task complexity and lack comprehensive, fine-grained instructions. To bridge this gap, we introduce CompBench, a large-scale benchmark specifically designed for complex instruction-guided image editing. CompBench features challenging editing scenarios that incorporate fine-grained instruction following, spatial and contextual reasoning, thereby enabling comprehensive evaluation of image editing models' precise manipulation capabilities. To construct CompBench, We propose an MLLM-human collaborative framework with tailored task pipelines. Furthermore, we propose an instruction decoupling strategy that disentangles editing intents into four key dimensions: location, appearance, dynamics, and objects, ensuring closer alignment between instructions and complex editing requirements. Extensive evaluations reveal that CompBench exposes fundamental limitations of current image editing models and provides critical insights for the development of next-generation instruction-guided image editing systems.

---

## 论文详细总结（自动生成）

# CompBench 论文总结

## 1. 核心问题与研究动机
- **背景**：现实应用（如创意设计、视觉内容生成）日益需要复杂的场景操控，但现有的指令引导图像编辑基准普遍简化任务、缺乏细粒度的操作说明。
- **核心问题**：既有基准无法全面衡量模型在**复杂指令**环境下的表现，尤其缺乏对精确操控、空间推理、上下文推理等高级能力的评测。
- **整体含义**：提出一个面向复杂指令的大规模基准，填补当前评估体系在任务复杂度与指令颗粒度上的空缺，推动下一代图像编辑系统的研发。

## 2. 方法论
- **整体框架**：**大模型-人协同构建框架（MLLM-human collaborative framework）**，结合自动化流程与人工校验来生成编辑任务。
- **任务管线**：设计针对复杂编辑的定制化构建流程，覆盖多样化的挑战场景。
- **指令解耦策略（Instruction Decoupling）**：
  - 将编辑意图分解为四个关键维度：**位置（Location）、外观（Appearance）、动态（Dynamics）、对象（Objects）**。
  - 这一解耦使得指令与复杂编辑需求之间形成更紧密的对齐，支持细粒度的能力分析。
- **技术关键**：不依赖传统的简单修改指令，而是构造包含空间关系、状态变化、多对象交互等复杂语义的指令，用于评测模型的**细粒度指令遵循**与**推理能力**。

## 3. 实验设计
- **数据集/基准**：构建了大规模基准 **CompBench**，包含丰富多样的复杂编辑场景。
- **评估场景**：涵盖精细指令跟随、空间推理、上下文推理等，跨越四个解耦维度（位置、外观、动态、对象）的组合。
- **对比方法**：对当前主流/前沿的图像编辑模型进行了系统评测（文中提及“Extensive evaluations reveal…” ，但未在摘要中列出具体模型名称）。
- **评估方式**：基于多维度指令解耦进行细粒度的指标分析，衡量模型在各维度上的操控精度与综合性能。

## 4. 资源与算力
- 摘要**未提及** GPU 型号、数量、训练时长等具体算力信息。构建过程仅需模型推理与人工协作，若无模型训练环节，算力需求主要来自多模态大模型（MLLM）推理和验证，但未给出量化描述。

## 5. 实验数量与充分性
- **实验量**：进行了大量评估，涉及多种当前图像编辑模型在 CompBench 上的表现对比（具体数目未在摘要列出，但从“Extensive evaluations”可知覆盖较广）。
- **充分性**：
  - 通过多维度解耦分析，能够诊断模型在不同能力轴上的薄弱环节，具备细粒度的诊断性。
  - 采用 MLLM-human 协同校验，提升数据质量与指令的合理性，减少偏差。
- **公平性**：使用统一的基准和维度划分测试所有模型，确保了评估的一致性。但未详述是否标准化了输入格式或后处理流程，公平性有待全文验证。

## 6. 主要结论与发现
- 当前图像编辑模型在 CompBench 的复杂指令任务上暴露出**根本性局限**。
- 模型在面对需要空间推理、上下文理解和多维解耦操控的任务时表现不足。
- 指令解耦策略有效揭示了模型在不同维度（如位置 vs. 外观）上的能力差异，为模型改进提供了关键洞察。
- CompBench 可作为下一代指令引导图像编辑系统的重要评测与发展平台。

## 7. 优点
- **基准设计前瞻性**：紧密贴合现实复杂编辑需求，超越简化任务的旧有基准。
- **细粒度分析**：提出的四维指令解耦，能够定位模型的具体能力短板，而非笼统的整体分数。
- **构建方法合理性**：MLLM 与人工协同，平衡了自动化规模与指令质量，减少纯自动生成带来的语义偏差。
- **推动研究导向**：为领域指出了“精确操控 + 推理”这一关键挑战，引导未来工作聚焦。

## 8. 不足与局限
- **基准覆盖**：尽管强调复杂指令，但摘要未说明覆盖了多少种编辑类型、场景多样性如何（如真实图像 vs. 合成图像、不同领域等），具体偏差风险需从全文判断。
- **评价指标**：摘要未提及自动评测与人工评测的具体标准或相关性，仅依赖四维划分可能无法完全反映主观感受与视觉质量。
- **应用限制**：基准主要用于指令遵循与推理能力的诊断，对模型生成图像的**视觉保真度、与原图的一致性**等常规维度关注不足。
- **算力透明度**：未透露构建与评估所需的计算资源，不利于复现或估算成本。
- **泛化性**：基准是否需要持续更新以应对新编辑范式（如基于扩散模型的新能力）尚未讨论。

（完）
