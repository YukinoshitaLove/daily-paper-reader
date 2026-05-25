---
title: Highly Compressed Tokenizer Can Generate Without Training
title_zh: 高压缩分词器无需训练即可生成
authors: "Lukas Lao Beyer, Tianhong Li, Xinlei Chen, Sertac Karaman, Kaiming He"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=rcjgzbYvhF"
tags: ["query:real-ir"]
score: 8.0
evidence: 一维分词器通过标记操作实现图像编辑与生成流程
tldr: 发现高度压缩的一维图像分词器可通过对离散标记的简单启发式操作（如复制替换）实现细粒度图像编辑和生成。利用该分词器潜在空间的表达能力，构建了基于梯度测试时优化的图像生成流程，无需额外训练，展示了压缩表示在生成任务中的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1730, \"height\": 1077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1767, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 1315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1347, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1357, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 1052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1648, \"height\": 1194, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1365, \"height\": 1360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1337, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1337, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1337, \"height\": 1051, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rcjgzbyvhf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1772, \"height\": 2181, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1751, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1747, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rcjgzbyvhf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1737, \"height\": 152, \"label\": \"Table\"}]"
motivation: 探索高压缩图像表示的生成与编辑能力。
method: 使用1D VQ分词器，通过标记复制替换实现编辑，并构建测试时优化生成管道。
result: 实现显著的图像编辑和从压缩标记的生成效果。
conclusion: 高压缩标记器为高效图像生成与编辑提供了新路径。
---

## Abstract
Commonly used image tokenizers produce a 2D grid of spatially arranged tokens. In contrast, so-called *1D* image tokenizers represent images as highly compressed one-dimensional sequences of as few as 32 discrete tokens. We find that the high degree of compression achieved by a 1D tokenizer with vector quantization enables image editing and generative capabilities through heuristic manipulation of tokens, demonstrating that even very crude manipulations -- such as copying and replacing tokens between latent representations of images -- enable fine-grained image editing by transferring appearance and semantic attributes. Motivated by the expressivity of the 1D tokenizer's latent space, we construct an image generation pipeline leveraging gradient-based test-time optimization of tokens with plug-and-play loss functions such as reconstruction or CLIP similarity. Our approach is demonstrated for inpainting and text-guided image editing use cases, and can generate diverse and realistic samples without requiring training of any generative model.

---

## 论文详细总结（自动生成）

好的，这是对论文《Highly Compressed Tokenizer Can Generate Without Training》的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：
    *   现代图像生成流程通常由两部分组成：一个将图像压缩到潜在空间的**分词器**，和一个在潜在空间上操作的**生成模型**。
    *   近期出现的 **1D 图像分词器**能将图像压缩至极少的离散标记中（例如 32 个），这比传统的 2D 网格标记压缩率高得多。
    *   论文的核心问题是：当压缩率极高时，分词器的解码器本身就具备了强大的生成能力。那么，这些高度压缩的 1D 分词器本身能在多大程度上被视为生成模型，是否能绕开昂贵的生成模型训练，直接用于生成和编辑任务。

*   **整体含义**：
    *   本文旨在证明，一个预训练的高压缩 1D 分词器无需任何额外的生成模型训练，仅通过对标记的启发式操作和测试时优化，就能实现精细的图像编辑和多样化的图像生成。

### 2. 论文提出的方法论

*   **核心思想**：
    *   高压缩 1D 分词器的离散标记空间具有高度语义性和表现力，可以直接进行编辑和优化。这得益于三个关键因素：**1D 序列结构**（非空间性）、**矢量量化** 和**少量标记**。

*   **关键技术细节**：
    1.  **启发式标记操作**：
        *   **标记重要性评估**：通过分析标记在不同图像分区间的特征方差，识别出与特定高级属性（如背景模糊、光照）高度关联的标记位置。
        *   **“复制-粘贴”编辑**：为了编辑一张图像，找到对应所需属性的标记位置，从参考图像中取出相应位置的标记，替换目标图像的对应标记。公式如下：
            $$I_{edit} = \text{Dec}(\text{Replace}_k(x_{target}, x_{ref}^{(k)}))$$

    2.  **基于梯度的测试时优化**：
        *   构建了一个通用的图像生成/编辑框架，通过优化连续特征向量 $\hat{z}^{(k)}$ 来最大化任意可插拔的损失函数。
        *   **文本引导编辑 / 生成**：损失函数是解码图像与文本提示之间的 CLIP 相似度。优化通过梯度回传进行，在矢量量化步骤使用直通估计器。
            $$\arg \max_{\hat{z}^{(1)}, ..., \hat{z}^{(K)}} \ell\left( \text{Dec}\left( \left[ \text{VQ}_D(\hat{z}^{(1)}), ..., \text{VQ}_D(\hat{z}^{(K)}) \right] \right) \right)$$
        *   **图像修补**：损失函数是图像未遮挡部分的重建损失（L1），并周期性地将解码图像的已知部分重置回原始图像后重新编码，以保持一致性。
        *   **算法优化技巧**：
            *   随机裁剪：在多个随机裁剪区域上平均 CLIP 损失，平滑梯度。
            *   标记噪声注入：在每次迭代开始时向标记添加高斯噪声。
            *   标记正则化：对连续特征向量应用 L2 正则化。
            *   指数移动平均：返回优化过程中标记的指数移动平均值。

### 3. 实验设计

*   **数据集与场景**：
    *   **图像编辑**：使用 ImageNet 验证集和用户提供的图像进行定性评估，涵盖属性转移（如变焦、调色）和文本引导编辑（如改变主体、背景）。
    *   **图像生成/修补**：主要在 **ImageNet ILSVRC2012** 上进行定量评估。
    *   **补充定性实验**：在非 ImageNet 类别和艺术风格迁移等分布外场景上测试。

*   **基准与指标**：
    *   **生成质量**：使用 **FID** 和 **Inception Score** 作为主要指标，遵循 ADM 的评估协议。
    *   **文本-图像对齐**：使用 **CLIP 相似度** 和 **SigLIP 相似度**，特别强调 SigLIP 以避免对 CLIP 模型的对抗性过拟合。
    *   **对比方法**：与无条件和半参数生成模型进行系统级比较，包括 **ADDP, RCG, RCDM, IC-GAN, RDM** 等。

### 4. 资源与算力

*   **计算成本**：文中明确指出，使用 VQ-LL-32 分词器进行 300 次文本引导优化迭代，在一张 **NVIDIA A100** GPU 上需要 **7 秒** 每张图像。
*   **训练成本**：本文方法是**训练自由**的，所有实验都基于公开的预训练 TiTok 模型，因此没有额外的生成模型训练成本。

### 5. 实验数量与充分性

实验设计相对充分，旨在全面验证核心观点。

*   **标记语义分析**：进行了多组定性实验（标记重要性、单标记扰动、“复制-粘贴”编辑）来证明 1D 标记空间的可编辑性。
*   **生成与编辑评估**：
    *   **核心消融实验**：对种子图像集大小（2000, 1000, 500）、种子关联策略（随机、CLIP-top1、CLIP-top1%）进行了定量消融，评估对 FID 和 IS 的影响。
    *   **分词器变体消融**：对比了 1D 连续/离散标记、不同标记数量（32, 64, 128）、不同码书大小以及 2D 分词器，定量验证了“更高压缩率带来更强生成能力”的观点。
    *   **优化算法消融**：对随机裁剪、EMA、标记噪声、标记正则化等优化技巧进行了消融研究，评估它们对生成质量的影响。
    *   **初始化方式对比**：定量对比了从种子图像初始化和从随机标记初始化的文本生成效果。
*   **客观性与公平性**：对比实验大多在相同或类似设置下进行，选用的 FID、IS、SigLIP 是领域内标准指标，具有较好的客观性。不过，一些早期对比方法的数值可能因实现细节不同而有差异。

### 6. 论文的主要结论与发现

*   **高压缩 1D 分词器具备内在生成能力**：无需额外训练，即可通过简单的标记操作实现图像编辑。
*   **标记位置与高级语义属性相关联**：特定的标记位置编码了如背景模糊、光照、图像质量等可解释的全局属性。
*   **基于梯度的测试时优化是有效的生成范式**：通过结合 CLIP 目标函数，可以从种子图像或随机噪声出发，生成多样化且高质量的图像，达到或超越了部分需要训练的早期无条件生成模型。
*   **压缩是生成能力的关键**：增加压缩率（更少的标记、矢量量化、更小的码书）能显著提升测试时优化的生成效果。这验证了思想实验：极致的压缩迫使解码器本身成为一个强大的生成模型。

### 7. 优点

*   **概念新颖，见解深刻**：从一个独特的角度（高压缩分词器即生成模型）切入，揭示了模型压缩与生成能力之间的内在联系，颠覆了“生成必训练”的常规认知。
*   **方法极其简洁高效**：所提出的图像生成和编辑方法无需任何生成模型训练，仅需数秒级的测试时优化，大大降低了计算门槛。
*   **实验论证系统且扎实**：从现象观察（标记语义）到方法提出（梯度优化），再到定量和定性评估，实验链条完整，消融研究充分，有力地支撑了核心论点。
*   **可解释性强**：“复制-粘贴”编辑和标记重要性分析直观地展示了模型潜在空间的组织方式。

### 8. 不足与局限

*   **对分词器要求极高**：方法性能严重依赖于预训练分词器的压缩率和质量。实验表明，只有使用最极端的 32 个标记的量化模型（VQ-LL-32）才能获得较好效果，计数稍多或连续标记模型表现急剧下降，限制了其通用性。
*   **生成多样性和质量仍逊于最先进模型**：尽管无需训练，但其 FID 和 IS 与当前需要训练的最优生成模型（如 RCG）仍有较大差距，特别是从零开始生成时。
*   **依赖预训练判别模型**：文本引导生成依赖 CLIP 模型，存在遭遇对抗样本的风险，且 CLIP 模型的偏见和局限会直接影响生成结果，尽管使用了 SigLIP 来缓解。
*   **训练域局限**：分词器仅在 ImageNet 上训练，导致其在生成非 ImageNet 类别或非自然图像风格时，能力有限或结果不准确。
*   **种子依赖性**：“从零生成”的质量和多样性优于随机种子，但仍不如基于种子图像初始化的生成，说明优化过程需要好的起点，且在开放式生成中，提示与种子的匹配度对结果影响很大。

（完）
