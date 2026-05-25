---
title: Manipulation Inversion by Adversarial Learning on Latent Statistical Manifold
title_zh: 基于隐统计流形对抗学习的操控逆映射
authors: "Jialu Zhang, yifei li, Mai Xu, Shengxi Li, Shuting Liu, Lai Jiang, Shuhang Gu"
date: 2025-01-24
pdf: "https://openreview.net/pdf?id=qyGurHI4As"
tags: ["query:real-ir"]
score: 8.0
evidence: 通过建立隐概率模型和统计流形改进GAN逆映射以实现真实图像编辑
tldr: 本文系统研究GAN的隐生成空间，揭示编辑真实性和重建精度可在抗操控逆映射下统一，提出将隐空间建模为概率模型，并利用统计流形通过对抗学习进行操控逆映射，从而提升编辑的真实性，解决了现有GAN逆映射方法编辑效果不佳的问题。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1681, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 778, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1698, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1691, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 801, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1583, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1583, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qygurhi4as/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1593, \"height\": 847, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qygurhi4as/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qygurhi4as/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 806, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qygurhi4as/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qygurhi4as/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 753, \"height\": 335, \"label\": \"Table\"}]"
motivation: 现有GAN逆映射主要关注重建而忽略编辑真实性。
method: 将隐空间建模为概率模型，在统计流形上进行对抗学习实现操控逆映射。
result: 统一了编辑真实性与重建精度，显著提升编辑效果。
conclusion: 为GAN逆映射在语义编辑中的应用提供了新方法。
---

## Abstract
The inversion of generative adversarial network (GAN) is able to investigate rich semantics within the generative models, thus receiving increasing research efforts most recently. Existing GAN inversion methods focus on reconstructing images, with relatively less focus on improving the editing realism, the most important criterion for evaluating the semantics achieved by inversion.  In this paper, we systematically investigate the latent generating space and prove that both the realism of editing and accuracy of reconstruction can be unified under the umbrella of the inversion against manipulations. Motivated by this, we propose to establish the generating space as latent probabilistic models, followed by the developed statistical manifold to minimise the distribution discrepancy. Based on the manifold, we further propose an adversarial learning strategy to avoid the excessive enumeration when calculating the manipulation inversion metric. We may also need to point out that the proposed method is universal to different architectures, as a novel plugin inversion method. We comprehensively evaluate our method across different types of network architectures, comparing it against the state-of-the-art inversion methods. The experimental results demonstrate that our method is able to achieve superior performances on both reconstruction accuracy and realism of editing.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：当前 GAN 逆映射（Inversion）方法大多侧重图像重建精度，对语义编辑真实性的关注不足。编辑真实感是衡量逆映射语义保真度的重要标准，但常与重建质量形成 trade-off。
- **核心问题**：如何同时提升 GAN 逆映射的**重建精度**与**编辑真实性**？作者通过对 StyleGAN 隐空间的性质分析，提出将两者统一在“**操控逆映射**”（Manipulation Inversion）框架下：即要求逆映射器不仅能完美还原原图，还能精确还原经过任意语义编辑后的图像。
- **整体含义**：通过建立隐统计流形并进行对抗学习，本文首次系统地处理操控逆映射问题，为 GAN 逆映射提供一种即插即用的新范式。

## 方法论
- **核心思想**：
  - 将隐空间建模为**概率分布**而非单点估计，以刻画局部曲率变化（ anisotropy 与 inconsistent variation 等发现）。
  - 在**统计流形**上优化分布差异，使逆映射器不仅能匹配单点隐向量，还能保持该点邻域内的编辑一致性。
  - 用**对抗学习**高效近似操控逆映射损失，避免过度枚举。
- **关键技术细节**：
  - **隐空间概率建模**：  
    \( w = S^T n + \epsilon + c \)，其中 \( S \) 为语义矩阵（每列一个解耦方向），\( \epsilon = J^T \eta \) 为经雅可比映射的图像噪声。分布分别为 \( \mathcal{N}(f(x), S^TS + J^TJ) \) 和 \( \mathcal{N}(h(z), S^TS + J^TJ) \)。
  - **统计流形构建**：  
    采用 Cramer-Rao 度量建立黎曼流形 \( M_w \)，其度量张量为 \( (S^TS + J^TJ)^{-1} \)。在此基础上定义黎曼梯度 \( \nabla_r \phi(w) = \nabla_e \phi(w)^T (S^TS + J^TJ) \)。
  - **操控逆映射优化**：  
    \[
    \min_f L_r = \min_f \int \left\| f\!\left(g\!\left(w+\beta \frac{v}{\|v\|}\right)\right) - \beta \frac{v}{\|v\|} - w \right\|_2^2 dv
    \]
    为免去积分，采用**对抗学习**寻找使该损失最大的方向 \( v^* \)（通过幂迭代求 Hessian 主特征向量），使优化 \( L_r^* \) 成为原损失的上界。
  - **总体损失**：  
    \( \mathcal{L} = \mathcal{L}_r + \lambda_1 \mathcal{L}_j + \lambda_2 \mathcal{L}_s + \lambda_3 \mathcal{L}_{ori} \)，其中 \( \mathcal{L}_{ori} \) 包含 MSE、LPIPS 和 ID 损失。
- **流程**：固定一个预测练编码器作为投影器生成 \( w \)，计算 \( v^* \) 并更新 \( w \)，再优化逆映射器（inverter）。

## 实验设计
- **数据集**：
  - 人脸：FFHQ 训练（1024×1024），CelebA-HQ 评估（1024×1024）。
  - 汽车：Stanford Cars（512×512），官方训练/测试划分。
  - 教堂：LSUN Church（256×256），官方划分。
- **对比方法**：
  - pSp、E4E、ReStyle（pSp 和 e4e 版本）、HyperInverter、HFGI、FSE、E2Style、StyleRes 等多个 SOTA 方法。
- **评估指标**：
  - 操控逆映射和重建任务均采用 MSE、LPIPS、SSIM、MS-SSIM。
  - 编辑方向：人脸用 InterFaceGAN（smile, eyeglasses, makeup），车/教堂用 GANSpace 的 PCA 方向。

## 资源与算力
- 文中明确说明：“**All evaluation experiments were conducted using a single NVIDIA GeForce RTX 4090 GPU.**”
- 未提及训练所用 GPU 数量、显存需求、训练时长或总计算量（如 GPU 小时）。

## 实验数量与充分性
- **实验组数**：
  - 在 **3 个场景**（人脸、汽车、教堂）上分别进行了操控逆映射和重建精度的定量对比（表1、表2）。
  - **消融实验**（表3）：逐步添加 latent restriction、Jacobian component、semantic component、adversarial learning，验证各模块贡献。
  - **架构兼容性验证**（表4、图5）：将所提方法嵌入 pSp、HFGI、E2Style、FSE 四种不同架构，均带来一致提升。
  - 提供了丰富的主观结果（图4、图6、图9 及附录编辑示例）。
- **充分性评价**：实验覆盖多个域、多个 SOTA 基准和消融研究，对比公平（使用官方预训练权重），能够有效支撑核心主张。缺少计算效率（推理时间、训练时间）和用户调研的定量分析，但整体比较充分。

## 主要结论与发现
- 通过显式地建模并优化操控逆映射，可以在重建质量和编辑真实感上**同时取得显著提升**。
- 所提方法可作为**即插即用的通用模块**，兼容不同编码器架构（pSp、HFGI、E2Style、FSE）并稳定增强其性能。
- 隐统计流形和对抗学习策略有效地考虑了局部曲率，克服了以往逐点估计在编辑场景下的缺陷。

## 优点
- **问题新颖性**：首次系统定义并解决“操控逆映射”问题，将重建与编辑统一到一个优化框架。
- **理论支撑**：基于隐空间性质分析（3个发现）和 Lemma 4.2 证明，方法有较强的几何直觉和理论依据。
- **即插即用**：不依赖特定生成器架构，可作为现有编码器的增强插件，实用性强。
- **实验扎实**：涵盖多域、多指标、多基准方法，并有充分的消融和兼容性分析。

## 不足与局限
- **计算效率未讨论**：缺乏推理时间、训练收敛速度等效率指标，与轻量编码器结合时的额外开销未知。
- **依赖外部语义方向**：编辑方向来自 InterFaceGAN 或 GANSpace，若这些方向质量不高或场景缺少预计算方向，系统泛化能力可能受限。
- **训练细节耦合**：需要设定多个超参数（如 \( \lambda_1, \lambda_2, \lambda_3 \) 以及编辑尺度 \( \beta \)），不同应用可能需要重新调优。
- **对抗学习开销**：虽然避免了枚举，但幂迭代求 Hessian 主特征向量仍带来额外计算，文中并未对比其相对于直接采样的效率提升定量结果。
- **局限域测试**：主要在人脸、汽车、教堂场景验证，缺少更多类别（如动物、风景）的测试；也未讨论在非 StyleGAN 生成器上的表现。
- **安全风险**：编辑真实性的提升可能加剧深度伪造等滥用风险，文中虽在 broader impact 提及，但未在方法层面内置防护。

（完）
