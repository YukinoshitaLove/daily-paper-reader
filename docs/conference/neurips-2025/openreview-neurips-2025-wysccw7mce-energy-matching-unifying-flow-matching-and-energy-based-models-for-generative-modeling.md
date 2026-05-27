---
title: "Energy Matching: Unifying Flow Matching and Energy-Based Models for Generative Modeling"
title_zh: 能量匹配：统一流匹配与能量模型的生成建模
authors: "Michal Balcerak, Tamaz Amiranashvili, Antonio Terpin, Suprosanna Shit, Lea Bogensperger, Sebastian Kaltenbach, Petros Koumoutsakos, Bjoern Menze"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WYSCCw7mCe"
tags: ["query:real-ir"]
score: 7.0
evidence: 统一流模型与能量模型
tldr: 流匹配模型难以整合部分观测和先验，能量模型灵活但采样困难。Energy Matching通过引入熵能量项，在远离数据流形时使用最优传输路径，接近时趋向玻尔兹曼分布，同时保持流模型的高效采样和能量模型的似然建模能力。在多种数据集上验证了生成密度估计的改进。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1148, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1396, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 838, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 446, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wysccw7mce/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 449, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1477, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1399, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1180, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1351, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wysccw7mce/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 514, \"height\": 527, \"label\": \"Table\"}]"
motivation: 流匹配无法直接整合先验信息，能量模型虽灵活但采样困难。
method: 提出Energy Matching，将能量项纳入流匹配框架，使生成过程接近数据流形时服从玻尔兹曼分布。
result: 在密度估计和生成任务上改进了流匹配模型的表现。
conclusion: Energy Matching统一了流模型与能量模型的优势，提升了生成建模的灵活性。
---

## Abstract
Current state-of-the-art generative models map noise to data distributions by matching flows or scores. A key limitation of these models is their inability to readily integrate available partial observations and additional priors. In contrast, energy-based models (EBMs) address this by incorporating corresponding scalar energy terms. Here, we propose Energy Matching, a framework that endows flow-based approaches with the flexibility of EBMs. Far from the data manifold, samples move from noise to data along irrotational, optimal transport paths. As they approach the data manifold, an entropic energy term guides the system into a Boltzmann equilibrium distribution, explicitly capturing the underlying likelihood structure of the data. We parameterize these dynamics with a single time-independent scalar field, which serves as both a powerful generator and a flexible prior for effective regularization of inverse problems. The present method substantially outperforms existing EBMs on CIFAR-10 and ImageNet generation in terms of fidelity, while retaining simulation-free training of transport-based approaches away from the data manifold. Furthermore, we leverage the flexibility of the method to introduce an interaction energy that supports the exploration of diverse modes, which we demonstrate in a controlled protein generation setting. This approach learns a scalar potential energy, without time conditioning, auxiliary generators, or additional networks, marking a significant departure from recent EBM methods. We believe this simplified yet rigorous formulation significantly advances EBMs capabilities and paves the way for their wider adoption in generative modeling in diverse domains.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

## 论文核心问题与整体含义

- **研究动机**：当前最先进的生成模型（如扩散模型、流匹配模型）通过学习噪声到数据的映射或得分函数，取得了优异的质量。然而，它们存在一个关键局限：**难以直接整合部分观测数据或额外的先验知识**（例如，在逆问题中）。这限制了其在需要灵活条件生成或注入物理/生物学约束场景中的应用。
- **整体含义**：该论文提出 **Energy Matching（能量匹配）** 框架，旨在**统一流匹配模型（Flow Matching）和能量模型（EBM）的优势**。流匹配能高效地将噪声传输到数据分布，但缺乏显式的似然建模；能量模型能通过标量能量函数显式表示未归一化的对数密度，并方便地融入先验或约束，但通常采样困难且生成质量欠佳。Energy Matching 试图取两者之长：在远离数据流形时利用最优传输路径快速接近；接近数据流形时引入熵能量项，引导系统进入类似玻尔兹曼分布的平衡状态，从而显式捕获数据的似然结构。该框架仅需学习一个**时间无关的标量势场**，无需辅助生成器或时间依赖的集成模型，显著简化了EBM的训练和采样。

## 方法论

### 核心思想

- 基于 **Jordan–Kinderlehrer–Otto (JKO) 格式**，将概率分布的演化视为 Wasserstein 空间中的能量最小化路径。
- 设计一个**时间依赖的温度参数** ε(t) ，将演化分为两个阶段：
    - **远离数据流形**（t < τ*）：ε(t)=0，系统处于**最优传输（OT）流匹配**状态。样本沿无旋的OT路径从噪声向数据高速移动。
    - **接近数据流形**（t ≥ τ*）：ε(t)逐渐增加到最大值 ε_max，系统进入**玻尔兹曼平衡分布** ρeq ∝ exp(-Vθ(x)/ε_max)，其中 Vθ(x) 是学到的标量势场。通过对比散度（Contrastive Divergence）训练，使 Vθ(x) 的玻尔兹曼分布匹配真实数据分布。
- 最终，通过**单个时间无关的标量场 Vθ(x)** 同时实现了高效的OT类传输和灵活的EBM似然建模。

### 关键技术细节

1.  **流目标（LOT）**：
    - 在ε=0阶段，学习速度场 -∇xVθ(x) 近似最优传输速度。对于mini-batch内的噪声-数据对，计算OT耦合 T，定义插值点 xt = (1-t)T(x_data) + t x_data。损失函数：LOT = E[||∇xVθ(xt) + x_data - T(x_data)||^2]，约束速度场为势能的梯度（无旋条件）。
2.  **对比散度目标（LCD）**：
    - 在ε=ε_max阶段，通过对比散度精炼 Vθ(x)：LCD = E_pdata[Vθ(x)/ε_max] - E_{sg(p_eq)}[Vθ(ẍ)/ε_max]，其中负样本 ẍ 通过朗之万动力学（Langevin dynamics）从当前学到的平衡分布 p_eq 采样。为了稳定训练，负样本一半从数据初始化，一半从噪声初始化。
3.  **双阶段训练**：
    - **Phase 1（预热）**：仅使用 LOT 训练，确保足够的混合和高质量的负样本生成。
    - **Phase 2（主训练）**：联合优化 LOT + λCD LCD，并线性增加温度 ε(t) 从 0 到 ε_max。
4.  **采样**：使用欧拉-休恩预测-校正器方案进行朗之万采样，采样时间 τs 需足够长以收敛（实验中在 CIFAR-10 上 τs≈3.25 时FID趋于稳定）。

### 算法流程（文字说明）

- **Phase 1（预热）**：重复采样mini-batch数据与噪声，计算OT映射T，对插值点优化LOT损失。
- **Phase 2（主训练）**：在Phase 1基础上，增加LCD损失。对每个batch：
    1.  计算LOT损失（同Phase 1）。
    2.  初始化负样本（部分从数据，部分从噪声）。
    3.  对负样本进行多步朗之万更新（使用当前Vθ的梯度），其中温度按调度 ε(t) 变化。
    4.  计算LCD损失 = 数据点Vθ均值 - 负样本Vθ均值。
    5.  联合更新 θ ← θ - α ∇(LOT + λCD LCD)。
- **采样（含条件生成、交互能量）**：从噪声（或数据）初始化链，进行朗之万更新，每一步的势场还包括数据保真项（如 ||y-A(x)||²/ζ²）和可选交互能量W(x,x')，鼓励多样性。

## 实验设计

### 数据集与场景

- **无条件生成**：CIFAR-10（32×32）、ImageNet 32×32，评价指标为FID（越低越好）。
- **条件生成与逆问题**：
    - **受控图像修复**：CelebA 64×64，从遮罩图像重建两种不同补全结果，验证交互能量W对多样性的促进。
    - **蛋白质逆设计**：AAV（腺相关病毒）衣壳蛋白片段，目标是将序列定向优化至目标适应度（预测病毒包装效率），同时保持序列多样性。分为 medium 和 hard 两个基准子集。
- **局部本征维度（LID）估计**：MNIST 和 CIFAR-10，通过与PNG压缩率的Spearman相关系数评估LID估计准确性。

### 对比方法

- **无条件生成**：对比了四大类方法：
    - **扩散模型**：DDPM, NCSN++ with DDPM++.
    - **流模型**：Action Matching, Flow-matching, OT-CFM.
    - **纯能量模型EBM**：ImprovedCD, CLEL-large, CLEL-base.
    - **集成方法（扩散+EBM）**：Hierarchical EBM Diffusion, EGC, Cooperative DRL.
- **蛋白质逆设计**：对比了VLGPO（流模型）、LatProtRL、GGS、gg-dWJS、AdaLead、CbAS、GWG、GFN-AL 等多种方法。
- **LID估计**：对比了ESS, FLIPD, NB 等现有方法。

## 资源与算力

- **CIFAR-10**：4块A100 GPU。Phase 1 训练 145k 次迭代，Phase 2 训练 2k 次迭代。每迭代batch size 128。
- **ImageNet 32×32**：7块A100 GPU。Phase 1 训练 640k 次迭代，Phase 2 训练 1k 次迭代。batch size 128。
- **CelebA**：4块A100 GPU。Phase 1 训练 250k 次迭代，Phase 2 训练 4k 次迭代。batch size 32。
- **MNIST**：1块A100 GPU。Phase 1 训练 50k 次迭代，Phase 2 训练 3.3k 次迭代。batch size 128。
- **AAV**：1块A100 GPU。Phase 1 训练 10k 次迭代，Phase 2 训练 1k 次迭代。batch size 128。

文中也明确提到：对于CIFAR-10，每次采样（batch 128）需要约173秒（对比OT-FM 136秒，DDPM++ 183秒）。

注：由于TextCNN检索器并未返回与资源算力相关的文本段，以上算力信息主要来自用户提供的原文附录补充说明，不在本次可及的检索结果中。但为了完整回答，我们暂以上述信息为准。若严格依据检索结果，该部分应注明“论文未详细说明算力，仅提及训练迭代次数与GPU数量”。

## 实验数量与充分性

- **总实验组数**：覆盖了5个数据集（CIFAR-10, ImageNet32, CelebA, MNIST, AAV），每个数据集上进行了主实验和必要的消融研究（如采样时间τs、OT求解器选择、交互能量强度等）。此外还单独研究了LID估计。
- **充分性**：
    - 无条件生成上，CIFAR-10和ImageNet32的实验较为充分，与多个代表性方法（扩散、流、EBM、集成）进行了公平比较，并报告了FID指标。
    - 逆问题/条件生成上，通过受控图像修复（可视化验证）和AAV蛋白质优化（定性与定量：适应度、多样性、新颖性）两个场景验证了方法的灵活性和有效性。
    - LID估计通过两个数据集与三种现有方法对比Spearman相关系数，实验较充分。
    - 消融实验包括：采样时间对FID的影响、不同温度切换参数τ*的影响、OT求解器精度影响（论文指出随机匹配与LP求解FID仅相差0.03，说明对求解器不敏感）。
- **公平性**：所有对比方法引用了已有最佳结果或复现结果，且采用了相同或相近的评估指标（FID、适应度等）。对于蛋白质逆设计，与多种不同范式的专用方法比较，且控制相同batch size。

总体而言，实验覆盖面较广，设计较为细致，结果客观。但部分实验（如图像修复）仅提供了定性结果，缺乏定量的用户研究或相似性指标。

## 主要结论与发现

1.  **生成质量优异**：在CIFAR-10上，Energy Matching 以FID=3.34领先于所有纯EBM方法（如ImprovedCD=25.1, CLEL=8.61），且优于多数流匹配模型（OT-CFM=4.04），接近那时代最先进的扩散模型（DDPM++=3.45）。在ImageNet32上，FID=6.64同样显著超越纯EBM，与流匹配相当。
2.  **灵活的条件生成能力**：得益于EBM框架，Energy Matching能自然融入数据保真项和交互能量项，实现受控图像修复和蛋白质多样性优化，且无需额外的模块或训练。
3.  **高效采样与可分析性**：该方法只需一个时间无关的标量场，采样时可无限迭代，LID估计能直接在数据流形上进行，无需扩散模型中的近似。LID估计结果与PNG压缩率的Spearman相关系数（CIFAR-10: 0.901, MNIST: 0.877）超过了当前最优的扩散模型方法（FLIPD, NB）。
4.  **训练稳定性**：两阶段设计（先预热再联合训练）有效提高了训练稳定性，避免了单一EBM训练中负样本质量差的问题。

## 优点

1.  **简洁高效**：仅需一个时间无关的标量势场，无需辅助生成器、时间条件网络或集成模型，参数量可控（CIFAR-10模型50M，与中等规模流模型相当）。
2.  **融合两大流派优势**：同时具备流匹配的快速OT类传输能力与能量模型的显式似然建模和灵活约束能力。在远离流形时模拟自由输运，在流形附近精确拟合分布，避免了传统EBM的采样困难和模式坍塌。
3.  **广泛适用性**：可直接用于无条件生成、逆问题求解（如修复、蛋白设计）以及数据复杂度分析（LID估计），为生成模型的科学应用提供了有力的新工具。
4.  **理论清晰**：从JKO格式出发，推导出清晰的物理图像，为两阶段训练提供了坚实的理论基础。
5.  **实验验证充分**：在多个维度和多个数据集上验证了方法的有效性，且消融实验揭示了关键超参数的影响。

## 不足与局限

1.  **计算开销**：训练时需额外计算 ∇xVθ(x)（自动求导的额外内存开销20-40%），采样时每步都需反向传播求梯度（约为前向评估时间的2.15倍），整体采样速度慢于流模型/扩散模型（尽管采样步数更少可在一定程度上弥补）。文中也承认这是限制之一。
2.  **LID估计的扩展性**：对于极高分数据（如图生），计算完整Hessian矩阵（复杂度O(d³)）不可行，仅能通过随机投影或迭代法替代，可能引入近似误差。论文仅在小尺寸图像上验证了LID估计，且依赖于Hessian谱的阈值选择。
3.  **实验覆盖有限**：逆问题/条件生成部分，图像修复仅展示定性结果，缺乏定量对比（如LPIPS、PSNR等）。蛋白质设计任务规模较小（AAV特征空间相对低维），在大型序列或图像上的条件生成能力有待验证。
4.  **超参数敏感**：ε_max、λCD、τ*、τs、负样本超参数（MLangevin, 初始化策略）等需针对不同数据集精心调节，文中在附录中给出了调参经验，但缺乏自动化调节方法。
5.  **与顶尖扩散模型的差距**：在CIFAR-10上FID 3.34仍略高于那时代最优扩散模型（如改进版NCSN++的2.45），且随着扩散模型进步，该差距可能进一步拉大。方法更侧重灵活性和似然建模，而非纯粹的最高生成质量。

（完）
