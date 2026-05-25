---
title: "RealRAG: Retrieval-augmented Realistic Image Generation via Self-reflective Contrastive Learning"
title_zh: RealRAG：通过自反对比学习的检索增强真实图像生成
authors: "Yuanhuiyi Lyu, Xu Zheng, Lutao Jiang, Yibo Yan, Xin Zou, Huiyu Zhou, Linfeng Zhang, Xuming Hu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dpbvg1mFBq"
tags: ["query:real-ir"]
score: 8.0
evidence: 引入检索增强生成框架实现逼真图像生成
tldr: 针对文本至图像扩散模型在面对未见特定真实对象时易产生扭曲和幻象的问题，本文提出RealRAG框架，首个将检索增强引入真实对象生成。它通过自反对比学习从真实图像库中记忆和检索相关图像，然后将其信息融入生成过程以精确描绘细粒度特征。实验证明，RealRAG能够高保真生成例如特斯拉Cybertruck等新颖物体，大幅降低了生成偏差，展示了检索增强在弥补模型知识缺失方面的巨大潜力，为真实世界生成任务开辟了新方向。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 824, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 1556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 860, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1636, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 268, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 268, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 265, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 266, \"height\": 251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 264, \"height\": 251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 262, \"height\": 255, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 263, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 264, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 277, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 278, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 278, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 278, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 279, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 277, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 276, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 272, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1750, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpbvg1mfbq/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1761, \"height\": 1706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dpbvg1mfbq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 718, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpbvg1mfbq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpbvg1mfbq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpbvg1mfbq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpbvg1mfbq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 496, \"label\": \"Table\"}]"
motivation: 解决生成模型对未见真实物体产生幻觉和失真的知识局限。
method: 提出检索增强生成框架RealRAG，自反对比学习真实图像。
result: 能高保真生成新颖真实物体，显著降低生成偏差。
conclusion: 检索增强有效弥补生成模型知识缺口，提升开放世界适应性。
---

## Abstract
Recent text-to-image generative models, e.g., Stable Diffusion V3 and Flux, have achieved notable progress. However, these models are strongly restricted to their limited knowledge, a.k.a., their own fixed parameters, that are trained with closed datasets. This leads to significant hallucinations or distortions when facing fine-grained and unseen novel real-world objects, e.g., the appearance of the Tesla Cybertruck. To this end, we present **the first** real-object-based retrieval-augmented generation framework (**RealRAG**), which augments fine-grained and unseen novel object generation by learning and retrieving real-world images to overcome the knowledge gaps of generative models. Specifically, to integrate missing memory for unseen novel object generation, we train a reflective retriever by **self-reflective contrastive learning**, which injects the generator's knowledge into the sef-reflective negatives, ensuring that the retrieved augmented images compensate for the model's missing knowledge. Furthermore, the real-object-based framework integrates fine-grained visual knowledge for the generative models, tackling the distortion problem and improving the realism for fine-grained object generation. Our Real-RAG is superior in its modular application to **all types** of state-of-the-art text-to-image generative models and also delivers **remarkable** performance boosts with all of them, such as a **gain of *16.18\%* FID score** with the auto-regressive model on the Stanford Car benchmark.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前最先进的文本到图像生成模型（如 Stable Diffusion V3, Flux 等）将所有的视觉知识隐式地存储在固定的模型参数中。这种“知识封闭性”导致了严重的“幻觉”和“失真”问题，尤其是在生成**细粒度对象**（如特定品牌型号的汽车）或**训练后出现的、未见过的真实世界新物体**（如特斯拉 Cybertruck）时。
*   **研究动机**：受大语言模型中检索增强生成（RAG）成功的启发，论文旨在为文本到图像生成任务提供一个统一的、基于真实对象图像的RAG框架。
*   **整体含义**：论文提出，通过引入一个**自反检索器**（Reflective Retriever），从真实世界图像数据库中检索生成模型“缺失的知识”，而不是简单地检索与文本提示最相关的图像，可以有效地补偿生成模型的知识盲区，从而显著提升生成图像的**真实感**和**准确性**。

### 2. 论文提出的方法论

论文的核心是提出了首个基于真实对象的检索增强生成框架 **RealRAG**，其关键创新点在于**自反对比学习**（Self-reflective Contrastive Learning）方法。

*   **核心思想**：传统的RAG方法检索与文本提示最相似的图像。而RealRAG则认为，最有用的参考图像并非相似度最高的，而是那些**能弥补生成模型自身知识缺陷的图像**。这些图像应位于生成模型的生成空间之外，但贴近目标文本的语义空间。
*   **关键技术细节**：
    *   **自反负样本生成**：给定一个文本提示 \( T \)，先用冻结的生成器 \( G \) 生成一幅图像 \( I_{gen} \)。然后，在真实对象数据库中，检索与 \( I_{gen} \) 在特征空间上最相似的图像作为“**自反负样本**” \( I_{neg} \)。这个 \( I_{neg} \) 代表了生成器已有的知识，是检索器需要学习的“不要检索”的对象。
    *   **自反对比学习**：基于CLIP模型训练一个"自反检索器"。其训练的对比损失函数鼓励检索器的输出（查询）拉近与正样本（真实对应的物体图像）的距离，并同时推远两种负样本：1) 批次内的其他图像（In-batch negatives）；2) 专门构造的自反负样本。
    *   **损失函数**：
        \[
        I_{neg} = \underset{I_k^{obj} \in \mathcal{I}}{\arg \max}\ \text{sim}(F_i(I_k^{obj}), F_i(G(T)))
        \]
        \[
        \mathcal{L} = -\log \frac{\exp(Z_q^T \cdot Z_{obj}^{pos} / \tau)}{\exp(Z_q^T \cdot Z_{obj}^{pos} / \tau) + D_{neg}^{nor} + D_{neg}^{ref}}
        \]
    其中 \( D_{neg}^{ref} \) 是查询特征与自反负样本特征的指数相似度。
    *   **检索增强生成**：训练好的自反检索器根据输入的文本提示 \( T \)，从真实物体数据库中检索出一张能补充知识缺失的参考图像 \( I_{ref} \)。然后，该参考图像和文本提示一起被送入生成器 \( G \) 进行条件生成： \( I_{res} = G(T, I_{ref}) \)。

### 3. 实验设计

*   **数据集与场景**：
    *   **细粒度对象生成**：在 `Stanford Cars`、`Stanford Dogs` 和 `Oxford Flowers` 三个细粒度数据集上进行评估。
    *   **未见新物体生成**：通过从互联网（Google Images）收集近期出现的新物体（如 Cybertruck, Volocopter 2x 等）图像构建数据库，并用LLM生成提示词进行评估。
*   **Benchmark（评价指标）**：
    *   **FID**：衡量生成图像与真实图像分布之间的距离，评估图像质量和真实感。
    *   **CLIP-T**：衡量生成图像与输入文本提示的语义一致性。
    *   **CLIP-I**：衡量生成图像与真实参考图像之间的视觉相似度。
    *   **分类准确率**：使用预训练的 OpenCLIP 模型对生成图像进行分类，准确率越高表示生成图像越符合其类别特征。
    *   **人工评估**：对未见新物体的生成结果进行7分制李克特量表评分和真/假图判断。
*   **对比方法**：
    *   **零样本RAG**：直接使用CLIP根据相似度检索。
    *   **普通RAG**：使用普通对比学习训练的检索器，旨在检索最相似的图像。
    *   **多种生成器基底模型**：将RealRAG模块化应用到**所有主流类型**的生成模型上，包括U-Net扩散模型（SD V2.1, SDXL）、DiT扩散模型（SD V3, Flux）和自回归模型（OmniGen, Emu）。

### 4. 资源与算力

*   论文中**未明确说明**训练自反检索器所使用的GPU型号、数量及具体训练时长。仅提及检索器是基于预训练的CLIP模型微调。

### 5. 实验数量与充分性

*   **实验数量**：实验量充足且全面。
    *   **主实验**：在3个细粒度数据集上，对6种不同的生成器进行性能增益评估，是一项庞大的实验组合。
    *   **消融实验**：通过对比零样本RAG、普通RAG和RealRAG（在3种生成器上），严格证明了自反对比学习的有效性；并通过训练过程中的性能曲线，验证了自反负样本在克服性能瓶颈中的作用。
    *   **可视化分析**：提供了丰富的定性生成结果对比，并通过 t-SNE 可视化展示了RealRAG能更好地拓展生成空间的分布。
    *   **人类评估**：引入了26名参与者进行主观评估，增加了结论的可靠性。
*   **充分性与公平性**：实验设计严谨、充分且公平。对比方法选择合理，涵盖了从零样本检索到强化的检索基线。所有方法均在相同的预训练生成器上应用，性能提升对比清晰可信。

### 6. 论文的主要结论与发现

*   RealRAG是一个强大且通用的框架，能够作为即插即用的模块，应用于所有三种主流类型的文本到图像生成模型上，并带来显著性能提升。
*   核心的**自反对比学习**方法非常有效，它训练的检索器能够真正召回“补充生成器知识缺口”的图像，而非简单的相似图像，这是实现性能突破的关键。
*   RealRAG在细粒度对象生成上显著提高了真实感和准确性，并在生成模型完全未知的、训练集出现后的新物体任务中展现出强大的能力，有效解决了幻觉问题。

### 7. 优点

*   **问题新颖且关键**：首次明确定义并尝试解决文本到图像生成中的“知识缺失型幻觉”，提出了从外部真实知识库进行补充的思路。
*   **方法创新性强**：**自反对比学习**的思想非常精巧。通过将生成器自身知识注入负样本的方式，巧妙地引导检索器去发掘模型“知识盲区”内的信息，这是对传统检索增强范式的深刻反思和改进。
*   **通用性与实用性强**：作为一个与模型架构解耦的框架，它可以无需任何再训练地配合几乎所有主流文本到图像模型使用，具有极大的应用价值和潜力。
*   **实验扎实全面**：在多个数据集、多个评价指标、多个模型架构以及人工评估上进行了细致验证，消融实验也清晰地证明了核心方法的有效性。

### 8. 不足与局限

*   **对数据库的依赖性**：生成质量和多样性的上限很大程度上受限于外部真实对象数据库的规模和覆盖范围。对于数据库中完全不存在的对象，方法可能会失效。
*   **未见新物体的检索挑战**：尽管RealRAG旨在生成未见过的物体，但对于一个完全未知的物体，检索器本身也需要在包含该物体的数据库中工作。这意味着数据库需要持续更新（例如从互联网实时获取），而论文的方法是在一个静态（虽然包含了新物体）的数据库上验证的。
*   **生成结果的可控性**：论文主要关注真实感，但检索到的参考图像可能会过度影响生成结果，例如固定了物体的视角、背景或大小，降低了生成的多样性。
*   **计算开销**：在推理时增加了检索和条件生成步骤，会引入额外的计算和时间成本。

（完）
