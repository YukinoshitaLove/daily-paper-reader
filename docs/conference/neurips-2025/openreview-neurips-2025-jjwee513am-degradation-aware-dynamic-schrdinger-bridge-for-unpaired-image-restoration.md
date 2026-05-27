---
title: Degradation-Aware Dynamic Schrödinger Bridge for Unpaired Image Restoration
title_zh: 退化感知动态薛定谔桥用于无配对图像修复
authors: "Jingjun Yi, Qi Bi, Hao Zheng, Huimin Huang, Yixian Shen, Haolan Zhan, Wei Ji, Yawen Huang, Yuexiang Li, Xian Wu, Yefeng Zheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=jJweE513Am"
tags: ["query:real-ir"]
score: 9.0
evidence: 利用退化先验的薛定谔桥进行无配对图像修复
tldr: 无配对图像修复面临配对数据缺乏的瓶颈。本文提出退化感知动态薛定谔桥（DDSB），学习清晰与退化分布之间的桥接，并嵌入物理退化先验减少误差累积。在多种退化类型上取得优于现有方法的无监督修复效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 1070, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 1067, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jjwee513am/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 1069, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jjwee513am/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1309, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jjwee513am/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1154, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jjwee513am/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jjwee513am/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 251, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jjwee513am/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 251, \"height\": 182, \"label\": \"Table\"}]"
motivation: 解决无配对图像修复中缺乏清晰-退化样本对的问题。
method: 学习清晰与退化分布间的薛定谔桥，融入物理退化先验。
result: 在模糊、低光照等多种退化任务上实现高质量无监督修复。
conclusion: 动态薛定谔桥结合先验可有效实现无配对修复。
---

## Abstract
Image restoration is a fundamental task in computer vision and machine learning, which learns a mapping between the clear images and the degraded images under various conditions (e.g., blur, low-light, haze).
Yet, most existing image restoration methods are highly restricted by the requirement of degraded and clear image pairs, which limits the generalization and feasibility to enormous real-world scenarios without paired images.
To address this bottleneck, we propose a Degradation-aware Dynamic Schr\"{o}dinger Bridge (DDSB) for unpaired image restoration.
Its general idea is to learn a Schr\"{o}dinger Bridge between clear and degraded image distribution, 
while at the same time emphasizing the physical degradation priors to reduce the accumulation of errors during the restoration process. 
A Degradation-aware Optimal Transport (DOT) learning scheme is accordingly devised.
Training a degradation model to learn the inverse restoration process is particularly challenging, as it must be applicable across different stages of the iterative restoration process.
A Dynamic Transport with Consistency (DTC) learning objective is further proposed to reduce the loss of image details in the early iterations and therefore refine the degradation model.
Extensive experiments on multiple image degradation tasks show its state-of-the-art performance over the prior arts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

图像修复是计算机视觉中的基础任务，旨在从退化图像（如模糊、低光照、雾霾、雨滴等）中恢复清晰图像。传统方法依赖配对数据（清晰-退化图像对）进行监督学习，但在真实场景中获取大量配对数据往往不可行，因为退化条件多样且缺乏真值。**无配对图像修复**近年来受到关注，但其关键挑战在于输入与输出之间缺乏显式对应关系，容易导致修复结果不真实或细节丢失。

现有生成模型（如扩散模型）虽取得进展，但仍受限于特定先验分布（如高斯分布），难以适应多样退化条件。薛定谔桥（Schrödinger Bridge, SB）作为一种熵正则化的最优传输（Optimal Transport, OT）框架，能够在任意两个分布之间建立随机过程，无需配对数据，为无配对修复提供了新途径。然而，传统SB在迭代修复过程中容易累积误差，且未利用物理退化先验，导致早期阶段的伪影被传播到最终结果。

**本文提出退化感知动态薛定谔桥（Degradation-aware Dynamic Schrödinger Bridge, DDSB）**，旨在解决SB在无配对修复中的误差累积问题，通过显式引入退化先验提升修复的真实性和鲁棒性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
DDSB将无配对修复建模为清晰图像分布与退化图像分布之间的动态薛定谔桥，并在传输过程中嵌入一个**可学习的退化模型**，用于放大修复模型产生的伪影和退化，从而施加额外约束，减少误差累积。同时，提出**动态传输一致性（DTC）** 学习目标，强化早期迭代步的监督，并利用轨迹级别的退化一致性来优化退化模型的训练。

### 关键技术细节

1. **无配对薛定谔桥（UNSB）**：
   - 将时间区间[0,1]离散化为N个步，从退化图像x_d（t=0）开始，通过马尔可夫链逐步向清晰图像x_c（t=1）传输。
   - 每一步使用条件生成器q_θ(x_c|x_ti)预测清晰估计，然后通过插值加噪得到下一步状态：  
     p(x_{tj+1}|x_c, x_tj) = N(μ_{j+1} x_c + (1-μ_{j+1})x_tj, σ^2_{j+1} I)
   - 优化目标为熵正则化最优传输（EROT）损失：  
     L_EROT = E[∥x_d - x_c∥²] - 2τ H(π) + KL(q_θ(x_c)∥p(x_c))

2. **退化感知最优传输（DOT）**：
   - 在经典EROT成本中加入退化一致性项：  
     c_DOT(x_d, x_c) = ∥x_d - x_c∥² + λ·∥ D_ϕ(x_c) - x_d ∥²
   - 其中D_ϕ是一个轻量级CNN（3层卷积），用于学习退化过程（即恢复的逆过程）。该模型能放大恢复过程中的伪影，使得约束更有效。
   - DOT损失在随机选取的时间步t_i处施加。

3. **动态传输一致性（DTC）**：
   - 针对早期迭代步更难、伪影更多的问题，DTC对整个轨迹（x_traj = {x_t0, ..., x_t_Ns}）施加监督。
   - 损失函数为：  
     L_DTC = ∥x_ti - x_c(x_ti)∥² + λ_ti · ∥ x_ti - D_ϕ(x_t_Ns) ∥²
   - 其中λ_ti采用余弦退火调度（随时间步靠近最终步而增加权重），使得D_ϕ的优化目标为整个轨迹的加权平均，从而减少早期不可靠预测对退化模型训练的影响。
   - DTC替代了DOT中的第二项，使退化模型学习更稳定。

4. **总体框架**：
   - 训练时随机选取一个时间步t_Ns，模拟前向传输得到轨迹，在每个中间步应用DOT和DTC损失。
   - 熵项通过互信息神经估计（MINE）计算，KL散度通过对抗学习实现（马尔可夫判别器）。
   - 生成器q_θ采用U-Net架构，退化模型为3层64通道CNN。

## 3. 实验设计

### 使用的数据集与场景
- **多任务图像修复**（4种退化）：
  - 去雨：Rain200L（1800训练/200测试）
  - 雨滴去除：Raindrop（1119对）
  - 去模糊：GoPro（2103训练/1111测试，1280×720）
  - 低光增强：LOL（485训练/15测试）
- **广义去雾泛化**：
  - 训练集：SOTS-indoor (RESIDE ITS, 13990对)
  - 测试集：SOTS-outdoor (500对)、NH-HAZE 2 (25对，真实非均匀雾)

### 评价指标
- 全参考指标：PSNR、SSIM、LPIPS
- 无参考指标：NIQE

### 对比方法
包括传统先验方法（DCP）、生成对抗方法（CycleGAN、YOLY、USID-Net、RefineDNet）、对比学习方法（CUT）、最短路径方法（Santa）、SB基线（UNSB）、正交解耦方法（ODCR）、密集归一化方法（DN）等。所有方法在相同配置下微调。

### 训练设置
- 输入图像统一缩放至512×512，强度归一化到[-1,1]。
- 时间步N=5，温度τ=0.01，λ=0.01。
- 批量大小1，学习率2e-4线性衰减，训练400轮。
- 生成器采用AdaIN层和正弦时间嵌入。

## 4. 资源与算力

论文中**未明确说明使用的GPU型号、数量或具体训练时长**。仅提到训练参数（batch size=1，400 epochs，图像尺寸512）。附录中也未提供硬件信息。因此，无法准确评估算力开销。但本文方法参数较少（14.68M），推理速度较快（0.019 ms/512×512图像），表明资源消耗相对较低。

## 5. 实验数量与充分性

### 实验数量
- **多任务修复实验**：表1和表2分别展示了PSNR+SSIM和LPIPS+NIQE，涵盖4个任务、10+种对比方法。
- **广义去雾实验**：表3展示了在3个测试集上的结果，并报告参数量和推理时间。
- **消融实验**：表4（各组件效果）、表5（时间步N）、表6（λ）、表7（D_ϕ层数）。
- **可视化对比**：图3、4、5-8提供了大量定性结果。

### 充分性评价
- **覆盖面广**：任务涵盖合成和真实场景退化，对比方法全面（包括经典和最新无配对方法）。
- **消融系统**：对每个核心组件（DOT、DTC）分别消融，并探究超参数（N、λ、层数）的影响，验证了设计合理性。
- **公平性**：所有方法在同一配置下训练和评估，遵循已有工作协议（如D4的泛化协议）。未报告误差棒，但多数对比方法是单次运行结果，符合该领域惯例。
- **客观性**：同时使用全参考和无参考指标，减少单一指标偏差。

总体而言，实验设计较为充分，结果可信。

## 6. 论文的主要结论与发现

- DDSB在无配对图像修复的多个任务（去雨、雨滴去除、去模糊、低光增强）上均达到**最优（SOTA）**，PSNR/SSIM显著超过先前方法（如DN，提升1-2 dB）。
- 在广义去雾任务上（训练室内，测试室外和真实非均匀雾），DDSB展现出**强大的泛化能力**，且参数少、推理极快（0.019 ms）。
- DOT组件通过引入退化先验有效减少误差累积，DTC组件通过轨迹级一致性监督强化早期修复细节，两者互补。
- 理论分析表明DDSB的泛化误差上界比标准SB更紧（加入退化项O(λ)）。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将退化感知先验引入薛定谔桥框架，提出DOT和DTC两个新颖训练目标，解决无配对修复中误差累积和细节丢失问题。
- **理论贡献**：给出了更紧的泛化误差上界（附录A.1），为方法有效性提供了理论支撑。
- **轻量高效**：退化模型仅3层CNN，总参数量14.68M，推理速度比大多数基线快几个数量级（如比DN快4600倍）。
- **实验充分**：覆盖多种退化类型、合成与真实场景，消融实验完整，结果一致性高。
- **可视化质量**：定性结果清晰展示DDSB能保留更多纹理和结构，伪影最少。

## 8. 不足与局限

- **未明确算力信息**：缺少GPU型号、训练时长等细节，不利于复现和公平比较效率。
- **无配对假设下的偏差风险**：虽然采用退化先验，但退化模型D_ϕ仅从数据中学习，可能无法覆盖所有真实物理退化（如雾、雨等复杂混合），存在域偏移风险。
- **超参数敏感**：时间步N、λ等需针对不同任务调整，论文仅给出了默认值（N=5, λ=0.01），未讨论在极端退化下的适应性。
- **真实场景测试有限**：除NH-HAZE 2外，多数数据集为合成或半合成，真实复杂退化（如多类型混合、动态变化）的泛化能力未验证。
- **仅评估了单任务**：未探索多任务联合训练或未知退化类型的零样本修复，应用广度有限。
- **未提供代码或预训练模型**：虽然承诺开源，但目前无法复现。

（完）
