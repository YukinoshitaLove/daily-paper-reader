---
title: "Edit-R1: Unleashing Reasoning-Based Reinforcement Learning for Image Editing"
title_zh: Edit-R1：释放基于推理的强化学习用于图像编辑
authors: "Hanzhong Guo, Jie Wu, Jie Liu, Yu Gao, Zilyu Ye, Linxiao Yuan, Xionghui Wang, Yizhou Yu, Weilin Huang"
date: 2025-09-03
pdf: "https://openreview.net/pdf?id=hKWCGxuD5v"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于推理强化学习的图像编辑
tldr: 针对图像编辑中缺乏通用、细粒度奖励模型的问题，提出Edit-R1，设计基于链式思维推理的奖励模型Edit-RRM，将编辑指令分解为可验证原则并逐项评分，减少了奖励偏差和幻觉，在多种编辑任务上显著提升了指令遵循准确性和结果可解释性，为RLHF在图像编辑中的应用开辟了新路径。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有编辑奖励模型缺乏细粒度、可解释的评估，限制RLHF在编辑中的应用。
method: 提出Edit-R1，构建链式思维推理奖励模型（Edit-RRM）逐项验证编辑指令。
result: 提升了编辑对复杂指令的遵循度和结果可解释性。
conclusion: 推理奖励模型有效解决了图像编辑中的奖励偏差和幻觉问题。
---

## Abstract
While Reinforcement Learning from Human Feedback (RLHF) has become a pivotal paradigm for text-to-image generation, its application to image editing remains largely unexplored. 
A key bottleneck is the lack of a robust general reward model for all editing tasks. 
Existing edit reward models usually give overall scores without detailed checks, ignoring different instruction requirements and causing biased rewards. 
To address this, we propose Edit-R1, which boosts image editing models with a chain-of-thought (CoT) reasoning reward model (RRM). 
This Edit-RRM breaks instructions into verifiable principles, evaluates the edited images against each principle, and aggregates fine-grained scores to reduce hallucinations and provide more interpretable criteria. 
To build such an RRM, we first apply supervised fine-tuning (SFT) as a “cold-start” to generate CoT reward trajectories. Then, we introduce Group Contrastive Preference Optimization (GCPO), a reinforcement learning algorithm that leverages human pairwise preference data to reinforce our pointwise RRM. 
After building the RRM, we use GRPO to train editing models with this non-differentiable yet powerful reward model.
Extensive experiments demonstrate that our Edit-RRM surpasses powerful VLMs such as Seed-1.5-VL and Seed-1.6-VL as an editing-specific reward model, and we observe a clear scaling trend, with performance consistently improving from 3B to 7B parameters. Moreover, Edit-R1 delivers gains to editing models like FLUX.1-kontext, highlighting its effectiveness in enhancing image editing.

---

## 论文详细总结（自动生成）

# Edit-R1：释放基于推理的强化学习用于图像编辑

## 1. 论文的核心问题与整体含义
- **研究动机**：从人类反馈中学习（RLHF）已成为文生图领域的核心范式，但将其应用于图像编辑仍处于早期阶段。关键瓶颈在于缺少一个通用、鲁棒的奖励模型，能够精准评估各类编辑任务的结果。
- **核心痛点**：现有编辑奖励模型通常只输出一个整体分数，缺乏对指令中不同要求的细粒度检查，导致奖励偏差，且评估过程不可解释。
- **整体含义**：论文提出通过**链式思维推理**构建可解释、可逐项验证的奖励模型，从而为图像编辑模型提供更精确的反馈信号，真正释放基于推理的强化学习在编辑任务中的潜力。

## 2. 论文提出的方法论
- **整体框架 Edit-R1**：围绕“推理奖励模型（Edit-RRM）”设计强化学习流程，用于增强图像编辑模型。
- **Edit-RRM 核心思想**：
  - 将复杂的编辑指令**分解为多个可验证的原则**（如“保持背景不变”“调整色调至暖色”）。
  - 对编辑后的图像，**逐项验证**每个原则是否被满足。
  - 将各原则的评分聚合为细粒度分数，以此减少幻觉并提供人类可理解的评估依据。
- **构建 Edit-RRM 的两阶段训练**：
  - **冷启动监督微调（SFT）**：生成链式思维奖励轨迹（CoT reasoning trajectories），让模型初步学会推理和评分。
  - **强化学习微调：组对比偏好优化（GCPO）**：设计专用于训练逐点奖励模型的强化学习算法，利用人类成对偏好数据，强化模型对好坏编辑的区分能力。
- **编辑模型的强化学习训练**：使用**GRPO**算法，以训练好的不可微但强大的 Edit-RRM 作为奖励信号，优化下游图像编辑模型（如 FLUX.1-kontext）。

## 3. 实验设计
- **奖励模型评估**：
  - 与强视觉语言模型（VLMs）对比，如 Seed-1.5-VL、Seed-1.6-VL，验证 Edit-RRM 作为编辑特定奖励模型的优势。
- **编辑模型增益验证**：
  - 在主流的图像编辑模型（如 FLUX.1-kontext）上，应用 Edit-R1 训练框架，观察性能提升。
- **缩放趋势检验**：
  - 观察从 3B 到 7B 参数规模，Edit-RRM 的性能呈现出一致的提升趋势，验证方法的可扩展性。
- 论文中未明确列出所用编辑数据集的具体名称或 benchmark 细节，但摘要强调实验涵盖“多种编辑任务”。

## 4. 资源与算力
- **文中未明确说明**所使用的 GPU 型号、数量以及具体训练时长。仅可从实验部分推断出，模型规模从 3B 参数扩至 7B 参数，训练过程涉及 SFT、GCPO 和 GRPO 三个阶段，算力需求应较大，但缺乏可量化论据。

## 5. 实验数量与充分性
- **实验组别**：
  1. Edit-RRM 与 Seed-1.5/1.6-VL 等基线奖励模型的对比实验。
  2. 不同参数规模（3B 与 7B）下的性能缩放实验。
  3. 将 Edit-R1 框架应用于 FLUX.1-kontext 的增益实验。
- **充分性评价**：从摘要描述看，实验覆盖了奖励模型本身的竞争力、缩放行为以及对下游编辑模型的提升，结构较完整。但缺乏与更广泛奖励模型（如 CLIP-based 或其它编辑专用模型）的对比细节，数据集和评测指标也未在摘要中提及，客观公平性需阅读全文进一步确认。

## 6. 论文的主要结论与发现
- **推理奖励模型显著优于直接评分的奖励模型**：Edit-RRM 通过链式思维推理，提供的细粒度、可解释评分更准确，能减少奖励偏差和幻觉。
- **Edit-R1 有效提升图像编辑模型的指令遵循度**：使用基于 GRPO 和 Edit-RRM 的训练后，编辑模型能更好地完成复杂、多约束的编辑任务。
- **方法具有可解释性和缩放潜力**：模型输出可追溯的推理过程，且性能随参数规模增大持续提升，展现出良好的扩展前景。

## 7. 优点
- **创新的推理奖励模型设计**：首次将链式思维推理引入图像编辑奖励建模，从整体评分转向可逐项验证的原则性评估。
- **专为奖励模型设计的 GCPO 算法**：有效利用人类偏好数据，对齐逐点奖励评分，方法学上有新意。
- **结构化训练流程**：SFT 冷启动 + GCPO 强化奖励模型 + GRPO 优化编辑模型，框架清晰，逻辑自洽。
- **可解释性**：打破了奖励评估的“黑箱”，使得编辑失败的具体原因可见、可查。

## 8. 不足与局限
- **实验细节不足**：摘要未提供使用的编辑数据集、评测基准和关键指标，难以完全判断实验的全面性和可比性。
- **算力成本未披露**：缺乏资源消耗信息，削弱了方法的可复现性和实际部署参考价值。
- **可能的数据偏差**：依赖人类偏好数据进行 GCPO，如果偏好数据覆盖的编辑类型有限，可能限制模型的泛化能力。
- **编辑模型的单一验证**：仅提到 FLUX.1-kontext 的增益，对其他主流编辑模型（如 InstructPix2Pix、MagicBrush 等）的效果未知。
- **推理效率**：奖励模型需要生成链式推理文本，可能增加训练和推理延迟，但论文未讨论这一代价。

（完）
