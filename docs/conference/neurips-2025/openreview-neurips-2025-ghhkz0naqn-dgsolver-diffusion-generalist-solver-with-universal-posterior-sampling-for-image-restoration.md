---
title: "DGSolver: Diffusion Generalist Solver with Universal Posterior Sampling for Image Restoration"
title_zh: "DGSolver: 具有通用后验采样的扩散通用求解器用于图像修复"
authors: "Hebaixu Wang, Jing Zhang, Haonan Guo, Di Wang, Jiayi Ma, Bo Du"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ghhKZ0NaQN"
tags: ["query:real-ir"]
score: 9.0
evidence: 用于通用图像修复的扩散通用求解器与后验采样
tldr: 针对现有扩散模型在图像修复中采样步骤有限时误差累积，以及降解表示通用性与修复质量难以平衡的问题，本文提出DGSolver。它首先推导出通用扩散模型的精确常微分方程以统一降解表示，然后设计定制的高阶求解器并结合通用后验采样。实验表明，DGSolver在多个修复任务上以更少的采样步骤取得了更优的保真度，兼顾了效率与质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1374, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1436, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1440, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1437, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ghhkz0naqn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1440, \"height\": 596, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1381, \"height\": 979, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1455, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ghhkz0naqn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1530, \"height\": 2392, \"label\": \"Table\"}]"
motivation: 现有扩散模型图像修复方法在有限采样步骤下误差累积，且降解表示通用性不足。
method: 推导通用扩散模型的精确ODE，设计高阶求解器并引入通用后验采样。
result: 在多种图像修复任务上以更少步骤获得更高保真度，效率与质量兼得。
conclusion: 通用求解器有效提升了扩散模型在图像修复中的实用性和性能。
---

## Abstract
Diffusion models have achieved remarkable progress in universal image restoration. However, existing methods perform naive inference in the reverse process, which leads to cumulative errors under limited sampling steps and large step intervals. Moreover, they struggle to balance the commonality of degradation representations with restoration quality, often depending on complex compensation mechanisms that enhance fidelity at the expense of efficiency. To address these challenges, we introduce \textbf{DGSolver}, a diffusion generalist solver with universal posterior sampling. We first derive the exact ordinary differential equations for generalist diffusion models to unify degradation representations and design tailored high-order solvers with a queue-based accelerated sampling strategy to improve both accuracy and efficiency. We then integrate universal posterior sampling to better approximate manifold-constrained gradients, yielding a more accurate noise estimation and correcting errors in inverse inference. Extensive experiments demonstrate that DGSolver outperforms state-of-the-art methods in restoration accuracy, stability, and scalability, both qualitatively and quantitatively. Code and models are publicly available at https://github.com/MiliLab/DGSolver.

---

## 论文详细总结（自动生成）

# 论文《DGSolver: Diffusion Generalist Solver with Universal Posterior Sampling for Image Restoration》详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

**研究动机**：现有的基于扩散模型的通用图像修复（Universal Image Restoration, UIR）方法在逆过程中采用朴素推理，导致在有限采样步数和较大步长下累积严重的离散化误差。此外，这些方法难以平衡退化表示的**通用性**（commonality）与修复质量，往往依赖复杂的补偿机制，虽然提升了保真度却牺牲了推理效率。具体而言，现有UIR方法分为两类：混合表示方法（blend-representation）和分离表示方法（distinct-representation），前者通过共享表示空间促进通用性但使修复负担加重，后者通过多编码器或提示机制处理特定退化但未充分挖掘退化间的互补信息。两类方法均缺乏一种既能高效又能高精度处理多种退化的统一解。

**论文目标**：提出一种精确且高效的通用图像修复求解器——**DGSolver**，它融合了常微分方程（ODE）求解器的高精度推理优势与扩散后验采样的通用补偿机制，在保持高通用性的同时提升修复精度和效率，无需额外训练。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：将通用扩散模型（Diffusion Generalist Model, DGM）的逆过程建模为半线性ODE，利用其解析结构设计高阶数值求解器以减小离散化误差；同时将贝叶斯后验采样机制无缝融入通用建模框架，提供流形约束梯度引导，进一步增强噪声估计的准确性。这两部分均依赖于预训练的噪声和残差预测器，无需微调。

**关键技术**：

- **ODE精确公式化**：首先推导通用扩散模型的SDE对应的概率流ODE，并证明其精确解可等价为三个积分之和（线性项可精确计算，非线性项需近似）。通过变量代换（α, β, δ 的逆函数），将积分转化为对残差预测器 \( \hat{I}_{\theta}^{\text{res}} \) 和噪声预测器 \( \hat{\epsilon}_\theta \) 在参数空间上的积分（见式(10)）。

- **高阶求解器**：利用泰勒展开近似非线性积分，得到k阶求解器公式。例如：
  - **一阶求解器**（k=1）：退化为现有方法的离散形式（如DiffUIR），但明确包含了线性项与非线性项的分离。（见式(15)）
  - **二阶求解器**（k=2）：引入一个中间时间点 \( t_u = r t_i + (1-r) t_{i-1} \)，通过有限差分近似一阶导数，修正更新公式。（见式(16)）
  - **三阶求解器**（k=3）：需要两个中间时间点 \( t_u, t_s \)，类似构建二阶导数逼近。（见式(148)）
  
- **队列加速采样策略**：针对高阶求解器需要多次函数评估（NFE）的问题，设计队列缓存机制：预计算中间时间点的结果并缓存，后续步骤复用，将复杂度从朴素采样的 \( O(nk) \) 降低到 \( O(n + k - 1) \)，效率提升约2～3倍。（见Alg. 8）

- **通用后验采样（Universal Posterior Sampling, UPS）**：借鉴DPS思想，将测量模型统一为 \( I_{\text{in}} = I_0 + I_{\text{res}} + n \)。利用条件期望近似 \( q(I_{\text{in}}|I_t) \)，并通过定理1证明Jensen间隙的上界依赖于噪声方差和预测误差。最终将梯度项 \( \nabla_{I_t} \log q(I_{\text{in}}|I_t) \) 近似为负梯度范数，修正噪声预测：  
  \[
  \hat{\epsilon}_\theta := \epsilon_\theta + \frac{\beta_t}{\sigma^2} \nabla_{I_t} \| I_{\text{in}} - (\hat{I}_0 + I_\theta^{\text{res}}) \|.
  \]
  此修正项无需重新训练，仅依赖预训练网络。

## 3. 实验设计

**任务与数据集**：
- **自然图像修复**：涵盖5类退化：
  - 去雨（Deraining）：DID、DeRaindrop、Rain13K、Rain100H/L、GT-Rain、RealRain-1k等
  - 低光增强（Enhancement）：LOL、MEF、VE-LOL-L、NPE
  - 去雪（Desnowing）：CSD、Snow100K-Real
  - 去雾（Dehazing）：SOTS、ITS_v2、D-HAZY、NH-HAZE、Dense-Haze、NHRW
  - 去模糊（Deblur）：GoPro、RealBlur
  所有通用方法在混合数据集上重新训练或微调。

- **遥感图像修复**（Remote Sensing）：包括去噪、增强、去模糊、去云、超分，数据集：Sen2_MTC、AID、NWPU-RESISC45、Second、PatternNet，均为合成数据或真实数据合成退化。

**对比方法**：
- **任务特定方法**：SwinIR、Restormer、MAXIM、IR-SDE、RDDM
- **通用方法**：Restormer（通用版）、AirNet、PromptIR、ProRes、IDR、AutoDIR、DA-CLIP、DiffUIR

**评估指标**：PSNR和SSIM。

**实验设置**：
- 训练：8×Nvidia A800 40GB GPU，PyTorch框架，210小时
- 优化器：Adam，L1损失，500k迭代，学习率1e-4，batch size 20
- 随机裁剪256×256，测试时使用8个采样步数（默认）
- 网络架构：U-Net，四种规模（T/S/B/L），通道数递增
- 消融：求解器阶数（k=1,2,3）、UPS开关、δ_T值、采样步数（4～10）
- 零样本泛化在真实场景图像上测试
- 复合修复：对同时含多种退化的图像多次应用模型

## 4. 资源与算力

论文明确说明：
- GPU：8张Nvidia A800 40GB GPU（也可适配Ascend 910B 64GB NPUs）
- 训练时长：210小时
- 优化配置：Adam优化器，L1损失，500k iterations，batch size 20
- 框架：PyTorch
- 测试时：8个采样步，全分辨率（256×256及以上）
- 代码和模型公开于 GitHub。

## 5. 实验数量与充分性

**实验数量**相对充分：
- **主实验（表1）**：在5个自然修复任务上对比了13种方法（含不同版本Ours-T/S/B/L），每个任务报告PSNR/SSIM，并汇总平均。
- **消融实验（表2、3、4）**：
  - 求解器阶数×UPS开关的6种配置
  - 不同δ_T值（0.1～1）的影响
  - 不同采样步数（4～10）的影响
- **可视化对比**：图4、图5等展示多种退化示例
- **复合修复**：图6、图A3、A4展示多次迭代处理多退化图像
- **零样本泛化**：图7、图A5在真实场景图像上的定性结果
- **遥感修复（表5）**：5种任务对比8种通用方法
- **效率对比（表A3）**：不同分辨率下内存、时间、FPS的详细数据，以及队列策略的对比（表A4）
- **附录**：包含理论推导、更多可视化、数据集细节、算法伪代码等。

**公平性**：所有通用方法在相同混合数据集上重新训练或微调（AutoDIR除外因其未开源训练代码）。任务特定方法按各自任务单独训练。实验设置一致，评估指标标准。

**充分性**：覆盖了主要退化类型、多种模型规模、关键设计消融、泛化能力检验、计算效率评估，结果支持结论。

## 6. 主要结论与发现

1. **性能领先**：DGSolver（Ours-L）在所有5个自然修复任务上平均PSNR 31.36，SSIM 0.920，显著优于现有最佳通用方法DiffUIR（29.93/0.907），也超过多数任务特定方法，且参数和计算量更低（Ours-L: 7.73M参数/32.93G FLOPs）。
2. **求解器阶数与UPS的作用**：二阶求解器+UPS达到性能饱和（表2配置iv），进一步增加阶数提升有限；UPS激活可稳定提升指标，尤其在低阶时效果更明显。
3. **通用性参数δ_T的影响**：δ_T=1（最大通用性）下仍取得最佳平均性能，证明方法能处理高度混合的退化分布。
4. **采样步数**：8步为最优平衡点，增加步数反而导致性能轻微下降（可能因过度匹配参考或随机性）。
5. **复合修复能力**：多次应用模型可逐步去除不同退化，且不损伤已恢复区域。
6. **零样本泛化**：在真实场景图像（如真实雨、雾、模糊）中视觉效果最优。
7. **遥感任务**：同样取得最佳或接近最佳结果，验证了可扩展性。
8. **效率提升**：队列策略将二阶求解器的速度提升近一倍，接近朴素一阶求解器。

## 7. 优点（方法/实验亮点）

- **理论创新**：首次为通用扩散模型推导了精确ODE解析形式，并提供了高阶求解器的通用公式（k阶），具有严格误差界分析（附录B）。
- **训练免费**：高阶求解器和通用后验采样均无需额外训练，可直接应用于预训练模型，带来即插即用的性能提升。
- **高效采样**：队列缓存策略显著降低高阶求解器的计算开销，使其实际速度与一阶方法相当。
- **参数效率**：Ours-T仅0.45M参数即可达到有竞争力的结果，利于轻量化部署。
- **实验全面**：覆盖5+5个任务、多种退化类型、真实/合成数据集，包含大量消融和泛化测试。
- **可迁移性**：作者指出该方法可扩展至其他扩散模型，具有潜在通用价值。

## 8. 不足与局限

- **GPU内存限制**：高阶求解器（k>3）和UPS需要存储梯度图，论文仅在k=1,2,3上测试，更高阶尚未验证；多尺度或更大模型时内存增长明显（见表A3）。
- **性能饱和现象**：二阶+UPS即达性能瓶颈，更高阶提升不明显，可能实际应用中无需进一步增加阶数，但理论更高阶的潜力未充分探索。
- **采样步数最优性不稳健**：8步最佳，但10步反而下降，说明模型对步数敏感，可能存在欠拟合或过度适应问题。
- **现实场景依赖合成数据**：遥感任务除去云外均为合成退化，真实退化分布可能更复杂，泛化性未在真实遥感图像上充分验证。
- **复合修复需手动迭代**：处理多退化图像时需多次运行模型，缺乏自动化判定终止机制。
- **未与其他高效加速技术对比**：如DDIM、DPM-Solver等，缺少与现有扩散加速方法的定量比较。
- **公平性潜在偏差**：AutoDIR因无训练代码未被充分比较；一些任务特定方法可能未调至最优。

（完）
