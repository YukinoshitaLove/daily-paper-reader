---
title: When and how can inexact generative models still sample from the data manifold?
title_zh: 不精确生成模型何时以及如何仍能从数据流形中采样？
authors: "Nisha Chandramoorthy, Adriaan A. de Clercq"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QBjuYL4gAX"
tags: ["query:real-ir"]
score: 4.0
evidence: 生成模型采样鲁棒性的理论分析
tldr: 生成模型在存在学习误差时仍能采样数据流形的原因尚不明确。本文从动力系统角度分析生成过程的概率流，揭示微小误差仅导致密度在流形上偏移而非偏离流形。该发现为生成模型的设计提供理论基础，但未涉及具体图像任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 887, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1198, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 873, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 883, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 587, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1310, \"height\": 1303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbjuyl4gax/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1311, \"height\": 656, \"label\": \"Figure\"}]"
motivation: 探究生成模型在学习误差下仍能维持数据流形采样的内在机制。
method: 采用动力系统方法分析生成过程的概率流和密度扰动。
result: 证明误差仅改变密度在流形上的分布而不改变支撑集。
conclusion: 为生成模型的鲁棒性提供了理论解释。
---

## Abstract
A curious phenomenon observed in some dynamical generative models is the following: despite learning errors in the score function or the drift vector field, the generated samples appear to shift \emph{along} the support of the data distribution but not \emph{away} from it. In this work, we investigate this phenomenon of \emph{robustness of the support} by taking a dynamical systems approach on the generating stochastic/deterministic process. Our perturbation analysis of the probability flow reveals that infinitesimal learning errors cause the predicted density to be different from the target density only on the data manifold for a wide class of generative models. Further, what is the dynamical mechanism that leads to the robustness of the support? We show that the alignment of the top Lyapunov vectors (most sensitive infinitesimal perturbation directions) with the tangent spaces along the boundary of the data manifold leads to robustness and prove a sufficient condition on the dynamics of the generating process to achieve this alignment. Moreover, the alignment condition is efficient to compute and, in practice, for robust generative models, automatically leads to accurate estimates of the tangent bundle of the data manifold. Using a finite-time linear perturbation analysis on samples paths as well as probability flows, our work complements and extends existing works on obtaining theoretical guarantees for generative models from a stochastic analysis, statistical learning and uncertainty quantification points of view. Our results apply across different dynamical generative models, such as conditional flow-matching and score-based generative models, and for different target distributions that may or may not satisfy the manifold hypothesis.

---

## 论文详细总结（自动生成）

# 论文总结：When and how can inexact generative models still sample from the data manifold?

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：生成模型（如扩散模型、流匹配模型）在学习误差（如分数函数或漂移向量场的近似误差）不可避免的情况下，为何生成的样本仍然能分布在数据分布的高密度区域（即数据流形）上，而不会偏离到零概率区域？作者将此现象称为“支撑集的鲁棒性”（robustness of support）。
- **研究动机**：在实际应用中，学习误差总是存在，理解何时以及为何生成模型仍能保持支撑集鲁棒性，对于关键领域（如气候预测）的理论保障至关重要。已有研究主要关注收敛性（如Wasserstein距离），但鲁棒性更贴近实践需求。
- **整体含义**：通过动力系统视角，证明误差仅导致预测密度在数据流形上偏移，而非离开流形；并揭示其动力学机制是：最敏感的李雅普诺夫向量（Lyapunov vectors）与数据流形的切空间对齐，使得误差在垂直于流形的方向上快速衰减。

## 2. 论文提出的方法论：核心思想与关键技术细节

- **核心思想**：将生成过程（确定性或随机）视为非自治动力系统，利用有限时间李雅普诺夫分析（finite-time Lyapunov analysis）研究微小扰动（学习误差）沿样本路径的传播。定义“最敏感子空间”（top Lyapunov subspaces）和“对齐属性”（alignment property），给出支撑集鲁棒性的充分条件。
- **关键技术与公式**：
  - **扰动统计学响应**：对生成密度 \( \rho_\tau \) 的扰动 \( u(\rho_\tau) \) 可通过目标响应场（target response field）表达，结果与目标密度 \( \rho_\tau \) 的乘积形式表明：扰动仅影响密度非零的区域（见公式 (2)）。
  - **切线空间动力学**：定义 Jacobian 矩阵 \( dF_t \)，其乘法 \( dF^\tau \) 作用于切向量，给出有限时间李雅普诺夫向量和指数。最重要的子空间 \( E^d_\tau(x) \) 通过 QR 分解构造。
  - **对齐属性定义**：若 \( E^d_\tau(x) \) 正交于目标分数 \( s_\tau(x) \) 在流形边界上，则称生成模型具有对齐属性。
  - **定理 4.3（对齐的充分条件）**：当生成动力学满足（i）压缩性（期后阶段总压缩因子大于1），（ii）交叉导数为零近似，（iii）二阶导数有界等条件时，对齐属性成立。这等价于向量场在流形边界附近表现为“吸引力”。
- **算法流程**：无需显式算法，主要理论分析；但可用于计算李雅普诺夫向量以估计流形切丛。

## 3. 实验设计：数据集、场景、基准和对比方法

- **场景与数据集**：
  - 低维：2D“双月”（two-moons）分布（流形为1D曲线），使用分析分数（解析解）进行干净控制。
  - 高维：MNIST手写数字（28×28），使用预训练扩散模型（DDPM）进行鲁棒性和李雅普诺夫向量可视化。
  - CIFAR-10（32×32），使用Song等人的预训练分数生成模型测试扰动后图像质量。
  - 对比方法：条件流匹配（Conditional Flow Matching, CFM）、最优传输条件流匹配（OT-CFM）、随机插值（Stochastic Interpolants），同样在2D双月分布上比较鲁棒性。
- **基准**：主要对比不同生成模型（SGM vs 流匹配变体）在相同误差幅度下的支撑集保持能力。
- **对比方式**：定性比较密度图（2D）和图像质量；定量地比较李雅普诺夫向量与分数之间的点积直方图来量化对齐程度。

## 4. 资源与算力

- 论文中**未明确报告具体GPU型号、数量或训练时长**。
- MNIST实验：使用PyTorch实现U-Net，训练30个epoch，batch size=64，Adam学习率2e-5；计算在常规硬件上进行（未指明具体型号）。
- CIFAR-10实验：直接使用开源预训练模型，无需额外训练。
- 低维实验：通过数值积分（无需神经网络）计算分数和Lyapunov向量，计算资源需求低。

## 5. 实验数量与充分性

- **实验数量**：主要包括三类：
  1. 2D双月分布上的解析实验：显示SGM在扰动后密度仍沿流形移动（图1），并计算Lyapunov向量可视化对齐（图2）；对比CFM、OT-CFM、随机插值（图7-8），展示不同模型的鲁棒性差异。
  2. MNIST上的训练+扰动实验：训练一个DDPM，计算Lyapunov向量（图3、图5），验证向量指数接近流形维度时出现间隙；展示沿前几个LV扰动仍生成合理数字，而沿高指数LV扰动则产生伪影。
  3. CIFAR-10上的预训练模型扰动实验：改变分数误差大小（0.1到1），生成图像仍保持视觉质量和似然分数。
- **充分性评价**：实验设计覆盖低维和高维、解析和神经网络、多种生成模型类型，验证了理论核心观点。但缺少更广泛的数据集（如ImageNet）、更系统的消融实验（如不同噪声调度、步数的影响），也未涉及大规模真实场景。实验相对充分但有限。

## 6. 论文的主要结论与发现

- **结论1**：在合理的正则性假设下，任意微小学习误差仅导致预测密度在数据流形上偏移，而不离开流形（统计响应与目标密度乘积形式）。
- **结论2**：支撑集鲁棒性的动力学机制是：最敏感的李雅普诺夫子空间与数据流形的切空间对齐（对齐属性）。该属性能通过有限时间QR分解高效计算。
- **结论3**：定理4.3给出了对齐的充分条件：向量场在后期表现为各向异性吸引，使垂直于流形的方向具有超稳定性（极大收缩），而沿流形方向允许缓慢变化。
- **结论4**：对齐属性具有正则性（在C1扰动下保持），因此对齐的生成模型可高精度估计流形切丛，用于流形学习。
- **结论5**：实验表明，基于分数的扩散模型（SGM）天然满足对齐和鲁棒性，而某些流匹配模型（如非直调流匹配）不满足，可能与动力学设计有关。

## 7. 优点

- **理论创新**：首次将有限时间李雅普诺夫分析引入生成模型鲁棒性研究，提出了新颖的“对齐属性”概念，为理解和设计鲁棒生成模型提供了理论基础。
- **方法普适**：理论不依赖于具体生成模型类型（SGM、流匹配、随机插值等），适用于确定性/随机过程；也不要求目标分布满足流形假设（可奇异或绝对连续）。
- **实用价值**：对齐属性可计算（通过QR算法和自动微分），可直接用于流形维数估计和切空间学习，简化了对生成模型精度的要求（只需方向对齐，不要求在垂直方向零误差）。
- **实验佐证**：通过多个维度（2D解析、MNIST训练、CIFAR预训练）和多种模型对比，一致性验证理论预测。

## 8. 不足与局限

- **充分必要性缺失**：论文仅给出对齐的充分条件，未证明必要性，因此不能断言所有鲁棒生成模型都一定满足对齐。
- **实验覆盖有限**：
  - 高维实验仅使用MNIST和CIFAR-10，未在更大规模数据集（如ImageNet、自然图像集）或更复杂任务（如文本、音频）上验证。
  - 仅对比了几种流匹配变体，未系统性测试不同时间积分方案、噪声调度等超参数影响。
- **理论假设强度**：定理4.3要求良好的正则性（C1光滑性、非退化压缩因子等），实际神经网络可能不严格满足；跨阶段扩张假设（i）可能不总是成立。
- **计算与训练细节不足**：论文未提供详细的计算资源信息（GPU型号、训练时长），可复现性受限；MNIST训练仅30 epoch，可能不是最优。
- **否类属性验证不充分**：虽然指出某些流匹配模型鲁棒性较差，但未提供严格的理论分析解释为何这些模型缺乏对齐。
- **实际应用风险评估**：论文未讨论在医疗、安全等高风险场景下，理论保证的局限性（如边缘情况或极端扰动可能导致错误）。

（完）
