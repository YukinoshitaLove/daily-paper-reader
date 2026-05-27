---
title: "SRSR: Enhancing Semantic Accuracy in Real-World Image Super-Resolution with Spatially Re-Focused Text-Conditioning"
title_zh: "SRSR: 通过空间重新聚焦文本条件增强真实世界图像超分辨率的语义准确性"
authors: "Chen Chen, Majid Abdolshah, Violetta Shevchenko, Hongdong Li, Chang Xu, Pulak Purkait"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=s91i4zNebu"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于扩散的真实世界超分辨率，采用空间重新聚焦文本条件
tldr: 针对扩散模型超分辨率中文本条件不准确导致语义歧义和幻觉细节的问题，本文提出空间重新聚焦超分辨率框架（SRSR）。其核心包括空间重新聚焦交叉注意力（SRCA），通过视觉分割掩码引导交叉注意力；以及频率分离策略。该方法作为即插即用模块，在不重新训练的情况下提升现有扩散超分模型的语义准确性。实验表明，SRSR有效减少了语义错位和幻觉，生成更符合文本描述的高分辨率图像。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1422, \"height\": 1193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1312, \"height\": 927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 835, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 837, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1442, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1447, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1345, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1446, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1020, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1438, \"height\": 1741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1439, \"height\": 1743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s91i4znebu/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1446, \"height\": 556, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-s91i4znebu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 842, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s91i4znebu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s91i4znebu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 641, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s91i4znebu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 298, \"label\": \"Table\"}]"
motivation: 现有扩散超分方法因文本条件不准确和注意力分散导致语义歧义和幻觉。
method: 提出即插即用的SRSR框架，包含空间重新聚焦交叉注意力和频率分离。
result: 在真实世界超分任务上显著减少语义错位和幻觉，提升了语义一致性。
conclusion: 空间引导的文本条件有效增强了扩散超分模型的语义理解能力。
---

## Abstract
Existing diffusion-based super-resolution approaches often exhibit semantic ambiguities due to inaccuracies and incompleteness in their text conditioning, coupled with the inherent tendency for cross-attention to divert towards irrelevant pixels. These limitations can lead to semantic misalignment and hallucinated details in the generated high-resolution outputs. To address these, we propose a novel, plug-and-play *spatially re-focused super-resolution (SRSR)* framework that consists of two core components: first, we introduce Spatially Re-focused Cross-Attention (SRCA), which refines text conditioning at inference time by applying visually-grounded segmentation masks to guide cross-attention. Second, we introduce a Spatially Targeted Classifier-Free Guidance (STCFG) mechanism that selectively bypasses text influences on ungrounded pixels to prevent hallucinations. Extensive experiments on both synthetic and real-world datasets demonstrate that SRSR consistently outperforms seven state-of-the-art baselines in standard fidelity metrics (PSNR and SSIM) across all datasets, and in perceptual quality measures (LPIPS and DISTS) on two real-world benchmarks, underscoring its effectiveness in achieving both high semantic fidelity and perceptual quality in super-resolution.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：现有基于扩散模型的图像超分辨率方法（如SeeSR、OSEDiff等）在使用文本条件引导时，由于文本提示提取不准确/不完整以及交叉注意力机制天然会分散到不相关像素，导致生成的高分辨率图像存在**语义歧义**和**幻觉细节**，即语义对齐错误和虚假纹理。
- **研究背景**：超分辨率旨在从低分辨率图像恢复高分辨率细节。真实世界超分辨率面临复杂退化（模糊、噪声、压缩等）。近期方法利用Stable Diffusion的文本条件能力，通过从LR图像提取提示（如DAPE）来改善语义一致性，但存在三大局限：
  1. **交叉注意力偏移**：文本标记会错误地关注不相关区域，导致误导性指导。
  2. **不准确的提示**：在严重退化下，提示提取器（如DAPE）仍会给出错误标签，误导生成。
  3. **不完整的覆盖**：提示无法覆盖全图，未接地区域（无对应文本标记的区域）易受无关文本影响，产生幻觉。
- **整体含义**：提出一种即插即用的推理时框架SRSR，通过空间重新聚焦文本条件来提升语义准确性，同时保持感知质量，无需重新训练。

## 2. 方法论：核心思想、关键技术、公式或算法流程

- **核心思想**：
  - 利用视觉接地（Grounded SAM）将DAPE提取的标签与图像区域关联，过滤不可靠标签，并为每个有效标签生成分割掩码。
  - 基于这些标签-掩码对，设计两个模块：**空间重新聚焦交叉注意力（SRCA）** 和**空间定向无分类器引导（STCFG）**，在推理时精细控制文本条件在空间上的作用范围。
- **关键技术细节**：
  - **步骤1：视觉接地**  
    使用Grounded SAM将DAPE标签接地到图像区域：仅保留能高置信度匹配的标签，丢弃不匹配的标签，同时为每个保留标签生成二值掩码。未接地像素集合定义为所有接地掩码的补集。
  - **步骤2：空间重新聚焦交叉注意力（SRCA）**  
    在U-Net的16个交叉注意力层中，对每个像素i和每个标记j，原始注意力权重为α<sub>ij</sub> = SoftMax(Q·K/√d)。SRCA施加二值掩码M<sub>ij</sub>（若标记j接地于像素i则M=1，否则0），然后重新归一化：
    - α<sup>SRCA</sup><sub>ij</sub> = M<sub>ij</sub>·α<sub>ij</sub>
    - 然后对α<sup>SRCA</sup>进行像素-标记联合归一化：α̂<sup>SRCA</sup><sub>ij</sub> = α<sup>SRCA</sup><sub>ij</sub> / Σ<sub>i',j'</sub>α<sup>SRCA</sup><sub>i'j'</sub>  
    这样每个像素只关注其对应的接地标记，忽略不相关标记，从而消除语义混淆。
  - **步骤3：空间定向无分类器引导（STCFG）**  
    对未接地像素，禁用CFG，即仅使用无条件预测ϵ<sub>θ</sub>(x<sub>t</sub>,ϕ)；对已接地像素，照常使用CFG（文本条件预测与无条件预测的插值）。具体公式：
    ```
    ϵ̂_i = (1-M_i)[ϵ_θ(x_t,ϕ) + s·(ϵ_θ(x_t,y) - ϵ_θ(x_t,ϕ))] + M_i·ϵ_θ(x_t,ϕ)
    ```
    其中M_i=1表示像素i未接地。这避免了无意义或全局标记（如EOS、标点）对未接地区域造成污染，从而抑制幻觉。
- **算法流程总结**：  
  输入LR图像 → DAPE提取标签 → Grounded SAM得到标签-掩码对 → 在U-Net推理过程中应用SRCA（每层交叉注意力施加掩码约束） → 在CFG阶段应用STCFG（根据接地掩码选择使用条件或无条件预测） → 经过T步去噪后解码得到SR图像。
- **重要特点**：无需训练或微调，即插即用；SRCA和STCFG都不引入新参数，仅修改推理过程。

## 3. 实验设计：数据集、Benchmark、对比方法

- **数据集**：
  - **合成数据集**：从DIV2K-Val随机裁剪3000张512×512图像，使用Real-ESRGAN退化管线生成LR-HR对。
  - **真实世界数据集**：
    - RealSR：128×128 LR-HR对。
    - DRealSR：512×512 LR-HR对。
- **Benchmark**：使用常见图像质量评估指标：
  - 全参考指标：PSNR、SSIM（保真度）、LPIPS、DISTS（感知质量）、FID（分布距离）。
  - 无参考指标：NIQE、MUSIQ、MANIQA、CLIPIQA。
- **对比方法**（共7个SOTA基线）：
  - StableSR（s200）、DiffBIR（s50）、PASD（s20）、ResShift（s15）、SinSR（s1）、OSEDiff（s1）、SeeSR（s50）。
  - 作者将SRSR分别融入SeeSR（50步）和OSEDiff（1步），得到SRSR-SeeSR和SRSR-OSEDiff，并与上述基线公平比较。

## 4. 资源与算力

- 论文中未明确说明训练所需算力（因为SRSR是纯推理方法，无需训练）。仅提及Grounded SAM的推理时间：对128×128图像仅需0.12秒/张（V100 GPU），对512×512图像需0.16秒。模型总参数量与基线相同（未增加）。训练资源细节未提及。

## 5. 实验数量与充分性

- **主要实验**：在3个数据集（1合成+2真实）上对比7种方法，报告全参考和无参考指标（表1）。
- **消融实验**（表2）：逐步去除组件，验证SRCA、STCFG、接地、语义分割（Mask2Former/DINO-X）等贡献，共10个变体（V1-V10）。
- **超参数分析**（表3）：不同接地置信度阈值（0.15~0.55），对比4个指标。
- **用户研究**（附录）：在RealSR和DRealSR上邀请两位标注员对比SRSR-SeeSR与SeeSR的偏好。
- **充分性评价**：实验设计较为充分，覆盖了重要组件消融、超参数敏感性、多种基线对比。但未在更多合成或真实数据集（如其他流行的SR基准）上验证，可能限制泛化性。对比方法均为近期强模型，比较公平。无参考指标表现反常，作者也指出其不可靠性，但依然进行了报告，增加了透明度。

## 6. 主要结论与发现

- SRSR（尤其是SRSR-SeeSR）在所有数据集上取得了**最好的全参考保真度指标（PSNR/SSIM）**，并多数情况下在感知质量（LPIPS/DISTS）上也最优或第二优。
- SRCA和STCFG共同作用：SRCA消除语义混淆，STCFG保护未接地区域，互补提升。
- 提示准确性比完全覆盖更重要：使用DAPE+接地优于使用语义分割（Mask2Former/DINO-X），因为后者的标签不准确。
- 无参考指标往往高估幻觉严重的输出，不可靠；建议以全参考指标作为主要评价依据。
- SRSR作为推理时模块，能显著改善基线（SeeSR、OSEDiff）的语义保真度，且不增加参数。

## 7. 优点

1. **即插即用、无需训练**：可无缝嵌入任何基于交叉注意力且使用文本先验的扩散超分模型，降低应用门槛。
2. **针对三大痛点提出有效解决方案**：接地过滤不正确标签、空间注意力约束缓解注意力偏移、空间CFG防止未接地区域受无关文本干扰。
3. **实验指标全面**：既包含保真度也包含感知指标，并揭示了无参考指标的缺陷。
4. **消融实验设计清晰**：逐步剥离组件，证明每个模块的必要性。
5. **用户研究支持**：附录中人类偏好实验进一步验证语义改进。
6. **分析深入**：多个可视化示例（图1-4、附录图S1-S17）直观展示幻觉消除和注意力聚焦。

## 8. 不足与局限

1. **依赖外部模型**：需要Grounded SAM进行接地，虽然效率高，但增加了管线复杂性和额外推理开销。
2. **接地阈值的敏感度**：虽然实验显示鲁棒，但阈值选择仍影响精度-覆盖平衡，不同场景可能需要调整。
3. **未在真实世界退化无HR参考的场景中评估**：所有实验均基于有HR参考的数据集，无法充分验证在完全盲场景下的表现。
4. **语义分割方案扩展性有限**：目前仅实验了DAPE+Grounding，未来更强降解感知的分割模型可能提升性能，但论文未深入探索。
5. **未考虑训练微调**：当前为纯推理方案，若将SRSR融入训练或微调可能进一步提升，但未进行实验，作者也承认这一点作为局限。
6. **无参考指标不可靠**：作者虽然指出问题，但未提出改进方案；在实际应用中如果无法获取HR参考，依赖现有无参考指标可能误导评估。
7. **计算资源细节缺失**：未提供基线方法的训练成本或SRSR推理的具体GPU时长（虽提及0.12s/0.16s，但未说明步数50步或200步对应的总时间）。
8. **仅测试了两个基线（SeeSR和OSEDiff）**：虽然声称通用，但验证覆盖有限，未在更多架构（如AddSR、TSD-SR）上展示。

（完）
