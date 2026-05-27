---
title: "What's Producible May Not Be Reachable: Measuring the Steerability of Generative Models"
title_zh: 可生成的未必可操控：度量生成模型的可控性
authors: "Keyon Vafa, Sarah Bentley, Jon Kleinberg, Sendhil Mullainathan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=A1Zte0ixms"
tags: ["query:real-ir"]
score: 6.0
evidence: 度量生成模型的可控性
tldr: 现有生成模型评估多关注可生成性（产出质量和多样性），忽略了用户能否按特定目标操控模型输出。该文提出可控性的数学分解和评估基准，首次将可控性与可生成性独立量化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 645, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 759, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 684, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 689, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1010, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 699, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 1831, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1460, \"height\": 1649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 1394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1449, \"height\": 1467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 499, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 453, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1072, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 872, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 879, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 327, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 783, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 833, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1zte0ixms/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1016, \"height\": 1328, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 738, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 625, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 824, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1353, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1523, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 796, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 690, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1zte0ixms/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 766, \"height\": 362, \"label\": \"Table\"}]"
motivation: 生成模型的实际价值不仅在于能生成什么，还在于用户能否按目标控制输出。
method: 提出可控性的数学分解方法，并设计基准任务来独立评估。
result: 在多个生成模型上展示了可生成性与可控性的差异。
conclusion: 可控性是生成模型评估中不可或缺的维度。
---

## Abstract
How should we evaluate the quality of generative models? Many existing metrics focus on a model's producibility, i.e. the quality and breadth of outputs it can generate. However, the actual value from using a generative model stems not just from what it can produce but whether a user with a specific goal can produce an output that satisfies that goal. We refer to this property as steerability. In this paper, we first introduce a mathematical decomposition for quantifying steerability independently from producibility. Steerability is more challenging to evaluate than producibility because it requires knowing a user's goals. We address this issue by creating a benchmark task that relies on one key idea: sample an output from a generative model and ask users to reproduce it. We implement this benchmark in user studies of text-to-image and large language models. Despite the ability of these models to produce high-quality outputs, they all perform poorly on steerability. These results suggest that we need to focus on improving the steerability of generative models.  We show such improvements are indeed possible: simple image-based steering mechanisms achieve more than 2x improvement on this benchmark.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **现有评估的不足**：当前生成模型（如 text-to-image、LLM）的评估大多聚焦于 **producibility**（可生成性），即模型能输出的质量、多样性和真实性。  
- **实际使用的挑战**：用户关心的是能否通过交互**精准、高效地引导模型生成自己想要的输出**，这被称为 **steerability**（可控性）。  
- **核心动机**：可生成性不等于可控性——一个模型能产出高质量图像，但用户可能反复尝试也无法复现自己脑海中的目标。  
- **论文目标**：首次提出可控性的独立数学量化，设计基准任务进行实证评估，并探索提升可控性的方法。

---

## 2. 论文提出的方法论

### 核心思想
- 将模型在人类使用下的总表现分解为两个部分：
  - **可生成性差距**：模型可生成集 \(S_m\) 与所有可能实例 \(X\) 之间的最大奖励差。
  - **可控性差距**：在可生成集内，人类实际输出与最优输出之间的奖励差。
- 公式：  
  \[
  r^*_X - r(h(m,r)) = \underbrace{(r^*_X - r^*_{S_m})}_{\text{可生成性差距}} + \underbrace{(r^*_{S_m} - r(h(m,r)))}_{\text{可控性差距}}
  \]

### 关键技术细节
- **基准任务设计**：
  - 从目标模型的可生成集中采样一个实例（图像/文本）作为 **goal instance**；
  - 让人类用户通过标准界面（如文本提示）尝试复现该目标，并允许最多 5 轮迭代；
  - 另请其他人类标注者根据相似度（0–10 评分）或满意度（4 级）等指标评估用户输出与目标的接近程度。
- **奖励函数**采用理想点形式：\( r(x) = -d(x_g, x) \)，其中 \(d\) 为人类感知的距离。
- **多模型比较的分解**（公式 5）：  
  当比较两个模型 \(M_1\) 和 \(M_2\) 的 steerability 差异时，可进一步分解为：
  - **由于操控机制本身的改进**（在相同可生成集下）；
  - **由于可生成集的差异**（即其他模型更容易产生易操控的实例）。

---

## 3. 实验设计

- **数据集/场景**：
  - **text-to-image 模型**：10 种（SD3-large/3.5-large/3.5-medium/3.5-large-turbo、DALL-E 2/3、Flux-dev/1.1-pro-ultra、Ideogram-v2-turbo、Photon-flash）。目标图像从 **PixelProse** 数据集的随机标题生成。另有**抽象几何图案**场景（通过 Claude 3.5 Sonnet 生成提示）。
  - **LLM**：5 种（Gemini-1.5-flash、Gemini-2.0-flash-exp、GPT-4o、Claude-3.5-Sonnet、Llama-3.3-70B-Instruct-Turbo）。目标文本来自 **Kaggle News Category** 数据集，经风格改写后作为目标。

- **Benchmark 流程**：
  - 给用户展示目标（图像/文本），限制 5 次尝试，每次可修改 prompt（禁止直接复制目标内容）。
  - 评价指标：
    - **Satisfaction rate**（4 级）
    - **Image similarity rating**（0–10）
    - **Improvement rate**（第5次是否比第1次更接近目标）
    - **Prompt-Output Misalignment (POM)**（prompt 更准确描述目标还是生成图像）

- **对比方法**：
  - 基本 **text steering**；
  - **专业 prompt 工程师**（Upwork 招募，34 例）；
  - **盲操控**（LLM 随机生成用户第 1 次 prompt 的变体，不依赖目标）；
  - **seed 选择、CFG 调节**等附加实验；
  - **image steering**（基于图像变体 + 随机/RL 建议），使用 **Stable Diffusion 1.4**。

---

## 4. 资源与算力

- **预测模型训练**（用于分解分析）：使用 **单块 A100 GPU**，未明确训练时长。
- **Image steering 实验**：使用 **8 块 H100 GPU** 服务器进行实时图像生成和扰动，文中称“高效”。
- **未提供**详细具体的时间开销或总 GPU 小时数。

---

## 5. 实验数量与充分性

- **主要文本操控实验**：
  - 554 个目标图像，2770 个（目标，生成）对，277 名参与者，共 18550 个人类评分。
- **LLM 实验**：132 名受访者，118 个目标标题，共 2030 个评分。
- **附加实验**：
  - 专业 prompt 工程师对比（34 例）
  - 盲操控（100 个轨迹 × 多种变体数量）
  - 种子控制、CFG 控制、不同约束种子下的可生成性-可控性权衡
  - Image steering 实验（500 名参与者，两个域：PixelProse 和几何图案）
- **充分性评价**：实验规模较大，覆盖多个模型系列、多种人类用户类型（普通/专业）、多种评价维度（人类+自动指标），对比条件丰富，结果统计显著（报告标准误）。**实验设计较为客观、充分**。

---

## 6. 论文的主要结论与发现

1. **所有评估模型的可控性普遍差**：60% 的生成结果被人类评定为不满意（其中 27% “非常不满意” vs. 仅 10% “非常满意”）。
2. **改进率低下**：仅 62% 的情况下第 5 次尝试比第 1 次更接近目标（基线 50%）。
3. **专业 prompt 工程师仅略优**（最终相似度高 10%），且改进率更低。
4. **盲操控可解释人类改进的一半以上**（52% 可与随机变体 LLM 匹配，87% 若给 20 次机会）。
5. **可控性与可生成性存在权衡**：约束种子可提升 steerability 但降低 producibility。
6. **不同模型间的 steerability 差异，约一半来自真正的操控机制改进，另一半来自可生成集差异**。
7. **Image steering（特别是学习建议分布）可在两个域上实现超过 2× 的改进**（相对于 text steering）。

---

## 7. 优点

- **方法创新**：首次将可控性作为独立指标从 producibility 中分离，并提供形式化分解。
- **基准设计巧妙**：通过“复现模型自身产出”来避免 producibility 干扰，同时隐式定义用户目标。
- **大规模人类研究**：涵盖 10+ 模型、数百名用户、多种指标，结果可信度高。
- **分解分析可解释**：能区分改进是来自操控机制还是可生成集，对模型开发有指导意义。
- **实际改进验证**：简单的 image steering 方案即显著提升，说明 steerability 是可行的优化方向。

---

## 8. 不足与局限

- **实验覆盖有限**：仅测试了文本和图像两种操控方式，未覆盖其他（如负提示、inpainting、条件控制等）。
- **Image steering 模型较小**：使用 Stable Diffusion 1.4（860M 参数），结果可能不能直接推广到更大模型。
- **RL 学习策略较基础**：仅学习扰动步长，更多复杂策略（如多模态建议）未探索。
- **未考虑长期学习**：实验仅在单次会话内，未研究用户随时间提升的可能性。
- **潜在偏差**：
  - 人类标注者的主观性（但通过重复和多数投票控制）。
  - 目标图像均来自模型生成，可能无法代表真实用户愿望的全分布。
- **应用限制**：高 steerability 可能被恶意利用（如生成特定有害内容），论文提及需安全对齐。

（完）
