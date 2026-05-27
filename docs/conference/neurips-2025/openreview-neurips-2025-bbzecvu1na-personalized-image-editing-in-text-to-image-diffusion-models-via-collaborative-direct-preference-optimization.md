---
title: Personalized Image Editing in Text-to-Image Diffusion Models via Collaborative Direct Preference Optimization
title_zh: 通过协作直接偏好优化实现文本到图像扩散模型的个性化图像编辑
authors: "Connor Dunlop, Matthew Zheng, Kavana Venkatesh, Pinar Yanardag"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BBZEcVu1nA"
tags: ["query:real-ir"]
score: 9.0
evidence: 通过偏好优化实现扩散模型的个性化图像编辑
tldr: 现有文本到图像扩散模型在编辑时缺乏个性化和美学偏好适应性。本文提出协作直接偏好优化（C-DPO）框架，通过动态偏好图编码用户并利用轻量图神经网络学习嵌入，实现用户间信息共享，从而在扩散模型中完成个性化图像编辑。实验表明该方法能有效对齐用户偏好并提升编辑质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1174, \"height\": 1165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 986, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1013, \"height\": 1271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1038, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1027, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 972, \"height\": 1457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bbzecvu1na/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 985, \"height\": 872, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 505, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1030, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1265, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1309, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 923, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1127, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 472, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1123, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1109, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 941, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 941, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bbzecvu1na/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1213, \"height\": 1972, \"label\": \"Table\"}]"
motivation: 现有扩散模型无法适应用户的个性化美学偏好，本文旨在解决图像编辑中的个性化问题。
method: 提出C-DPO方法，将用户编码为动态偏好图中的节点，使用图神经网络学习嵌入，结合协作信号优化编辑。
result: 该方法在个性化图像编辑任务上取得了优于当前方法的性能，能够有效对齐用户偏好。
conclusion: C-DPO为个性化图像编辑提供了有效框架，通过协作学习提升编辑质量。
---

## Abstract
Text-to-image (T2I) diffusion models have made remarkable strides in generating and editing high-fidelity images from text. Yet, these models remain fundamentally generic, failing to adapt to the nuanced aesthetic preferences of individual users. In this work, we present the first framework for personalized image editing in diffusion models, introducing Collaborative Direct Preference Optimization (C-DPO), a novel  method that aligns image edits with user-specific preferences while leveraging collaborative signals from like-minded individuals. Our approach encodes each user as a node in a dynamic preference graph and learns  embeddings via a lightweight graph neural network, enabling information sharing across users with overlapping visual tastes. We enhance a diffusion model's editing capabilities by integrating these personalized embeddings into a novel DPO objective, which jointly optimizes for individual alignment and neighborhood coherence.  Comprehensive experiments, including user studies and quantitative benchmarks, demonstrate that our method consistently outperforms baselines in generating edits that are aligned with user preferences.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的文本到图像（T2I）扩散模型在生成和编辑高保真图像方面取得了显著进展，但这些模型本质上是通用的，无法适应个体用户的细微美学偏好。当前图像编辑方法采用“一刀切”的策略，不区分用户个人风格，导致用户需要反复纠正或微调输出，限制了AI编辑器在真实创意工作流中的实用性。
- **研究动机**：作者首次提出个性化图像编辑的问题设定，即编辑模型需要针对每个用户的偏好进行定制，学习用户喜欢的风格（如色彩、纹理、主题等），并利用用户社区中的协作信号来增强个性化效果——因为具有相似品味的用户之间可以相互借鉴。
- **整体含义**：该论文旨在通过引入协作直接偏好优化（C-DPO）框架，将用户偏好编码为图中的节点，利用图神经网络传递相似用户的信息，从而在保持个体对齐的同时，通过邻居偏好增强泛化能力，实现真正个性化的图像编辑。

## 2. 论文提出的方法论

### 核心思想
- 提出**协作直接偏好优化（C-DPO）** 框架，将每个用户表示为一个可学习的嵌入向量，并构建用户-偏好二分图，利用图神经网络（GNN）聚合邻居信息，得到上下文相关的用户嵌入。
- 将这些嵌入作为软提示（soft prompt）注入语言模型，使用扩展的DPO损失联合优化个体偏好和邻居一致性。

### 关键技术细节
1. **图构建**：定义二分图 \( G = (U, P, E) \)，其中 \( U \) 为用户节点（可学习嵌入），\( P \) 为偏好属性节点（如颜色、纹理，以预训练语言模型的稠密文本嵌入初始化），\( E \) 为用户与偏好之间的边（喜欢/不喜欢）。
2. **图神经网络编码**：使用2层GraphSAGE编码器（平均聚合），后接2层线性层作为解码器。预训练阶段在辅助边分类任务上预测用户-属性边的正负性，以学习有意义的用户嵌入。
3. **相似度度量**：用户 \( u \) 和 \( v \) 的相似度 \( w_{uv} \) 定义为共享邻居（共同偏好属性）数量的归一化值。
4. **C-DPO损失函数**：
   \[
   L_{\text{C-DPO}} = L_{\text{DPO}}(u) + \lambda \sum_{v \in N(u)} \frac{w_{uv}}{\sum_{v} w_{uv}} L_{\text{DPO}}(v)
   \]
   - 第一项为个体DPO损失（条件于用户 \( u \)），第二项为协作正则项，利用邻居 \( N(u) \) 的加权DPO损失。
   - 参考模型 \( \pi_{\text{ref}} \) 保持用户无关，避免退化为全局平均政策。
5. **用户条件注入**：GNN输出的用户嵌入 \( h_u \) 通过两层MLP转换为固定数量的软提示标记（soft tokens），拼接到文本指令前，实现用户条件化而不修改基础模型架构。
6. **两阶段训练**：
   - 第一阶段：在InstructPix2Pix数据集上进行监督微调（SFT），训练LoRA适配器作为参考模型 \( \pi_{\text{ref}} \)。
   - 第二阶段：复制同一LoRA适配器作为策略模型 \( \pi_{\theta} \)，使用C-DPO损失在合成用户偏好数据集上进行协作偏好优化。
7. **图像编辑后端**：使用FLUX.1-dev + ControlNet（Canny条件）将个性化编辑提示转换为像素级编辑。

## 3. 实验设计

### 数据集
- **合成用户偏好数据集**：生成3,000个合成用户配置文件（含年龄、地理、社会经济地位等维度），每个用户分配4张COCO类别图像，生成48个标注的编辑指令（喜欢的/不喜欢的），总计144K样本。
- 划分：2,900个用户用于训练，100个用户用于测试。

### 基准与对比方法
- **通用VLM基线**：Qwen-VL、LLaVA（无用户身份感知）。
- **编辑感知但无用户条件**：Qwen (SFT)（在InstructPix2Pix上微调）、Vanilla DPO（在偏好数据上训练，无用户ID）。
- **用户条件但无协作**：DPO-User（使用可学习用户嵌入，类似PPD目标）。
- **本文方法**：Collaborative DPO（在DPO-User基础上加入图协作）。

### 评估指标
- **提示级别对齐**：CLIP文本相似度（生成指令 vs. 用户真实喜欢指令），在三种信息条件下（Like+Dislike、Likes-only、Dislikes-only）。
- **图像级别对齐**：DINO、CLIP-I、CLIP-T、HPS等，比较原始图像与编辑后图像的相似度，以及编辑后图像与原始文本描述的对齐度。
- **用户研究**：50名参与者评判三种方法（Vanilla DPO、DPO-User、Ours）的编辑结果，询问一般偏好和视觉吸引力。另有10名真实用户参与个性化偏好研究。

### 消融实验
- 协作尺度参数 \( \lambda \)（0.01, 0.15, 0.50）
- 邻域大小 \( K \)（2, 3, 5, 12）
- 不同编辑后端（SDEdit, Ledits++, InstructPix2Pix, TurboEdit, Flux ControlNet, RF Inversion）
- 提示工程基线（直接文本描述用户与邻居偏好，不使用GNN）

## 4. 资源与算力

- **训练**：单个NVIDIA L40 (48GB) GPU即可运行完整流程，但使用多GPU加速。
  - 第一阶段SFT：2块L40 GPU，约3小时，1个epoch。
  - 第二阶段C-DPO：3块L40 GPU，约1小时，3000步。
- **推理**：生成一个个性化编辑约需1分钟（使用TurboEdit后端可加速至1秒）。

## 5. 实验数量与充分性

- **定量实验**：报告了多个表格（表2-表9），覆盖提示级别（三种信息条件）、图像级别（多种指标）、以及与人提示工程基线、SOTA编辑模型（BAGEL、SEED-LLAMA、Nexus-Gen）的对比。
- **消融实验**：对协作参数、邻域大小、编辑方法、提示工程基线分别进行实验，验证了各组件的重要性。
- **用户研究**：两项用户研究（50名合成用户 + 10名真实用户），通过主观评价和偏好比率验证方法优势。
- **充分性与公平性**：实验覆盖了多种条件、多种基线、多种指标；标准化了所有方法的输入格式（统一提示模板）；消融实验系统。总体实验设计充分、客观、公平。

## 6. 论文的主要结论与发现

- C-DPO在所有评估配置（Like+Dislike、Likes-only、Dislikes-only）下均取得最高的CLIP文本相似度，证明其从部分偏好信号中恢复用户意图的能力最强。
- 在图像级别（DINO、CLIP、HPS等）也优于所有基线，表明生成的编辑图像在保留原始内容的同时更好地对齐用户偏好。
- 用户研究中，C-DPO的编辑结果获得最高偏好率和视觉吸引力评分。
- 协作信号通过图正则化显著提升了数据稀疏用户的个性化效果，同时避免了退化为全局平均。

## 7. 优点

- **首次提出个性化图像编辑问题**：定义了新问题设定，超越了现有的“一刀切”范式。
- **创新的C-DPO损失**：将图结构正则化引入DPO，同时建模个体和邻居偏好，实现协作学习。
- **模型无关的编辑后端**：框架可适配不同T2I编辑模型（如FLUX、Stable Diffusion变体），具有灵活性。
- **合成数据集贡献**：发布包含144K样本的用户编辑偏好基准，方便后续研究。
- **丰富的实验验证**：包括定量指标、消融、用户研究，验证了方法的有效性和泛化能力。

## 8. 不足与局限

- **冷启动问题**：当新用户缺乏个人编辑历史和图中紧密邻居时，系统退化为通用编辑。
- **依赖预训练模型**：编辑后端（Flux、ControlNet）可能继承其偏差，影响输出。
- **合成数据局限**：当前数据集为合成生成，虽可扩展但无法完全捕捉真实用户偏好的多样性和细微差别。
- **强化审美“过滤气泡”风险**：系统迎合用户已有品味，可能限制用户接触不同视觉风格。
- **缺乏视频和多目标一致性扩展**：论文指出未来可探索视频领域，但当前未涉及。
- **未提及隐私与公平性设计**：图形化用户偏好数据可能涉及隐私，文中未详细讨论防护措施。

（完）
