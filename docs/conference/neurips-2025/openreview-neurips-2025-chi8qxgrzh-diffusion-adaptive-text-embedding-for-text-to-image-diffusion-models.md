---
title: Diffusion Adaptive Text Embedding for Text-to-Image Diffusion Models
title_zh: 面向文本到图像扩散模型的扩散自适应文本嵌入
authors: "Byeonghu Na, Minsang Park, Gyuwon Sim, Donghyeok Shin, HeeSun Bae, Mina Kang, Se Jung Kwon, Wanmo Kang, Il-chul Moon"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cHi8QxGrZH"
tags: ["query:real-ir"]
score: 8.0
evidence: 文本到图像扩散模型的自适应文本嵌入
tldr: 文本到图像扩散模型中文本嵌入固定不变，限制了生成对齐。DATE通过在每个采样步基于中间噪声图像优化文本嵌入，提高模型对文本条件的适应能力。无需额外训练即可显著提升图像-文本对齐，且不损失多样性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 998, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 418, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 586, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 763, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 443, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 915, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 510, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 386, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 849, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1031, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 902, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 514, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1445, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 594, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1420, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 811, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1146, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chi8qxgrzh/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1435, \"height\": 620, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1381, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 994, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 653, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 780, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 579, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1039, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 377, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1453, \"height\": 1304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1437, \"height\": 1497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chi8qxgrzh/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 450, \"label\": \"Table\"}]"
motivation: 固定的文本嵌入无法适应扩散过程的逐步变化，导致对齐不佳。
method: 在扩散采样中动态优化文本嵌入，以最大化预测图像与文本的匹配度。
result: 在多个文本到图像基准上提升对齐分数，无需重新训练模型。
conclusion: DATE为提升文本到图像扩散模型的对齐能力提供了轻量高效的方案。
---

## Abstract
Text-to-image diffusion models rely on text embeddings from a pre-trained text encoder, but these embeddings remain fixed across all diffusion timesteps, limiting their adaptability to the generative process. We propose Diffusion Adaptive Text Embedding (DATE), which dynamically updates text embeddings at each diffusion timestep based on intermediate perturbed data. We formulate an optimization problem and derive an update rule that refines the text embeddings at each sampling step to improve alignment and preference between the mean predicted image and the text. This allows DATE to dynamically adapts the text conditions to the reverse-diffused images throughout diffusion sampling without requiring additional model training. Through theoretical analysis and empirical results, we show that DATE maintains the generative capability of the model while providing superior text-image alignment over fixed text embeddings across various tasks, including multi-concept generation and text-guided image editing. Our code is available at https://github.com/aailab-kaist/DATE.

---

## 论文详细总结（自动生成）

# Diffusion Adaptive Text Embedding (DATE) 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有文本到图像扩散模型在采样过程中使用固定的文本嵌入（text embedding），这些嵌入由预训练文本编码器（如CLIP）生成，并在所有扩散时间步中保持不变。然而，不同扩散时间步对生成的影响不同，固定嵌入无法适应生成过程的逐步演变，导致文本-图像对齐（semantic alignment）不佳。
- **研究动机**：作者观察到，中间预测图像（mean predicted image）的文本-图像对齐分数（如ImageReward）随时间步变化很大，固定嵌入限制了对齐的进一步提升。因此，提出在采样过程中动态更新文本嵌入，使其适应每个时间步的当前噪声图像，从而改善对齐。
- **整体含义**：DATE是一种无需额外模型训练、即插即用的测试时优化方法，能显著提升文本-图像对齐，且不降低生成多样性（FID），可广泛应用于多种扩散模型和后处理任务。

## 2. 论文提出的方法论

### 核心思想
- 在每个扩散采样步 t，基于当前噪声图像 \(x_t\) 和原始文本嵌入 \(c_{\text{org}}\)，通过梯度上升优化一个文本-图像对齐评估函数 \(h(\bar{x}_0; y)\)，得到更新后的嵌入 \(c_t\)，其中 \(\bar{x}_0\) 是通过Tweedie公式从 \(x_t\) 预测的干净图像。
- 优化目标：在嵌入的 \(L_2\) 球约束内（半径为 \(\rho\)），最大化 \(h(\bar{x}_0; y)\)，从而引导生成更符合文本的图像。

### 关键技术细节
- **目标函数近似**：原始需要蒙特卡洛采样，作者用一阶泰勒近似简化为在均值预测图像上的评估函数 \(h(\bar{x}_0; y)\)。
- **更新规则**：通过梯度计算得到最优更新方向，归一化后乘以 \(\rho\) 加到原始嵌入上：
  \[
  c_t = c_{\text{org}} + \rho \frac{\nabla_c h_t(x_t, c_{\text{org}}; y, \theta)}{\|\nabla_c h_t(x_t, c_{\text{org}}; y, \theta)\|_2}
  \]
- **算法流程**（Algorithm 1）：
  1. 初始化 \(x_T \sim p_T\)，获取原始嵌入 \(c_{\text{org}} = I_\phi(y)\)。
  2. 从 t = T 到 1 循环：
     - 如果当前步是“更新步”，则计算梯度并更新嵌入。
     - 然后使用更新后的嵌入执行一步反向扩散（例如DDIM采样）。
- **理论保证**：Proposition 1 证明约束优化结果至少不差于固定嵌入；Theorem 2 表明DATE更新等价于在原分数函数上引入一个与对齐相关的引导项。

## 3. 实验设计

### 数据集与场景
- **主实验**：COCO 2017验证集（5,000张图像，随机采样caption）。
- **下游任务**：
  - 多概念生成：AnE数据集（3类prompt：动物-动物、动物-物体、物体-物体）。
  - 文本引导图像编辑：ImageNet-R-TI2I数据集（30张源图像×5个目标prompt）。

### Benchmark与基线方法
- **主方法对比**：
  - 固定文本嵌入（baseline）
  - EBCA（能量注意力引导，2023）
  - Universal Guidance（数据空间引导，2023）
  - CONFORM（多概念生成专用，2024）
  - DDPM inversion（图像编辑，2024）
- **评估指标**：
  - FID（零样本，分布质量）
  - CLIP Score（语义对齐）
  - ImageReward（人类偏好对齐）
  - Aesthetic Score（美学质量）
  - PickScore（偏好分数）
  - LPIPS（感知相似度，编辑任务）

### 主要实验结果
- 在Stable Diffusion v1.5、PixArt-α、SD3、FLUX、SDXL等多种背骨上，DATE均优于固定嵌入，尤其在对齐指标上提升显著。
- 仅用10%步数更新即可获得可观提升，几乎不增加采样时间（7.82 min vs 5.64 min）。
- 可在半精度下运行，减少内存和计算开销。
- 结合多目标评估函数（如CS+IR）可同时提升多个指标。

## 4. 资源与算力

- 论文未明确列出总训练算力或GPU数量，但说明：
  - **主实验使用**：单张NVIDIA A100 GPU（CUDA 11.4）。
  - **部分消融实验**：单张Intel Gaudi v2（SynapseAI 1.18.0）。
  - 采样时间：对于64张图像，固定嵌入50步约5.64分钟，DATE 10%更新约7.82分钟，全步更新约24.20分钟。
  - 内存：固定嵌入约24.0 GB，DATE全步更新约61.5 GB（由于梯度计算）；半精度可降至约30-33 GB。
- 作者指出计算开销是主要局限，但通过稀疏更新和半精度可缓解。

## 5. 实验数量与充分性

### 实验组数
- 主表（Table 1）对比了3种背骨×多种配置（固定、EBCA、Universal Guidance、DATE变体），共约15+组。
- 不同评估函数消融（Table 2, Table 10）涵盖AS、CS、IR、PS及其组合，约20+组。
- 不同CFG尺度（Table 9）和采样器（DDIM、DDPM）实验。
- 跨背骨实验（Table 3）：SD3、FLUX、SDXL共3个背骨。
- 多概念生成（Table 13, 另附）与图像编辑（LPIPS vs CS图）。
- 消融实验（Table 5, 图7-10）包括随机更新、无归一化梯度、不同ρ、不同更新策略等。

### 充分性与公平性
- **充分**：覆盖主流背骨、采样器、评估指标，消融实验全面，统计学显著性检验（p=0.00056）。下游任务验证了泛化能力。
- **客观公平**：控制随机种子，采样步数匹配时间，基线复现准确（EBCA和Universal Guidance来自官方代码）。但部分实验（如EBCA）在FID上表现很差，可能因未调参或方法本身局限。

## 6. 论文的主要结论与发现

1. **动态文本嵌入有效**：DATE在所有测试模型和采样器上显著提升文本-图像对齐（CLIP Score, ImageReward），同时FID略有改善或持平。
2. **无需训练通用性强**：DATE是测试时优化，无需修改模型参数或架构，即插即用。
3. **时间与实例自适应**：不同时间步的最优嵌入方向几乎不相关（余弦相似度约85%小于0.1），不同实例之间也高度差异，证明需要动态自适应。
4. **下游任务有效**：在多概念生成和图像编辑中，DATE提升了概念表示和编辑保真度。
5. **理论支撑**：DATE可解释为在原分数函数上引入对齐引导项，平衡模型先验与文本条件。

## 7. 优点

- **创新性**：首次系统提出并验证了扩散采样中动态文本嵌入的必要性和有效性，理论推导完整。
- **实用性**：无需训练，兼容现有模型和采样器，易于集成；稀疏更新策略降低计算开销。
- **全面实验**：覆盖多种背骨（U-Net和Transformer）、采样器、评估指标、下游任务，消融充分。
- **理论分析**：提供了优化保证和分数函数解释，增强了方法可信度。
- **代码开源**：提供GitHub仓库，便于复现和应用。

## 8. 不足与局限

- **计算开销**：全步更新时GPU内存和采样时间显著增加，虽然可通过稀疏更新和半精度缓解，但仍有额外成本。
- **依赖评估函数**：性能受限于所选评估函数 \(h\) 的质量，若 \(h\) 有偏（如Aesthetic Score与语义弱相关），可能损害其他指标。
- **超参数敏感性**：需要调节 \(\rho\) 和更新步数比例，不同任务可能需调优。
- **实验覆盖不足**：未评估在更大模型（如Imagen）或长时间序列（>100步）上的表现；仅测试了英语prompt。
- **潜在过拟合风险**：优化目标对齐指标可能过度拟合特定评估函数，生成图像在其它维度（如多样性）上可能略受影响。
- **公平性讨论缺失**：未分析方法对敏感属性（种族、性别）的生成偏差影响。

（完）
