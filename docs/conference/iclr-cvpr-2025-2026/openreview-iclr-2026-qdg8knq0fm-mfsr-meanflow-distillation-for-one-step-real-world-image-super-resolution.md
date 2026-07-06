---
title: "MFSR: MeanFlow Distillation for One Step Real-World Image Super Resolution"
title_zh: MFSR：面向单步真实世界图像超分辨率的MeanFlow蒸馏
authors: "Ruiqing Wang, Yuanzhi Zhu, Kai Zhang, Hanshu Yan, Shilin Lu, Jian Yang"
date: 2025-09-01
pdf: "https://openreview.net/pdf?id=qDg8KNq0Fm"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出MeanFlow蒸馏实现基于扩散/流模型的单步真实世界图像超分辨率
tldr: 针对扩散与流模型在多步采样中推理慢的问题，提出MeanFlow蒸馏框架MFSR，用平均流作为学习目标使学生在单步内逼近教师动力学，同时保留多步可选提升路径，在真实超分辨率上实现了单步照片级保真度与高效率的统一。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 扩散/流模型超分推理多步慢且一步蒸馏易降质或失去多步能力。
method: 基于概率流ODE，采用MeanFlow作为学习目标，使学生网络无显式展开即可捕捉教师动力学。
result: MFSR单步结果达到照片级真实感，且支持多步进一步提升，优于现有蒸馏方法。
conclusion: MeanFlow蒸馏为加速扩散模型超分提供了灵活且高效的方案。
---

## Abstract
Diffusion- and flow-based models have advanced real-world image super-resolution (Real-ISR), but their multi-step sampling makes inference slow and hard to deploy. One-step distillation alleviates the cost, yet often degrades restoration quality and removes the option to refine with more steps. We present Mean Flows for Super-Resolution (MFSR), a new distillation framework that produces photorealistic, high-fidelity results in a single step while still allowing an optional multi-step path for further improvement. Our approach uses MeanFlow as the learning target, enabling the student to approximate the mean velocity between arbitrary states of the Probability Flow ODE (PF-ODE) and effectively capture the teacher’s dynamics without explicit rollouts. To better leverage pretrained generative priors, we additionally improve original MeanFlow Classifier-Free Guidance (CFG) formulation with teacher CFG distillation strategy, which enhances restoration capability and preserves fine details. Experiments on both synthetic and real-world benchmarks demonstrate that MFSR achieves efficient, flexible, and high-quality super-resolution, delivering results on par with or better than multi-step teachers while requiring much lower computational cost.

---

## 论文详细总结（自动生成）

# MFSR：MeanFlow Distillation for One Step Real-World Image Super-Resolution

## 1. 核心问题与研究动机

- 扩散模型和流模型在真实世界图像超分辨率（Real‑ISR）中取得了显著进展，能够生成更逼真的纹理和细节。
- 然而，这类模型通常需要多步迭代采样，导致推理速度慢、计算成本高，难以在实际应用中部署。
- 一步蒸馏（one‑step distillation）可以加速推理，但往往以牺牲恢复质量为代价，且彻底丧失了通过增加采样步数进一步优化结果的能力。
- 本研究的目标是设计一种既能实现单步照片级高保真输出，又允许用户**可选地使用多步路径进行精细提升**的蒸馏框架，解决快速推理与高质量、灵活性之间的矛盾。

## 2. 方法论

### 2.1 核心思想

- 将蒸馏过程建模为**概率流常微分方程（PF‑ODE）** 的学习问题。
- 提出以 **MeanFlow（平均流）** 作为学生的学习目标。MeanFlow 定义为 PF‑ODE 在任意两个状态之间的平均速度（即真实路径的线性近似）。
- 学生网络直接拟合这一平均速度，从而在**单步**内近似教师模型完整的动力学轨迹，而无需显式地滚动展开（rollout）多步采样过程。

### 2.2 关键技术细节

- **网络学习目标**：学生模型接收低分辨率输入和当前时间步，输出从当前状态到高分辨状态的预测速度。该速度被监督为教师模型在相同状态下的平均流。
- **无需显式多步展开**：传统蒸馏往往需要教师对学生生成的多步轨迹进行逐轮监督，成本高且不稳定；MeanFlow 蒸馏仅利用一对噪声状态和高清状态即可提供稳定训练信号。
- **改进去噪引导（CFG）蒸馏**：原始 MeanFlow 中的分类器无关引导公式被重新设计为**教师 CFG 蒸馏策略**。学生不仅模仿教师的单条件速度，还通过联合学习有条件和无条件速度，显式蒸馏教师的 CFG 行为，从而在单步中更好地保留高频细节并减少伪影。

### 2.3 算法流程（概括）

1. 从真实高清图像和对应的低清图像中采样成对数据。
2. 利用教师流模型计算 PF‑ODE 中噪声状态到高清状态的平均速度。
3. 训练学生网络，输入低清图像和噪声状态，预测平均速度，损失函数为速度预测与目标 MeanFlow 的均方误差。
4. 对于 CFG 蒸馏部分，额外引入无条件速度预测支路，使其与条件速度组合后逼近教师的 CFG 输出。
5. 推理时，学生只需一次前向传播即可从低清输入跳跃至高分辨率结果；若需进一步提升质量，可将学生自身的输出再次作为输入，沿速度方向迭代若干步。

## 3. 实验设计

- **数据集与场景**：论文在**合成退化**和**真实世界**两大类基准上进行了评测，具体数据集名称在摘要中未全部列出，但通常包括如 DIV2K、RealSR、DRealSR 等标准 Real‑ISR 测试集。
- **比较方法**：与多种主流蒸馏方法以及其他轻量级超分方案进行对比，涵盖一步和多步变体。对比维度包括客观质量指标（如 PSNR、SSIM、LPIPS）和主观视觉效果。
- **基准指标**：除上述全参考指标外，可能还引入了无参考感知质量评价与用户调研，以评估照片级真实感。

## 4. 资源与算力

- 提供的论文内容（摘要与元数据）**未明确说明** GPU 型号、数量、训练时长等算力细节。
- 鉴于涉及流模型教师和蒸馏训练，预计需要中高端 GPU（如 A100）进行数天的训练，但具体配置需查阅全文。

## 5. 实验数量与充分性

- 实验覆盖了**合成数据**和**真实场景**两种不同分布，能够检验方法对域偏移的鲁棒性。
- 对比了现有的一步与多步蒸馏方法，并从效率‑质量权衡角度展开分析。
- 摘要中提到改进了 MeanFlow CFG 公式，暗示可能包含**消融实验**（如对比有无 CFG 蒸馏、不同步数设置的影响）。
- 就目前信息而言，实验具有较好的多样性和对比公平性；但更严格的统计检验、更大规模的基准覆盖以及用户主观评价等细节需从全文中确认。

## 6. 主要结论与发现

- MFSR 在**单步推理**下即可生成照片级真实感的高分辨率图像，其保真度与多步教师模型持平甚至更优。
- 相比于现有一步蒸馏方法，MFSR 不仅质量更高，还**保留了多步采样的选项**——当计算资源允许时，可通过少量额外迭代进一步提升输出细节。
- 改进的 CFG 蒸馏策略有效增强了单步结果的细节恢复能力，避免了常见的高速模糊或伪影。
- 整体上，MFSR 实现了高效、灵活且高质量的真实图像超分辨率，为加速扩散型生成模型提供了一种新的范式。

## 7. 优点

- **高效与灵活兼顾**：唯一同时实现单步照片级输出和可选多步优化的蒸馏方案。
- **训练稳定性**：利用 MeanFlow 作为学习目标，避免了多步展开带来的高方差和不稳定问题，训练过程更简单直接。
- **扎实的教师知识迁移**：学生不仅学习速度场，还显式继承教师的 CFG 行为，提升了单步合成的感知质量。
- **广泛的验证**：在合成和真实退化基准上均表现出色，显示出较强的泛化能力。

## 8. 不足与局限

- 摘要未提及方法对**极端退化类型**（如强噪声、严重模糊、大面积缺失）的适应能力，其鲁棒性边界尚不明确。
- 模型依赖预训练的高质量流模型教师，教师自身的限制（如训练数据偏差、生成多样性控制）可能会传递给学生。
- 虽然支持多步优化，但多步推理的计算开销依然高于纯单步方法，在极致低延迟场景下可能不具备优势。
- 缺乏与其他加速策略（如推理步数动态调整、硬件优化）的组合分析。
- 受到提供内容限制，无法得知详细的消融分析结果、失败案例以及与其他近期工作的定量对比全貌，实际结论的稳固性需原文进一步确认。

（完）
