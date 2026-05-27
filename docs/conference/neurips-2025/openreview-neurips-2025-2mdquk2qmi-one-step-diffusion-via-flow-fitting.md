---
title: One Step Diffusion via Flow Fitting
title_zh: 通过流拟合实现一步扩散
authors: "Hamadi Chihaoui, Paolo Favaro"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=2mDquK2qMI"
tags: ["query:real-ir"]
score: 8.0
evidence: 通过流拟合实现一步扩散生成
tldr: 现有扩散和流匹配模型需要多步采样，计算成本高。本文提出FlowFit，通过学习从噪声到数据的连续流轨迹，在推理时仅需单步评估即可生成高质量图像，避免了迭代去噪过程，在保持生成质量的同时显著降低计算开销。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2mdquk2qmi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2mdquk2qmi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1463, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2mdquk2qmi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 930, \"height\": 607, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2mdquk2qmi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 569, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2mdquk2qmi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 612, \"height\": 136, \"label\": \"Table\"}]"
motivation: 扩散模型多步采样计算成本高。
method: 提出FlowFit，拟合从噪声到数据的连续流轨迹，实现单步生成。
result: 单步生成高质量图像，无需迭代去噪。
conclusion: FlowFit实现了高效的一步生成，降低了推理成本。
---

## Abstract
Diffusion and flow-matching models have demonstrated impressive performance in generating diverse, high-fidelity images by learning transformations from noise to data. However, their reliance on multi-step sampling requires repeated neural network evaluations, leading to high computational cost. We propose FlowFit, a family of generative models that enables high-quality sample generation through both single-phase training and single-step inference. FlowFit learns to approximate the continuous flow trajectory between latent noise \(x_0\) and data \(x_1\) by fitting a basis of functions parameterized over time \(t \in [0, 1]\) during training. At inference time, sampling is performed by simply evaluating the flow only at the terminal time \(t = 1\), avoiding iterative denoising or numerical integration. Empirically, FlowFit outperforms prior diffusion-based single-phase training methods achieving superior sample quality.

---

## 论文详细总结（自动生成）

# 论文《One Step Diffusion via Flow Fitting》详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：扩散模型和流匹配模型在生成高质量图像方面表现出色，但它们依赖多步迭代采样（如128步），每次采样需要多次神经网络评估，导致推理计算成本高、速度慢，限制了在实时或资源受限场景中的应用。
- **动机**：现有加速推理的方法（如蒸馏）通常需要两阶段训练：先训练一个教师扩散模型，再训练学生模型模拟教师行为。这增加了训练复杂性和内存需求，且可能受限于固定教师。
- **目标**：提出一种**单阶段训练、单步推理**的生成框架，在保持生成质量的同时实现高效的采样。

## 2. 方法论

### 核心思想
- 直接参数化从噪声 \(x_0\) 到数据 \(x_1\) 的连续流轨迹 \(\psi_t(x)\)，使用一组固定基函数（如多项式、傅里叶）展开，通过神经网络学习每个基函数的系数。这样，整个轨迹被紧凑表示，推理时只需计算 \(t=1\) 处的值即可一步生成。

### 关键技术细节
- **轨迹参数化**：
  \[
  \psi_\theta(x_0, t) = x_t = \sum_{k=1}^K f_{\theta,k}(x_0) \, \gamma_k(t)
  \]
  其中 \(\gamma_k(t)\) 是固定基函数（如多项式 \(t^k\) 或三角函数），\(f_{\theta,k}(x_0)\) 是神经网络输出的系数。
- **联合训练两个网络**：
  - **流网络** \(\psi_\theta\)：参数化轨迹。
  - **速度网络** \(v_{\theta'}\)：建模时间相关的速度场。
- **损失函数**：
  - **条件流匹配损失 (CFM)**：监督速度网络匹配线性插值路径的速度 \(x_1 - x_0\)。
  - **导数一致性损失**：强制流网络的时间导数与速度网络在对应位置上的预测一致（使用stop-gradient），即
    \[
    \left\| \frac{d\psi_\theta}{dt}(x_0, t) - v_{\theta'}(\text{sg}[\psi_\theta(x_0, t)], t) \right\|^2
    \]
- **训练算法**（Algorithm 1）：
  1. 初始化 \(\theta, \theta'\)，时间窗口 \(\alpha_t \leftarrow 0\)。
  2. 每步采样 \(x_0 \sim \mu_0, x_1 \sim \mu_1, t \sim U[0,1]\)。
  3. 用CFM损失更新速度网络。
  4. 用导数损失更新流网络。
  5. 逐渐增加 \(\alpha_t\) 到1（文中指出实际上不需要手动调度 \(t\)，损失依然有效）。
- **采样算法**（Algorithm 2）：只需从噪声分布采样 \(x_0\)，然后计算 \(\psi_\theta(x_0, t=1)\) 即可一步生成。

## 3. 实验设计

### 数据集与场景
- **主要实验**：无条件图像生成，使用 **CelebAHQ-256** 数据集（256×256分辨率）。
- **附录补充**：类条件生成，使用 **ImageNet-256** 数据集。

### Benchmark 与对比方法
- **统一架构**：所有方法均使用相同的 DiT-B（Diffusion Transformer）骨干网络。
- **对比基线**：
  - **两阶段训练方法**：Progressive Distillation, Consistency Distillation, Reflow。
  - **单阶段训练方法**：Diffusion, Flow Matching, Consistency Training, Live Reflow, Shortcut Models。
- **评估指标**：FID-50k（50k生成样本计算FID），报告128步、4步、1步的结果（FlowFit仅单步）。

## 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量、训练时长等信息。仅提到：
  - 使用AdamW优化器，学习率4×10⁻⁵，无权重衰减，训练**500K迭代**。
  - 潜空间使用sd-vae-ft-mse自编码器。
  - 所有模型在相同实现和设置下训练。
  - 消融实验中提到受计算资源限制，仅探索到阶数8。
- **结论**：算力细节缺失，无法全面评估训练成本。

## 5. 实验数量与充分性
- **主要实验**：CelebAHQ-256无条件生成，对比多个基线，报告1步FID=14.1。
- **消融实验**：
  - **基函数阶数**：比较阶数2（FID 18.2）vs 阶数8（FID 14.1），高阶更好。
  - **基函数类型**：多项式（FID 14.1）vs 三角函数（FID 16.3），多项式更优。
- **定性实验**：潜空间插值（图2），显示语义平滑过渡。
- **充分性评估**：
  - **公平性**：与基线共享架构和训练设置，但基线结果引用自[3]，可能不完全一致（超参数、训练细节可能略有差异）。
  - **局限**：仅在单一数据集（CelebAHQ-256）上报告主要定量结果（ImageNet结果在附录，文中未展示具体FID）；仅使用FID指标，未报告IS、LPIPS等其他指标；缺乏统计显著性检验（如置信区间）；消融实验仅两个维度，范围有限。
  - 总体而言，实验设计合理，但覆盖范围不够广泛（如高分辨率数据集、更多架构变体、多步扩展等）。

## 6. 主要结论与发现
- FlowFit在**单步生成**上显著优于其他单阶段训练方法（FID 14.1，远优于Consistency Training的33.2、Shortcut Models的20.5等）。
- 与两阶段蒸馏方法（如Progressive Distillation FID 14.8）相当，但FlowFit是单阶段训练，更简单。
- 高阶多项式基（阶8）优于低阶；多项式基优于三角函数基。
- 潜空间展现出有意义的语义结构，插值结果平滑连续。

## 7. 优点
- **创新性**：首次提出用基函数拟合流轨迹实现单步生成，避免了迭代数值积分。
- **训练高效**：单阶段端到端训练，无需预训练的教师模型或额外数据生成。
- **推理极快**：一次前向传播即可生成，速度提升可达128倍（对比128步采样）。
- **生成质量高**：在单步生成中达到与蒸馏方法竞争的性能，且潜空间语义结构好。

## 8. 不足与局限
- **需要训练两个网络**（流网络+速度网络），增加了参数规模和训练开销。
- **仅支持单步推理**，无法灵活调整推理步数以在质量和速度间权衡（而Shortcut Models等支持可变步数）。
- **基函数阶数有限**：仅探索到阶数8，更高阶的效果未知，可能带来挑战。
- **实验覆盖不全面**：仅在CelebAHQ-256上报告主要结果；缺少高分辨率（如512×512）、多数据集、多种架构的验证；未报告计算资源（GPU型号、时长），难以复现和比较训练成本。
- **缺乏统计显著性**：未提供误差条或多次运行结果，单次结果可能存在波动。
- **潜在偏差风险**：基线结果来自其他文献，可能训练条件不完全一致；仅使用FID指标，可能忽略其他维度（如多样性、模式覆盖）。
- **方法局限性**：导数一致性损失依赖速度网络的预测，初期速度网络可能不准确，但作者声称算法稳定。

（完）
