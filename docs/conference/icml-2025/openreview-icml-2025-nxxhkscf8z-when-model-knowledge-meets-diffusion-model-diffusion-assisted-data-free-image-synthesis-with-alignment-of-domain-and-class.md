---
title: "When Model Knowledge meets Diffusion Model: Diffusion-assisted Data-free Image Synthesis with Alignment of Domain and Class"
title_zh: 当模型知识遇见扩散模型：领域与类别对齐的扩散辅助无数据图像合成
authors: "Yujin Kim, Hyunsoo Kim, Hyunwoo J. Kim, Suhyun Kim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NxxHkScf8z"
tags: ["query:real-ir"]
score: 7.0
evidence: 扩散辅助的无数据图像合成
tldr: DDIS 首次将文本到图像扩散模型用作强大的图像先验，以解决无数据图像合成中因缺乏自然图像先验而导致的分布偏差问题。该方法通过提取预训练模型知识并结合扩散先验，生成更符合目标域与类别的图像。实验表明，合成图像质量显著提升，为模型复用与数据受限场景提供了有效的生成方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1293, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 851, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 840, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 596, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 849, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 822, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1734, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1762, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1529, \"height\": 1549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1495, \"height\": 2118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1503, \"height\": 2124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1402, \"height\": 2252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1752, \"height\": 965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1747, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1765, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1761, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1103, \"height\": 1299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nxxhkscf8z/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1091, \"height\": 591, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1702, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1172, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1114, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nxxhkscf8z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1227, \"height\": 186, \"label\": \"Table\"}]"
motivation: 现有无数据图像合成方法因缺少自然图像先验，导致生成样本偏离训练数据分布。
method: 提出 DDIS，利用文本到图像扩散模型作为图像先验，并结合模型知识提取实现域与类别对齐。
result: 生成图像的质量和分布拟合度明显优于现有无数据合成方法。
conclusion: DDIS 开创性地将扩散先验引入无数据合成，提升了生成图像的真实性与实用性。
---

## Abstract
Open-source pre-trained models hold great potential for diverse applications, but their utility declines when their training data is unavailable. Data-Free Image Synthesis (DFIS) aims to generate images that approximate the learned data distribution of a pre-trained model without accessing the original data. However, existing DFIS methods produce samples that deviate from the training data distribution due to the lack of prior knowledge about natural images. To overcome this limitation, we propose DDIS, the first Diffusion-assisted Data-free Image Synthesis method that leverages a text-to-image diffusion model as a powerful image prior, improving synthetic image quality. DDIS extracts knowledge about the learned distribution from the given model and uses it to guide the diffusion model, enabling the generation of images that accurately align with the training data distribution. To achieve this, we introduce Domain Alignment Guidance (DAG) that aligns the synthetic data domain with the training data domain during the diffusion sampling process. Furthermore, we optimize a single Class Alignment Token (CAT) embedding to effectively capture class-specific attributes in the training dataset. Experiments on PACS and ImageNet demonstrate that DDIS outperforms prior DFIS methods by generating samples that better reflect the training data distribution, achieving SOTA performance in data-free applications.

---

## 论文详细总结（自动生成）

# 论文总结：When Model Knowledge meets Diffusion Model: Diffusion-assisted Data-free Image Synthesis with Alignment of Domain and Class

## 1. 论文的核心问题与整体含义
- **研究背景**：开源预训练模型（如图像分类器）具有广泛的应用潜力，但往往因隐私、版权等原因无法获取其原始训练数据，限制了其在知识蒸馏、模型剪枝等任务中的使用。
- **核心问题**：如何在无法访问原始训练数据的条件下，生成逼近模型所学数据分布的图像？现有数据自由图像合成方法（DFIS）由于缺乏自然图像先验，搜索空间极大，生成的图像常存在不自然纹理、域偏移等问题，与真实训练分布差距明显。
- **整体含义**：首次将文本到图像的扩散模型（T2I diffusion model）作为强大的图像先验引入 DFIS，通过从给定的预训练模型中提取分布知识来引导扩散过程，实现生成图像在**域**和**类别**两个层面的精细对齐，从而显著提升合成图像的质量与下游应用效果。

## 2. 论文提出的方法论
- **核心思想**：将扩散模型强大的自然图像生成能力与 DFIS 相结合，并通过两个关键技术弥补直接使用扩散模型导致的分布偏差。
- **关键技术细节**：
  - **Domain Alignment Guidance (DAG)**：
    - **动机**：Batch Normalization（BN）层的运行统计量（均值、方差）编码了训练集的域知识。
    - **做法**：在扩散采样的每个时间步，将当前生成的图像潜变量解码为图像，送入预训练模型计算各 BN 层的特征图统计量，与模型中储存的运行统计量计算 MSE 损失。将该损失对潜变量的梯度作为引导项，修正采样方向。
    - **公式**：$\tilde{z}_t = z_t - \eta \nabla_{z_t} \mathcal{L}_{BN}(D(z_t))$，其中 $\mathcal{L}_{BN}$ 为 BN 层统计量对齐损失，$D$ 为解码器。然后将修正后的潜变量 $\tilde{z}_t$ 结合无分类器引导（CFG）进行噪声预测，从而迭代生成域对齐的图像。
  - **Class Alignment Token (CAT)**：
    - **动机**：类别标签本身可能含有歧义（如“tiger cat”被当作“虎”），无法准确描述训练集中的细粒度类别属性。
    - **做法**：在扩散模型的文本编码器中新增一个伪词标记 `S_c`，并仅优化其嵌入向量 $v_c$。使用固定模板 `“A/An {S_c} {class label}”` 构建提示词，通过 DAG 引导的采样过程生成最终图像 $\hat{x}_0$，将该图像输入预训练分类器，计算交叉熵损失，反向传播仅更新 CAT 的嵌入。
    - **特点**：仅优化最终时刻的图像损失，且梯度不经过整个扩散过程（梯度跳跃），大幅降低显存占用，并利用分类器对真实分布的感知引导嵌入学到正确的类别特征。
- **算法流程**：对每个类别，定义并初始化 CAT，迭代优化其嵌入；优化完成后，使用固定的 CAT 和 DAG 即可快速合成该类别的图像。

## 3. 实验设计
- **数据集与场景**：
  - **多域图像合成**：照片域（ImageNet-1k 1000 类）、艺术画域（PACS Art Painting）、卡通域（PACS Cartoon）、漫画域（StyleAligned Manga）、讽刺画域（StyleAligned Caricature）。每域约 7 类（ImageNet-1k 为 1000 类），用于验证方法的域适应能力。
  - **数据自由应用**：数据自由知识蒸馏（DFKD）与数据自由剪枝微调，使用 PACS 与 ImageNet-1k。
- **评价指标**：
  - **图像质量**：Inception Score (IS)、Fréchet Inception Distance (FID)、Precision、Recall。
  - **下游任务**：知识蒸馏后学生模型的 Top-1 准确率；剪枝微调后模型在不同剪枝率下的准确率。
- **对比方法**：
  - **传统 DFIS**：DeepInversion (DI)、PlugInInversion (PII)。
  - **朴素扩散基线**：直接使用 Stable Diffusion 2.1 生成图像（SD 2.1），无任何引导。
  - 同时也对比了使用原始训练数据的理想情况（Original）。

## 4. 资源与算力
- **硬件配置**：实验中提到使用单张 **NVIDIA RTX 4090** GPU。
- **计算开销**：
  - 每个类别优化 CAT 嵌入大约耗时 **7.5 分钟**（类少时），找到最优嵌入后可固定用于快速采样。
  - 合成 10 万张 ImageNet-1k 图像的总迭代次数与耗时对比：DDIS 仅需 **3 万次**迭代（30 轮/类 × 1000 类），总计约 **126 小时**；而 DI 需 800 万次迭代（约 1844 小时），PII 需 112 万次迭代（约 245 小时），体现了显著的效率优势。

## 5. 实验数量与充分性
- **主要实验组数**：
  - **定性可视化**：对比多种方法在 PACS 艺术画、卡通、StyleAligned 以及 ImageNet-1k 上的生成样本，展示域对齐和类别消歧效果。
  - **定量图像质量**：在 5 个域上进行了 IS、FID、Precision、Recall 的全面评估（表 1）。
  - **数据自由知识蒸馏**：在 3 个数据集（PACS-art, cartoon, ImageNet-1k）上，使用不同师生网络结构组合（ResNet-34/18, VGG-16/11 等）进行了约 18 组对比实验（表 2）。
  - **数据自由剪枝**：在 3 个数据集上对 ResNet-34 和 VGG-16 进行 50%~90% 剪枝比下的微调，提供准确率曲线（图 6）。
  - **消融实验**：验证 DAG 与 CAT 的独立作用，以及不同组件组合对 IS、FID、Precision、Recall 的影响。
  - **额外分析**：CAT 嵌入权重缩放的影响、零样本类合成、设计选择验证等。
- **充分性与公平性**：实验覆盖了多样的数据域和模型架构，对比了当前 SOTA 的 DFIS 方法，且统一使用相同的 Stable Diffusion 2.1 基座，对比公平。消融实验和参数分析也较为细致。

## 6. 论文的主要结论与发现
- DDIS 通过结合 T2I 扩散模型的图像先验与预训练模型的内部知识，成功解决了传统 DFIS 生成图像偏离真实分布的问题。
- **域对齐**（DAG）能有效利用 BN 统计量将合成图像引导至训练集所属的视觉域。
- **类别对齐**（CAT）能通过简单优化一个令牌嵌入，解决类别标签的词汇歧义，精准捕捉细粒度类别属性。
- 生成的图像在视觉质量和分布近似度上大幅超越现有 DFIS 方法，并在数据自由知识蒸馏和剪枝中取得最优性能，甚至优于直接使用扩散模型生成的数据。

## 7. 优点
- **方法新颖性**：首次将扩散模型用作 DFIS 的图像先验，提出了域与类别双重对齐的新框架。
- **技术简洁有效**：DAG 直接借用 BN 统计量，无需额外训练；CAT 仅优化极少量参数（784 维），计算高效且能解决语义歧义。
- **实验全面扎实**：覆盖 5 个视觉域、2 种下游应用，定量指标丰富，并与多个强 Baseline 进行了严格对比。
- **实用性强**：一旦获得 CAT 嵌入，图像采样速度极快，且整体效率优于传统迭代优化方法。

## 8. 不足与局限
- **对特定域效果欠佳**：在**素描（Sketch）** 等高度抽象域上表现不佳，生成的图像仍难以准确捕捉该类抽象特征。
- **依赖模型架构**：DAG 依赖于预训练模型中的 BN 层统计数据，因此不能直接应用于无 BN 层的模型（如 Transformer），限制了方法的通用性。作者计划在未来探索模型无关的域引导方法。
- **隐私风险说明**：作者声明方法仅利用整个数据集的平均统计量，不易泄露个体样本，但数据合成方法本身仍存在潜在的隐私争议，文中未有机制性保障。
- **计算资源消耗**：虽然整体效率优于传统 DFIS，但 CAT 优化过程仍需对每个类别进行一定轮次的扩散采样与反向传播，对于类别数极多（如 ImageNet-21k）的情况可能计算量较大。

（完）
