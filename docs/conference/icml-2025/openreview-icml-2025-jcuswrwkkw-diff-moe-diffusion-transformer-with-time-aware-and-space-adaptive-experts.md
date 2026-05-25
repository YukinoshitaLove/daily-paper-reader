---
title: "Diff-MoE: Diffusion Transformer with Time-Aware and Space-Adaptive Experts"
title_zh: Diff-MoE：具有时间感知和空间自适应专家的扩散Transformer
authors: "Kun Cheng, Xiao He, Lei Yu, Zhijun Tu, Mingrui Zhu, Nannan Wang, Xinbo Gao, Jie Hu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JCUsWrwkKw"
tags: ["query:real-ir"]
score: 7.0
evidence: 混合专家架构改进扩散Transformer的可扩展性
tldr: 针对扩散模型计算开销大和架构僵化的问题，提出Diff-MoE，将扩散Transformer与混合专家结合，利用时间感知和空间自适应专家分配动态计算资源。该架构提升了生成任务的灵活性和效率，可潜在应用于图像生成和复原。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 886, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 1752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jcuswrwkkw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1634, \"height\": 2182, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1586, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 606, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 736, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jcuswrwkkw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1533, \"height\": 411, \"label\": \"Table\"}]"
motivation: 扩散模型处理所有生成阶段和令牌时缺乏灵活性和效率。
method: 引入专家特定的时间步条件，动态分配空间令牌，并全局特征重校准。
result: 提升了扩散Transformer的效率和可扩展性。
conclusion: Diff-MoE为扩散模型提供了更灵活高效的基础架构。
---

## Abstract
Diffusion models have transformed generative modeling but suffer from scalability limitations due to computational overhead and inflexible architectures that process all generative stages and tokens uniformly. In this work, we introduce Diff-MoE, a novel framework that combines Diffusion Transformers with Mixture-of-Experts to exploit both temporarily adaptability and spatial flexibility. Our design incorporates expert-specific timestep conditioning, allowing each expert to process different spatial tokens while adapting to the generative stage, to dynamically allocate resources based on both the temporal and spatial characteristics of the generative task. Additionally, we propose a globally-aware feature recalibration mechanism that amplifies the representational capacity of expert modules by dynamically adjusting feature contributions based on input relevance. Extensive experiments on image generation benchmarks demonstrate that Diff-MoE significantly outperforms state-of-the-art methods. Our work demonstrates the potential of integrating diffusion models with expert-based designs, offering a scalable and effective framework for advanced generative modeling.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
扩散模型虽然推动了生成模型的革命，但在可扩展性方面存在明显瓶颈：  
- **计算开销巨大**：传统密集激活架构（如 DiT）所有参数在每个时间步都被激活，导致高昂的计算成本。  
- **架构僵化**：所有生成阶段与所有空间令牌均被统一处理，无法区分早期全局结构建模与后期局部细节精炼的不同需求。  
- **混合专家（MoE）在扩散模型中的应用未充分挖掘**：现有工作要么仅在时间维度划分专家（如 DTR、Switch-DiT），要么仅在空间维度划分专家（如 DiT-MoE），未能同时结合时间和空间两个维度以实现更优的资源分配。

为此，本文提出 **Diff‑MoE**，一个将扩散 Transformer 与混合专家深度融合的框架，旨在利用**时间自适应**和**空间灵活**的特性，动态分配计算资源，从而在保持参数效率的同时大幅提升生成性能。

### 2. 论文提出的方法论
Diff‑MoE 的核心设计包含以下关键技术：

- **优化的基础架构（Sec. 4.1）**  
  - 在标准 DiT 的基础上引入 **旋转位置嵌入（RoPE）** 以增强空间依赖建模。  
  - 使用 **门控线性单元（GLU）** 替代普通 MLP，增强非线性表征能力。  
  - 在 MoE 模块前添加 **深度可分离卷积（Depthwise Conv）** 以提升局部特征提取。  
  - 构建 **空间 MoE**：将密集 FFN 替换为多个专家，并通过门控路由为不同令牌分配不同专家；同时引入共享专家以缓解知识冗余。

- **专家特定时间步条件（Sec. 4.2）**  
  为每个专家配备专用的时间步嵌入投射，通过专门的 AdaLN 参数使专家行为随去噪阶段动态变化。这使得路由器只需关注令牌的空间特征，从而解耦时间适应与空间专门化，提升专家利用率和路由质量。

- **全局特征重校准机制（Sec. 4.3）**  
  通过平均池化提取全局上下文嵌入 \(x_g\)，并在专家内部将其与局部令牌特征进行通道级乘法，以动态调整不同通道的贡献，强化全局一致性和长距离依赖建模。

- **低秩分解压缩参数（Sec. 4.4）**  
  为控制专家特定条件与全局上下文的参数量，对相关投影矩阵进行低秩分解（如 \(W_t = A_t \times B_t\)），在几乎不损失性能的前提下大幅压缩参数。

最终，每个 MoE 块的计算可概括为：  
1. 对输入令牌执行 MSHA 和 AdaLN。  
2. 经 DWConv 后，路由为令牌分配 top-k 专家。  
3. 被激活的专家结合时间步条件与全局上下文进行特征变换并输出。

### 3. 实验设计
- **数据集与任务**：  
  仅在 **ImageNet 256×256** 上进行类条件图像生成，训练集含约 128 万张 1000 类图片。使用 Stable Diffusion 的预训练 VAE 将图像压缩为 32×32×4 的潜在表示。

- **基准方法与对比对象**：  
  - **密集 DiT 变体**：DiT、SiT、SiT-LLaMA（S/B/L 不同规模）。  
  - **基于专家的方法**：时间专家（DTR、Switch-DiT）和空间专家（DiT-MoE），以及其不同规模配置。  
  所有对比均控制激活参数量基本一致，并在相同训练迭代数（400K）和采样设置（250 DDPM 步）下进行。

- **评估指标**：  
  FID（50K 样本）作为主要指标，IS 作为辅助指标，部分实验也报告 sFID、Precision、Recall。

- **模型规模与配置**：  
  设计了 S/B/L/XL 及 S+/B+/XL+ 六个版本，总参数量从 107M 到 4.3B，激活参数量从 36M 到 1.5B，与现有方法对齐。

- **训练与细节**：  
  使用 AdamW，学习率 1e-4，batch size 256，训练 400K 迭代。默认使用整流流（Rectified Flow）和负载均衡损失，并应用指数移动平均（EMA）。部分实验对比了有无整流流的差异。

### 4. 资源与算力
- 论文未明确说明所使用的 GPU 型号、数量及具体训练时长。  
- 仅提到所有模型均训练 400K 迭代，批量大小为 256，且由于资源限制，未能在更大规模（如 7M 迭代）下评估 XL 等大模型的极限性能。

### 5. 实验数量与充分性
- 进行了 **多组对比实验**：与 6 种以上不同架构（密集 DiT、时间 MoE、空间 MoE）在 S/B/L/XL 多尺寸下进行性能对比。  
- **消融实验**：逐步验证 RoPE、GLU、DWConv、空间 MoE 的增益；进一步验证专家特定时间条件、全局特征重校准和低秩分解的效果。  
- 提供了 **收敛曲线**（FID 随训练步数的变化）和 **专家选择可视化**，证明方法有效且公平。  
- 整体实验覆盖较为全面，对比公平（控制激活参数量、训练步数、采样参数），但仅在 ImageNet 256 单一任务上验证，缺少更高分辨率或多模态证据。

### 6. 论文的主要结论与发现
- Diff‑MoE 在所有规模下均显著优于密集 DiT 和现有专家方法，例如在 S 级模型上，FID 相对 SiT-LLaMA-S 降低 17.8%，IS 提升 28.2%。  
- 通过同时利用时间和空间维度的专家分工，模型能够更高效地分配计算资源，提升生成质量和多样性。  
- 全局特征重校准与专家特定时间条件互补，可进一步增强专家表征能力；低秩分解则在维持性能的同时有效控制参数总量。

### 7. 优点
- **创新性整合**：首次在扩散 Transformer 中同时实现时间自适应与空间自适应的专家设计，填补了领域空白。  
- **高效的参数利用**：通过稀疏激活与低秩压缩，激活参数量远低于密集模型，却取得更好性能，展现了优异的可扩展性。  
- **模块化设计清晰**：基础架构改进、时间条件注入、全局重校准、低秩分解各模块相互独立，便于消融与后续改进。  
- **实验设计严格**：控制激活参数量、训练步数、采样参数，与多个主流方法进行公平对比，收敛曲线和可视化进一步验证了设计的有效性。

### 8. 不足与局限
- **任务与数据集局限**：仅验证了 ImageNet 256×256 条件下的类条件生成，未涉及高分辨率、文本到图像或视频等更复杂的生成场景，泛化性有待检验。  
- **训练规模受限**：受计算资源限制，未进行业界常见的长周期（如 7M 迭代）训练，无法完全展示 XL 等大模型在极致训练下的性能上限。  
- **潜在偏差风险**：所有实验均在 ImageNet 上进行，该数据集本身存在类别和人种等偏差，可能被模型继承并放大。  
- **实用性约束**：虽然激活参数量低，但总参数量较大，在存储和部署上仍有一定压力；此外，未报告推理延迟或吞吐量数据，实际应用效率尚不明确。

（完）
