---
title: Inductive Moment Matching
title_zh: 归纳矩匹配：一种新的少步生成模型
authors: "Linqi Zhou, Stefano Ermon, Jiaming Song"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pwNSUo7yUb"
tags: ["query:real-ir"]
score: 9.0
evidence: 无需蒸馏的少步生成模型训练新方法
tldr: 针对扩散模型推理慢及蒸馏训练不稳定问题，提出矩匹配自蒸馏（MMSD）方法，一种单阶段生成模型训练框架。MMSD无需预训练初始化，且保证分布级收敛，在ImageNet等数据集上以极少步数取得领先FID指标。该方法为快速高质量生成提供了简单稳定的解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1595, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 418, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 416, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1545, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 850, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 445, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 854, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1509, \"height\": 1863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1596, \"height\": 2073, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pwnsuo7yub/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1596, \"height\": 2072, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 904, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 920, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 809, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 384, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 1329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 553, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 543, \"height\": 110, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pwnsuo7yub/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 619, \"height\": 209, \"label\": \"Table\"}]"
motivation: 扩散模型采样慢，蒸馏训练不稳定且需大量调参。
method: 通过单阶段训练，匹配分布矩实现自蒸馏，支持一/少步采样。
result: 在ImageNet和CIFAR-10上以2-8步取得SOTA的FID值。
conclusion: MMSD以简单稳定的方式实现了高效生成，优于现有蒸馏方法。
---

## Abstract
Diffusion models and Flow Matching generate high-quality samples but are slow at inference, and distilling them into few-step models often leads to instability and extensive tuning. To resolve these trade-offs, we propose Moment Matching Self-Distillation (MMSD), a new class of generative models for one- or few-step sampling with a single-stage training procedure. Unlike distillation, MMSD does not require pre-training initialization and optimization of two networks; and unlike Consistency Models, MMSD guarantees distribution-level convergence and remains stable under various hyperparameters and standard model architectures. MMSD surpasses diffusion models on ImageNet-256x256 with 2.13 FID using only 8 inference steps and achieves state-of-the-art 2-step FID of 2.05 on CIFAR-10 for a model trained from scratch.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以中文、Markdown格式，对提供的论文《Inductive Moment Matching》进行结构化、深入、客观的总结。

# Inductive Moment Matching 论文总结

## 1. 论文的核心问题与整体含义

*   **核心问题**：当前主流的生成模型（如扩散模型和Flow Matching）面临一个“三难困境”：高质量生成、快速推理和稳定训练这三者难以同时兼得。
    *   **扩散模型**：生成质量高，但推理（采样）速度极慢，需要成百上千步。
    *   **蒸馏模型**：为了加速推理，将预训练的扩散模型蒸馏为少步模型，但这一过程通常不稳定，需要大量工程调优和正则化，且是两阶段训练（预训练+蒸馏）。
    *   **一致性模型**：虽然可以从头训练进行少步生成，但其训练同样面临不稳定性，容易崩溃，并且理论上缺乏分布级别的收敛保证。
*   **整体含义**：本文提出了Inductive Moment Matching（IMM），这是一个**单阶段、从头训练**的生成模型框架，旨在解决上述三难困境。IMM能够实现**一到数步的快速采样**，同时保证**分布级别的收敛**和**稳定的训练**，无需预训练模型或复杂的对抗训练。

## 2. 论文提出的方法论
IMM的核心思想是，**通过数学归纳法，学习一个能够将任意噪声水平分布直接映射到任意更低噪声水平分布的“一步采样器”**，并通过不断匹配模型自身的分布来引导其收敛到真实数据分布。

*   **核心思想与关键技术细节**：
    *   **问题建模**：基于随机插值理论，定义了一条从数据分布（`t=0`）到先验噪声分布（`t=1`）的连续路径。IMM的目标是学习一个确定性映射 `g_θ(x_t, s, t)`，它能将时刻 `t` 的样本 `x_t` 作为输入，并预测出时刻 `s`（`s < t`）的真实、无噪声样本 `x`。
    *   **“归纳”学习过程**：
        1.  **自举**：训练目标是最小化两个分布的差异：一个是模型直接从 `t` 时刻一步映射到 `s` 时刻产生的分布 `p_{θ_{s|t}}(x_s)`；另一个是模型先一步从 `t` 映射到中间时刻 `r` (`s < r < t`)，再一步从 `r` 映射到 `s` 时刻产生的分布 `p_{θ_{s|r}}(x_s)`。这迫使模型满足“一致性”，即从远距离映射和分步映射的结果是相同的。
        2.  **边界条件**：由于从 `t` 时刻到 `t` 时刻的映射是恒等映射（无需学习），这为“归纳”提供了一个确定的起点，确保了学习的稳定性。
    *   **矩匹配损失**：
        *   使用**最大平均差异（MMD）**来衡量上述两个分布之间的差异。MMD以**匹配分布的所有阶矩**。
        *   在实践中，使用拉普拉斯核函数从一批样本中估计MMD，公式参考原文。
        *   通过使用“stop gradient”技术，公式可简化为一种对比形式的损失，它同时吸引正样本对、排斥负样本对，从而稳定地匹配分布矩。
    *   **算法流程**：
        1.  从数据分布中采样真实图像 `x`，从先验分布中采样噪声 `ε`。
        2.  构建噪声样本 `x_t`。
        3.  采样目标时间步 `s` 和中间时间步 `r`。
        4.  生成的样本组：在线模型从 `x_t` 生成目标样本，目标模型（`stop gradient`）从 `x_t` 生成中间样本 `x_r`，再从 `x_r` 生成目标样本。
        5.  计算MMD损失，更新在线模型 `θ`。
        6.  重复以上步骤，通过指数移动平均更新目标模型。

## 3. 实验设计

*   **数据集与场景**：
    *   **CIFAR-10**：无条件图像生成。
    *   **ImageNet-256x256**：类别条件图像生成。
*   **对比方法**：论文进行了全面对比，涵盖了多个类别。
    *   **扩散 & Flow模型**：DDPM， NCSN++， EDM， Flow Matching， Rectified Flow 等。
    *   **蒸馏模型**：Progressive Distillation, KD, DMD， CTM， CD 等。
    *   **从头训练的少步模型**：iCT, ECT， sCT， Shortcut Models。
    *   **GAN/自回归模型**：BigGAN， StyleGAN-XL， VQGAN， VAR 等。
*   **评估指标**：主要采用Fréchet Inception Distance (FID)。

## 4. 资源与算力
*   论文未明确提及所用GPU的具体型号、数量及单次训练的总时长。
*   论文在附录的实验设置中提供了训练所用的**架构**、**参数量**、**训练步数**和**批量大小**等关键信息。
    *   例如，在ImageNet-256x256上，其主要结果基于DiT-XL/2架构（675M参数），训练了**1.2M次迭代**，批量大小为**4096**。这些参数可以用于估算所需的算力规模，属于大规模实验。
    *   CIFAR-10上的实验使用了55M参数的模型，训练了400K次迭代。

## 5. 实验数量与充分性

实验设计**非常全面且充分**，遵循了客观、公平的原则。
*   **大量实验组合**：在两个标准数据集上进行了主要结果对比，并进行了多组消融实验。
*   **主要结果对比**：在CIFAR-10和ImageNet-256x256上与超过20种主流方法进行了FID对比，且严格区分了方法类别（蒸馏、从头训练等）。
*   **消融实验**：
    *   **稳定性分析**：对比了IMM与一致性模型在不同时间嵌入（位置编码 vs. 傅里叶编码）下的训练稳定性，证明了IMM的鲁棒性。
    *   **参数研究**：研究了粒子数 `M`、噪声条件缩放 `c`、映射函数 `r(s,t)` 的选择、损失权重 `w(s,t)` 等关键超参数对性能的影响。
    *   **结构选择**：对比了不同的流轨迹（Cosine， OT-FM）、网络参数化（Identity， Simple-EDM， Euler-FM）以及采样器类型（直推式 vs. 重启式）的效果。
*   **可扩展性分析**：验证了IMM在模型大小（DiT-S/B/L/XL）和推理步数（1/2/4/8步）增加时的性能扩展趋势，表现出强相关性。

## 6. 论文的主要结论与发现

*   **有效性**：IMM在少步生成的场景下达到了顶级性能。在ImageNet-256x256上，以**8步**推理取得了**1.99的FID**，超越了相同架构的扩散模型（250步）和其他从头训练的少步模型。
*   **稳定性**：IMM成功解决了此前少步生成模型（如一致性模型）的训练不稳定问题。它在标准架构下、对各种超参数不敏感，无需特殊训练技巧。
*   **理论支撑**：
    *   证明了IMM在无限数据和网络容量下，能够保证分布级别的收敛。
    *   揭示了一致性模型是IMM在特定设置下的一个特例，为理解CM的不稳定性提供了新视角。
*   **简洁性**：IMM是一个单阶段、单网络、单一损失函数的训练框架，极大地简化了少步生成模型的训练流程。

## 7. 优点
*   **方法论创新**：通过“归纳式自举”和“分布矩匹配”的结合，巧妙地解决了单阶段训练少步生成模型的理论和稳定性难题。
*   **强大的稳定性**：这是其最突出的优点。实验证明它在多种配置下均能稳定收敛，无需像其他方法那样进行繁琐的调参。
*   **理论清晰**：有严谨的定理保证收敛性，并清晰地建立了与其他方法（特别是CM， Diffusion GAN）的联系，加深了领域内的理解。
*   **实验扎实**：实验覆盖全面，从性能对比、稳定性测试、可扩展性分析到消融实验，充分验证了方法的有效性和鲁棒性。
*   **简洁高效**：单阶段、单模型、单损失的设计使其易于复现和实际应用。

## 8. 不足与局限
*   **算力需求未明确**：论文未报告具体的GPU消耗和训练时长，这使得评估其完全复现的成本变得困难。
*   **粒子数`M`的权衡**：MMD估计的准确性与`M`（粒子数）正相关，但增大`M`会减少每个批次的`t`的多样性，从而影响收敛速度。论文指出需要找到一个平衡点，这引入了一个额外的超参数。
*   **数据集局限**：实验主要在CIFAR-10和ImageNet上进行，未在更大、更复杂的数据集（如文生图COCO，或其他模态如文本、音频）上验证其有效性。尚未触及大规模文本到图像的生成任务。
*   **缺乏人类评估**：评估仅依赖FID指标。虽然FID与视觉质量强相关，但在某些情况下可能无法完全反映人类偏好，缺少用户研究作为补充。
*   **采样器未充分探索**：虽然论文提到重启采样器可能获得更好结果，但主要结果都基于直推式采样，对重启采样器的探究留给了未来工作。

（完）
