---
title: Learning an Image Editing Model without Image Editing Pairs
title_zh: 无需图像编辑配对数据学习图像编辑模型
authors: "Nupur Kumari, Sheng-Yu Wang, Nanxuan Zhao, Yotam Nitzan, Yuheng Li, Krishna Kumar Singh, Richard Zhang, Eli Shechtman, Jun-Yan Zhu, Xun Huang"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=OHqZ61ZqNO"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用少步扩散和VLM反馈训练无配对数据的图像编辑模型
tldr: 针对当前图像编辑模型严重依赖人工标注或合成配对数据的问题，提出一种免配对训练范式，通过展开少步扩散模型并结合视觉语言模型反馈进行直接优化。该方法无需任何输入-目标图像对，即可使模型遵循文本编辑指令，在多个基准上取得有竞争力的表现，为图像编辑模型的训练开辟了新方向。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 解决图像编辑模型依赖大规模配对数据训练的瓶颈。
method: 通过展开少步扩散模型并利用视觉语言模型反馈直接优化模型，消除配对数据需求。
result: 在无需成对数据情况下实现指令驱动的图像编辑。
conclusion: 提出全新训练范式，摆脱了图像编辑对合成配对数据的依赖。
---

## Abstract
Recent image editing models have achieved impressive results while following natural language editing instructions,  but they rely on supervised fine-tuning with large datasets of input-target pairs. This is a critical bottleneck, as such naturally occurring pairs are hard to curate at scale. Current workarounds use synthetic training pairs that leverage the zero-shot capabilities of existing models. However, this can propagate and magnify the artifacts of the pretrained model into the final trained model. In this work, we present a new training paradigm that eliminates the need for paired data entirely. Our approach directly optimizes a few-step diffusion model by unrolling it during training and leveraging feedback from vision-language models (VLMs).  For each input and editing instruction, the VLM evaluates if an edit follows the instruction and preserves unchanged content, providing direct gradients for end-to-end optimization. To ensure visual fidelity, we incorporate distribution matching loss (DMD), which constrains generated images to remain within the image manifold learned by pretrained models. We evaluate our method on standard benchmarks and include an extensive ablation study.  Without any paired data, our method performs on par with various image editing diffusion models trained on extensive supervised paired data, under the few-step setting. Given the same VLM as the reward model, we also outperform RL-based techniques like Flow-GRPO.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当前遵循自然语言指令的图像编辑模型取得了显著成果，但其训练严重依赖大规模“输入-目标图像”配对数据集（例如，成对的原始图片和编辑后图片）。这种天然配对数据极难大规模获取，成为关键瓶颈。
- **现有解决方案的局限**：现有方法通常利用已有模型的零样本能力生成合成配对数据。但这会把预训练模型自身的缺陷（artifacts）引入并放大到最终训练的编辑模型中，影响生成质量。
- **整体含义**：本文提出一种全新的训练范式，彻底摆脱对图像编辑配对数据的依赖，为图像编辑模型训练开辟了无需昂贵人工标注或合成数据的新方向。

### 2. 论文提出的方法论
- **核心思想**：采用**免配对训练范式**，通过展开少步扩散模型（few-step diffusion model）并结合**视觉语言模型（VLM）的反馈**进行端到端优化，使模型学会遵循文本编辑指令，整个过程无需任何输入-目标图像对。
- **关键技术细节**：
    - **模型展开**：在训练中显式展开少步扩散模型的生成过程，使梯度能够从输出端回传至模型参数。
    - **VLM 反馈机制**：对每张输入图像和编辑指令，VLM 评估两件事：
        - 编辑是否遵循了指令（编辑一致性，edit-following）；
        - 是否保留了不应改变的内容（非编辑区域保持度）。
      VLM 提供的评估信号直接转化为梯度，用于优化扩散模型。
    - **分布匹配损失（DMD）**：为保证生成图像的视觉保真度，引入分布匹配损失，约束生成图像保持在预训练模型所表征的真实图像流形（image manifold）内。
- **算法流程**（文字描述）：输入图像 + 编辑指令 → 少步扩散模型生成编辑结果 → VLM 对结果进行打分（编辑准确度、内容保持度） → 计算损失（含 VLM 损失与 DMD 损失） → 梯度反向传播以更新模型参数；训练中完全不使用目标真值图像。

### 3. 实验设计
- **数据集与场景**：论文未详细列出数据集名称，但从“标准基准（standard benchmarks）”可推断使用了图像编辑社区常用的评测数据集，如基于指令的图像编辑基准。
- **对比方法**：
    - 在少步设定下，与大量**基于大规模监督配对数据训练的扩散编辑模型**进行比较。
    - 在相同 VLM 作为奖励模型的情况下，与基于强化学习的方法（如 **Flow-GRPO**）进行对比。
- **消融研究**：论文提到进行了“广泛的消融研究”，应包含对 VLM 反馈、DMD 损失等关键组件的验证。

### 4. 资源与算力
- 提供的 PDF 提取文本和元数据中**未明确提及 GPU 型号、数量或训练时长**。无法得知具体算力消耗。

### 5. 实验数量与充分性
- 虽未给出实验的精确数量，但摘要与元数据提到：
    - 在标准基准上的评估；
    - 与多类方法的对比（监督配对方法、RL 方法）；
    - 广泛的消融研究。
- **充分性与公平性**：从描述看，实验覆盖了核心比较（vs 配对训练模型）和自身部件消融，且在与 RL 方法对比时控制为相同的 VLM 奖励模型，较为公平。但由于缺乏完整正文，具体指标和显著性无法判断。

### 6. 论文的主要结论与发现
- 提出的免配对训练范式**无需任何配对数据**，在少步设定下，其性能与大量使用监督配对数据训练的扩散编辑模型相当。
- 在相同的 VLM 奖励模型下，该方法优于基于强化学习的 Flow-GRPO 方法。
- 验证了通过 VLM 反馈和分布匹配损失可直接优化图像编辑模型，为摆脱合成数据依赖提供了有效路径。

### 7. 优点
- **范式创新**：首次完全消除了图像编辑训练对配对数据的需求，突破了重要数据瓶颈。
- **技术思路巧妙**：利用现成的 VLM 作为可微分“评分器”，将高阶语义评价转化为训练信号，结合 DMD 保障视觉质量。
- **对比全面**：既与强监督基线比，也与 RL 类方法比，结论有说服力。
- **实用性强**：方法适用于少步扩散模型，有利于实际部署的效率。

### 8. 不足与局限
- **缺乏详细技术细节**：由元数据无法得知模型架构、VLM 具体选用、训练稳定性等关键细节，评估其技术严谨性受限。
- **VLM 偏差风险**：过度依赖 VLM 的评判，若 VLM 本身存在偏见或对某些编辑类型不敏感，可能将偏差传导至编辑模型。
- **应用限制**：目前仅在少步扩散模型上验证，对不同类型的编辑模型（如 GAN 式或多步扩散）的泛化性未提及。
- **实验透明度**：由于未提供训练算力、具体数据集和量化结果，难以评估方法的实际计算成本和复现难度。

（完）
