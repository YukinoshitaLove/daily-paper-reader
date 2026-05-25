---
title: "PAK-UCB Contextual Bandit: An Online Learning Approach to Prompt-Aware Selection of Generative Models and LLMs"
title_zh: PAK-UCB上下文强盗：面向生成模型和LLM的提示感知在线学习选择方法
authors: "Xiaoyan Hu, Ho-fung Leung, Farzan Farnia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mqDgNdiTai"
tags: ["query:real-ir"]
score: 4.0
evidence: 通过上下文强盗根据提示选择生成模型
tldr: 针对不同提示下生成模型性能各异的问题，提出基于上下文强盗的在线学习算法PAK-UCB，用于动态选择最优模型，从而降低查询成本并与评估分数选择互补。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 839, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1580, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1224, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 538, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 532, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 540, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 592, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 688, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 577, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1624, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1770, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1624, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1616, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1766, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1775, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1762, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1764, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 893, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1777, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 890, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 894, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1777, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 873, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1729, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1506, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1764, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1760, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1769, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1776, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1780, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1749, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1775, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1777, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqdgnditai/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 882, \"height\": 590, \"label\": \"Figure\"}]"
motivation: 不同提示下生成模型性能变化，固定模型选择成本高。
method: 使用上下文强盗在线学习，依据提示动态选择生成模型。
result: 方法能自适应选择模型，降低查询成本。
conclusion: 在线学习为生成模型的高效选择提供了新方法。
---

## Abstract
Selecting a sample generation scheme from multiple prompt-based generative models, including large language models (LLMs) and prompt-guided image and video generation models, is typically addressed by choosing the model that maximizes an averaged evaluation score. However, this score-based selection overlooks the possibility that different models achieve the best generation performance for different types of text prompts. An online identification of the best generation model for various input prompts can reduce the costs associated with querying sub-optimal models. In this work, we explore the possibility of varying rankings of text-based generative models for different text prompts and propose an online learning framework to predict the best data generation model for a given input prompt. The proposed PAK-UCB algorithm addresses a contextual bandit (CB) setting with shared context variables across the arms, utilizing the generated data to update kernel-based functions that predict the score of each model available for unseen text prompts. Additionally, we leverage random Fourier features (RFF) to accelerate the online learning process of PAK-UCB. Our numerical experiments on real and simulated text-to-image and image-to-text generative models show that RFF-UCB performs successfully in identifying the best generation model across different sample types. The code is available at: [github.com/yannxiaoyanhu/dgm-online-select](github.com/yannxiaoyanhu/dgm-online-select).

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：传统的生成模型选择通常基于“平均最优分数”（例如平均CLIPScore），但这种方式忽略了一个关键事实：不同的模型对于不同类型的文本提示（prompt）表现会有显著差异。例如，Stable Diffusion在生成“汽车”类提示时得分更高，而PixArt-α在“狗”类提示上更优；LLM在代码补全和代码翻译任务上也可能出现相反的排名。
- **研究动机**：若对所有提示都固定使用平均最优模型，会在许多提示上产生次优结果，并造成查询成本的浪费。因此，需要一种能够根据实时输入的提示动态选择最佳模型的方法。
- **整体含义**：论文将这种“提示感知”的模型选择问题形式化为**上下文强盗（Contextual Bandit）** 问题，并提出了在线学习算法，通过学习提示与各模型得分之间的关系，在每次生成时决策使用哪个模型，以最小化累计遗憾（regret）。

### 2. 论文提出的方法论
- **核心思想**：将文本提示作为共享的上下文（context），将每个可选生成模型视为一个臂（arm）。算法通过在线学习预测每个臂（模型）对于给定提示的期望得分，并选择得分最高的模型，同时通过上置信界（UCB）平衡探索与利用。
- **关键技术细节**：
  - **PAK-UCB（Per-Arm Kernelized UCB）**：不同于经典的内核化CB（为所有臂学习一个共享权重），**每个臂独立学习一个核岭回归函数**，以捕捉不同模型对不同提示的独特响应。算法利用每个模型被选中时产生的提示-得分对，为每个臂构建Gram矩阵，计估算均值μ和不确定性σ，选择UCB值最高的臂。
  - **RFF-UCB加速变体**：为降低PAK-UCB计算成本（迭代时间复杂度达O(t³)），引入**随机傅里叶特征（RFF）** 来近似位移不变核（如高斯核）。RFF-UCB将提示映射到低维随机特征空间，将核回归转化为线性回归，使每轮计算开销降至O(tD²)，实现与T轮线性增长的开销。
  - **理论保证**：文章理论上证明PAK-UCB及其RFF变体能够实现亚线性遗憾界，即O(√(GT))，其中G是模型数，T是轮数。
- **算法流程概要**：
  1. 观察新提示y_t。
  2. 对每个模型g，利用已选它的历史数据（提示-得分对）进行核岭回归，计算预测均值μ_g和不确定性σ_g，得到UCB分数s_g = μ_g + ησ_g。
  3. 选择UCB分数最高的模型生成回复，获得真实得分。
  4. 更新该模型的历史数据集。

### 3. 实验设计
- **任务与数据集**：
  - **文本到图像（T2I）**：使用Stable Diffusion v1.5、PixArt-α、UniDiffuser、DeepFloyd等模型。提示从MS-COCO数据集按类别（如“狗”、“汽车”、“火车”等）均匀随机采样，以CLIP嵌入作为上下文。
  - **LLM选择**：代码生成（BigCodeBench的Python补全，HumanEval-X的C++到Java翻译），使用Gemini-2.5-Flash、Claude-3.5-Haiku、Qwen-Plus等；数独求解（o3-mini、Deepseek-Chat）。上下文提示由RoBERTa或CodeBERT嵌入。
  - **其他生成任务**：图像描述（合成专家+高斯噪声）、文本到视频（MSR-VTT数据集）的合成实验。
- **评估指标**：
  - **Outscore-the-best (OtB)**：算法获得的得分与所有模型中最高平均得分的差值。
  - **最优选择比率 (OPR)**：算法选出该提示下的真实最优模型的比例。
- **对比方法**：
  - KernelUCB（共享权重的标准做法）、LinUCB、One-arm Oracle（始终选平均得分最高的模型）、Random。
  - 消融对比：PAK-UCB-lin（线性核）、Naive-KRR（不探索，即η=0）。

### 4. 资源与算力
- 论文**未明确说明**所使用GPU型号、数量或总训练时长。文中仅提供了一次性能对比：在合成实验中，2,000次迭代的PAK-UCB-RBF约耗时10分钟，RFF-UCB-RBF则少于2分钟，但未给出硬件平台细节。其余实验涉及多组预训练模型的调用（如Stable Diffusion、Gemini等），但未报告具体的计算资源消耗。

### 5. 实验数量与充分性
- **实验组数**：包含4种主要设置（T2I两组模型、T2I三组模型、LLM代码生成、LLM数独）、2种适应性实验（引入新模型、新提示类别）以及3种合成任务（T2I、图像描述、T2V），总计约10组主实验。
- **消融与参数敏感性**：针对RBF核的带宽σ、RFF特征数D、多项式核的γ参数、正则化参数α均进行了消融研究。
- **充分性与公平性**：实验设计丰富，覆盖图像、文本、视频等多模态及真实与合成场景。对比基线包括在线UCB系列方法、“最优平均模型”和随机策略，比较较为全面。所有结果均汇报了多次试验的平均值，保障了客观性。

### 6. 论文的主要结论与发现
- PAK-UCB及其RFF变体在所有实验中均能快速收敛到按提示选择最优模型的策略，其OtB和OPR指标**显著优于**仅选择平均最优模型的One-arm Oracle和共享权重的KernelUCB。
- RFF-UCB在保持相近选择性能的同时，大幅降低了计算时间，证明了随机傅里叶特征在在线模型选择中的有效性。
- 在线学习方法具有良好的**适应性**，当新模型或新提示类型在运行过程中加入时，算法能快速调整选择策略。

### 7. 优点
- **方法创新**：首次为提示感知的生成模型选择设计了每臂独立内核化UCB算法，克服了传统单权重向量无法捕捉模型间差异的局限。
- **理论与实践结合**：不仅给出了理论遗憾界，还引入了RFF实现高效近似，并进行了充分的数值验证。
- **应用广泛**：实验覆盖T2I、LLM、图像描述、T2V等多领域，证明了方法的通用性。
- **适应性展示**：专门设计了反映真实世界动态变化（引入新模型或新提示）的实验，突显了在线学习的优势。

### 8. 不足与局限
- **嵌入依赖**：完全依赖于预训练模型（CLIP、RoBERTa等）对提示的嵌入质量。若提示语义不能很好地被这些嵌入模型捕捉，算法性能可能下降。
- **评价指标单一**：主要基于CLIPScore或二元成功/失败，未能涵盖生成多样性、真实性或人类偏好等更全面的维度。
- **理论假设**：假设评分函数在再生核希尔伯特空间中线性可实现，且未考虑模型调用延迟或推理成本（尽管论文提到了这是未来的方向）。
- **未报告算力**：缺乏详细的算力消耗说明，使得其他研究者难以准确评估方法的资源门槛。
- **场景简化**：LLM的选择任务采用二元奖励，可能未能完全反映生成文本质量的细微差别。合成实验中对非专家模型简单加噪，虽可控但可能与真实差异有出入。

（完）
