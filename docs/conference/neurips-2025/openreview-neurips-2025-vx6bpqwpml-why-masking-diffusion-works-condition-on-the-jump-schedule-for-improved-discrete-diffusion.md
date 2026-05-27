---
title: "Why Masking Diffusion Works: Condition on the Jump Schedule for Improved Discrete Diffusion"
title_zh: 掩码扩散为何有效：基于跳跃调度的条件改进离散扩散
authors: "Alan Nawzad Amin, Nate Gruver, Andrew Gordon Wilson"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vx6bPQWpmL"
tags: ["query:real-ir"]
score: 7.0
evidence: 对掩码扩散模型优越性的理论解释
tldr: 离散扩散模型中掩码扩散性能最佳但原因不明。本文指出连续与离散马尔可夫过程的本质差异：离散过程通过不连续跳跃进化。掩码扩散利用这一特性，避免了逐步去噪的局限性。该理论为设计更优离散扩散模型提供了指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1337, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1333, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1241, \"height\": 195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1359, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vx6bpqwpml/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 717, \"height\": 610, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vx6bpqwpml/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 609, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vx6bpqwpml/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 627, \"height\": 221, \"label\": \"Table\"}]"
motivation: 解释掩码扩散在离散扩散模型中性能最优的内在原因。
method: 分析连续与离散马尔可夫过程差异，揭示跳跃调度的关键作用。
result: 证明掩码扩散利用不连续跳跃优势，优于其他离散扩散形式。
conclusion: 为离散扩散模型的改进提供了理论依据。
---

## Abstract
Discrete diffusion models, like continuous diffusion models, generate high-quality samples by gradually undoing noise applied to datapoints with a Markov process. Gradual generation in theory comes with many conceptual benefits; for example, inductive biases can be incorporated into the noising Markov process. In practice, however, the consistently best performing discrete diffusion model is masking diffusion, which does not denoise gradually. Here we explain the superior performance of masking diffusion by noting that it makes use of a fundamental difference between continuous and discrete Markov processes: discrete Markov processes evolve by discontinuous jumps at a fixed rate and, unlike other discrete diffusion models, masking diffusion builds in the known distribution of jump times and only learns where to jump to. We show that we can similarly bake in the known distribution of jump times into any discrete diffusion model. The resulting models -- schedule-conditioned diffusion (SCUD) -- generalize classical discrete diffusion and masking diffusion. By applying SCUD to models with noising processes that incorporate inductive biases on images, text, and protein data, we build diffusion models that outperform masking.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：在离散扩散模型中，尽管理论上逐步去噪（如均匀扩散、结构化扩散）能融入归纳偏置，但实际性能最优的模型却是 **掩码扩散（Masking Diffusion）**，它并不逐步去噪，而是直接以恒定速率将每个 token 跳转到掩码状态。为何掩码扩散性能最好？能否使其他前向过程获得同等优势？
- **动机**：作者发现离散马尔可夫过程与连续扩散存在根本差别——离散过程通过 **不连续跳跃** 以固定速率演化。掩码扩散利用了这一点：它将已知的跳跃时间分布“内置”到反向过程中，只学习“跳到何处”；而经典离散扩散需要同时学习“何时跳”与“跳到何处”，后者更难拟合。
- **整体含义**：如果所有离散扩散模型都能像掩码扩散一样内置跳跃时间分布，就能提升性能。由此提出的 **SCUD (Schedule-Conditioned Diffusion)** 框架统一了经典离散扩散与掩码扩散，并使得结构化的前向过程（如高斯、BLOSUM）首次能够超越掩码扩散。

---

## 2. 论文提出的方法论

### 核心思想
- 将前向过程的跳跃调度 \( S = \{t_1, t_2, \dots, t_M\} \)（即状态发生改变的时刻集合）作为附加条件。
- 将 ELBO 分解为 **“何时跳跃”** 和 **“何处跳跃”** 两部分：
  - “何时跳跃”项：KL(\(p(S) \| q(S)\))，通过强制 \(q(S) = p(S)\) 使其为零，从而消除对跳跃时间的学习负担。
  - “何处跳跃”项：学习每个事件发生后应该跳转到哪个状态 \(q_\theta(\text{pr}(x_t) | x_t, s_t)\)，其中 \(s_t\) 是到时间 \(t\) 为止发生的事件数。

### 关键技术细节
1. **事件化表示**：引入辅助“事件”（event）概念，事件以恒定速率 \(r\) 发生，每事件可能引起状态转换（也可能不转）。前向过程由速率 \(r\) 和转移矩阵 \(K = L/r + I\) 定义。参数 \(\gamma = r^*/r\)（\(r^* = \max_b -L_{b,b}\)）控制事件速率：\(\gamma \to 1\) 时接近全条件调度（掩码扩散），\(\gamma \to 0\) 时退化为经典离散扩散。
2. **SCUD 损失函数**（公式 6）：
   \[
   -\mathbb{E}_{t\sim\text{Unif}(0,1)} \mathbb{E}_{p(x_t,x_0,S)} \frac{\beta_t}{\int_0^t \beta_s ds} \sum_d s_t^d \, \text{KL}\big( p(\text{pr}(x_t^d)|x_t^d,s_t^d,x_0^d) \,\big\|\, q_\theta(\text{pr}(x_t^d)|x_t, s_t) \big)
   \]
   其中 \(\beta_t\) 是速率缩放函数，\(s_t^d\) 是维度 \(d\) 到时间 \(t\) 的事件数。
3. **参数化**：将经典扩散中的时间 \(t\) 替换为 \(s_t\)（D 维向量），使用 FiLM 层将其注入网络，不增加额外参数。
4. **采样**（算法 2）：先采样最终噪声 \(x_1 \sim p(x_\infty)\) 和事件调度 \(S\)，然后按预算 \(C\) 分步逆转事件，每一步使用 \(q_\theta(\text{pr}^k(x_t^d)|x_t, s_t)\) 公式单次前向即可逆转多个事件。

### 理论连接
- 当 \(\gamma = 1-1/D\) 且前向为均匀过程时，SCUD 等价于掩码扩散。
- 当 \(\gamma \to 0\) 时，SCUD 损失收敛到经典离散扩散的 SEDD 损失。

---

## 3. 实验设计

| 数据集/场景 | 前向过程 | 对比方法 | 评价指标 |
|-------------|----------|----------|----------|
| **CIFAR-10**（图像，B=128/256） | 均匀 (Uniform)、高斯 (Gaussian) | D3PM, τLDR, MD4，以及作者自己实现的经典均匀/高斯扩散 | Bits per dimension (NLL) |
| **UniRef50**（蛋白质，B=31） | 均匀、BLOSUM（基于突变矩阵） | 文献中的 D3PM，以及作者实现的经典均匀/BLOSUM扩散 | Perplexity |
| **LM1B**（语言，B=30522） | 均匀、10-近邻图结构 | D3PM（离散时间掩码和图结构） | Perplexity |

- **消融实验**：在 CIFAR-10（B=128）上改变 \(\gamma\) 从 0.1 到 1，观察 NLL 变化，验证调度条件程度与似然改进的正相关。
- **预训练迁移**：在蛋白质上使用预训练的 ESM2 骨干，对比 SCUD 与 DPLM（掩码），进一步验证 SCUD BLOSUM 优于掩码。

---

## 4. 资源与算力

- **硬件**：2 块 NVIDIA A100 GPU，部署在学术集群上。
- **训练时长**：
  - CIFAR-10 大模型：约 2 天（2.6 × 10⁹ images）。
  - CIFAR-10 小模型（图 1 的消融）：1.5–2 小时。
  - UniRef50 蛋白质模型：2 天（1.1 × 10¹¹ tokens）。
  - LM1B 语言模型：2 天（1.1 × 10¹⁰ tokens）。
- **显存与批次**：具体显存未列出，批次大小分别为 16（小模型）、128（蛋白质）、512 累积（语言）。
- **说明**：论文未详细列出所有模型的显存占用，但指出 SCUD 的计算开销与经典扩散几乎相同（<10% 差异）。

---

## 5. 实验数量与充分性

- **实验数量**：涵盖 3 个领域（图像、蛋白质、语言），每个领域包含多种 baselines（文献已有结果 + 作者自己实现的经典扩散）。在图像上还有 γ 消融（5 个点）和模型规模对比。
- **公平性**：作者尽量保持架构、训练超参数、计算预算一致（如所有模型训练相同时间、相同批次大小）。对于文献中的 D3PM/τLDR/MD4，直接引用其报告值；对于经典扩散，作者自己复现以消除实现差异。
- **充分性**：实验设计较好地支撑了核心结论——调度条件能显著提升所有前向过程的似然，且结构化前向过程+调度条件可超越掩码。但主要聚焦于似然（ELBO），未评估生成样本质量（除附录中 CIFAR-10 的定性样本外），这是研究重心的有意选择。

---

## 6. 论文的主要结论与发现

1. **掩码扩散出色的原因**：它内置了跳跃调度信息（知道“何时跳跃”），从而避免了学习跳跃时间的困难；而经典离散扩散需同时学习“何时”和“何处”。
2. **SCUD 框架**：通过将已知的跳跃时间分布嵌入任何前向过程，使模型只需学习“何处跳跃”，从而大幅提升似然。
3. **结构化前向过程的价值**：在调度条件下，带有归纳偏置的前向过程（如图像高斯、蛋白质 BLOSUM）能显著超越不带结构的均匀（即掩码）扩散——此前的经典扩散做不到这一点。
4. **计算优势**：SCUD 只需计算 \(K^{s_t}\) 而非矩阵指数 \(\exp(tL)\)，因而可处理词汇量很大的稀疏/低秩前向过程，使基于图结构的语言扩散首次可行。

---

## 7. 优点（方法或实验设计亮点）

- **理论深度**：首次将 ELBO 显式分解为“何时”与“何处”两项，精准解释了掩码扩散的优势来源。
- **通用性**：SCUD 不限于特定前向过程，可应用于任何离散马尔可夫过程（均匀、高斯、BLOSUM、图结构等）。
- **计算高效**：避免矩阵指数运算，使得大规模词汇表下的结构化前向过程成为可能（如 LM1B 的稀疏图结构）。
- **无额外参数**：仅将时间 \(t\) 替换为事件计数 \(s_t\)，网络结构几乎不变，训练开销增加甚微。
- **实验对比严谨**：在三个领域均复现了经典扩散，与文献结果做了交叉验证，同时进行了 γ 消融，结论可靠。

---

## 8. 不足与局限

- **缺乏采样质量评估**：论文主要报告 ELBO（似然），未系统评估生成样本的质量（如 FID、IS、多样性和保真度）。虽然附录展示了 CIFAR-10 样本，但仅定性。采样质量是离散扩散的重要指标，本文未覆盖。
- **语言领域提升有限**：在 LM1B 上，SCUD 图结构仅比 SCUD 均匀（掩码）有微小提升（37.82 vs. 37.63 perplexity），说明所设计的 10-近邻图结构可能并非最优，或语言数据本身更偏好掩码。
- **调度信息的权衡**：加入过多信息（如每个突变的确切位置）会使 \(p(x_1|S,x_0)\) 退化为点质量（永不收敛），存在应用范围上限。论文未深入探讨最优信息量。
- **实验偏倚风险**：主要实验在 CIFAR-10、UniRef50、LM1B 上进行，未在更多元的数据集（如分子图、音频离散化、医疗序列）上验证，需警惕过度泛化。
- **未与最新的离散流匹配（Discrete Flow Matching）直接对比**：虽然附录讨论了扩展至流匹配，但实验部分未与 2024-2025 年提出的离散流匹配方法（如 Gat et al. 2024）进行性能比较。

---

（完）
