---
title: Diffusion Counterfactual Generation with Semantic Abduction
title_zh: 基于语义溯因的扩散反事实生成
authors: "Rajat R Rasal, Avinash Kori, Fabio De Sousa Ribeiro, Tian Xia, Ben Glocker"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Wqrqcc8O2v"
tags: ["query:real-ir"]
score: 9.0
evidence: 引入基于扩散的因果机制，用于反事实图像编辑与语义溯因
tldr: 针对反事实图像生成中保持身份、感知质量和因果一致性难题，本文提出一套基于扩散模型的因果机制，包括空间、语义和动态溯因，将语义表示集成到扩散过程中，实现了高保真且忠于因果模型的反事实图像编辑，提升了可扩展性和真实性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 815, \"height\": 1113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 842, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 840, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 787, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 933, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 853, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1680, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 798, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1742, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1743, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1321, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1763, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wqrqcc8o2v/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1732, \"height\": 329, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 565, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 1169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 887, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1329, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wqrqcc8o2v/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1322, \"height\": 196, \"label\": \"Table\"}]"
motivation: 现有自编码框架在反事实编辑上可扩展性和保真度不足。
method: 提出扩散因果机制框架，结合空间、语义和动态溯因进行编辑。
result: 实现了高保真、身份一致且符合因果模型的反事实图像生成。
conclusion: 为扩散模型在因果可控图像编辑中的应用提供了新范式。
---

## Abstract
Counterfactual image generation presents significant challenges, including preserving identity, maintaining perceptual quality, and ensuring faithfulness to an underlying causal model. While existing auto-encoding frameworks admit semantic latent spaces which can be manipulated for causal control, they struggle with scalability and fidelity. Advancements in diffusion models present opportunities for improving counterfactual image editing, having demonstrated state-of-the-art visual quality, human-aligned perception and representation learning capabilities. Here, we present a suite of diffusion-based causal mechanisms, introducing the notions of spatial, semantic and dynamic abduction. We propose a general framework that integrates semantic representations into diffusion models through the lens of Pearlian causality to edit images via a counterfactual reasoning process. To the best of our knowledge, ours is the first work to consider high-level semantic identity preservation for diffusion counterfactuals and to demonstrate how semantic control enables principled trade-offs between faithful causal control and identity preservation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：反事实图像生成旨在回答“如果某个变量改变了，图像会变成什么样？”的假设性问题，对个性化医疗、公平AI等至关重要。现有基于VAE、GAN等的方法在保持图像身份、感知质量和忠实于因果模型方面面临挑战。
- **核心问题**：扩散模型虽在图像合成与编辑上表现优异，但缺乏可控的语义表示空间，难以直接用于反事实推理。如何将语义控制与身份保持融入扩散模型，实现高保真、忠于因果模型的反事实编辑，是本文要解决的关键问题。
- **整体含义**：本文首次从Pearl因果层次（L3）视角系统研究扩散模型的反事实生成，提出一套结合空间、语义与动态溯因的扩散因果机制，揭示了扩散模型在因果控制与身份保持之间的内在权衡，为将扩散模型从关联/干预层面提升到真正的反事实推理提供了方法论与实验依据。

### 2. 论文提出的方法论

- **核心思想**：将Pearl的结构因果模型（SCM）与扩散模型结合，通过**溯因-行动-预测**三步流程生成反事实。定义多种扩散机制来实现外生噪声的分解与溯因，从而在保持图像身份的同时实现因果干预。
- **关键技术细节**：
    - **空间机制**：以DDIM反向过程作为溯因，将图像映射到噪声 `u`，再以干预后的父变量为条件重新生成，实现灵活的结构信息保留与编辑。
    - **语义机制**：在空间噪声基础上引入可解码的高级语义变量 `z`，通过变分自编码器学习语义后验，在溯因时采样 `z`，使生成过程固定高级语义，从而增强身份保持。
    - **摊销反因果引导**：将无分类器引导重新解释为反因果得分放大，通过调整引导强度 `ω` 和控制无条件训练概率 `p∅`，在因果控制（有效性）和身份保持（组合性、可逆性）之间实现可控权衡。
    - **动态语义溯因**：对引导标记进行逐时刻优化（CTA算法），对齐逆向轨迹与引导轨迹，进一步改善背景和细节保留，但增加计算开销。
- **公式与流程（文字说明）**：对于空间机制，图像生成 `x = hθ(u, pa)`，溯因 `u = hθ^{-1}(x, pa)`；语义机制增加 `z ~ qφ(z|x)` 和 `x = hθ(u, z, pa)`；引导预测时使用 `εω = ε_uncond + ω(ε_cond - ε_uncond)`；动态溯因通过梯度下降更新 `∅*` 以最小化重建误差。

### 3. 实验设计

- **数据集与场景**：
    - **Morpho-MNIST**：可控的玩具场景，已知真实SCM，包含数字、倾斜、厚度、强度等父变量，构造包括**单父变量（d→x）**和**多父变量复杂SCM**，以及一个**彩色变体**。
    - **CelebA-HQ (64×64)**：真实人脸数据集，建模微笑、张嘴、眼镜等属性，并额外引入性别、口红等混杂因子作为独立父变量。
    - **EMBED (192×192)**：真实乳腺X线影像，用于去除皮肤标记（三角形、圆形）的伪影，父变量包括标记类型、乳腺密度和癌症标签。
- **对比方法**：
    - 基于VAE/HVAE的Deep SCM（Pawlowski et al.; De Sousa Ribeiro et al.）。
    - 扩散因果模型DiffSCM（Sanchez & Tsaftaris, 2022）以及基于VAE的VCI（Wu et al., 2024）。
    - 各机制的消融：是否使用语义潜变量、是否使用引导、引导强度、`p∅` 值、动态溯因等。
- **评估指标**：遵循**组合性、可逆性、有效性**三公理，有效性使用预训练分类器准确率/F1或测量函数误差；身份保持额外使用LPIPS。

### 4. 资源与算力

- **推理算力**：文中明确指出，动态语义溯因生成单张反事实图像约需**3分钟**（对于CelebA-HQ，批大小128），而空间和语义机制分别约需3分和3.5分，使用**单张NVIDIA GeForce RTX 4090**。
- **训练算力**：**未明确说明**训练使用的GPU数量、训练轮数对应总时长。仅在附录中给出了各数据集的训练轮数（如Morpho-MNIST 1000 epochs，CelebA-HQ 6000 epochs），但缺少实际训练时钟时间。

### 5. 实验数量与充分性

- **实验数量**：覆盖**3个不同尺度和领域的数据集**；在每个数据集上对比了多个基线方法，并对**引导强度ω、无条件概率p∅、有无语义变量、是否使用动态溯因**等关键超参数进行了系统性消融；同时在Morpho-MNIST上测试了不同干预类型（do(d), do(s), do(t), do(i)）以及完整SCM下的效果。
- **充分性与公平性**：
    - 实验设计较为**全面**，从可控合成数据到真实人脸、医学影像逐步验证方法的可扩展性。
    - 使用统一的反事实公理标准进行评估，对比主流因果生成模型，**公平性较强**。
    - 对于基线方法，论文指出了VCI在CelebA-HQ上预处理不同导致性能下降的问题，并在附录中展示了不裁剪时的失效结果，增加了分析的客观性。
    - 不足之处：未在更大规模、更高分辨率的数据集（如256×256以上）上验证；未包含文本驱动的扩散编辑方法作为对比，尽管它们常用于近似反事实。

### 6. 论文的主要结论与发现

- 扩散模型可有效用作SCM中的图像生成机制，通过DDIM反演实现高质量的Pearl式溯因。
- **语义机制**能够在保持与空间机制相当或略降的有效性前提下，**显著提高身份保持能力**（组合性、可逆性更优）。
- 通过调节引导强度 `ω` 和 `p∅`，可以实现**因果控制（有效性）与身份保持之间的精细权衡**：更高的 `ω` 和更小的 `p∅` 增强有效性但损害身份保持，这与L2追求多样性的设置不同，突显L3推理的特殊性。
- **动态语义溯因**可进一步改善背景和局部细节的保留，但以计算时间为代价。
- 提出的框架能够成功应用于**真实医学伪影去除**，展示了实际价值。

### 7. 优点

- **方法论创新**：首次将语义潜变量显式融入扩散模型的溯因过程，并以因果透镜重新诠释扩散引导，系统定义了空间、语义、动态三种溯因机制。
- **理论深度**：基于Pearl因果层次架起L2与L3的桥梁，明确指出了扩散模型中常用于采样的超参数在反事实推理中的不同影响。
- **实验全面性**：跨越合成、人脸、医学三个领域，进行了多维度的消融和对比，清晰展示了各机制的优势与trade-off。
- **可复现性**：开源代码链接已提供，附有详细的网络结构和超参数表。

### 8. 不足与局限

- **计算开销大**：动态溯因虽然有效，但生成单张图像需数分钟，难以应用于实时交互场景。
- **模型可识别性未解决**：语义潜变量使用无条件高斯先验，导致模型不可识别，可能使同一观测下的不同溯因得出不一致的反事实。
- **数据集规模与分辨率**：使用的数据集规模较小，分辨率最高仅192×192，尚不清楚在大规模、高分辨率图像上的表现。
- **假设限制**：基于马尔可夫SCM和因果充分性假设，未考虑未观测混杂或标签噪声的影响，论文自身也指出了这一点。
- **缺乏人类偏好评估**：仅依赖自动化指标，未进行用户研究来评估反事实编辑的感知真实性和身份一致性。
- **训练算力未报备**：缺少训练所需GPU数量及总时长的具体数据，不利于评估实际部署成本。

（完）
