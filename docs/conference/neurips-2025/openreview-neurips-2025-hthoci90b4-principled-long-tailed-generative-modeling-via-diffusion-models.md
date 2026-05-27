---
title: Principled Long-Tailed Generative Modeling via Diffusion Models
title_zh: 基于扩散模型的原则性长尾生成建模
authors: "Pranoy Das, Kexin Fu, Abolfazl Hashemi, Vijay Gupta"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HThoCI90b4"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于扩散模型的长尾生成建模
tldr: 扩散模型在处理长尾数据时头部类主导，尾部类表现差。该文提出基于深度互学习的正则化训练目标，结合标准扩散损失和互学习项，并通过多玩家博弈达到纳什均衡，实现了各类别平衡生成。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hthoci90b4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1425, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hthoci90b4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1348, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hthoci90b4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 1162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hthoci90b4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hthoci90b4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1596, \"height\": 1584, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hthoci90b4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 812, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hthoci90b4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 760, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hthoci90b4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hthoci90b4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 546, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hthoci90b4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 630, \"height\": 250, \"label\": \"Table\"}]"
motivation: 扩散模型在长尾数据集上性能严重偏向头部类。
method: 引入互学习正则项，通过多玩家博弈框架优化，达到纳什均衡。
result: 在长尾数据集上实现各类别平衡生成。
conclusion: 为扩散模型在真实世界长尾场景的应用提供了理论基础。
---

## Abstract
Deep generative models, particularly diffusion models, have achieved remarkable success  but face significant challenges when trained on real-world, long-tailed datasets- where few "head" classes dominate and many "tail" classes are underrepresented. This paper develops a  theoretical framework for long-tailed learning via diffusion models through the lens of deep mutual learning. We introduce a novel regularized training objective that combines the standard diffusion loss with a mutual learning term, enabling balanced performance across all class labels, including the underrepresented tails. Our approach to learn via the proposed regularized objective is to formulate it as a multi-player game, with Nash equilibrium serving as the solution concept. We derive a non-asymptotic first-order convergence result for individual gradient descent algorithm to find the Nash equilibrium.  We show that the Nash gap of the score network obtained from the algorithm is upper bounded by $\mathcal{O}(\frac{1}{\sqrt{T_{train}}}+\beta)$ where $\beta$ is the regularizing parameter and $T_{train}$ is the number of iterations of the training algorithm. Furthermore, we theoretically establish hyper-parameters for training and sampling algorithm that ensure that we find conditional score networks (under our model) with a worst case sampling error $\mathcal{O}(\epsilon+1), \forall \epsilon>0$ across all class labels. Our results offer insights and guarantees for training diffusion models on imbalanced, long-tailed data, with implications for fairness, privacy, and generalization in real-world generative modeling scenarios.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：扩散模型在真实世界的长尾数据分布上训练时，性能严重偏向头部类（高频出现），尾部类（低频）生成质量极差，甚至无法识别。
- **研究动机**：尾部类虽单个频率低，但集合起来概率高，且在隐私、公平性上存在风险（模型可能过拟合尾部类数据）。现有工作（如CBDM）缺乏严格理论保证。
- **整体意义**：首次从深度互学习（Deep Mutual Learning）视角出发，为扩散模型在长尾数据上的训练建立严谨数学理论，保证各类别（包括尾部）的生成误差有上界，推动公平、隐私和泛化。

## 2. 方法论：核心思想与关键技术

### 核心思想
- 将条件扩散模型的训练视为一个多玩家博弈，每个类别对应一个玩家（条件分数网络），目标是最小化**最差类别**的KL散度（生成质量）。通过引入互学习正则项，迫使不同类别的分数网络在高噪声区域对齐，从而提升尾部类性能。

### 关键技术细节
1. **正则化训练目标**：
   - 标准扩散损失：`L_{conti}(θ_y)`
   - 互学习损失：`L_{mut}(θ_y, θ_{-y})` —— 衡量不同类别分数网络输出之间的差异。
   - 总损失：`L_{reg}(θ_y, θ_{-y}) = L_{conti}(θ_y) + β * L_{mut}(θ_y, θ_{-y})`
2. **博弈框架与纳什均衡**：
   - 定义多玩家博弈：每个玩家优化自己的正则化损失，纳什均衡作为解概念。
   - 使用个体梯度下降（Individual Gradient Descent）算法迭代更新。
3. **理论保证**：
   - 非渐近一阶收敛：纳什间隙（NE-gap）上界为 `O(1/√T_train + β)`。
   - 最差情况采样误差（各类别KL散度最大值）上界为 `O(ϵ + 1)`，通过调节超参数可任意小（除常数项）。
4. **分数网络参数化**：
   - 采用两层ReLU随机特征网络（宽度m），便于理论分析。
5. **算法流程**（Algorithm 1）：
   - 初始化每个类别的参数θ_y。
   - 每轮迭代中，依次对每个类别计算梯度并更新：`θ_y ← θ_y - η * ∇_{θ_y} L_reg(θ_y, θ_{-y})`。

## 3. 实验设计

### 数据集
- **合成数据**（Gaussian Mixture Model）：
  - 情况一：两个高斯分布，调节均值间距和方差，imbalance ratio = 2.5。
  - 情况二：类别1为两个高斯混合，类别2为单个高斯。
- **真实世界数据集**：CIFAR10 的长尾版本 **CIFAR10LT**（imbalance factor = 0.01），由[5]构造。

### Benchmark与方法对比
- **基准方法**（baseline）：
  - Vanilla DDPM（β=0，即无互学习）。
  - Class-Balancing Diffusion Models (CBDM) [23]。
- **对比指标**：
  - FID（Fréchet Inception Distance，越低越好）
  - IS（Inception Score，越高越好）

### 主要实验
- **合成数据实验**：计算各类别的KL散度，验证互学习能降低尾部类误差而不显著损害头部类（在分布距离适中时）。
- **CIFAR10LT实验**：训练60k步，生成15k样本/类，比较FID和IS。
- **超参数调节**：不同β值（0, 0.1, 1.0）和不同学习率η（2e-4, 1e-4, 1e-5）的FID/IS表格。

## 4. 资源与算力

- **文中明确说明**：
  - 部分实验在MacBook Air (2023) 上进行。
  - 主要实验在**Gilbreth集群**的**子集群B**上进行：16节点，每节点24核、192GB内存、3个Nvidia A30 GPU（24GB），节点间100 Gbps InfiniBand互连。
  - 未明确给出单次训练具体GPU时长，但指出共享代码与详细参数可复现。

## 5. 实验数量与充分性

- **实验数量**：共两类实验（合成数据 + 真实数据）。合成数据包含两种具体设置；真实数据（CIFAR10LT）提供了与两个基准（Vanilla DDPM和CBDM）的比较，并报告了不同超参数的影响。
- **充分性评价**：
  - 合成数据实验直观验证理论（降低尾部KL散度），但样本量小（50个训练样本），不足以代表复杂真实分布。
  - 真实数据实验只使用了CIFAR10LT一个数据集，且与CBDM的比较只有一组默认超参数（β=0.1，η=1e-4），未进行系统调优对比。文中也承认“不声称互学习优于CBDM”，主要贡献是理论。
  - 消融实验：对β和η进行了网格搜索（2×3共6组），覆盖了关键超参数。
  - **公平性**：CBDM代码来自公开仓库，设置相似（60k步），但未进行多次随机种子重复实验（仅提到±标准差），因此统计显著性有待加强。

## 6. 主要结论与发现

- **理论贡献**：第一个为扩散模型在长尾数据上的训练提供严格理论保证，证明互学习正则化与个体梯度下降可逼近纳什均衡，最差类别的采样误差可控（`O(ϵ+1)`）。
- **实验发现**：
  - 互学习能显著降低尾部类的拟合误差（合成数据热力图对比）。
  - 在CIFAR10LT上，互学习（FID=14.58）优于Vanilla DDPM（FID=16.58）和CBDM（FID=15.28），但优势不大且需进一步验证。
  - 当类别分布相距较远时，互学习可能损害头部类性能（合成数据情况一）。

## 7. 优点

- **理论严谨性**：首次将深度互学习与扩散模型结合，并给出收敛性和泛化误差的完整数学证明，包括非渐近上界。
- **问题定义清晰**：将长尾学习转化为最小化最差类别误差的博弈问题，提出纳什均衡作为公平解概念。
- **算法简单有效**：个体梯度下降无需复杂计算，易于实现。
- **全面性**：讨论了超参数选择、扩展至深层网络的可行性、联邦学习应用等。

## 8. 不足与局限

- **实验覆盖不足**：
  - 仅在CIFAR10LT一个真实数据集上验证，未使用CIFAR100LT、ImageNet-LT等更大规模长尾数据集。
  - 对CBDM的直接比较非完全公平（仅一次训练，未调优CBDM参数）。
- **理论假设较强**：
  - 假设数据分布有紧支撑（compact support），且分数函数连续可微。
  - 采用两层随机ReLU网络，与实际常用的U-Net架构有差距（虽然作者讨论了扩展可能性）。
- **头部类性能可能退化**：当类别分布差异大时，互学习可能降低头部类生成质量。
- **常数项不可消除**：最终采样误差包含`O(1)`常数项（来自C(y)），导致不能任意小。
- **缺乏计算效率分析**：未讨论互学习带来的额外计算开销。

（完）
