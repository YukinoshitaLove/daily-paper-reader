---
title: "RelationAdapter: Learning and Transferring Visual Relation with Diffusion Transformers"
title_zh: RelationAdapter：基于扩散Transformer的视觉关系学习与迁移
authors: "Yan Gong, Yiren Song, Yicheng Li, Chenglin Li, Yin Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DOb47fj0cl"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于扩散Transformer的少样本图像编辑
tldr: 现有图像编辑方法难以处理非刚性变换，RelationAdapter利用扩散Transformer的上下文学习能力，通过源-目标图像对提取编辑意图并迁移到新图像。构建包含218种编辑任务的数据集Relation252K，实验证明在多种编辑任务上优于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 701, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 689, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 2046, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 2046, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dob47fj0cl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1449, \"height\": 2043, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 629, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 620, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 482, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 468, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 975, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 455, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1019, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dob47fj0cl/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1135, \"height\": 262, \"label\": \"Table\"}]"
motivation: 单参考图像编辑难以处理非刚性变换，且需要大量示例。
method: 提出RelationAdapter轻量模块，附加到扩散Transformer上，从少量示例中学习并迁移视觉变换。
result: 在Relation252K数据集上的多种编辑任务取得领先效果。
conclusion: 该方法为基于扩散Transformer的少样本图像编辑提供了有效方案。
---

## Abstract
Inspired by the in-context learning mechanism of large language models (LLMs), a new paradigm of generalizable visual prompt-based image editing is emerging. Existing single-reference methods typically focus on style or appearance adjustments and struggle with non-rigid transformations. To address these limitations, we propose leveraging source-target image pairs to extract and transfer content-aware editing intent to novel query images. To this end, we introduce RelationAdapter, a lightweight module that enables Diffusion Transformer (DiT) based models to effectively capture and apply visual transformations from minimal examples. We also introduce Relation252K, a comprehensive dataset comprising 218 diverse editing tasks, to evaluate model generalization and adaptability in visual prompt-driven scenarios. Experiments on Relation252K show that RelationAdapter significantly improves the model’s ability to understand and transfer editing intent, leading to notable gains in generation quality and overall editing performance.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有单参考图像编辑方法（如基于风格或外观调整）难以处理非刚性变换（如物体姿态、几何布局等结构变化），且通常需要大量示例或依赖文本指令，而文本指令往往存在歧义性和表达能力不足的问题。
- **研究背景**：受大语言模型（LLM）中上下文学习（in-context learning）机制的启发，利用源-目标图像对（before–after pair）来隐式编码编辑意图，并迁移到新图像上，成为一种更具通用性和数据效率的视觉编辑范式。但现有基于图像对的方法（如Edit Transfer、VisualCloze）存在内存消耗高、文本提示退化等问题。
- **本文目标**：构建一个轻量级、模块化的框架，能够从少量示例中准确提取视觉变换信号（包括语义、结构、风格），并将其高效地应用于新图像，同时具备对未见编辑任务的强泛化能力。

### 2. 方法论：核心思想与关键技术细节
- **整体架构**：
  - **RelationAdapter**：一种基于Diffusion Transformer (DiT) 的轻量级适配器模块，通过在每个DiT块中嵌入新的注意力处理器，捕捉并注入视觉变换特征。
  - **In-Context Editor**：将图像编辑建模为条件生成任务，联合编码源图像与文本描述，通过双向注意力机制实现精确编辑指导。
- **RelationAdapter关键技术**：
  - **视觉编码器**：采用SigLIP-SO400M-Patch14-384（替代CLIP），提取视觉提示特征（源图像Iprm和参考图像Iref），拼接得到视觉表征cV。
  - **解耦注意力注入**：为视觉提示设计独立的键值投影矩阵（W'k, W'v），与骨干网络共享查询Q，计算视觉注意力输出ZV，并通过可调系数α与原始DiT注意力输出ZB融合：Z_new = ZB + α·ZV。避免视觉提示过长削弱文本引导。
- **In-Context Editor关键技术**：
  - **位置编码克隆**：将源条件cS与噪声潜变量z的位置编码对齐，建立一致的像素级坐标映射，减少结构失真。
  - **LoRA微调**：对DiT模块进行高效率的LoRA（rank=128）微调，参数高效地适应大规模编辑数据集。
  - **无噪声条件特征范式**：在整个去噪过程中保持源图像特征cS为干净状态，提供稳定精确的参考。
- **Relation252K数据集**：
  - 包含218种编辑任务（分为低层处理、风格迁移、图像编辑、定制生成四类），共33,274张图像，通过排列生成251,580个训练样本。
  - 使用GPT-4o自动生成图像描述与编辑指令（源描述、目标描述、编辑指令），通过MidJourney和Discord实现半自动化构建。

### 3. 实验设计
- **数据集与场景**：主要使用自建的Relation252K数据集，覆盖218种任务。Benchmark子集包含6,540个样本（2.6%），其中6,240个来自训练见过的任务，300个来自未见任务。
- **对比方法**：
  - Edit Transfer、VisualCloze（两者均为基于图像对的上下文学习方法）。
  - 消融实验对比不加RelationAdapter的上下文学习变体。
  - 额外与MidJourney在未见风格迁移任务上对比（附录B.5）。
- **评估指标**：
  - 客观指标：MSE（像素级误差）、CLIP-I（语义相似度）、FID（整体视觉质量）。
  - 主观指标（基于GPT-4o的自动评测）：Editing Consistency (GPT-C)、Editing Accuracy (GPT-A)。
  - 用户研究：30名志愿者对编辑准确性、一致性、整体偏好进行盲评。
- **实验公平性**：固定随机种子，使用官方实现和默认超参数，确保可重复性。所有数据随机采样，顺序随机化避免偏差。

### 4. 资源与算力
- **训练配置**：4块NVIDIA H20 GPU，训练100,000步，约48小时，显存消耗约74 GB。
- **推理配置**：单块H20 GPU，显存约40 GB，每张1024×1024图像推理时间<9秒（相较上下文方法13秒，提速30.8%）。
- **模型规模**：总可训练参数1,569.76百万（其中LoRA参数占358.6M，rank=128）。

### 5. 实验数量与充分性
- **定量对比**：与Edit Transfer、VisualCloze的全面比较，在MSE、CLIP-I、FID、GPT-C、GPT-A五个指标上系统报告（表1）。
- **消融实验**：
  - 去除RelationAdapter（表2），验证其有效性。
  - 不同注意力融合系数α = 0.5, 1, 2（表9，附录D）。
  - 不同LoRA rank（16 vs 128）（表10，附录E）。
  - 不同视觉编码器选择的讨论（附录D提及SigLIP vs CLIP）。
- **额外对比**：低层感知任务（边缘检测、分割、深度估计、表面法向）与VisualCloze对比（附录B.3，表4-7）。
- **用户研究**：30人，三组对比（与上下文基线、VisualCloze、Edit Transfer），报告百分比偏好。
- **实验充分性**：实验设计全面，覆盖多种任务类型（低层、风格、编辑、定制）、多种评估维度（像素、感知、语义、人类偏好），消融实验验证核心贡献。

### 6. 主要结论与发现
- RelationAdapter在所有定量指标上显著优于Edit Transfer和VisualCloze。例如，MSE从0.043降至0.020，CLIP-I从0.827提升至0.905，FID从4.908降至2.201（表1）。
- 消融实验证明RelationAdapter模块对性能提升起关键作用：去除后MSE上升、CLIP-I下降、FID升高（表2）。
- 在未见任务上，模型仍表现出良好的泛化性，用户偏好中在编辑准确性和一致性上均优于基线。
- 解耦注意力注入相比直接拼接视觉提示更高效，避免了文本引导弱化，同时降低内存和推理时间。

### 7. 优点
- **方法创新性**：首次基于DiT设计轻量级适配器（RelationAdapter）用于提取和迁移视觉关系，通过解耦注意力保持文本引导有效性；位置编码克隆确保空间对齐；无噪声条件特征提高编辑保真度。
- **效率优势**：相比上下文拼接方法，内存节省约3GB，推理速度提升30.8%，训练时间减少6.8%。
- **数据集贡献**：构建大规模多样化编辑数据集Relation252K（218种任务，25万+样本），并由GPT-4o自动化标注，支持未来研究。
- **实验严谨性**：多维度评估（客观+主观+用户），包含消融、超参数分析、低秩配置测试，统计显著性报告（表3给出均值±标准差）。

### 8. 不足与局限
- **文本渲染失败**：在生成图像中渲染文本细节时表现不佳，这是当前扩散模型的普遍问题（论文第6节）。
- **罕见任务敏感性**：对极罕见或前所未见的编辑任务，性能可能略有下降，表明对任务特定细微差异敏感。
- **计算资源要求**：虽然轻量，但训练仍需要4块H20 GPU（74GB显存），推理需40GB，对资源有限者不友好。
- **实验覆盖**：主要依赖于自建数据集，未在标准公开编辑基准（如I2P、PIE等）上验证；对比方法较少（仅两个上下文基线和MidJourney），未与其他框架如InstructPix2Pix、SDEdit等对比（但作者论证了任务范式差异）。
- **用户研究规模**：30人规模较小，且未报告参与者背景多样性。
- **公平性考虑**：未讨论潜在的误用风险（如生成虚假图像），也未提及相应的安全措施。

（完）
