---
title: "Balancing Preservation and Modification: A Region and Semantic Aware Metric for Instruction-Based Image Editing"
title_zh: 平衡保留与修改：面向指令式图像编辑的区域与语义感知评估指标
authors: "Zhuoying Li, Zhu Xu, Yuxin Peng, Yang Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Nrs6csi52N"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出用于指令式图像编辑评估的BPM指标
tldr: 针对现有指令式图像编辑缺乏全面评估指标的不足，本文提出BPM指标，通过显式解耦区域保留与指令修改评估，在保持无关区域不变和忠实执行指令之间取得平衡。实验表明该指标更符合人类判断，BPM有效克服了现有指标偏向，为编辑质量评估提供了新标准和可靠的自动评估手段。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1646, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 839, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 767, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1671, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1483, \"height\": 1127, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1745, \"height\": 1140, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1663, \"height\": 1540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 319, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 322, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 320, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 320, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 323, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 329, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1750, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 324, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 328, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 325, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 328, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nrs6csi52n/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1651, \"height\": 1864, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1735, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1730, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 79, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 522, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 602, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 109, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 604, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1669, \"height\": 1039, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1763, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1334, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1724, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 731, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 698, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1732, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 635, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1750, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nrs6csi52n/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1750, \"height\": 459, \"label\": \"Table\"}]"
motivation: 现有评估指标无法全面衡量编辑的修改准确性与区域保留。
method: 提出BPM指标，显式解耦评估修改与保留。
result: 指标与人类判断高度一致。
conclusion: 提供了更可靠的指令式编辑评估方法。
---

## Abstract
Instruction-based image editing, which aims to modify the image faithfully towards instruction while preserving irrelevant content unchanged, has made advanced progresses. However, there still lacks a comprehensive metric for assessing the editing quality. Existing metrics either require high costs concerning human evaluation, which hinders large-scale evaluation, or adapt from other tasks and lose specified concerns, failing to comprehensively evaluate the modification of instruction and the preservation of irrelevant regions, resulting in biased evaluation. To tackle it, we introduce a new metric Balancing Preservation Modification (BPM), that tailored for instruction-based image editing by explicitly disentangling the image into editing-relevant and irrelevant regions for specific consideration. We first identify and locate editing-relevant regions, followed by a two-tier process to assess editing quality: Region-Aware Judge evaluates whether the position and size of the edited region align with instruction, and Semantic-Aware Judge further assesses the instruction content compliance within editing-relevant regions as well as content preservation within irrelevant regions, yielding comprehensive and interpretable quality assessment. Moreover, the editing-relevant region localization in BPM can be integrated into image editing approaches to improve the editing quality, manifesting its wild application. We verify the effectiveness of BPM metric on comprehensive instruction-editing data, and the re- sults show that we yield the highest alignment with human evaluation compared to existing metrics, indicating efficacy. The code is available at https://joyli-x.github.io/BPM/.

---

## 论文详细总结（自动生成）

# 论文总结：平衡保留与修改——面向指令式图像编辑的区域与语义感知评估指标

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：指令式图像编辑任务要求根据文本指令修改图像，同时保留与指令无关的区域。该领域虽已取得显著进展，但缺乏全面、可靠的自动化评估指标。
- **现有指标缺陷**：
  - 人力评估成本过高，难以规模化。
  - 现有的自动指标（如 LPIPS、CLIPScore、DINOScore 等）多从图像生成任务迁移而来，无法同时利用“原图—编辑图—指令”三个要素，导致评估偏颇。
  - 这些指标将图像视为整体进行评估，忽略了“需修改区域”和“需保留区域”的不同要求，导致常与人类判断相悖（如过度偏好全图噪声或全图生成结果）。
- **研究动机**：亟需一个能够分离区域、兼顾修改准确性和保留完整性的专用评估指标，以提供更可信赖、可解释的评价结果。

## 2. 论文提出的方法论

### 核心思想
- 提出 **BPM（Balancing Preservation Modification）** 指标，显式将图像分解为“编辑相关区域”和“编辑无关区域”，分别评估修改的指令一致性和保留的内容保真度。

### 关键技术细节与流程
1. **指令解析与编辑区域定位**：
   - 使用大语言模型（LLM，如 Gemma-2-9b）解析指令，提取源对象 *o1*、目标对象 *o2*、尺寸变化要求 *size_st* 和位置变化要求 *pos_st*。
   - 利用检测和分割模型（Grounding DINO + Grounded SAM）分别在原图和编辑图中定位 *o1* 和 *o2*，得到边界框 *Borigin/Bedit* 和掩码 *Morigin/Medit*。
2. **区域感知评判（Region-Aware Judge）**：
   - **位置对齐**：检查编辑对象中心坐标是否符合指令（左/右/上/下/不变），并引入显著性检查（IOU 阈值）确保编辑有效。
   - **尺寸对齐**：比较区域面积变化是否符合指令（变大/变小/不变），通过面积比率阈值判断显著性。
   - 两项得分均为 0 或 1，合成区域得分 *Sregion*。
3. **语义感知评判（Semantic-Aware Judge）**：
   - **指令一致性**：裁剪编辑区域，计算 CLIP 方向相似度（公式：*Smodify = cos(CLIP_I(Amedit) - CLIP_I(Amorigin), CLIP_T(o2) - CLIP_T(o1))*），以此衡量修改是否与指令对齐且保留无关属性。
   - **内容保留**：使用掩码并集排除编辑区域，计算剩余部分的 L2 距离，得到保留得分 *Spreserve = 1 - L2(Aporigin, Apedit)*。
   - *Ssemantic* = 归一化后的 *Smodify + Spreserve*。
4. **BPM 总分**：
   - *BPM = α · Ssemantic + (1-α) · Sregion*，其中 *α* 取 0.7。
5. **应用扩展**：
   - 将定位的编辑区域掩码 *Mall* 集成到图像编辑模型的分类器自由引导过程中，通过掩码限制指令引导的范围，减少无关区域修改，提升编辑质量。

## 3. 实验设计

### 数据集与场景
- **局部编辑**：从 MagicBrush 数据集中采样，涵盖添加、替换、动作变化、颜色变化、移除、图案变化等 6 种典型指令类型。
- **全局编辑**：从 PIE-Bench 数据集的全局编辑子集中采样。
- 共收集 **960 条带人工评分的**样本。

### Benchmark 与对比方法
- **对比指标类别**：
  - **保留类指标**：L2 distance、LPIPS、CLIP-I、DINOScore。
  - **修改类指标**：CLIPScore。
  - **平衡类指标**：CLIPScore + CLIP-I 组合。
  - **VLM 类指标**：GPT-4o（使用 HQ-Edit 的评估提示）。
- **编辑模型**：IP2P、MGIE、DALLE-2、FT IP2P、HQ-Edit（仅全局编辑）、PIE-Bench 自身基线。

### 评估方式
- **人类对齐测试**：比较成对模型编辑结果的人工排名与指标排名一致性，以“对齐率”衡量。
- **真值测试**：构建三元组（过度保留图、过度修改图、真实良好编辑图），统计各指标偏好正确结果的比例。
- 所有对比均在两种编辑类型（局部/全局）上分别进行。

## 4. 资源与算力

- 论文未明确给出训练所需的 GPU 型号、数量或训练时长，因为 BPM 是一个**无需训练**的评估指标，仅需推理。
- 推理阶段使用 Gemma-2-9b-it-SimPO 进行指令解析，并调用 Grounding DINO + SAM 和 CLIP 模型。推理速度实验显示 **BPM 平均每张图 1.5 秒**，远快于 GPT-4o 的 11.4 秒，具有较好的实用性。

## 5. 实验数量与充分性

- 进行了多组实验，覆盖**局部编辑**和**全局编辑**两个数据集，**6 种编辑模型**之间的成对比较，共 **6 对人机对齐测试**（见表1、2）。
- **真值测试**对比了所有基线指标对不同类型图像的偏好分布。
- **消融实验**验证了：
  - *Smodify* 和 *Spreserve* 分别优于单纯 CLIPScore 和 L2 distance。
  - *Sposition* 和 *Ssize* 与人工判断的对齐度（在每个模型上均 > 0.69）。
  - 方向相似度相较于普通 CLIPScore 的增益。
  - 不同 α 权重的影响（α = 0.7 最优）。
  - 不同 LLM（Gemma、GPT-4o、Gemini、Deepseek-v3）的解析准确率均高于 97%，表明模块稳定。
- **编辑增强实验**：在 IP2P、FT IP2P、MGIE 上添加掩码引导，验证了保留和修改性能的提升以及用户偏好测试（91% 样本更好或持平）。
- **推理速度和掩码质量**也进行了测试。整体实验设计全面且对比公平。

## 6. 论文的主要结论与发现

- BPM 在局部和全局编辑场景下，与人类评价的对齐度均显著优于现有所有自动指标，甚至优于 GPT-4o，同时推理速度更快。
- 显式分离编辑相关/无关区域是避免评估偏差的关键，BPM 能准确识别真实良好编辑，而非偏好过度保留或过度修改的图像。
- BPM 的编辑区域定位可以无缝嵌入现有编辑方法，作为一种无训练的增强策略，有效减少无关区域修改，提升编辑质量。
- 方向相似度（CLIP 空间变化）比简单的图文对齐更能反映编辑忠实度，因为它隐式检查了无关属性的保持。

## 7. 优点

- **问题针对性强**：首次针对指令式图像编辑任务设计专门的解耦评估框架，同时考虑修改和保留，并且区分不同区域的不同要求。
- **方法论完整且可解释**：从指令解析、区域定位到分层评价（区域尺寸/位置 + 语义内容），每一步有明确的设计逻辑，最终得分组成清晰可拆解。
- **与人类判断高度一致**：在全面的成对比较实验中证明了其可靠性，远超传统单一指标。
- **扩展性好**：编辑区域定位模块可即插即用，直接提升多种编辑模型的效果，无需额外训练。
- **实用性高**：推理速度快，且不依赖昂贵的 VLM 做端到端判断，成本可控。
- **实验扎实**：覆盖两个数据集、多种编辑模型、多维度消融、真值测试，对比基线广泛。

## 8. 不足与局限

- **对指令解析的依赖**：LLM 有时可能因指令模糊（如代词指代不清）或复杂空间关系（如“among”）而出错，尽管整体准确率很高，但在极端情况下可能引入噪声。
- **区域定位的局限**：当前仅支持单一对象或简单交互的编辑，对于同时涉及多个对象且指令未明确指定源-目标映射的场景，定位可能不够精确。
- **掩码质量依赖底层模型**：检测和分割模型的性能会直接影响评估可靠性，当对象细小、遮挡或为非典型类别时，边缘情况可能失败。
- **只评估局部语义一致性**：对纹理、光照等低级视觉属性的变化缺乏细粒度的评价，完全依赖 CLIP 空间的方向相似度，可能无法捕捉所有感知差异。
- **评估范围固定**：虽已覆盖局部和全局编辑，但未在更复杂场景（如视频编辑、3D 编辑）上验证。
- **增强应用的限制**：掩码引导编辑提升时，需进行两次推理（初次编辑生成用于获取掩码，二次编辑应用引导），增加了计算开销。
- **缺少与最新统一生成模型（如扩散 Transformer 等）的直接对比**，实验中所用的编辑模型多为之前的流行方法。

（完）
