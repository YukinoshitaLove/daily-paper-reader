---
title: Masked Autoencoders Are Effective Tokenizers for Diffusion Models
title_zh: 掩码自编码器是扩散模型的有效标记器
authors: "Hao Chen, Yujin Han, Fangyi Chen, Xiang Li, Yidong Wang, Jindong Wang, Ze Wang, Zicheng Liu, Difan Zou, Bhiksha Raj"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dzwUOiBlQW"
tags: ["query:real-ir"]
score: 9.0
evidence: 利用掩码建模为扩散模型学习语义丰富的潜在空间
tldr: 该论文发现扩散模型的潜在空间结构对生成质量至关重要，提出MAETok自编码器，通过掩码建模学习语义丰富的潜在空间，同时保持重建保真度。大量实验验证了分析结论，证明变分自编码器并非必需，所提标记器能提升扩散模型性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 878, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 810, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1761, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 899, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1754, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1599, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1598, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1598, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1599, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1598, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1597, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1600, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1601, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1598, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1598, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1600, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dzwuoiblqw/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1597, \"height\": 757, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1526, \"height\": 946, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1524, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 771, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 536, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 893, \"height\": 924, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 805, \"height\": 839, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 806, \"height\": 875, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1754, \"height\": 904, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1698, \"height\": 768, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1606, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dzwuoiblqw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 539, \"height\": 215, \"label\": \"Table\"}]"
motivation: 扩散模型的潜在空间特性研究不足，影响生成质量。
method: 提出MAETok，利用掩码建模构建结构更好的潜在空间。
result: MAETok潜在空间模式更少、特征更具区分性，提升生成质量。
conclusion: 掩码建模是学习扩散模型有效标记器的关键。
---

## Abstract
Recent advances in latent diffusion models have demonstrated their effectiveness for high-resolution image synthesis. However, the properties of the latent space from tokenizer for better learning and generation of diffusion models remain under-explored. Theoretically and empirically, we find that improved generation quality is closely tied to the latent distributions with better structure, such as the ones with fewer Gaussian Mixture modes and more discriminative features. Motivated by these insights, we propose MAETok, an autoencoder (AE) leveraging mask modeling to learn semantically rich latent space while maintaining reconstruction fidelity. 
Extensive experiments validate our analysis, demonstrating that the variational form of autoencoders is not necessary, and a discriminative latent space from AE alone enables state-of-the-art performance on ImageNet generation using only 128 tokens. MAETok achieves significant practical improvements, enabling a gFID of 1.69 with 76× faster training and 31× higher inference throughput for 512×512 generation. Our findings show that the structure of the latent space, rather than variational constraints, is crucial for effective diffusion models. Code and trained models will be released.

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与整体含义（研究动机和背景）
- 当前主流扩散模型依赖从图像压缩得到的潜在空间（latent space）进行高效生成，但“什么样的潜在空间对扩散模型最有利”这一问题仍未被充分探究。
- 现有方法多使用变分自编码器（VAE）作为标记器（tokenizer），其KL约束虽能促使潜在分布平滑，但常损害重建保真度；普通自编码器（AE）重建好但潜在空间可能纠缠、不利于生成。
- 该文意图揭示潜在空间结构与扩散模型性能之间的内在关联，进而设计一种兼具高重建保真度与良好结构化潜在表示的自编码器，从根本上摆脱对变分形式的依赖。

## 2. 论文提出的方法论
### 2.1 核心思想
- **关键发现**：含有更少高斯混合模型（GMM）模态、更具判别性的潜在空间，能让扩散模型获得更低的扩散损失和更好的生成质量。
- 基于此提出 **MAETok**，一种使用掩码建模（Masked Autoencoding）训练的普通自编码器（AE），在不施加变分约束的前提下，学习语义丰富且结构更优的潜在空间。

### 2.2 技术架构与流程
- **编码器**：Vision Transformer（ViT）结构。输入图像被分块映射为嵌入（image tokens），同时定义一组可学习的潜在令牌（latent tokens）。编码器对拼接后的序列进行处理，仅输出潜在令牌对应的表示 \(\mathbf{h}\)。
- **解码器（像素重建）**：ViT 结构，接受潜在表示 \(\mathbf{h}\) 与一组可学习的解码器图像令牌拼接作为输入，输出重建的图像块嵌入，再经线性层回归像素值。
- **掩码建模策略**：
  1. 在编码器端对 image tokens 随机施加 **40%–60% 的掩码**，用可学习的掩码令牌替换；潜在令牌保留，迫使潜在表示从可见块中聚合信息以重建缺失块。
  2. 除主像素解码器外，引入**多个浅层的辅助解码器**，预测掩码位置的多重目标特征（HOG、DINO-v2、CLIP 特征、文本 BPE 索引等），均采用 MSE 损失，仅作用于被掩码的块。
- **解耦训练策略**：
  1. 第一阶段用掩码建模联合训练编码器、像素解码器及辅助解码器。
  2. 第二阶段**冻结编码器**，仅微调解码器（并逐步降掩蔽比至0），恢复像素重建细节，而不会破坏已学到的良好潜在空间。

### 2.3 关键公式
- 训练损失：\( \mathcal{L} = \mathcal{L}_{\text{recon}} + \lambda_1 \mathcal{L}_{\text{percep}} + \lambda_2 \mathcal{L}_{\text{adv}} \)（无 KL 项）。
- 掩蔽辅助损失：\( \mathcal{L}_{\text{mask}} = \sum_j \| \mathbf{M} \odot (\hat{\mathbf{y}}_j - \mathbf{y}_j) \|_2^2 \)，其中 \(\mathbf{M}\) 为掩码指示符。

## 3. 实验设计
### 3.1 数据集与任务
- **ImageNet**（256×256 和 512×512 分辨率）用于训练与评测触笔器及最终生成模型。
- 部分设定在 **LAION-COCO** 子集上训练触笔器。
- 评测域外泛化：MS-COCO（触笔器重建泛化）。

### 3.2 基准与对比方法
- **标记器对比**：SD‑VAE、DC‑AE、VA‑VAE、SoftVQ‑VAE、TexTok 等连续或离散标记器，指标为 rFID、PSNR、SSIM。
- **生成模型对比**：
  - 自回归模型：VQGAN、ViT‑VQGAN、MaskGIT、LlamaGen‑3B、VAR、MAR‑H 等。
  - 扩散模型：LDM‑4、U‑ViT‑H、DiT‑XL/2、SiT‑XL/2、REPA、USiT‑2B、LightningDiT 等。

### 3.3 使用生成模型
- 以 **SiT‑XL** (675M) 和 **LightningDiT** 作为扩散生成器，使用仅 **128 个潜在令牌**进行评估，报告带/不带无分类器引导（CFG）的 gFID、IS、Precision、Recall。

## 4. 资源与算力
- 文中未详细列出所有实验的 GPU 总数和训练时长，但提供了多处线索：
  - 触笔器训练设置：全局 batch size 512，训练 500K 迭代，ViT‑Base 编码器/解码器（176M 参数），但未明确 GPU 数量。
  - 扩散模型训练：SiT‑XL 训练 4M 步（batch size 256），LightningDiT 训练 400K 步（batch size 1024）。
  - 推理对比提到“single A100”用于吞吐量测试。
- 总体**算力消耗较大**但具体 GPU·时、型号数量未完整披露，读者难以精确复算资源需求。

## 5. 实验数量与充分性
- 实验设计**较为充分**，包含：
  1. **GMM 分析和理论推导**：从模态数角度建立与扩散损失的关联。
  2. **关键消融实验**（表1）：掩码建模有无、解码器微调、不同重建目标（像素/HOG/DINO/CLIP等）、掩码比、辅助解码器深度、潜在令牌数量、位置编码类型等，覆盖了方法的主要组成部分。
  3. **标记器重建对比**（表4）：在 ImageNet 和 MS‑COCO 上与多种连续标记器比较。
  4. **生成性能全面对比**（表2、3、10、11）：与自回归和扩散两大类代表性模型在 256² 和 512² 分辨率对比，同时给出带/不带 CFG 的指标。
  5. **潜在空间分析**：UMAP 可视化（图4）、线性探测准确率与 gFID 关系（图5a）、训练过程 gFID 曲线（图5b）。
  6. **无条件和带引导生成**：专门分析无 CFG 时的表现，并讨论 CFG 尺度调优困难。
- **对比公平性**：自训 AE 与 VAE 使用相同训练方案和维度，主流生成模型尽量沿用原设置，实验设计较为客观公平。

## 6. 论文的主要结论与发现
- 扩散模型的生成质量与潜在空间**模态数量负相关**：GMM 模态越少、潜在判别性越强，扩散损失越低、训练越快、最终 gFID 越好。
- 普通 AE 通过掩码建模即可获得这样优质的潜在空间，**变分 KL 约束并非必要**。
- MAETok 仅用 128 个潜在令牌，在 ImageNet 512² 上实现 gFID 1.69（SiT‑XL + CFG），超越此前 2B 参数的 USiT；训练速度提升 76倍，推理吞吐提升 31倍。
- “冻编码器 + 微调解码器”策略解耦了表示学习与重建保真度，使高掩码率下仍能恢复细节。

## 7. 优点
- **深刻的理论与实证结合**：用 GMM 模态数量定量解释潜在空间质量，并给出样本复杂度下界，直觉与理论高度统一。
- **简洁有效的方法**：不引入复杂变分技巧，仅通过掩码建模和辅助目标预测，显著提升潜在判别性。
- **显著的实际效益**：大幅压缩潜在令牌数（128），带来训练和推理效率的巨幅提升，且生成质量达到 SOTA 水平。
- **设计合理且可复用**：基于标准 ViT 结构，辅助解码器轻量，训练技巧（冻结编码器微调解码）易推广至其他 tokenizer 设计。
- **分析全面**：从模态数、线性探测、可视化、消融实验等多角度验证了“结构优先于变分”的观点。

## 8. 不足与局限
- **算力与训练细节披露不完整**：未明确训练所用 GPU 型号、数量和总时长，部分超参数（如 CLIP 特征维度、BPE 具体设置）说明简略。
- **对变分方法的局限性探讨有限**：尽管证明 AE 可替代 VAE，但未深入分析 VAE 在何种场景下仍有优势（如多样性、平滑性）。
- **CFG 调优问题**：作者指出无类别标签也能学习语义，导致传统 CFG 线性组合效果下降，CFG 尺度极度敏感。目前仅实验了有限方案，未提出系统性解决策略。
- **应用域较窄**：主要聚焦于 ImageNet 类条件生成，对文本到图像、高多样性开放域生成等场景的泛化能力需进一步验证。
- **潜在空间维度固定**：128 个 latent tokens 虽高效，但可能成为表达能力的瓶颈，论文未探索 token 数量与生成质量的上界。
- **理论假设较强**：GMM 分析依赖均值有界、分离性假设，真实潜在空间可能不完全满足，对结论的普适性有影响。

（完）
