---
title: One Diffusion Step to Real-World Super-Resolution via Flow Trajectory Distillation
title_zh: 单步扩散实现真实世界超分辨率：基于流轨迹蒸馏
authors: "Jianze Li, Jiezhang Cao, Yong Guo, Wenbo Li, Yulun Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=riYSkLG0vt"
tags: ["query:real-ir"]
score: 10.0
evidence: 基于流匹配的单步扩散真实世界超分辨率
tldr: 针对多步扩散模型计算量大的问题，提出FluxSR，一种基于流匹配的单步扩散真实世界超分辨率方法。通过利用FLUX.1-dev作为教师模型和基座模型，实现了一步采样生成高质量图像，显著降低了推理开销。该方法在真实场景超分辨率任务上取得优异效果，为高效图像增强提供了新方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-riysklg0vt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-riysklg0vt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1728, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-riysklg0vt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1760, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-riysklg0vt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-riysklg0vt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 787, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-riysklg0vt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-riysklg0vt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-riysklg0vt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-riysklg0vt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 237, \"label\": \"Table\"}]"
motivation: 多步扩散模型计算开销大，单步模型受限于教师模型性能。
method: 使用FLUX.1-dev作为教师和基座，通过流轨迹蒸馏实现一步超分辨率。
result: 在真实世界超分辨率上实现高效且高质量的一步生成。
conclusion: FluxSR有效平衡了速度与质量，推动了扩散模型在图像增强中的应用。
---

## Abstract
Diffusion models (DMs) have significantly advanced the development of real-world image super-resolution (Real-ISR), but the computational cost of multi-step diffusion models limits their application. One-step diffusion models generate high-quality images in a one sampling step, greatly reducing computational overhead and inference latency. However, most existing one-step diffusion methods are constrained by the performance of the teacher model, where poor teacher performance results in image artifacts. To address this limitation, we propose FluxSR, a novel one-step diffusion Real-ISR technique based on flow matching models. We use the state-of-the-art diffusion model FLUX.1-dev as both the teacher model and the base model. First, we introduce Flow Trajectory Distillation (FTD) to distill a multi-step flow matching model into a one-step Real-ISR. Second, to improve image realism and address high-frequency artifact issues in generated images, we propose TV-LPIPS as a perceptual loss and introduce Attention Diversification Loss (ADL) as a regularization term to reduce token similarity in transformer, thereby eliminating high-frequency artifacts. Comprehensive experiments demonstrate that our method outperforms existing one-step diffusion-based Real-ISR methods. The code and model will be released at \url{https://github.com/JianzeLi-114/FluxSR}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：真实世界图像超分辨率（Real-ISR）任务中，多步扩散模型（如基于FLUX.1-dev的大模型）虽然能生成高质量、逼真的图像，但其迭代采样过程计算开销极高，难以实际应用。
- **研究动机**：现有单步蒸馏方法虽然能大幅降低推理延迟，但在处理大型流匹配模型时面临两大挑战：
  1.  **生成分布偏移**：直接微调预训练文本到图像（T2I）模型会破坏其原有的噪声-图像映射流，导致生成图像出现伪影和退化。
  2.  **训练成本高昂**：蒸馏一个超大规模的学生模型时，若额外引入同规模教师模型在线参与训练，会带来极其庞大甚至不可行的显存占用（例如8张A800-80GB GPU也无法满足直接应用OSEDiff在FLUX上的需求）。
- **整体含义**：论文旨在提出一种高效、大模型友好的一步扩散Real-ISR方法，在保留大型预训练模型强大生成能力的同时，实现一步采样的极致推理效率。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想：流轨迹蒸馏（Flow Trajectory Distillation, FTD）**
  - 不直接学习从低分辨率（LR）图像到高分辨率（HR）图像的流，而是通过固定预训练的噪声-图像流（T2I流），间接推导出LR-HR流。
  - 将蒸馏问题转化为：在保持HR图像分布（数据的真实分布）不变的条件下，学习一个从LR图像分布出发的流轨迹，从而避免生成分布偏移。
- **关键技术细节**
  1.  **建立流轨迹关系**：利用流匹配的线性性质，定义LR图像对应的时刻 \(T_L\)，推导出从LR图像 \(x_L\) 到HR图像 \(x_0\) 的流速度 \(u_t^{SR}\)、原始噪声-图像流速度 \(u_t\) 和噪声-LR流速度 \(u_t^L\) 三者关系：\(u_t^{SR} = (u_t - u_t^L) / T_L \cdot (1-T_L)\)。通过只参数化 \(u_t^{SR}\)，让单一模型同时表达 \(u_t^{SR}\) 和 \(u_t^L\)。
  2.  **大模型友好训练策略**：
      - 教师模型（FLUX.1-dev）**无需在线参与**训练。预先用教师模型生成大量噪声-图像对作为离线训练数据，直接计算出真实的 \(u_t\)，避免了单步推断的估计误差和庞大的显存需求。
      - 蒸馏损失（FTD loss）结合预测值和真实值计算，并辅以重建损失。
  3.  **抗伪影损失函数**：
      - **TV-LPIPS 感知损失**：在标准LPIPS基础上，增加对图像总变分（Total Variation）图的LPIPS距离，促使模型抑制平坦区域的像素突变，同时增强对高频成分的感知，减少周期性高频伪影。
      - **注意力多样化损失（Attention Diversification Loss, ADL）**：作为正则化项，强制Transformer中不同token的特征向量多样化，降低彼此余弦相似度，从而消除由于token同质化导致的周期性棋盘状伪影。
- **训练算法流程**（对应原文 Algorithm 1）
  1. 从预生成的噪声-图像对数据集采样。
  2. 计算FTD损失：对随机时刻 \(t \in [T_L, 1]\)，利用公式计算预测速度和损失。
  3. 计算重建损失：组合MSE和TV-LPIPS。
  4. 计算ADL损失。
  5. 总损失为三者加权和，更新生成器 \(G_\theta\) 参数。

### 3. 实验设计：使用了哪些数据集/场景，它的benchmark是什么，对比了哪些方法

- **训练数据**：
  - 由FLUX.1-dev模型生成的2400对尺寸为1024x1024的噪声-图像合成数据。
  - 对应的LR图像通过RealESRGAN退化流水线生成。**未使用任何真实图像数据**。
- **测试数据集**：
  - **合成数据集**：DIV2K-val（应用相同退化）。
  - **真实数据集**：RealSR、RealSet65。
- **评价指标**：
  - 全参考指标：PSNR、SSIM、LPIPS、DISTS。
  - 无参考指标：MUSIQ、MANIQA、TOPIQ、Q-Align。
- **对比方法**：
  - **多步扩散方法**：StableSR (s200)、DiffBIR (s50)、SeeSR (s50)、ResShift (s15)、AddSR (s4)。
  - **单步扩散方法**：SinSR (s1)、OSEDiff (s1)、AddSR (s1)、TSD-SR (s1)。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力

- 论文**未明确说明**训练FluxSR最终使用的GPU型号、数量以及具体训练时长。
- 文中仅作为**动机提及**，当尝试将现有方法OSEDiff直接应用于FLUX.1-dev时，即使是配备**8张A800-80GB GPU**的服务器也会出现**显存不足**的问题，以此反衬出其提出的大模型友好训练策略在降低资源需求方面的必要性。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平

- **实验组数概览**：
  - **主实验**：在3个数据集（DIV2K-val、RealSR、RealSet65）上，对比了9种现有方法（4种多步，4种单步+自身），共产生多个指标结果表格。
  - **消融实验**：在RealSR数据集上进行了2组消融研究。
    1.  **FTD损失有效性**：对比仅用重建损失训练与加入FTD损失的效果。
    2.  **损失函数组件消融**：对比不同感知损失（LPIPS、TV-LPIPS、EA-DISTS）和有无ADL正则化项的多种组合。
  - **定性实验**：提供了多幅视觉对比图，展示FluxSR与其他方法在细节、伪影抑制上的优势。
- **充分性与公平性评价**：
  - 实验设计较为充分，涵盖了合成和真实场景，使用了全参考和无参考等多维度指标，并从定量和定性角度全面评估。
  - 对比方法包含了当前性能最优的单步和多步扩散超分模型，基线选取有代表性。
  - 消融实验清晰地验证了核心模块（FTD）和定制化损失（TV-LPIPS、ADL）的贡献。
  - 所有对比均在相同的标准benchmark上进行，指标一致，比较公平。

### 6. 论文的主要结论与发现

- FluxSR作为一种基于12B参数大模型的一步扩散Real-ISR方法，在所有测试数据集上的**无参考感知质量指标（MUSIQ、MANIQA等）均达到最优**，显著超越其他单步方法，甚至逼近或超越了部分多步方法。
- 提出的**流轨迹蒸馏（FTD）** 成功解决了大型预训练模型直接微调时出现的生成分布偏移问题，是模型保持高逼真度的关键。
- **TV-LPIPS和ADL损失**的有效组合能够显著减轻生成图像中的高频周期性伪影，进一步提高视觉质量。
- 整体而言，FluxSR在仅需一步采样的前提下，实现了极佳的图像真实感和细节还原能力。

### 7. 优点：方法或实验设计上有哪些亮点

- **首个大模型一步超分**：首次在超过120亿参数的FLUX模型上成功应用一步蒸馏实现Real-ISR，具有开创性。
- **优雅的理论框架（FTD）**：巧妙的利用流匹配线性性质，将T2I流和LR-HR流关联起来，无需破坏原有生成分布即可完成知识迁移，理论清晰且有效。
- **实用的训练策略**：通过离线生成噪声-图像对，彻底排除了庞大的教师模型在线训练的需求，极大降低了训练显存门槛和计算成本，使大模型蒸馏成为可能。
- **针对性的伪影解决方案**：提出的TV-LPIPS和ADL分别从像素和特征层面，精准地解决了在超大模型蒸馏中观察到的特定高频伪影问题，实验效果显著。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **模型体积与效率**：模型参数量巨大（12B），计算成本依然很高，作者也承认其参数多、成本高，尚未达到轻量化部署的要求。
- **伪影未完全消除**：周期性伪影问题虽然得到缓解，但论文明确指出“我们并未完全消除”它，表明方法仍有改进空间。
- **训练数据依赖性**：虽然无需真实图像，但模型蒸馏完全依赖于教师模型生成的2400对合成数据，其泛化能力受限于教师模型所覆盖的图像分布和退化模拟的多样性。
- **实验对比范围**：主要对比集中在扩散模型系列方法，未与非扩散的GAN或传统对比学习等SOTA超分方法进行横向对比（尽管可能已在补充材料中提供，但主文中未体现）。
- **全参考指标表现**：在PSNR、SSIM等像素级保真度指标上，作为生成式方法，其得分普遍低于部分保真度优先的方法，体现了生成真实性和像素保真度之间的固有权衡。

（完）
