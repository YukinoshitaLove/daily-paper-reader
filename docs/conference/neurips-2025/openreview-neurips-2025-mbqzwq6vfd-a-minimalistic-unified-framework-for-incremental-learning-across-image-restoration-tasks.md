---
title: A Minimalistic Unified Framework for Incremental Learning across Image Restoration Tasks
title_zh: 一个极简的统一框架用于图像修复任务的增量学习
authors: "Xiaoxuan Gong, Jie Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MBQZwQ6vFd"
tags: ["query:real-ir"]
score: 9.0
evidence: 图像修复的任务增量学习
tldr: 现有全合一图像修复架构针对固定任务集，无法增量添加新任务而不遗忘旧任务。MINI框架通过简单有效的机制解决跨任务参数干扰，实现近乎无遗忘的任务增量学习，覆盖去噪、去模糊、超分等多种任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbqzwq6vfd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbqzwq6vfd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1306, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbqzwq6vfd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1148, \"height\": 1063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbqzwq6vfd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 878, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbqzwq6vfd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 324, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1476, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 599, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 844, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbqzwq6vfd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1434, \"height\": 150, \"label\": \"Table\"}]"
motivation: 现有图像修复模型无法在不遗忘旧任务的前提下增量学习新任务。
method: 提出MINI框架，通过参数解耦机制避免任务间干扰。
result: 在多种图像修复任务增量序列上表现接近联合训练。
conclusion: 为图像修复模型的持续学习提供了高效轻量的方案。
---

## Abstract
Existing research in low-level vision has shifted its focus from "one-by-one" task-specific methods to "all-in-one" multi-task unified architectures. However, current all-in-one image restoration approaches primarily aim to improve overall performance across a limited number of tasks. In contrast, how to incrementally add new image restoration capabilities on top of an existing model — that is, task-incremental learning — has been largely unexplored. To fill this research gap, we propose a minimalistic and universal paradigm for task-incremental learning called MINI. It addresses the problem of parameter interference across different tasks through a simple yet effective mechanism, enabling nearly forgetting-free task-incremental learning. Specifically, we design a special meta-convolution called MINI-Conv, which generates parameters solely through lightweight embeddings instead of complex convolutional networks or MLPs. This not only significantly reduces the number of parameters and computational overhead but also achieves complete parameter isolation across different tasks. Moreover, MINI-Conv can be seamlessly integrated as a plug-and-play replacement for any convolutional layer within existing backbone networks, endowing them with incremental learning capabilities. Therefore, our method is highly generalizable. Finally, we demonstrate that our method achieves state-of-the-art performance compared to existing incremental learning approaches across five common image restoration tasks. Moreover, the near forgetting-free nature of our method makes it highly competitive even against all-in-one image restoration methods trained in a full-supervised manner. Our code is available at https://github.com.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
当前图像修复领域的研究正从单任务专用模型转向“全合一”（All-in-One）多任务统一架构。然而，现有全合一方法主要针对固定任务集提升整体性能，缺乏在已有模型基础上**增量地添加新任务**（即任务增量学习）的能力，且面临严重的**参数冲突**和**灾难性遗忘**问题。为解决这一空白，论文提出了一个极简且通用的增量学习范式 **MINI**，旨在实现近乎无遗忘的多任务增量学习，并可作为即插即用模块增强现有骨干网络的增量能力。

### 2. 论文提出的方法论：核心思想、关键技术细节
**核心思想**：通过**硬参数隔离**机制，为每个任务分配专用的嵌入参数，避免跨任务干扰。与传统元卷积（Meta-Conv）依赖复杂子网络生成动态权重不同，MINI仅使用轻量级嵌入池，实现极低计算开销。

**关键技术细节**：
- **MINI-Conv**：替换标准卷积层。每个MINI-Conv包含两个嵌入池（权重嵌入池和偏置嵌入池），每个池包含 \(T\) 个嵌入向量（\(T\) 为最大任务数）。通过查询函数 \(q(x)\) 选择当前任务对应的嵌入，经reshape后作为卷积权重进行前向计算，其他嵌入完全隔离，不参与前向和反向传播。计算过程：\(t = q(x), W_t = \text{reshape}(e_w^{(t)}), b_t = e_b^{(t)}, h' = W_t \circledast h + b_t\)。
- **退化查询机制**：一个两层分类MLP，先判断全局/局部退化类型，再细粒度分类，输出任务ID。可预先单独训练，损失函数包含全局/局部分类和任务分类项。
- **嵌入一致性正则化（ECR）**：训练新任务时，约束其嵌入与已有任务嵌入的均值相近，增强模型对查询错误的鲁棒性。损失项：\(\mathcal{L}_{\text{ecr}} = \sum_{l} \|W_{t_{\text{now}}}^{(l)} - \bar{W}^{(l)}\|_2^2 + \sum_{l} \|b_{t_{\text{now}}}^{(l)} - \bar{b}^{(l)}\|_2^2\)。
- 总损失：\(\mathcal{L}_{\text{all}} = \mathcal{L}_{\text{main}} + \lambda_{\text{ecr}} \mathcal{L}_{\text{ecr}}\)。

### 3. 实验设计：数据集、基准与对比方法
- **数据集与任务（共5个）**：Rain100H（去雨）、RESIDE-6k（去雾）、GoPro（去模糊）、Raindrop（去雨滴）、LOLv2（低光增强）。
- **基准**：任务专用（one-for-one）训练、全合一（all-in-one）联合训练、增量学习（MINI）对比。
- **对比方法**：
    - 骨干网络：MAXIM、NAFNet、Restormer、IR-SDE、DA-CLIP。
    - 通用增量学习方法：LwF、EWC、SI、MAS、L2P、DualPrompt（以NAFNet为骨干）。
- **评估指标**：PSNR、SSIM、LPIPS。

### 4. 资源与算力
论文明确说明：实验使用**两块NVIDIA 2080ti GPU**。全合一联合训练2000 epochs（扩散模型3000 epochs），增量训练每个任务400 epochs（扩散模型600 epochs）。骨干网络训练采用余弦退火学习率（峰值0.0002），损失函数为L2损失加VGG16感知损失。MINI的查询模块和主网络分开训练。

### 5. 实验数量与充分性
实验非常充分：
- **表2**：在5个数据集上对比了6种骨干网络在三种训练范式下的性能，共30种子情况。
- **表3**：与6种通用增量学习方法在NAFNet骨干上对比，共30个数据点。
- **消融实验**：
    - ECR有效性：在不同错误分类率（0%~60%）下对比有/无ECR的性能（图4）。
    - 任务顺序影响：4种不同任务序列下的最终性能（表5）。
    - 全嵌入 vs 仅MINI-Conv（表6）。
    - 在Transformer骨干（SwinIR）上的初步验证（表7）。
- 计算开销对比：MetaConv vs MINI-Conv的FLOPs和参数量（表4）。
结论：实验设计客观、公平，覆盖了主要消融和敏感性分析。

### 6. 论文的主要结论与发现
- MINI框架在各种骨干网络上均显著提升多任务性能，甚至接近任务专用模型水平。
- 在增量学习场景下，MINI几乎消除灾难性遗忘，远超现有增量学习方法（如LwF、EWC等）。
- 嵌入一致性正则化（ECR）有效提升对查询错误的容错性。
- 任务顺序对MINI最终性能影响极小（PSNR波动<0.3dB），体现出色参数隔离性。
- MINI-Conv相比传统MetaConv**不增加推理FLOPs**，仅参数量随任务数线性增长，实用性强。

### 7. 优点
- **极简设计**：仅靠嵌入池实现参数隔离，无需复杂子网络，易于理解和实现。
- **即插即用**：可替换任意现有骨干网络的标准卷积层，赋予其增量学习能力，无需大幅修改架构。
- **低计算开销**：推理时计算量与标准卷积相同，参数量虽增加但可控。
- **高鲁棒性**：ECR有效应对查询错误，模型对误分类不敏感。
- **实验全面**：覆盖5种任务、6种骨干、多种增量基线，消融充分，结论可靠。

### 8. 不足与局限
- **任务数固定**：嵌入池大小 \(T\) 需预先设定，无法动态扩展，不适应任务数未知或持续增长的场景。
- **参数膨胀**：参数量随任务数线性增加（\(T\) 倍），在资源受限设备上可能存在存储压力。
- **未覆盖Transformer全面适配**：仅在SwinIR上初步测试，对Attention层未做完整替代（仅替换卷积），未来需探索更通用的嵌入策略。
- **仅考虑图像修复任务**：未在更广泛的低层视觉任务（如超分、去噪等混合场景）或高层视觉任务中验证。
- **查询模块依赖预训练**：若任务类型变化或新增未知退化，查询模块需重新训练或更新，可能引入额外开销。

（完）
