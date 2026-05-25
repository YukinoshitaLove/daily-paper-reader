---
title: "Modulated Diffusion:  Accelerating Generative Modeling with Modulated Quantization"
title_zh: 调制扩散：通过调制量化加速生成建模
authors: "Weizhi Gao, Zhichao Hou, Junqi Yin, Feiyi Wang, Linyu Peng, Xiaorui Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=y8hMadAgrz"
tags: ["query:real-ir"]
score: 7.0
evidence: 基于调制量化和误差补偿的扩散模型加速
tldr: 针对扩散模型采样计算瓶颈，提出调制扩散（MoDiff）框架，通过调制量化和误差补偿原理，全面加速扩散模型。MoDiff不仅继承了缓存和量化方法的优点，还为所有扩散模型提供了一种普适加速框架，有效平衡速度与生成质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 549, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1404, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1400, \"height\": 2238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 2241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1401, \"height\": 1750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1401, \"height\": 1749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1347, \"height\": 1601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y8hmadagrz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1347, \"height\": 1601, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1593, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 802, \"height\": 652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 806, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 598, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 793, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1065, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1384, \"height\": 939, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1357, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1357, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1008, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 933, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1590, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 715, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 769, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1679, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 794, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 791, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y8hmadagrz/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 791, \"height\": 161, \"label\": \"Table\"}]"
motivation: 现有加速技术缓存和量化存在计算误差和生成质量限制。
method: 引入调制量化和误差补偿，构建统一的扩散模型加速框架。
result: 在扩散模型上实现加速，同时保持生成质量。
conclusion: MoDiff为扩散模型提供了一种严格有效的普适加速方案。
---

## Abstract
Diffusion models have emerged as powerful generative models, but their high computational cost in iterative sampling remains a significant bottleneck. In this work, we present an in-depth and insightful study of state-of-the-art acceleration techniques for diffusion models, including caching and quantization, and reveal their limitations in computation error and generation quality. To break these limits, this work introduces Modulated Diffusion (MoDiff), an innovative, rigorous, and principled framework that accelerates generative modeling through modulated quantization and error compensation. MoDiff not only inherits the advantages of existing caching and quantization methods but also serves as a general framework to accelerate all diffusion models. The advantages of MoDiff are supported by solid theoretical insight and analysis. In addition, extensive experiments on CIFAR-10 and LSUN demonstrate that MoDiff significantly reduces activation quantization from 8 bits to 3 bits without performance degradation in post-training quantization (PTQ). Our code implementation is available at https://github.com/WeizhiGao/MoDiff.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
扩散模型虽生成能力强，但迭代采样带来的高昂计算成本成为其规模化应用的主要瓶颈。现有加速技术，如**缓存重用（caching）** 和**后训练量化（PTQ）**，虽取得一定成效，却各自面临重大局限：

- **缓存重用**：重用历史中间计算结果时，近似误差会随扩散步数累积，严重偏离标准生成路径，最终损害生成质量。
- **后训练量化**：扩散模型的激活值范围在不同时间步变动剧烈，且存在大量异常值，导致低比特（如<8位）量化时产生巨大的裁剪和舍入误差，性能急剧下降。

针对上述问题，本文提出 **MoDiff（调制扩散）**，一个统一、严格且有理论保证的框架。其核心思想是利用扩散过程中相邻时间步的激活值在时域上的相似性（即时域差分范围更小、分布更集中），通过 **调制量化** 和 **误差补偿** 两种机制，在几乎不损失生成质量的前提下，将激活量化比特数从8比特大幅压缩至3比特，从而显著加速扩散模型推理。

### 2. 论文提出的方法论
MoDiff 的核心由 **调制计算与量化** 和 **误差补偿调制** 两部分构成，其关键流程如下：

- **调制量化（Modulated Quantization）**：
  - **观察**：激活值的时域差分 \(a_t - a_{t+1}\) 的范围远小于原始激活值，且分布更集中，量化误差天然更小。
  - **计算重构**：对于去噪网络中的每个线性算子 \(A\)（如卷积层），利用其线性性质，将当前步输出 \(o_t = A(a_t)\) 等价改写为 \(o_t = A(a_t - a_{t+1}) + o_{t+1}\)。
  - **量化应用**：实际运算时，仅对时域差分进行量化 \(Q(a_t - a_{t+1})\)，再与缓存的实数前一步输出 \(\hat{o}_{t+1}\) 相加。这实现了对“差值”的低比特整数运算，而非对原始激活本身。

- **误差补偿调制（Error-Compensated Modulation）**：
  - **误差追踪**：引入中间变量 \(\hat{a}_t\) 存储“实际通过量化恢复的激活值”，即 \(\hat{a}_t = Q(a_t - \hat{a}_{t+1}) + \hat{a}_{t+1}\)。该变量精确跟踪了量化误差 \(e_t = a_t - \hat{a}_t\)。
  - **误差注入补偿**：由于实际输出使用 \(\hat{o}_t = A(\hat{a}_t)\)，下一次量化时输入的差分是 \(a_{t-1} - \hat{a}_t = (a_{t-1} - a_t) + e_t\)。这使得前一步的量化误差 \(e_t\) 被天然地补偿到下一步的计算中。
  - **理论保证**：论文定理证明，标准调制缓存会导致误差线性/超线性累积；而误差补偿调制能使前序误差以指数速率 \((2c)^{T-k-1}\) 衰减（\(c<1/2\)），彻底避免误差累积。

### 3. 实验设计
- **数据集**：CIFAR-10 (32×32)、LSUN-Bedrooms (256×256)、LSUN-Church-Outdoor (256×256)。还扩展至 MS-COCO（用于 Stable Diffusion）和 ImageNet（用于 DiT 变换器）。
- **基线与对比方法**：
  - 全精度激活（32位）模型。
  - 两种典型的 PTQ 方法：**Q-Diffusion（Q-Diff）** 和 **动态通道级量化（LCQ）**（也测试了动态张量级量化 LTQ）。
  - MoDiff 分别与上述基线结合（如 LCQ+MoDiff）。
- **评估指标**：Inception Score（IS）、Fréchet Inception Distance（FID）、sliced FID（sFID）、Precision/Recall，以及计算量指标 GBOPs。
- **实验配置**：覆盖多种权重量化位宽（4/8 bit）和激化量化位宽（8/6/4/3/2 bit）。主要实验使用 DDIM 采样器（CIFAR-10 100步）和 LDM（LSUN 200/500步），消融实验还测试了 DDPM、DPM-Solver、PLMS 等。

### 4. 资源与算力
论文未明确提及具体使用的 GPU 型号、数量及任何训练或校准的计算时长。鉴于 MoDiff 属于后训练量化框架，其“加速”主要体现在以 **理论二进制运算次数（GBOPs）** 评估的推理效率上，不涉及大模型的重训练。文中仅提及利用校准数据集学习量化缩放因子，但未报告此过程的算力开销。

### 5. 实验数量与充分性
实验设计非常充分、客观且公平：
- **全面性**：至少包含 **2个大型量化方法、3个主要数据集、5种以上激活位宽（32/8/6/4/3/2）、2种权重量化位宽** 的交叉实验。
- **消融研究**：系统分析了误差补偿、不同采样器（DDPM/DPM）、Warm-up 策略、内存消耗、张量级量化、少步生成（20步）以及变换器架构（DiT）等的性能，验证了各模块的贡献与方法的泛化性。
- **公平对比**：所有方法均基于相同的预训练模型，使用统一的评估指标和流程，确保了比较的公正性。

### 6. 论文的主要结论与发现
- **比特极限突破**：MoDiff 成功将扩散模型的后训练激活量化极限从 8 比特推至 **3 比特**，在 CIFAR-10 上实现无损加速，计算量降低超过 10 倍（从 1636 GBOPs 降至 154 GBOPs）。
- **通用加速框架**：MoDiff 可与任意 PTQ 算法、多种采样器（DDIM、DDPM、DPM-Solver）及不同架构（UNet、DiT）正交结合，展现了强大的泛化能力。
- **误差补偿机制关键**：即使无误差补偿，调制计算本身也优于直接量化；但补偿机制是实现极低比特（≤4位）无损量化的决定性因素，它成功将误差累积控制为指数衰减。

### 7. 优点
- **理论坚实**：提供了严格定理，从量化误差与输入范围关系、误差传播与衰减速率两方面，给出了理论支撑。
- **即插即用、无需训练**：作为一种 PTQ 增强技术，MoDiff 无需任何模型重训练或代价高昂的超参搜索，易于部署。
- **效果显著且正交**：不与现有方法冲突，能叠加在 SOTA 量化方法上，大幅提升其低比特性能，将失效的位宽重新变为可用。
- **洞察直观**：利用“时域差分”代替“原始激活”进行量化的思想，简洁而高效地解决了激活分布范围大、异常值多的难题。

### 8. 不足与局限
- **内存开销**：需要为每一层缓存前一时刻的激活 \(\hat{a}_t\) 和输出 \(\hat{o}_t\)，增加了少量内存需求（论文展示额外开销仅数 MB，属于可接受范围，但客观存在）。
- **真实加速未验证**：所有效率评估均停留于 GBOPs 这一理论指标，未在 GPU 等实际硬件上实现并报告推理延迟降低（Wall-clock time speedup）。
- **高分辨率退化**：在 LSUN-Bedroom 等更大规模数据集上，将激活压至极低位宽（如 4-bit）时，生成质量仍会明显下降，极限不如 CIFAR-10。
- **依赖模型特性**：其增益依赖于相邻步激活的高度相似性。对于引入较大随机噪声的采样器（如 DDPM），该相似性减弱，带来收益也相应变小。
（完）
