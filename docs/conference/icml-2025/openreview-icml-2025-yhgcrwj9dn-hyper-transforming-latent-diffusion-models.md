---
title: Hyper-Transforming Latent Diffusion Models
title_zh: 超变换潜在扩散模型
authors: "Ignacio Peis, Batuhan Koyuncu, Isabel Valera, Jes Frellsen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yhgcRwJ9Dn"
tags: ["query:real-ir"]
score: 6.0
evidence: 用基于Transformer的超网络扩展潜在扩散模型
tldr: 本文针对隐式神经表示生成中 MLP 超网络扩展性不足的问题，提出将 Transformer 超网络集成到潜在扩散模型中，通过“超变换”策略微调解码器并冻结潜空间，实现了对已有生成模型的高效适配。实验证明该方法在函数生成任务上提升了表示容量与计算效率，为潜在扩散模型的应用扩展提供了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 830, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1527, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1781, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1706, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1736, \"height\": 1067, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1701, \"height\": 1262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1704, \"height\": 1901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yhgcrwj9dn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1703, \"height\": 1900, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1753, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 885, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 620, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yhgcrwj9dn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1626, \"height\": 2300, \"label\": \"Table\"}]"
motivation: 现有基于MLP超网络的方法存在可扩展性瓶颈，限制了生成模型的表示能力。
method: 提出用Transformer超网络替换扩散模型解码器，并设计“超变换”微调策略。
result: 在函数生成任务上，模型表示容量和计算效率均优于传统方法。
conclusion: 该方法为潜在扩散模型的通用生成能力提供了可扩展的新框架。
---

## Abstract
We introduce a novel generative framework for functions by integrating Implicit Neural Representations (INRs) and Transformer-based hypernetworks into latent variable models. Unlike prior approaches that rely on MLP-based hypernetworks with scalability limitations, our method employs a Transformer-based decoder to generate INR parameters from latent variables, addressing both representation capacity and computational efficiency. Our framework extends latent diffusion models (LDMs) to INR generation by replacing standard decoders with a Transformer-based hypernetwork, which can be trained either from scratch or via hyper-transforming—a strategy that fine-tunes only the decoder while freezing the pre-trained latent space. This enables efficient adaptation of existing generative models to INR-based representations without requiring full retraining. We validate our approach across multiple modalities, demonstrating improved scalability, expressiveness, and generalization over existing INR-based generative models. Our findings establish a unified and flexible framework for learning structured function representations.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：现有隐式神经表示（INR）的生成模型通常使用基于多层感知机（MLP）的超网络来生成网络参数，但这存在严重的**可扩展性瓶颈**。当目标INR的维度增高时，MLP超网络难以有效生成全部参数，限制了生成模型的表示能力和灵活性。
*   **研究动机**：
    *   INRs能够以连续函数的形式表达任意分辨率的数据，是强大的表示工具。
    *   现有方法要么受限于MLP超网络的容量（如GASP、VAMoH），要么是确定性的Transformer方法（如Trans-INR），无法进行概率建模。
    *   需要一种能高效、可扩展地学习INR参数分布的生成框架。
*   **整体含义**：本文旨在通过将 **Transformer超网络** 集成为**潜在扩散模型（LDM）的解码器**，构建一个统一、灵活且可扩展的函数生成框架，克服现有方法的局限性。

### 2. 论文提出的方法论

论文的核心方法论是**潜在扩散模型（LDM）的隐式神经表示（LDMI）**，它包含一个关键的创新组件：**超Transformer解码器（HD）**。

*   **核心思想**：用Transformer架构替换传统LDM中的CNN解码器，将压缩的潜变量直接转换为构成INR的权重和偏置矩阵，实现从潜变量空间到函数参数空间的映射。
*   **关键技术细节：I-VAE框架（第一阶段）**
    *   **编码器**：一个标准的编码器（如CNN），将数据（如坐标和像素值）映射为张量化的潜变量 $z$ 的变分后验分布 $q_\psi(z|X, Y)$。
    *   **超Transformer解码器 (HD)**：这是论文的核心创新。它接收潜变量 $z$，并生成目标INR的全部参数 $\Phi$。其内部结构为：
        1.  **分词器**：将张量潜变量切分为小块（patch），并线性投影为token。
        2.  **Transformer编码器**：通过自注意力处理潜变量token，生成“潜变量token”。
        3.  **Transformer解码器**：以一组全局共享的、可学习的“初始权重token”作为查询（Query），对潜变量token进行交叉注意力，生成“输出权重token”。
        4.  **权重分组与重建**：为控制计算开销，输出token对应的是权重矩阵的**列组**，而非单列。最终通过一个新颖的重建算子 $R_{\text{scale}}$ 与可学习的“权重模板”结合，恢复到完整的权重维度。该算子为 $W = (1 + w_o) \odot \bar{W}_b$，有效解决了SIREN等周期性激活函数的训练不稳定问题。
    *   **训练目标**：整个I-VAE通过最大化证据下界（ELBO）进行训练，并可选择性加入感知损失和对抗损失。
*   **算法流程：潜在扩散（第二阶段）**
    *   在第一阶段I-VAE训练完成后，固定其编码器和解码器。
    *   收集所有训练数据潜变量的后验分布，得到聚合后验 $q_\psi(z)$。
    *   在潜变量空间上训练一个标准的去噪扩散概率模型（DDPM）来近似这个聚合后验，即学习先验 $p_\theta(z)$。
*   **超变换训练策略**：
    *   一种高效的替代方案。当存在一个预训练好的LDM时，冻结其编码器和扩散模型，**仅训练HD解码器**将预训练的潜变量映射到INR参数。这允许快速将现有LDM适配到基于INR的生成，而无需完全重新训练。

### 3. 实验设计

论文在多个数据模态和任务上验证了LDMI框架的优越性。

*   **数据集/场景**:
    *   **自然图像**: CelebA-HQ (64×64 和 256×256)、ImageNet (256×256)
    *   **3D形状**: ShapeNet Chairs (32×32×32 占有率网格)
    *   **极地气候**: ERA5 温度数据
*   **基准方法**:
    *   **GASP**: 基于对抗训练的MLP超网络方法（Dupont et al., 2022b）。
    *   **Functa/Spatial Functa**: 基于优化的方法，为每个数据点拟合一个INR，然后在表示上训练生成模型（Dupont et al., 2022a; Bauer et al., 2023）。
    *   **VAMoH**: 基于变分推理和MLP超网络的概率INR生成模型（Koyuncu et al., 2023）。
*   **对比任务与指标**:
    *   **无条件生成**: 使用FID分数评估生成图像的质量和多样性。
    *   **重建**: 使用PSNR（图像/气候）或准确率（3D形状）评估从潜变量编码-解码后的信息保留程度。
    *   **多分辨率重建/生成**: 评估模型在任意分辨率下工作的能力。
    *   **数据补全**: 在CelebA-HQ 256×256上进行中心遮罩补全实验，展示条件生成能力。

### 4. 资源与算力

*   论文明确提到所有模型均在 **NVIDIA H100 GPU** 上训练。
*   **未明确说明**的部分：论文没有给出训练单个模型所需的**具体GPU数量、总训练时长或浮点运算次数**等详细算力开销。关于训练效率的表述是定性的，例如“高度高效的方法”、“缓解计算瓶颈”。

### 5. 实验数量与充分性

*   **实验数量**：
    *   在 **4个** 不同模态/规模的数据集上进行了实验。
    *   与 **3种** 代表性的基准方法（GASP, Functa, VAMoH）进行了比较。
    *   涵盖了**生成、重建、多分辨率、数据补全、超变换策略、消融实验**等多种任务和设置，实验组数超过10个。
*   **充分性、客观性与公平性**：
    *   **充分性**：实验设计较为全面，覆盖了多个维度，有力地支持了论文所声称的“统一和灵活”的框架。
    *   **客观性与公平性**：作者承认了比较中的不公平之处。例如，他们指出Functa更高的PSNR源于测试时的逐样本优化，而非像LDMI一样采用摊销推理，这种坦诚的讨论体现了客观性。在对比方法时，也选择了同领域最具代表性的工作。

### 6. 论文的主要结论与发现

*   **方法论验证**：提出的LDMI框架成功地将Transformer超网络集成到LDM中，能够进行高质量、可扩展的INR生成。
*   **性能优势**：LDMI超越了基于MLP的同类生成模型（VAMoH），并在重建质量上取得了有竞争力的结果。其参数效率极高，使用更少的超网络参数量生成了更大的INR模型。
*   **灵活性**：“超变换”策略是有效的，能高效地将预训练的标准LDM适配为分辨率无关的INR生成模型，而无需从头训练整个框架。
*   **通用性**：该框架在图像、3D形状、气候数据等多种模态上均表现出色，证明其是一个通用的函数生成框架。

### 7. 优点

*   **创新的架构设计**：提出的**超Transformer解码器（HD）** 是本文的主要亮点，它通过分词、编解码、权重分组与新颖的重建算子，优雅地解决了大尺寸INR参数生成的扩展性问题。
*   **高效灵活的“超变换”策略**：这一训练范式极具实用价值，允许“零成本”地复用大量现有预训练LDM，极大地降低了模型适配的算力门槛和时间成本。
*   **简洁统一的框架**：LDMI将INR、VAE、Transformer和扩散模型无缝整合，提供了一个面向函数生成任务的、简洁且强大的通用解决方案。
*   **参数效率高**：在相同的任务上，其超网络参数量远小于MLP基线，却能生成更大的INR并取得更好的性能，这在表3和表4的消融实验中得到了清晰验证。

### 8. 不足与局限

*   **对预训练模型的依赖**：“超变换”策略的有效性高度依赖于已有预训练LDM的质量和可用性。对于非图像或没有高质量预训练模型的领域，此优势不复存在，仍需两阶段从头训练。
*   **对比实验的公平性细节**：虽然指出了与Functa比较的不公平，但在与GASP比较时，直接比较FID（尽管GASP不支持重建）未做深入分析，其对抗性设计使得与LDMI的比较维度不完全对等。
*   **应用限制**：框架目前生成的是固定拓扑结构（MLP）的INR。对于需要更复杂、异质网络结构的函数空间，方法的表达力可能受限。
*   **算力开销透明度不足**：论文未提供任何训练时长、GPU内存消耗等具体算力开销数据。缺少这些关键信息，读者难以评估该方法在实践中的训练成本和碳足迹，尤其是在与MLP方法对比时。

（完）
