---
title: Learning Vision and Language Concepts for Controllable Image Generation
title_zh: 学习视觉与语言概念以实现可控图像生成
authors: "Shaoan Xie, Lingjing Kong, Yujia Zheng, Zeyu Tang, Eric P. Xing, Guangyi Chen, Kun Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hUHRTaTfvZ"
tags: ["query:real-ir"]
score: 8.0
evidence: 学习视觉-语言概念以实现可控图像生成与编辑
tldr: 尽管从图像和文本中学习原子概念对可解释生成模型至关重要，但保证概念可被唯一识别的理论条件一直缺失。本文针对多模态分布，提出一种基于潜在变量识别和图模型的概念学习框架，严格推导出了原子概念及其交互的可识别性条件。在此基础上，设计了一种可实践的学习算法。实验在可控图像生成和编辑任务上验证了理论的有效性，成功解耦出视觉和语言原子概念，并展示了在图像编辑任务中如何利用这些概念进行精细控制，表明该框架能为构建真正可控的生成模型提供指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 369, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 1170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 819, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 756, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1477, \"height\": 1869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1666, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1653, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1823, \"height\": 1947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1791, \"height\": 1202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-huhrtatfvz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1699, \"height\": 2026, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 827, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 906, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 981, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 991, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 836, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-huhrtatfvz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1587, \"height\": 464, \"label\": \"Table\"}]"
motivation: 现有可控生成缺乏对多模态原子概念可识别性的理论保证。
method: 将概念学习建模为潜在变量识别，推导可识别性条件。
result: 解耦出语义明确的视觉语言概念，支持可控图像编辑。
conclusion: 为可解释可控生成模型提供了坚实的理论基础。
---

## Abstract
Concept learning seeks to extract semantic and interpretable representations of atomic concepts from high-dimensional data such as images and text, which can be instrumental to a variety of downstream tasks (e.g., image generation/editing). Despite its importance, the theoretical foundations for learning atomic concepts and their interactions, especially from multimodal distributions, remain underexplored.
In this work, we establish fundamental conditions for learning atomic multimodal concepts and their underlying interactions With identfiability guarantees. We formulate concept learning as a latent variable identification problem, representing atomic concepts in each modality as latent variables, with a graphical model to specify their interactions across modalities. Our theoretical contribution is to provide component-wise identifiability of atomic concepts under flexible, nonparametric conditions that accommodate both continuous and discrete modalities.  Building on these theoretical insights, we demonstrate the practical utility of our theory in a downstream task text-to-image (T2I) generation. We develop a principled T2I model that explicitly learns atomic textual and visual concepts with sparse connections between them, allowing us to achieve image generation and editing at the atomic concept level. Empirical evaluations show that our model outperforms existing methods in T2I generation tasks, offering superior controllability and interpretability.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对给定的论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：当前的多模态生成模型（如文本到图像生成）通常将文本和图像映射到高度纠缠的表示空间中。这导致模型的可控性差，当用户对文本提示进行细微修改时，生成的图像往往会产生意料之外的变化。这种“牵一发而动全身”的现象，根源在于模型未能学习到可解耦的“原子概念”（例如，视觉中的“毛皮”、“翅膀”，文本中的“狗”、“鸟”）及其稀疏的交互关系。
*   **核心问题**：核心问题是**如何从多模态数据（如图文对）中，以可识别的方式，学习到构成数据的基本“原子概念”以及这些概念之间的跨模态交互关系**。
*   **整体含义**：本文为多模态概念学习奠定了理论基础，并证明了在特定条件下，可以唯一地识别出这些原子概念。在此基础上，构建了一个具备更优可控性和可解释性的文本到图像生成模型。

### 2. 论文提出的方法论

*   **核心思想**：将多模态概念学习形式化为一个**潜在变量识别问题**。文本和图像被看作是由各自的原子概念（潜在变量 `zT` 和 `zI`）经由可逆映射生成的。文本概念 `zT` 在因果上先于视觉概念 `zI`，并通过一个稀疏图模型 `Gt→i` 影响视觉概念的形成。
*   **理论贡献与关键条件**：论文提出了一个两阶段识别理论：
    *   **第一阶段（识别视觉概念 `zI`）**：利用文本概念`zT`（通过观测变量 `t` 体现）的变化，引发视觉概念条件分布 `p(zI|zT)` 的充分变化。通过引入**充分变化性条件**，可以从图像中解耦出独立的视觉原子概念 `zI_n`。
    *   **第二阶段（识别文本概念 `zT` 和图 `Gt→i`）**：在视觉概念 `zI` 被识别后，将其视为可观测变量。此时，利用**稀疏连接条件**（每个文本概念只影响部分、且互不包含的视觉概念子集），可以进一步识别出离散的文本原子概念 `zT_m` 以及它们之间的因果图 `Gt→i`。
*   **技术细节与差异**：理论的关键优势在于其**组分级别可识别性**、**非参数化假设**（不限制分布形式），以及能够同时处理**连续和离散模态**。这使其比以往的共享子空间识别或半参数方法更灵活、更精细。
*   **模型实现（ConceptAligner）**：基于上述理论，设计了一个包含四大模块的生成模型：
    1.  **文本网络 (`R_T`)**：使用 Perceiver Resampler 将文本嵌入 `t̃` 解耦为文本概念 `zT`。
    2.  **图像网络 (`R_I`)**：类似 VAE，将图像 `i` 映射为外生噪声 `ϵ` 的均值和方差，并重参数化采样 `ϵ`。
    3.  **概念网络 (`R_C`)**：接受文本概念 `zT` 和噪声 `ϵ`，通过一个**带有可学习稀疏掩码 `m` 的模块**，生成视觉概念 `zI`。掩码 `m` 的稀疏性对应理论中的图结构 `Gt→i`。
    4.  **条件生成模型 (`v_θ`)**：以视觉概念 `zI` 而非原始文本为条件，使用扩散 Transformer 进行图像生成。
*   **训练目标**：
    *   **扩散损失 (`L_diff`)**：标准的 Flow Matching 或去噪损失。
    *   **KL 散度损失 (`L_kl`)**：约束外生噪声 `ϵ` 的分布接近标准正态分布。
    *   **稀疏性正则化 (`L_spa`)**：对掩码 `m` 施加 L1 范数惩罚，以鼓励稀疏的跨模态连接。
    *   **总体目标**: `L = L_diff + λ_spa * L_spa + λ_kl * L_kl`。

### 3. 实验设计

*   **数据集**:
    *   **训练集**: 使用 FLUX-S 模型结合 LAION 数据集中的提示词，生成了 200 万张图像，并利用 QWEN2-VL 模型为其生成了更精准的文本描述，构建了一个高质量的训练集。
    *   **测试集（可控生成/编辑）**:
        *   **EMU-Edit 数据集**: 包含 3589 对修改前后提示词，用于评估模型根据文本修改进行精确图像编辑的能力。
        *   **PIE-Bench 数据集**: 另一个图像编辑评估基准。
        *   **自行构建的动物-动作/背景改变数据集**: 用于定量评估解耦能力。
*   **Benchmark 与对比方法**: 与当前主流的文本到图像生成模型进行了全面比较，包括：
    *   SD3.5-Medium & Large
    *   FLUX.1-dev & FLUX.1-Schnell
    *   SANA 及 SANA-Finetune（在相同训练数据上微调，作为重要基线）
*   **评估指标**:
    *   **图像对一致性**: CLIP-I (Image similarity)、DINO similarity、LPIPS (Perceptual distance)。值越低越好（LPIPS），或越高越好（CLIP-I, DINO），表明修改前后图像中未编辑部分越相似，编辑越精确。
    *   **图文一致性**: CLIP-T (Text similarity)，评估生成图像是否与目标提示词匹配。
    *   **解耦指标**: 使用 Qwen2.5-VL 模型评估“主体一致性”（动物身份是否保留）和“提示一致性”（动作/背景是否按要求改变）。

### 4. 资源与算力

*   **算力配置**: 论文中明确提到，**推理速度的对比是在单个 H100 GPU 上进行的**。
*   **训练细节**: 论文提到了训练的超参数，如 `batch size = 768` 和 `learning rate = 5e-5`，但**未明确说明训练使用的 GPU 总数、型号以及总训练时长**。

### 5. 实验数量与充分性

*   **实验组数**: 实验设计较为全面，主要包括四大类：
    1.  **主要基线对比**: 在 EMU-Edit 和 PIE-Bench 两个标准数据集上与 5~6 种先进模型进行了定量对比。
    2.  **可控性与解耦分析**: 设计了专门的动作/背景修改实验，并引入 VLM 进行定量评估；定性展示了多种概念修改（属性、风格、多概念同时编辑）。
    3.  **消融实验**: 定量和定性地分析了移除稀疏性正则化、扩散损失、KL 损失对模型性能的影响。
    4.  **模型分析**: 可视化了学习到的概念，并展示了长文本提示和真实图像编辑场景下的性能。
*   **充分性与公平性**:
    *   **充分性**: 实验覆盖了多个数据集、多种编辑类型（属性、风格、布局等），并结合了多种自动度量和人工/VLM 评估，较为充分地验证了理论主张。
    *   **公平性**: 与基线模型的比较是公平的。特别值得一提的是，对比了在**相同高质量数据上微调的 SANA 模型**，这有力地排除了性能提升仅仅来源于更好训练数据的可能性。所有对比均固定随机种子。

### 6. 论文的主要结论与发现

*   本文成功建立了从多模态数据中组分级别识别原子概念的**理论条件**，尤其关键的是，视觉模态的**充分变化性**和跨模态交互的**稀疏性**。
*   基于这些理论见解设计的模型 **ConceptAligner**，在可控文本到图像生成和编辑任务中，**性能显著优于**现有的 SOTA 方法（包括经过相同数据微调的 SANA）。
*   ConceptAligner 能更忠实地执行文本编辑指令，**最大限度地减少了非预期的属性变化**，体现了优越的可控性。
*   可视化和解耦分析证实，该模型确实学习到了可解释、可分离的原子视觉与文本概念，通过控制这些概念可以实现对生成图像的精细操控。

### 7. 优点

*   **坚实的理论基础**: 论文最大的亮点是提供了严格、清晰且条件相对灵活的概念可识别性理论，为“解耦”提供了数学保证，填补了该领域的理论空白。
*   **理论与实践紧密结合**: 模型架构和损失函数（特别是稀疏掩码和 KL 损失）是理论条件的直接实现，并非简单的工程堆砌，这种设计哲学使得模型行为更具可解释性和可预测性。
*   **实验设计严谨**: 采用了高质量的自建训练集，并对比了在相同数据上微调的强大基线（SANA-Finetune），有力地证明了方法本身的有效性。解耦分析的实验设计新颖且有说服力。
*   **概念级别的可解释性与编辑能力**: 实现了在传统生成模型上难以达到的精细操控水平，如在“蝙蝠侠”和“孔雀”之间置换“披风”和“羽毛”的概念。

### 8. 不足与局限

*   **对数据质量的依赖**: 作者在局限部分也明确指出，视觉概念识别的条件之一（充分变化性）要求训练数据中的文本描述必须足够**多样且信息丰富**。这意味着在文本描述质量较差、变化贫乏的数据集上，理论的保证可能不成立，模型性能可能会下降。
*   **理论到模型的差距**: 理论假设的映射函数都是可逆的，而实际模型使用神经网络近似，可逆性并不能完全保证。稀疏约束（L1 范数）是理论中“非子集”条件的松弛实现，严格的理论条件在优化中可能无法完美满足。
*   **评估的局限性**: 解耦能力的量化评估依赖于 Qwen2.5-VL 等视觉语言模型，其判断标准本身可能存在偏差或不完全一致。虽然实验证明了在特定编辑类型上的优越性，但其在所有场景下的泛化能力仍需更广泛的测试。
*   **未提及的算力成本**: 论文未给出训练所需的 GPU 时等具体算力开销，这可能使得其他研究者难以精确评估其资源需求。

（完）
