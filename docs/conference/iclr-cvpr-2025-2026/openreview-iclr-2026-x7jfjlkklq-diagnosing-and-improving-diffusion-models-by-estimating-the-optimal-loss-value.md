---
title: Diagnosing and Improving Diffusion Models by Estimating the Optimal Loss Value
title_zh: 通过估计最优损失值诊断和改进扩散模型
authors: "Yixian Xu, Shengjie Luo, Liwei Wang, Di He, Chang Liu"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=X7JfjLKKLQ"
tags: ["query:real-ir"]
score: 8.0
evidence: 估计扩散模型的最优损失以进行诊断和改进
tldr: 针对扩散模型训练中损失值含义模糊的问题，推导出统一框架下最优损失的闭式表达，并设计可扩展的随机估计器，从而为扩散模型训练提供内在评价指标，可用于诊断欠拟合、过参数化等问题，提升模型开发效率，对各类扩散模型应用具有通用指导意义。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 扩散模型损失值无法直接反映数据拟合质量，因为最小损失未知。
method: 推导扩散模型最优损失的闭式解，并提出可扩展估计器。
result: 提供了一种内在度量，可诊断训练不足或过参数化等问题。
conclusion: 最优损失估计是理解和改进扩散模型训练的有效工具。
---

## Abstract
Diffusion models have achieved remarkable success in generative modeling. Despite more stable training, the loss of diffusion models is not indicative of absolute data-fitting quality, since its optimal value is typically not zero but unknown, leading to the confusion between large optimal loss and insufficient model capacity. In this work, we advocate the need to estimate the optimal loss value for diagnosing and improving diffusion models. We first derive the optimal loss in closed form under a unified formulation of diffusion models, and develop effective estimators for it, including a stochastic variant scalable to large datasets with proper control of variance and bias. With this tool, we unlock the inherent metric for diagnosing training quality of mainstream diffusion model variants, and develop a more performant training schedule based on the optimal loss. Moreover, using models with 120M to 1.5B parameters, we find that the power law is better demonstrated after subtracting the optimal loss from the actual training loss, suggesting a more principled setting for investigating the scaling law for diffusion models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：扩散模型在生成任务中表现优异，但其训练损失值无法直接反映模型对数据的绝对拟合质量。
- **核心矛盾**：扩散模型的最优损失通常不为零且未知，导致训练者难以区分“损失大是因为模型容量不足”还是“该任务本身存在较大的不可约损失”。
- **研究动机**：需要一种方法估计最优损失值，从而为扩散模型训练提供内在的、绝对的诊断指标，帮助判断欠拟合、过参数化等问题，并指导训练调度和规模定律研究。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：推导出扩散模型在统一数学框架下的最优损失闭式解，并设计可扩展的随机估计器来近似该最优值。
- **关键技术细节**：
  - **闭式解推导**：将主流扩散模型变体纳入统一公式，从概率流或得分匹配角度推导出理想情况下（模型容量无限、数据分布完全匹配）训练损失所能达到的理论下界。
  - **可扩展估计器**：提出一种随机变体估计器，通过控制方差和偏差，使其能应用于大规模数据集。估计器利用训练过程中的统计量或额外采样，计算出最优损失的近似值。
  - **应用方式**：将实际训练损失减去估计的最优损失，得到“超额损失”（excess loss），该指标更纯粹地反映模型拟合不足的程度，用于诊断训练状态、调整训练计划。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集/场景**：摘要未列出具体数据集名称，但提到用于主流扩散模型变体（如 DDPM、Score SDE 等）的训练诊断和改进。
- **基准对比**：未提及与其他诊断方法的直接对比；实验重点在于验证最优损失估计的准确性，以及利用该指标改进训练调度、分析参数量从 120M 到 1.5B 模型的规模定律。
- **任务类型**：生成模型训练过程的内部诊断，不涉及生成样本质量的外部基准（如 FID）的直接比拼，而是将最优损失作为新工具。

### 4. 资源与算力

- **算力信息**：摘要和元数据中未明确说明所使用的 GPU 型号、数量或训练时长，仅提及使用了参数量为 120M 至 1.5B 的模型进行实验。具体计算资源细节在摘要中缺失。

### 5. 实验数量与充分性

- **实验范围**：根据摘要推断，至少包含：
  1. 最优损失估计器的准确性验证（可能对比真实最优值或理论值）。
  2. 在不同主流扩散模型变体上应用该指标进行训练诊断。
  3. 基于最优损失改进训练调度并对比性能。
  4. 在不同参数规模（120M~1.5B）下分析幂律缩放行为（实际损失减去最优损失后）。
- **充分性与公平性评估**：摘要未提及消融实验细节，但多模型变体、多参数量设置表明实验具有一定广度。由于是提出新工具，对比对象为未使用该指标的传统训练方式，比较逻辑内在合理。是否绝对公平取决于估计器引入的偏差是否被有效控制，摘要声称有偏差控制。

### 6. 论文的主要结论与发现

- **最优损失可估且有用**：提出的估计器能有效近似扩散模型的最优损失，为训练提供绝对的拟合质量度量。
- **诊断能力**：该指标可用于诊断模型训练不足或过参数化等问题。
- **改进训练调度**：基于最优损失设计的训练调度能提升模型性能。
- **规模定律新见解**：在从实际训练损失中减去最优损失后，模型的损失值与参数规模之间呈现出更好的幂律关系，这为研究扩散模型的缩放规律提供了更具原则性的设定。

### 7. 优点：方法或实验设计上的亮点

- **提供内在度量标准**：首次为扩散模型训练提出并实现了最优损失估计，填补了损失值难以解读的空白，具有通用指导意义。
- **理论结合实践**：既有闭式解的理论支撑，又有可扩展的随机估计器，兼顾精确性和实用性。
- **发现规模定律新视角**：减去最优损失后的幂律关系发现，可能影响未来大模型训练的资源分配和预测。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验细节缺失**：从摘要看，具体数据集、对比方法、消融实验设置未详细说明，难以评估结论的广泛适用性。
- **估计偏差风险**：随机估计器的偏差和方差控制虽被提及，但其在高维复杂数据上的实际表现和理论保证可能有限，可能影响诊断的准确性。
- **应用范围限制**：主要适用于其统一公式覆盖的扩散模型变体；对最新或非标准扩散架构的拓展性未讨论。
- **算力成本不明**：估计最优损失可能引入额外计算开销，但文中未说明其代价。

（完）
