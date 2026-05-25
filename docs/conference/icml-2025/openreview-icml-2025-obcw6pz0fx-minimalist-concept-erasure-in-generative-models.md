---
title: Minimalist Concept Erasure in Generative Models
title_zh: 生成模型中的极简概念擦除
authors: "Yang Zhang, Er Jin, Yanfei Dong, Yixuan Wu, Philip Torr, Ashkan Khakzar, Johannes Stegmaier, Kenji Kawaguchi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oBCw6PZ0fX"
tags: ["query:real-ir"]
score: 4.0
evidence: 生成模型中的概念擦除
tldr: 该工作针对生成模型中概念擦除方法易过度修改、损害模型整体效用的弊端，提出基于最终生成输出分布距离的最小修改擦除目标。通过可微优化和端到端反向传播实现高效训练，在移除特定概念的同时最大程度保留模型生成能力，为生成模型的安全合规应用提供了有效工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 1083, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1426, \"height\": 1785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 1172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1765, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 900, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1423, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 1093, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1783, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-obcw6pz0fx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1779, \"height\": 850, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 1083, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 663, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 690, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 802, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-obcw6pz0fx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 791, \"height\": 540, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法往往对模型进行过多修改，牺牲了模型的整体生成质量。
method: 提出基于最终输出分布距离的最小化擦除目标，并利用端到端可微优化。
result: 在移除不安全概念时，模型生成性能的下降远小于以往方法。
conclusion: 该方法实现了安全和版权保护与模型实用性之间的更好平衡。
---

## Abstract
Recent advances in generative models have demonstrated remarkable capabilities in producing high-quality images, but their reliance on large-scale unlabeled data has raised significant safety and copyright concerns. Efforts to address these issues by erasing unwanted concepts have shown promise. However, many existing erasure methods involve excessive modifications that compromise the overall utility of the model.
In this work, we address these issues by formulating a novel minimalist concept erasure objective based *only* on the distributional distance of final generation outputs. 
Building on our formulation, we derive a tractable loss for differentiable optimization that leverages backpropagation through all generation steps in an end-to-end manner. 
We also conduct extensive analysis to show theoretical connections with other models and methods. 
To improve the robustness of the erasure, we incorporate neuron masking as an alternative to model fine-tuning. 
Empirical evaluations on state-of-the-art flow-matching models demonstrate that our method robustly erases concepts without degrading overall model performance, paving the way for safer and more responsible generative models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**：以FLUX、SD3.5为代表的最新生成模型在生成高质量图像方面能力强大，但其训练依赖大规模、无标注的网络数据，这导致模型可能生成不安全内容（如NSFW图像、武器）、侵犯版权（如生成受保护的IP角色、模仿艺术家风格）或被滥用于制造虚假信息。
*   **核心问题**：现有概念擦除方法（Concept Erasure）旨在从模型中移除这些有害概念。然而，这些方法通常对模型参数进行**过度修改**，严重损害了模型的整体生成能力、通用性和图像质量，导致“杀敌一千，自损八百”的局面。
*   **整体含义**：本文提出一个 **“极简概念擦除 (Minimalist Concept Erasure)”** 框架，其核心思想是：在移除目标有害概念的同时，对模型和其生成过程施加**最小程度的侵入性改变**，从而在模型安全性（移除了概念）与模型效用（保持了生成质量）之间取得最佳平衡。

### 2. 论文提出的方法论
*   **核心思想**：
    *   **仅关注最终输出**：不同于许多现有方法在生成过程的每一步都施加监督信号，本方法**仅以最终生成的完整图像作为优化目标**，允许模型自主学习一个最优的生成轨迹来达成擦除目的。
    *   **最小化分布距离**：将擦除问题形式化为一个优化问题，目标是在保持中性概念（C<sub>N</sub>）生成分布不变的前提下，最小化针对有害概念（C<sub>R</sub>）的条件生成概率。

*   **关键技术细节**：
    *   **损失函数设计**：推导出一个由两部分组成的可处理损失函数上界。
        1.  **擦除损失 (Erasure Loss, L<sub>r</sub>)**：最大化生成结果与目标概念之间的不相关性，本质上是通过最小化一个KL散度上界，最终转化为一个均方误差（MSE）项。该损失引导模型，当接到有害概念提示时，生成的图像应等同于原模型在**空文本（或中性文本）** 提示下的生成结果。
        2.  **保持损失 (Preservation Loss, L<sub>p</sub>)**：确保在生成中性概念时，修改后的模型与原模型的输出分布保持一致，同样转化为MSE项。通过超参数 $\beta$ 平衡擦除与保持。
    *   **端到端优化与梯度检查点**：为实现“仅关注最终输出”，通过整个生成过程（所有采样步骤）执行**端到端的反向传播**。为解决长序列反向传播导致的内存爆炸问题，采用**步骤级梯度检查点 (Step-wise Gradient Checkpointing)** 技术，实现内存消耗与生成步数无关的恒定成本。
    *   **神经元掩码 (Neuron Masking)**：摒弃传统的模型微调（fine-tuning），转而学习一个二值掩码 $M$，直接“切除”模型中与目标概念相关的神经元连接（$\theta = M \odot \theta'$）。这种方法更鲁棒，更像是在“拔除”概念对应的物理连接，而非进行可能被对抗攻击绕过的“虚假对齐”。

*   **算法流程简述**：
    1.  使用原模型为有害概念（C<sub>R</sub>）与中性概念（C<sub>N</sub>）提示分别生成成对的图像。
    2.  利用这些图像对，通过可微的掩码参数，并结合步骤级梯度检查点技术，对整个生成流程进行端到端优化，以最小化上述总损失函数 $\mathcal{L}$。

### 3. 实验设计
*   **应用场景与模型**：实验主要基于当前最先进的12B参数流匹配模型 **FLUX.1-Schnell**。
*   **评估概念与数据集**：评估了四类有害概念，并使用GPT-4o为每类概念生成“包含该概念的正常文本提示”作为测试集（未在训练中使用）。
    *   **不适当物品 (Inappropriate Objects)**：枪支、刀、毒品。
    *   **知识产权角色 (IP Characters)**：绿巨人、超人、金刚狼等。
    *   **艺术风格 (Art Styles)**：梵高、毕加索、莫奈等。
    *   **裸体 (Nudity)**：特别用于鲁棒性评估。
*   **对比方法 (Benchmark)**：选择了可在流匹配DiT模型上应用的方法作为基线。
    *   **概念擦除方法**：ESD, CA, SLD, EAP。
    *   **流模型编辑方法**：FlowEdit。
*   **评估指标**：
    *   **擦除成功率 (ACC ↓)**：使用LLaVA对生成图像进行目标概念检测的成功率。
    *   **提示词对齐度 (CLIP ↑)**：评估生成图像与文本提示的匹配程度。
    *   **图像质量 (FID ↓)**：在LAION-5k提示集上计算，衡量生成图像的保真度。
    *   **结构相似度 (SSIM ↑)**：衡量擦除后图像与原始模型生成图像的结构相似性，用于评估“最小改变”。
*   **鲁棒性评估**：使用四种对抗攻击/真实用户提示数据集（Ring-A-Bell, MMA-Diffusion, P4D, I2P）测试方法在“裸体”概念上的抗攻击能力。

### 4. 资源与算力
*   **硬件配置**：论文在训练配置表格（Table 6）中明确指出，所有实验均在 **1个 NVIDIA H100 GPU** 上完成。
*   **训练参数**：训练步数为400步（Steps），批大小（Batch size）为4。

### 5. 实验数量与充分性
*   **实验组数**：实验设计较为全面，包含：
    *   **主实验**：针对三类不同性质概念（物体、角色、风格），与5种基线方法进行完整指标对比。
    *   **鲁棒性实验**：针对1类更敏感概念（裸体），在4个对抗数据集上对7种方法（5基线+本文+原始模型）进行评估。
    *   **消融实验**：至少包含6组消融研究，探究了提示词过滤、$\beta$ 超参数、掩码目标模块选择、优化步数、擦除数据集规模等因素的影响。
*   **充分性与客观公平性评估**：实验覆盖面广，消融研究深入，鲁棒性测试也采用了社区公认的对抗基准。对比基线时，作者提及对基线方法（如ESD, CA）的关键参数（如 $\beta$）进行了超参数搜索和消融，以确保公平比较，这一点增强了实验的客观性。

### 6. 论文的主要结论与发现
*   **优越的整体性能**：本文方法（Ours）在多种概念擦除任务上效果出色。例如，在IP角色擦除任务中，该方法将检测率降至10%，而同期其他方法最低为11%（CA），且本文方法的图像质量指标（CLIP, FID, SSIM）均全面优于或接近最佳水平，成功实现了“有效擦除”与“保持质量”的平衡。
*   **卓越的鲁棒性**：在面对复杂的对抗性攻击时，本文方法展现了极强的抵抗力。例如，在Ring-A-Bell攻击下，本文方法的攻击成功率（ASR）仅为19%，远低于CA（62%）、ESD（45%）和FlowEdit（78%）等方法。
*   **关键设计有效性**：
    *   **提示词过滤**能显著提升擦除效果。
    *   **神经元掩码**策略（特别是对FFN层和归一化层）是实现高质量、鲁棒擦除的关键。
    *   **超参数 $\beta$ 控制着擦除和保持之间的权衡**，较小的 $\beta$ 倾向于更彻底的擦除。

### 7. 优点
*   **理论与实践并重**：从分布距离出发，为“极简擦除”提供了严谨的数学形式化，并将其与RLHF（人类反馈强化学习）联系起来，提供了理论洞见。
*   **方法论创新**：
    *   “仅关注最终输出”的优化视角，相比逐步监督，更符合“最小干预”原则。
    *   将“神经元掩码”用于概念擦除以提升鲁棒性，是一个直接有效的思路，从“连接主义”角度解决了“虚假对齐”的隐患。
*   **技术适用性广**：声称并初步证明了方法是模型无关的，可同时应用于流匹配和扩散模型，并在最新的DiT架构（FLUX）上得到验证，实用价值高。
*   **实验评估严谨**：评估维度全面（有效性、质量、鲁棒性），对比基线丰富，消融实验详实，结论说服力强。

### 8. 不足与局限
*   **优化实现限制**：论文明确指出，当前依赖的步骤级梯度检查点实现较为初级，**不支持多GPU训练**，这限制了该方法向更细粒度的权重级掩码扩展，也阻碍了掩码学习后的微调（fine-tuning），性能可能未达上限。
*   **效率与开销**：端到端的优化方式虽然内存恒定，但计算和训练时间长于传统微调方法。同时，需要为每个要擦除的概念对生成训练数据。
*   **评估的局限性**：
    *   **对抗攻击覆盖有限**：鲁棒性实验仅围绕“裸体”这一种概念展开，未能验证该方法在移除其他概念（如武器、艺术风格）时是否同样鲁棒。
    *   **模型和数据集单一**：主要验证在FLUX.1-Schnell模型上，在其他大型、不同架构的生成模型上的泛化能力有待更多实验验证。中性概念的评估仅依赖LAION-5K，可能无法完全代表通用生成能力。
*   **超参数敏感性**：擦除效果依赖于超参数如 $\beta$ 和优化步数，实践中可能需要针对不同概念进行调整，自动化寻参是未来方向。

（完）
