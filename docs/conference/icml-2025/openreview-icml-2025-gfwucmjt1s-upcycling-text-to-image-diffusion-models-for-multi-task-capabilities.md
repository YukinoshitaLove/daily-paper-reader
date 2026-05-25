---
title: Upcycling Text-to-Image Diffusion Models for Multi-Task Capabilities
title_zh: 文本到图像扩散模型的多任务升级
authors: "Ruchika Chavhan, Abhinav Mehrotra, Malcolm Chadwick, Alberto Gil Couto Pimentel Ramos, Luca Morreale, Mehdi Noroozi, Sourav Bhattacharya"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=GfWucMJt1S"
tags: ["query:real-ir"]
score: 8.0
evidence: 将文本到图像扩散模型升级用于多任务图像到图像生成
tldr: 本文提出多任务升级方法MTU，通过将预训练文本到图像扩散模型中的FFN层替换为小专家网络并引入动态路由，实现高效的多任务图像到图像生成。该方法无需重新训练，便于设备端部署，扩展了扩散模型的应用范围。MTU在多个图像合成任务上验证了有效性，为扩散模型的多功能化提供了轻量级方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1524, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1626, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1781, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1624, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1419, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1608, \"height\": 1356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 1865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1612, \"height\": 1896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gfwucmjt1s/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1616, \"height\": 1972, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 862, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gfwucmjt1s/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1291, \"height\": 244, \"label\": \"Table\"}]"
motivation: 现有方法扩展任务需重训或增参，不利于部署。
method: 用专家网络和动态路由替换FFN层，微调扩展多任务。
result: 实现多种图像到图像任务，无需全量重训。
conclusion: 提供了一种高效扩展扩散模型能力的方法。
---

## Abstract
Text-to-image synthesis has witnessed remarkable advancements in recent years. Many attempts have been made to adopt text-to-image models to support multiple tasks. However, existing approaches typically require resource-intensive re-training or additional parameters to accommodate for the new tasks, which makes the model inefficient for on-device deployment. We propose *Multi-Task Upcycling* (MTU), a simple yet effective recipe that extends the capabilities of a pre-trained text-to-image diffusion model to support a variety of image-to-image generation tasks. MTU replaces Feed-Forward Network (FFN) layers in the diffusion model with smaller FFNs, referred to as *experts*, and combines them with a dynamic routing mechanism. To the best of our knowledge, MTU is the first multi-task diffusion modeling approach that seamlessly blends multi-tasking with on-device compatibility, by mitigating the issue of parameter inflation. We show that the performance of MTU is on par with the single-task fine-tuned diffusion models across several tasks including *image editing, super-resolution*, and *inpainting*, while maintaining similar latency and computational load (GFLOPs) as the single-task fine-tuned models.

---

## 论文详细总结（自动生成）

## 论文总结：Upcycling Text-to-Image Diffusion Models for Multi-Task Capabilities

### 1. 核心问题与整体含义
- **研究动机**：文生图扩散模型（如Stable Diffusion）能力强大，但在边缘设备上部署时，若要同时支持多个图像生成任务（编辑、超分辨率、修复等），现有方法通常需要重新训练全部参数或引入大量新增参数，导致模型庞大、计算代价高昂，难以实现高效的本地部署。
- **核心问题**：如何在**不显著增加参数量和计算开销**的前提下，将单个预训练的文本到图像扩散模型扩展为可处理多种图像到图像（I2I）任务的多功能模型。
- **整体含义**：提出“多任务升级”（Multi-Task Upcycling, MTU），利用混合专家（MoE）思想，将扩散模型的FFN层拆分为多个小型专家网络，并引入动态路由，实现**参数高效、计算量可控的多任务扩散模型**，特别适配于设备端部署。

### 2. 方法论
- **核心思想**：基于一个关键观察——微调扩散模型时，FFN层的权值相较于预训练权值偏移最大（表明FFN层专职学习下游任务），从而将FFN层替换为“若干小专家+任务路由”的结构。
- **关键技术细节**：
  - **专家架构替换**：将预训练模型的每个FFN层拆分成 $N$ 个较小的专家FFN，每个专家的隐藏维度 $d_{\text{expert}} = d_{\text{FFN}} / N$，从而保持总参数量近似不变。
  - **动态路由**：为每个任务 $\tau$ 学习一个任务嵌入 $e_\tau$，通过一个轻量路由器（两层MLP+softmax）为每个专家生成加权系数。层的输出为专家输出的加权和：
    $$
    E^l_{\text{FFN}}(x_\tau) = \sum_{i=1}^{N} w^l_i \times E^l_i(x_\tau), \quad w^l_i = \operatorname{softmax}(g(e_\tau;\theta^l_r))_i
    $$
  - **任务特定层归一化**：在每个专家前添加任务特定的LayerNorm，以更好地适应不同任务的特征分布。
  - **任务特定输入层**：针对不同任务（如图像条件通道数不同），使用独立的输入卷积层。
- **训练流程**：冻结主干网络中除FFN专家、路由器、任务特定LayerNorm和输入层外的所有参数。使用多任务联合损失（加和所有任务的扩散噪声预测损失）进行训练。

### 3. 实验设计
- **数据集/场景**：
  - **文生图 (T2I)**：COCO Captions数据集。
  - **图像编辑 (IE)**：InstructPix2Pix数据集，基于文本指令编辑图像。
  - **超分辨率 (SR)**：Real-ESRGAN数据集，生成低分辨率图像作为输入。
  - **修复 (Inpainting, IP)**：GQA-Inpaint数据集，文本描述引导的目标移除。
- **基准与对比方法**：
  - 单任务基线：对应任务上单独微调的扩散模型（如InstructPix2Pix、官方SDv1.5的SR和IP版本）。
  - 多任务基线：Versatile Diffusion、UniDiffuser。
  - 参数高效微调（PEFT）方法：在FFN层上应用LoRA和IA³。
- **评价指标**：T2I用FID；IE用I-T Directional Similarity；SR用LPIPS；IP用I-I Directional Similarity。同时比较计算量（TFLOPs）和参数量。

### 4. 资源与算力
- **GPU配置**：8张A100 GPU。
- **训练轮次**：100个epochs。
- **批量大小**：每GPU 16张图片，图像分辨率512×512。
- **额外说明**：SDXL使用AdamW优化器（学习率5e-5，权重衰减0.01），SDv1.5使用Adam（学习率1e-4）。推理时SDv1.5用20步，SDXL用50步去噪。论文未提供具体的总训练耗时（wall clock time），但描述了硬件规模和训练设置。

### 5. 实验数量与充分性
- **实验组数**：进行了丰富的实验，包括：
  - 主结果：在SDv1.5和SDXL上，比较MTU与多种单任务、多任务及PEFT方法（表格2、3）。
  - 消融实验：专家数量、专家尺寸、粒度约束（表格4），任务组合干扰分析（表格5），路由器专家分配可视化（图5）。
  - 模型骨架：覆盖两种不同规模（860M，2.6B）的扩散模型。
- **充分性与客观性**：实验设计较为全面，对比了单任务、多任务和PEFT等方法，并严格在同计算量或等参数量的设置下进行分析。消融研究深入探讨了专家数量与容量的权衡，任务间互相干扰也做了多种组合测试，总体客观且充分。

### 6. 主要结论与发现
- MTU能在与单任务模型相似的**计算量和参数量**下，取得与其相当甚至更优的性能（例如SDv1.5的IE指标17.2对15.4，SR指标24.8对38.0大幅提升；SDXL也保持竞争力）。
- 与参数高效微调（LoRA, IA³）相比，MTU在所有任务上都有显著优势。
- FFN层是扩散模型适配下游任务的关键组件，将其拆分为专家并配合路由和任务特定归一化，能有效实现多任务学习。
- 任务间存在干扰：例如T2I与IE高度兼容，IP与SR兼容性较低。论文建议未来可引入梯度冲突缓解等技术。
- 对于浅层模型（SDv1.5），较小专家更有利；对于深层模型（SDXL），保持原始FFN尺寸的专家表现更好。

### 7. 优点
- **参数与计算高效**：首次在扩散模型领域实现“等FLOPs”多任务升级，无需额外推理开销。
- **方法简单有效**：基于可解释的FFN偏移观察，改造轻量，易于实现。
- **设备端友好**：特意考虑了边缘部署的限制，保持模型紧凑。
- **实验详实**：覆盖多种任务、模型尺度、对比方法和消融维度，提供实用的硬件选择指南（如专家数目与模型深度的关系）。

### 8. 不足与局限
- **任务干扰问题未完全解决**：部分任务组合（如IP与SR）存在明显性能下降，未提出自动化的多任务平衡策略。
- **应用范围限制**：目前仅在基于UNet的潜扩散模型（SDv1.5, SDXL）上验证，未在更先进的架构（如DiT/Transformer类扩散模型）上测试。
- **路由器路由策略单一**：仅使用基于任务嵌入的静态权值，未考虑输入内容动态路由，可能限制灵活性。
- **训练数据与任务种类**：仅涉及4种I2I任务，尚未扩展到更多模态或更复杂的生成类型。
- **训练资源需求未给出精确耗时**，仅说明8张A100训练100个epoch，实际时间消耗对复现参考有限。
- **专家尺寸与模型深度的适配结论**主要基于经验观察，缺少理论解释。

（完）
