---
title: "FlowDrag: 3D-aware Drag-based Image Editing with Mesh-guided Deformation Vector Flow Fields"
title_zh: FlowDrag：基于网格引导变形向量流场的3D感知拖拽图像编辑
authors: "Gwanhyeong Koo, Sunjae Yoon, Younghwan Lee, Ji Woo Hong, Chang D. Yoo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=sDK6bSmHgM"
tags: ["query:real-ir"]
score: 9.0
evidence: 引入基于3D网格和UNet去噪的拖拽式图像编辑方法
tldr: 针对现有拖拽编辑方法忽略整体几何导致不一致的问题，提出FlowDrag，从图像构建3D网格并用能量函数引导网格变形，将位移投影到2D并融入UNet去噪过程。实现精确的拖拽点对齐同时保持结构完整性，提升了拖拽式图像编辑的几何一致性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 822, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1744, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1670, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 995, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 761, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 843, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 851, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 867, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1564, \"height\": 2178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1553, \"height\": 1545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1687, \"height\": 1030, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sdk6bsmhgm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1759, \"height\": 1172, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sdk6bsmhgm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 820, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdk6bsmhgm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdk6bsmhgm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 786, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sdk6bsmhgm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 606, \"height\": 319, \"label\": \"Table\"}]"
motivation: 现有方法只关注点匹配，忽视几何结构，导致编辑不一致。
method: 构建图像3D网格，基于拖拽点变形，投影2D位移并嵌入UNet去噪。
result: 实现精确点对齐与结构保持，减少伪影。
conclusion: FlowDrag通过几何先验提升了拖拽编辑的准确性和一致性。
---

## Abstract
Drag-based editing allows precise object manipulation through point-based control, offering user convenience. However, current methods often suffer from a geometric inconsistency problem by focusing exclusively on matching user-defined points, neglecting the broader geometry and leading to artifacts or unstable edits. We propose FlowDrag, which leverages geometric information for more accurate and coherent transformations. Our approach constructs a 3D mesh from the image, using an energy function to guide mesh deformation based on user-defined drag points. The resulting mesh displacements are projected into 2D and incorporated into a UNet denoising process, enabling precise handle-to-target point alignment while preserving structural integrity. Additionally, existing drag-editing benchmarks provide no ground truth, making it difficult to assess how accurately the edits match the intended transformations. To address this, we present VFD (VidFrameDrag) benchmark dataset, which provides ground-truth frames using consecutive shots in a video dataset. FlowDrag outperforms existing drag-based editing methods on both VFD Bench and DragBench.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
拖拽式图像编辑允许用户通过“拖拽点”精细操控对象，但现有方法往往**只关注局部点匹配，忽略了图像整体几何结构**，导致编辑后出现几何变形、伪影或稳定性下降等问题。为解决这一几何不一致，本论文提出 **FlowDrag**，利用 **3D 网格变形**为2D拖拽编辑提供全局几何约束，提升变换的准确性与连贯性。同时，由于已有基准缺乏真值图像，难以评估编辑准确性，作者构建了**VFD-Bench**数据集，以视频连续帧提供真值编辑结果。

## 2. 论文提出的方法论
- **核心思想**：从单张图像重建3D网格，基于用户拖拽点对网格进行“尽可能刚性”变形，将3D位移投影为2D向量流场，并注入基于UNet扩散模型的拖拽编辑流程。
- **关键技术细节**：
  - **3D网格生成**：采用深度估计（Marigold）或扩散模型（Hunyuan3D 2.0）生成前景网格（DepthMesh/DiffMesh）。
  - **渐进式网格变形**：将2D拖拽点映射为网格上的约束点（handle vertex→target vertex），采用**SR-ARAP能量函数**优化，并引入**渐进式变形策略**：分K步逐次移动手柄点，同时增加**步间平滑正则项**（Inter-Step Smoothness，参数β）防止大位移突变。
  - **2D向量流场生成**：变形前后网格顶点投影到2D，计算每顶点位移向量，组成密集流场Φ。
  - **向量流场采样与编辑引导**：从流场中通过**量级优先采样**选取若干代表性向量，替换原拖拽编辑中的运动监督损失（Lms）中的点优化目标。此外，将变形后网格投影**π(M̂)** 经DDIM反演后，作为**布局特征注入**到去噪早期阶段，提供结构上下文。
- **公式/算法流程**：整体分为三个步骤（如图3、4）：
  1. 生成3D网格。
  2. 映射拖拽点→执行渐进SR-ARAP变形→生成2D向量流场。
  3. 将流场向量用于运动监督和点追踪，同时注入投影网格布局特征，最终得到编辑图像。

## 3. 实验设计
- **数据集/场景**：
  - **DragBench**：包含205张图像及349对拖拽点，用于评估无真值情况下的保真度（1‑LPIPS）与拖拽距离（MD）。
  - **VFD-Bench**（自建）：从DAVIS、LOVEU‑TGVE、TVR及版权免费Pexels视频中选取250对连续帧（动物、人体、物体），提供真值图像，使用PSNR、1‑LPIPS、MD在编辑区域内评估。
- **对比方法**：DiffEditor、DragDiffusion、DragNoise、FreeDrag、GoodDrag等基于运动或梯度引导的拖拽编辑方法。
- **评价指标**：Image Fidelity (1‑LPIPS)、Mean Distance (MD，基于DIFT特征)、PSNR；并在用户研究中评估拖拽准确性与图像质量。

## 4. 资源与算力
- **本文未明确说明使用何种GPU型号、数量及训练/推理时长**。仅提及基于Stable Diffusion 1.5，图像分辨率512×512，LoRA微调200步，DDIM反演至步数38，推理过程包括网格变形（约5秒/样本）和扩散编辑。

## 5. 实验数量与充分性
- **定量实验**：在DragBench和VFD-Bench两个数据集上进行对比，涵盖5种主流方法，证明FlowDrag在MD上最优、VFD‑Bench上全面领先。
- **消融实验**：
  - 渐进SR‑ARAP中正则项β的取值（0.2~1.0），引入网格刚性指标（MELR、mARAP Error），得出β=0.8最优。
  - 采样向量数量对PSNR/1‑LPIPS的影响（最优约10个向量）。
  - 流场采样策略（均匀采样子vs.量级优先采样），证明量级优先更优。
- **用户研究**：25名志愿者对50张图像打分，与三个方法对比。
- **敏感性分析**：深度网格简化比和扩散网格采样步数的鲁棒性测试。
- 实验覆盖多维度，对比公平，消融和敏感性分析较为充分，额外自建基准增强了评估客观性。

## 6. 主要结论与发现
- FlowDrag通过引入3D网格变形和2D向量流场，明显缓解了拖拽编辑中的几何不一致问题。
- 在具备真值对比的VFD‑Bench上，FlowDrag的PSNR、1‑LPIPS和MD均优于现有方法，证明其能更好地保持结构完整性。
- 在DragBench上，FlowDrag的拖拽对齐精度（MD）最优，尽管1‑LPIPS略低于改动极少的DiffEditor。
- 用户研究也表明FlowDrag在准确性和图像质量上更受认可。

## 7. 优点
- **引入几何先验**：用3D网格变形提供全局结构指导，而非仅依赖2D特征匹配，显著提升刚性编辑（如旋转、位移）的稳定性。
- **渐进式变形与步间平滑**：防止大位移变形失真，保持网格质量。
- **双分支机制**：向量流场优化潜在表征 + 布局特征注入，实现几何一致性。
- **新基准VFD-Bench**：首次为拖拽编辑提供真值图像，可更客观评估编辑准确性。
- **实验设计全面**：对比多种方法、消融与敏感性分析、用户研究，验证贡献。

## 8. 不足与局限
- **依赖网格稳定性**：过度简化网格或低质量扩散网格会导致编辑失败，拖拽距离受限，仅适合适度刚性编辑。
- **编辑类型单一**：主要支持刚性编辑（旋转、位移、姿态变化），难以处理内容生成、删除或大幅度非刚性改变（如比例缩放可能断裂）。
- **3D信息损失**：投影到2D后丢失深度维度细节，且底层Stable Diffusion本身缺乏3D理解，无法完全保持原物体的3D几何。
- **计算开销**：需额外进行3D重建和网格变形，增加了预处理时间（约5秒/样本），实时性受限。
- **泛化风险**：VFD-Bench来源虽多样但规模有限（250对），动物类别占比较大，可能影响在其他场景下的性能评估公平性。
- **真值标注主观性**：手动定义拖拽点，可能引入一定偏差。
- **未提供算力详情**：未说明GPU资源，可复现性和效率评估受限。

（完）
