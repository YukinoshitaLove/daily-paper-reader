---
title: "AnyEdit: Mastering Unified High-Quality Image Editing for Any Idea"
title_zh: AnyEdit：掌握统一高质量图像编辑以应对任意想法
authors: "Yu, Qifan, Chow, Wei, Yue, Zhongqi, Pan, Kaihang, Wu, Yang, Wan, Xiaoyang, Li, Juncheng, Tang, Siliang, Zhang, Hanwang, Zhuang, Yueting"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yu_AnyEdit_Mastering_Unified_High-Quality_Image_Editing_for_Any_Idea_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 9.0
evidence: 250万对的大规模多模态指令编辑数据集及统一编辑模型
tldr: 为解决指令编辑模型难以处理复杂指令的问题，构建了包含250万个高质量编辑对的AnyEdit数据集，涵盖20多种编辑类型和五个领域，通过自适应编辑流程和自动选择保证多样性。基于该数据集，训练了具有任务感知路由的AnyEdit Stable Diffusion统一模型，实现了对多种编辑思路的精准执行。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 1145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1792, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 426, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1797, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 836, \"height\": 647, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1761, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 823, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1351, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 880, \"height\": 1032, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-anyedit-mastering-unified-high-quality-image-editing-for-any-idea-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 834, \"height\": 188, \"label\": \"Table\"}]"
motivation: 现有模型在低质、有限编辑类型数据下训练，难以准确执行复杂指令。
method: 构建多样高质量多模态编辑数据集，训练带任务感知路由的稳定扩散统一模型。
result: 支持任意想法编辑，数据集和模型显著提升复杂指令编辑的准确性和多样性。
conclusion: 为统一且高质量图像编辑提供了大规模数据集和有效模型架构。
---

## Abstract
Instruction-based image editing aims to modify specific image elements with natural language instructions. However, current models in this domain often struggle to execute complex user instructions accurately, as they are trained on low-quality data with limited editing types. We present AnyEdit, a comprehensive multi-modal instruction editing dataset, comprising 2.5 million high-quality editing pairs spanning over 20 editing types and five domains. We ensure the diversity and quality of the AnyEdit collection through three aspects: initial data diversity, adaptive editing process, and automated selection of editing results. Using the dataset, we further train a novel AnyEdit Stable Diffusion with task-aware routing and learnable task embedding for unified image editing. Comprehensive experiments on three benchmark datasets show that AnyEdit consistently boosts the performance of diffusion-based editing models. This presents prospects for developing instruction-driven image editing models that support human creativity.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对提供的 CVPR 2025 论文《AnyEdit: Mastering Unified High-Quality Image Editing for Any Idea》进行结构化、深入、客观的总结。

### **1. 论文核心问题与研究动机**

*   **核心问题**：当前基于指令的图像编辑模型（Instruction-based Image Editing）在准确执行复杂的、多模态的用户指令方面存在困难。
*   **根本原因**：作者指出，这种局限性源于两个方面：
    1.  **训练数据质量低**：现有数据集往往存在数据偏差、编辑对不精确、图像质量不高等问题。
    2.  **编辑类型有限**：现有方法主要关注简单的局部或全局编辑，忽视了需要复杂感知和推理能力的任务，例如空间组合编辑、相机视角变换、常识理解和基于参考图的视觉编辑。
*   **研究动机**：为了开发一个能够真正理解并执行“任何想法”的强大图像编辑模型，迫切需要解决高质量、多类型编辑数据的匮乏问题，并设计一个能充分利用这些数据的统一模型框架。

### **2. 方法论**

论文的核心贡献分为两大部分：构建大规模、高质量数据集 **AnyEdit** 和设计统一编辑模型 **AnyEdit Stable Diffusion (AnySD)**。

#### **2.1 AnyEdit 数据集构建**
这是一个多模态指令编辑数据集，包含 250 万高质量编辑对，覆盖 25 种编辑类型和 5 大领域（局部编辑、全局编辑、相机移动编辑、隐式编辑、视觉编辑）。其构建流程强调自动化和高质量：

*   **核心思想**：通过自适应流水线和自动筛选机制，以低资源方式扩展高质量编辑数据。
*   **关键技术细节**：
    1.  **初始数据多样性**：为解决数据偏差，不仅收集了 ~680K 真实世界图文对（来自 MSCOCO 等），还创新性地引入了 **“反事实合成场景对”**（Counterfactual Synthetic Scene Pair），即组合语料库中的罕见概念（tail concepts），利用大语言模型生成描述，再用文本到图像模型生成图像，从而平衡数据分布。
    2.  **自适应编辑流水线**：摒弃了“一刀切”的固定编辑流程。系统根据任务类型（共 25 种），动态选择 **9 个核心编辑流水线** 之一。例如，生成局部编辑数据时会引入膨胀掩码（dilated masks）以减少伪影，生成相机移动数据时会利用几何引导。
    3.  **指令生成与质量增强**：
        *   **指令生成**：利用 Llama3-8b 模型，结合任务类型约束和上下文示例，将原始图像描述转化为多样化编辑指令。
        *   **前置过滤**：使用特定任务的启发式规则和美学评估，在编辑前滤除不明确或低质量的指令和图像。
        *   **后置过滤**：编辑完成后，通过多维度自动评估（CLIP 对齐度、CLIP 图像相似度、L1 距离、CLIP 方向相似度、目标检测等）筛选出语义准确且保真度高的编辑对。

#### **2.2 AnySD 模型架构**

*   **核心思想**：为充分挖掘 AnyEdit 数据集的潜力，设计了一个能处理多种编辑任务的统一扩散模型。
*   **关键技术细节**：
    1.  **视觉提示投影器**：当编辑任务涉及视觉条件（如参考图）时，该模块使用一个冻结的 CLIP 图像编码器将视觉特征 \(z_V\) 对齐到文本指令的嵌入空间，形成视觉提示 \(c_V\)，并将其集成到 U-Net 的去噪过程中。
        *   **训练目标公式**：\(L = E_{\mathcal{E}(x), \mathcal{E}(c_I), c_T, c_V, \epsilon, t} \left[ \| \epsilon - \epsilon_\theta(z_t, t, \mathcal{E}(c_I), c_T, c_V) \|_2^2 \right]\)
        *   该公式表示在扩散过程中，模型 \(\epsilon_\theta\) 需要根据原始图像 \(c_I\)、文本指令 \(c_T\) 和视觉提示 \(c_V\) 来预测噪声 \(\epsilon\)。
    2.  **任务感知路由**：在 U-Net 中引入混合专家（MoE, Mixture of Experts）模块。该模块包含一个路由器（router），它根据**任务嵌入**（task embedding）动态地将视觉提示 \(c_V\) 分配给不同的“专家”注意力层。这使得模型可以针对不同编辑任务的粒度（如局部像素修改 vs. 全局风格迁移）激活不同的处理路径。
    3.  **可学习的任务嵌入**：为每种编辑任务学习一个嵌入向量 \(v_i\)。它有两个作用：一是与视觉提示结合输入 MoE 模块；二是作为路由器的输入，决定专家的权重分配。这有助于协调不同任务间的复杂性，防止灾难性遗忘。
*   **训练流程**：
    *   **阶段一（指令理解）**：冻结任务路由，预训练 U-Net 以理解基本的编辑指令。
    *   **阶段二（任务调优）**：解冻 MoE 模块、路由器、视觉投影器和任务嵌入，进行微调，让模型掌握各任务特有的编辑粒度和技能。

### **3. 实验设计**

*   **数据集与基准**：
    *   **训练数据**：仅使用自建的 **AnyEdit** 数据集（250万对）。
    *   **标准评测基准**：在 **EMU-Edit Test** 和 **MagicBrush** 这两个权威基准上进行评估。
    *   **自建挑战基准**：构建了 **AnyEdit-Test**，这是一个从 AnyEdit 数据集中手动筛选出的、难度更高的测试集，包含 1250 个高质量编辑对（25个类别，每类50个），训练时不可见，旨在评估模型在复杂场景下的泛化能力。
*   **对比方法**：与多个 SOTA 方法进行了全面比较，涵盖了：
    *   **专用编辑方法**：PnP, Null-Text。
    *   **指令编辑方法**：InstructPix2Pix, MagicBrush, HIVE, EMU-Edit, UltraEdit。
    *   **视觉条件方法**：Uni-ControlNet（用于视觉编辑对比）。
*   **评估指标**：采用语义相似度（CLIPim, CLIPout）和视觉相似度（DINO, L1 distance）进行量化评估。

### **4. 资源与算力**

论文中并未明确提及训练 AnySD 模型所使用的 GPU 型号、数量或具体训练时长。这是论文在可复现性方面一个缺失的关键信息。

### **5. 实验数量与充分性**

*   **实验覆盖**：论文设计了多组实验，覆盖了：
    1.  **不同基准测试**：在 EMU-Edit、MagicBrush 和自建的 AnyEdit-Test 上进行了评估。
    2.  **不同编辑类别**：在 AnyEdit-Test 上，对局部、全局、相机移动、隐式、视觉编辑五大类别进行了细分评估。
    3.  **消融实验**：对 AnySD 模型的关键组件（任务感知路由、任务嵌入）和数据（AnyEdit 合成场景部分）进行了消融研究。
    4.  **数据规模分析**：分析了 AnyEdit 数据量从 0.5M 增长到 2.5M 时模型性能的变化趋势。
*   **充分性与公平性**：
    *   实验设计**较为充分**，不仅在标准基准上验证，还通过更难的 AnyEdit-Test 揭示了现有模型的不足以及本方法的鲁棒性。
    *   对比**具有公平性**，例如，主实验表格中通过使用相同架构的“SD1.5 w/ AnyEdit”与“SD1.5 w/ MagicBrush”进行对比，成功隔离了训练数据的影响，证明了 AnyEdit 数据集本身的质量优势。

### **6. 主要结论与发现**

1.  **数据集质量优越**：AnyEdit 数据集在语义相似度（CLIPin +16.0%）和视觉相似度（DINOv2 +25.2%）上相比 UltraEdit 等数据集有显著提升。
2.  **模型性能领先**：基于 AnyEdit 数据集训练的 AnySD 模型在 EMU-Edit 和 MagicBrush 基准上刷新了记录，在指令遵循（高 CLIPout）和图像保真度（低 L1，高 DINO/CLIPim）方面均达到 SOTA。
3.  **复杂任务泛化能力强**：在更具挑战性的 AnyEdit-Test 上，其他 SOTA 模型性能大幅下降，而 AnySD 在所有类别（包括隐式编辑和视觉编辑）中都表现出色，证明了其处理复杂、多样编辑指令的鲁棒性。
4.  **架构设计有效**：消融实验证明，任务感知路由和可学习的任务嵌入对于处理多任务编辑、保持视觉一致性至关重要。
5.  **数据扩展与平衡的重要性**：数据量扩大可以持续提升性能，而通过反事实合成场景平衡数据分布对模型泛化到罕见概念上有关键作用。

### **7. 优点**

*   **系统性的编辑任务分类**：提出了一种新颖、全面的编辑能力分类法（五大类、25种类型），为后续研究提供了清晰框架。
*   **创新的数据构建策略**：“反事实合成场景”的概念有效缓解了训练数据的长尾分布问题，是数据集构建的一大亮点。自适应编辑流水线和自动化质量筛选机制，为低资源、大规模构建高质量多模态数据提供了新范式。
*   **模型与数据的协同设计**：AnySD 的架构（MoE、任务路由、任务嵌入）专门为匹配 AnyEdit 数据集的多样性和复杂性而设计，二者形成了有效闭环。
*   **挑战性评测基准**：AnyEdit-Test 暴露了现有模型在真实、复杂编辑需求下的短板，其发布将推动社区更全面地评估编辑模型能力。

### **8. 不足与局限**

*   **算力信息缺失**：未提供模型训练的算力开销，降低了可复现性，读者无法评估其实际应用成本。
*   **依赖现有模型**：数据集构建流程高度依赖多个预训练大模型（LLaMA-3、VILA、CLIP 等），这些上游模型的固有问题和偏差可能会被引入 AnyEdit 数据集。
*   **评估指标的局限性**：虽然 CLIP 和 DINO 等指标被广泛使用，但它们并非与人类对编辑质量的感知完全对齐，尤其是对于精细的局部编辑。定性结果虽好，但仍需人类评估来提供更有说服力的证据。
*   **合成图像的潜在伪影**：数据集中包含大量由 T2I 模型生成的初始图像，这些图像可能存在内在伪影，将其作为编辑素材的“原始图像”可能会让模型学习到不真实的世界表征。

（完）
