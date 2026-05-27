---
title: "AlignedGen: Aligning Style Across Generated Images"
title_zh: AlignedGen：对齐生成图像之间的风格
authors: "Jiexuan Zhang, Yiheng Du, Qian Wang, Weiqi Li, Yu Gu, Jian Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ax0y9DvLCp"
tags: ["query:real-ir"]
score: 6.0
evidence: 使用DiT模型进行风格一致的图像生成
tldr: 扩散模型在跨图像生成中难以保持风格一致性，且现有方法主要基于U-Net架构。AlignedGen针对DiT模型提出无需训练的解决方案，通过移位位置嵌入和高级注意力共享显著增强风格一致性，兼容Flux等主流模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1381, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1380, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1389, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1380, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1380, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1430, \"height\": 1159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1444, \"height\": 1476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ax0y9dvlcp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1160, \"height\": 1808, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ax0y9dvlcp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ax0y9dvlcp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1267, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ax0y9dvlcp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1392, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ax0y9dvlcp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 203, \"label\": \"Table\"}]"
motivation: 现有风格对齐方法在DiT模型上表现不佳。
method: 提出Shifted Position Embedding和Advanced Attention Sharing实现无需训练的风格对齐。
result: 在DiT模型上显著提升了跨图像风格一致性。
conclusion: 无需训练的风格对齐方法可扩展到新兴DiT架构。
---

## Abstract
Diffusion-based generative models struggle to maintain high style consistency across generated images via text description.
Although several style-aligned image generation methods have been proposed to address this issue, they exhibit suboptimal performance and are primarily built upon the U-Net architecture, limiting their compatibility with DiT diffusion models like Flux that has emerged as a predominant model in the field of image generation.
To address these limitations, we propose AlignedGen, a novel training-free style-aligned image generation method for DiT models to significantly enhance style consistency across generated images.
Specifically, AlignedGen incorporates two key components to achieve this: Shifted Position Embedding (ShiftPE) and Advanced Attention Sharing (AAS).
ShiftPE alleviates the text controllability degradation observed in prior methods when applied to DiT models through its non-overlapping position indices design, while AAS comprises three specialized techniques to unleash the full potential of DiT for style-aligned generation.
Furthermore, to broaden the applicability of our method, we present an efficient query, key, and value feature extraction algorithm, enabling our method to seamlessly incorporate external images as style references. 
Extensive experimental results validate that our method effectively enhances style consistency across generated images while maintaining favorable text controllability. Code: https://github.com/Jiexuanz/AlignedGen.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：大规模文本到图像扩散模型（如 Flux、DiT）在生成一系列图像时，难以通过文本描述保持跨图像的风格一致性（style consistency）。这种一致性对于书籍插图、虚拟资产设计、图形小说等应用至关重要。
- **现有方法的不足**：
  - 基于微调的方法（如 Textual Inversion、DreamBooth）需要为每种风格收集数据并重新训练，时间和计算成本高。
  - 基于风格编码器的方法（如 IP-Adapter、StyleShot）需要高质量训练数据集，且“风格”定义困难，性能次优。
  - 无训练方法 StyleAligned 基于 U-Net（SDXL），不兼容当前主流的 DiT 架构（如 Flux），直接应用到 DiT 会导致文本控制能力严重下降和内容泄露。
- **整体目标**：提出 AlignedGen，一种针对 DiT 模型的**无训练**（training-free）风格对齐生成方法，在不牺牲文本控制的前提下显著增强跨图像风格一致性，并可无缝集成外部图像作为风格参考。

## 2. 论文提出的方法论

### 核心思想
AlignedGen 通过**注意力共享**（attention sharing）传递风格信息，但发现直接套用 StyleAligned 的机制在 DiT 中失效，根源是**位置嵌入冲突**（Positional Collision）。为此提出两个关键组件：

1. **Shifted Position Embedding (ShiftPE)**——解决位置冲突  
   - 原始 RoPE 为参考图和目标图中相同像素坐标 (i,j) 赋予相同的位置嵌入，导致目标图过度关注参考图中空间对应的区域，造成内容泄露。
   - ShiftPE 将参考图的位置索引在宽度方向偏移（从 (i,j) 变为 (i, j+w)），使两图占据非重叠的坐标空间，从而消除冲突，恢复文本控制能力。

2. **Advanced Attention Sharing (AAS)**——充分释放 DiT 潜力，包含三项技术：
   - **Selective Shared Attention (SSA)**：仅共享图像 token 的 Key 和 Value，不共享文本 token，避免目标图的文本控制被干扰，同时降低计算开销。
   - **Controllable Style Consistency via Key Scaling**：引入缩放因子 λ 对参考图的 Key 进行缩放，λ 越大风格一致性越强（需权衡文本对齐）。
   - **Layer-Selective Application**：仅在 Flux 的 Single Blocks（第 19~57 层）应用注意力共享，Double Blocks 保持不变，以平衡自然度与风格一致性。

### 算法流程（文字说明）
1. 给定一组文本提示（均含相同风格描述），随机选一个作为参考图（reference），其余为目标图（target）。
2. 对于每步去噪（共 T 步）：
   - 对参考图噪声潜变量与目标图潜变量分别计算 Q/K/V。
   - 应用 ShiftPE：将参考图位置索引偏移，使两图位置空间不重叠。
   - 应用 AAS：
     - 使用 SSA：仅对图像 token 的 Q 做 AdaIN 对齐（参考图→目标图），K、V 分别拼接参考图与目标图（仅图像部分）。
     - 作用 λ 缩放参考图的 Key（控制风格强度）。
     - 仅在指定层（Single Blocks）替换原 MM-Attention 为修改后的注意力。
3. 生成目标图，其风格自动接近参考图。
4. **外部图像风格参考**：对用户提供的参考图，通过前向扩散过程（添加噪声→输入模型）缓存其每步的 Q/K/V，然后注入目标图生成过程。

## 3. 实验设计

- **评测数据集**：来自 StyleAligned 的 100 个 prompt 集合，涵盖多种生成目标和风格描述。
- **评估指标**：
  - `Stext`：图文对齐（CLIP 余弦相似度）
  - `Ssty`：风格一致性（CLIP 嵌入的成对平均相似度）
  - `Sdino`：风格一致性（DINO 嵌入的成对平均相似度，更擅长区分风格）
- **对比方法**：
  - StyleAligned（基于 U-Net 的无训练方法）
  - IP-Adapter（基于 Flux 的适配器版本）
  - B-LoRA（基于单图像微调的 LoRA）
  - StyleShot（数据集驱动）
  - CSGO（内容-风格组合）
  - 另与零样本编辑方法 RF-Solver、RF-Edit 进行对比（附录 B）
- **实验组别**：
  - **定量比较**：Table 1，在 100 个 prompt 上计算平均指标。
  - **定性比较**：Figure 7，展示多组生成样例。
  - **用户研究**：40 名参与者对方法进行排名（结果 Table 2）。
  - **消融研究**：Table 3 及 Figure 8-9：
    - 验证 ShiftPE 的必要性（w/ RoPE vs w/ ShiftPE）
    - 验证 SSA 的有效性（w/o SSA）
    - 验证分层选择：不同 block 组（0-19、19-38、38-57）
    - 验证缩放因子 λ（0.9~1.15）
  - **泛化性**：在 SD3、SD3.5 等 DiT 模型上测试（Figure 10）。
  - **兼容性**：与 DreamBooth（主体保持）、Depth-Control 等工具组合（Figure 11、14、15）。

## 4. 资源与算力

文中仅提及具体实现细节：
- 基于 Flux.1-dev 模型（DiT 架构），使用 30 步采样，CFG=3.5。
- **未明确说明**使用的 GPU 型号、数量、总训练/推理时长（该方法为无训练，仅涉及前向推理，不涉及训练过程；外部图像特征提取也仅需一次前向传播）。因此无法给出具体算力参数。

## 5. 实验数量与充分性

- 实验数量较为充足：包括定量、定性、用户研究、多角度消融（位置编码、共享策略、层选择、缩放因子）、跨模型泛化、工具组合。
- 充分性**较高**：
  - 消融实验覆盖了核心设计选择（ShiftPE、SSA、层、λ），提供了定量和可视化证据。
  - 对比方法涵盖主流风格对齐方法（包括训练型、无训练型、编辑型）。
  - 评价指标使用了 CLIP 和 DINO，后者更适合风格判别。
- 客观性：用户研究共 40 人，排名结果清晰（AlignedGen 平均排名 1.20，显著领先）。代码已开源，可复现。
- 潜在不足：测试集仅 100 个 prompt，风格多样性可能有限；未报告方差或置信区间；未比较在 U-Net 上的表现（仅聚焦 DiT）。

## 6. 论文的主要结论与发现

1. **首次提出针对 DiT 的无训练风格对齐方法** AlignedGen，无需微调或额外模块。
2. **发现位置嵌入冲突是注意力共享在 DiT 中失败的根本原因**，并设计 ShiftPE 有效解决，恢复文本控制。
3. **AAS 三项技术**（SSA、λ 缩放、分层应用）在 DiT 上显著提升风格一致性和生成质量。
4. 通过前向扩散过程缓存 QKV，可支持任意外部图像作为风格参考，扩展实际应用。
5. 在定量、定性、用户研究上全面超越现有方法，且可无缝兼容其他生成控制技术（如 DreamBooth、Depth-Control），并泛化到 SD3、SD3.5。

## 7. 优点

1. **无训练、即插即用**：无需收集风格数据或微调模型，直接应用于 DiT 预训练模型（如 Flux），实用性高。
2. **创新性好**：首次深入分析 DiT 中注意力共享失效的机制，并提出简洁优雅的 ShiftPE 解决方案，为后续研究提供洞见。
3. **设计全面**：AAS 中的选择性共享、可控缩放、分层选择均针对 DiT 架构特性设计，非简单套用。
4. **扩展性强**：支持外部图像作为风格参考，兼容多种下游工具（个性化、深度控制），可泛化至其他 DiT 模型。
5. **实验充分**：包含多维度对比、消融、用户研究及泛化验证，结果可靠。

## 8. 不足与局限

1. **计算开销未量化**：虽然无训练，但每步注意力需要拼接两图的 K/V，序列长度加倍，可能增加推理时间，文中未分析或比较。
2. **评估数据集局限**：仅使用 StyleAligned 提供的 100 个 prompt，涵盖的风格和内容有限，可能未能充分验证在复杂或极端风格（如抽象艺术、混合风格）上的表现。
3. **未报告统计误差**：定量结果未给出多次运行的方差或置信区间，难以判断显著性。
4. **未讨论失败案例**：文中未展示方法失效或效果较差的例子，可能隐藏了某些边界情况（如强透视、大尺度变化）。
5. **安全性讨论不足**：虽然提到潜在的负面社会影响，但未对生成不当内容（如侵权风格、伪造）做具体防护或讨论。
6. **对参考图质量依赖**：当外部参考图存在噪声、低分辨率或包含混乱内容时，特征提取可能引入干扰，文中未探讨。

（完）
