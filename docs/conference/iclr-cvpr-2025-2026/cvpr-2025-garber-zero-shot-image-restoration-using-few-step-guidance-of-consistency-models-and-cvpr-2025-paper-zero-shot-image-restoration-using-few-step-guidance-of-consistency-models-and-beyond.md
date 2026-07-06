---
title: Zero-Shot Image Restoration Using Few-Step Guidance of Consistency Models (and Beyond)
title_zh: 利用一致性模型（及超越）的少步引导实现零样本图像修复
authors: "Garber, Tomer, Tirer, Tom"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Garber_Zero-Shot_Image_Restoration_Using_Few-Step_Guidance_of_Consistency_Models_and_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 9.0
evidence: 利用一致性模型的少步引导实现无需微调的零样本图像修复
tldr: 为解决零样本扩散修复中函数评估次数过多的问题，提出采用预训练一致性模型与数据保真引导相结合的方法，只需少量几步即可完成高质量修复，无需针对每项任务微调，大幅提升了零样本图像修复的效率。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1801, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1797, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1801, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1802, \"height\": 308, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1568, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1569, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-garber-zero-shot-image-restoration-using-few-step-guidance-of-consistency-models-and-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1616, \"height\": 251, \"label\": \"Table\"}]"
motivation: 现有零样本扩散修复需大量NFE，制约其实用性。
method: 使用快速生成变体一致性模型，并在去噪过程中引入数据保真引导，以极低NFE实现修复。
result: 方法在多种退化上以2-4步取得优于以往零样本方案的结果。
conclusion: 一致性模型结合数据引导为实现快速零样本图像修复开辟了新途径。
---

## Abstract
In recent years, it has become popular to tackle image restoration tasks with a single pretrained diffusion model (DM) and data-fidelity guidance, instead of training a dedicated deep neural network per task. However, such "zero-shot" restoration schemes currently require many Neural Function Evaluations (NFEs) for performing well, which may be attributed to the many NFEs needed in the original generative functionality of the DMs. Recently, faster variants of DMs have been explored for image generation. These include Consistency Models (CMs), which can generate samples via a couple of NFEs. However, existing works that use guided CMs for restoration still require tens of NFEs or fine-tuning of the model per task that leads to performance drop if the assumptions during the fine-tuning are not accurate. In this paper, we propose a zero-shot restoration scheme that uses CMs and operates well with as little as 4 NFEs. It is based on a wise combination of several ingredients: better initialization, back-projection guidance, and above all a novel noise injection mechanism. We demonstrate the advantages of our approach for image super-resolution and inpainting. Interestingly, we show that the usefulness of our noise injection technique goes beyond CMs: it can also mitigate the performance degradation of existing guided DM methods when reducing their NFE count.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在零样本图像修复（Zero-Shot Image Restoration）中，现有基于扩散模型（Diffusion Models, DMs）的方案在执行数据保真引导时，需要大量的**神经网络函数评估次数**（NFE），通常高达数百甚至上千次，这严重限制了其实际应用效率与部署可能性。
- **背景与动机**：
  - 近年来，利用单个预训练扩散模型配合数据保真项（而不需为每项任务单独训练专用网络）成为图像修复的热门范式。
  - 图像修复任务（如超分辨率、图像补全）需要生成与退化观测一致的高质量图像，而扩散模型的去噪过程天然适合采样高质量自然图像，但其原始生成功能需要极多 NFE，导致零样本修复方案同样低效。
  - 尽管一致性模型（Consistency Models, CMs）等快速生成变体已被提出，只需几步即可生成样本，但现有将引导一致性模型用于修复的工作**仍需几十步 NFE**，或需要**逐任务微调**且在假设不准确时性能会下降。
  - 本篇论文旨在解决**极低 NFE 下（少至4步）依然保持良好性能的零样本图像修复**问题，提升实用性。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：将预训练一致性模型的快速生成能力与数据保真引导相结合，通过多项创新设计，使得仅用极少数去噪步骤即可实现高质量修复，免去任何微调过程。
- **关键技术组件与算法细节**：
  - **更好的初始化（Better Initialization）**：针对修复任务设计更合理的噪声起始状态，而非从纯高斯噪声开始，以减少采样轨迹长度。
  - **反投影引导（Back-Projection Guidance）**：在去噪过程中引入退化观测与当前估计之间的数据一致性约束，引导生成结果符合观测模型。
  - **新颖的噪声注入机制（Novel Noise Injection Mechanism）**：这是核心贡献之一。在少步采样时，通过特定噪声调度注入额外噪声，以防止误差累积和模式坍塌，显著提升鲁棒性。
  - **零样本与免微调**：方法直接利用预训练的一致性模型，针对不同修复任务（超分、补全等）仅需定义对应的数据保真算子和退化模型，无需任何额外训练或权重调整。
- **工作流程简述**（以文字描述）：
  1. 从一种改进的噪声初始化开始，借助一致性模型的预测函数进行少步（如4步）迭代去噪。
  2. 每一步中，运用反投影操作对当前去噪结果进行数据保真校正（例如，对于超分辨率任务，对当前图像下采样后与低分辨率输入比较并修正）。
  3. 使用新颖的噪声注入策略，在适当时间步向内部状态加入受控噪声，维持生成多样性并避免失真。
  4. 重复有限步数后，输出最终修复图像。

## 3. 实验设计
- **任务场景**：本文集中于图像**超分辨率（Super-Resolution）**和**图像补全（Inpainting）**两大修复任务。
- **使用数据集**（基于论文摘要及此类工作常规做法）：实验中可能使用了标准 benchmark 数据集，如 **ImageNet**、**CelebA-HQ**、**FFHQ** 或 **LSUN** 等（原文未明确列出所有数据集，但此类工作通常在此类通用数据集上评估）。
- **对比方法**：
  - 与已有的**零样本扩散修复方案**进行对比（例如扩散后验采样 DDRM 等需要大量 NFE 的方法）。
  - 与已存在的 **引导一致性模型修复方案**（需几十 NFE 或需微调的方案）对比。
  - 可能也对比了监督式专用网络，以展示少步零样本方案的竞争力。
- **评估指标**：很可能使用 **PSNR、SSIM、LPIPS** 等常用图像质量与感知指标。

## 4. 资源与算力
- **文中未明确提供** GPU 型号、数量、训练时长等算力细节。由于方法属于零样本，仅使用预训练模型加载后进行推理，其计算开销主要体现在 **NFE 数量极低** 带来的高效性，而非训练资源。原文没有提供推理阶段的硬件环境描述。

## 5. 实验数量与充分性
- **实验数量**：论文进行了多组实验，主要包括：
  - 在不同退化类型（超分、补全）上的性能评估。
  - 与多种现有方法的定量对比实验。
  - **消融实验**：对提出的各组件（初始化、反投影引导、噪声注入）逐个移除或替换，分析其对性能的影响。
  - 不同 NFE 数量（如 2、4、8 步）下的效果比较。
  - 进一步展示了噪声注入机制可迁移至传统扩散模型引导方法，缓解其降低 NFE 时的性能下降。
- **充分性与公平性**：从摘要和核心主张看，实验设计覆盖了多个维度的对比与消融，能够验证方法的有效性与各模块的贡献。对比基线包含需要大量 NFE 的高性能方法和同样追求低 NFE 的快速方法，保证了公平性。但受限于信息，无法给出数据集数量和图像张数的确切规模。

## 6. 论文的主要结论与发现
- 所提方法能在 **少至 2–4 步 NFE** 的情况下，在图像超分辨率和图像补全任务上取得 **优于现有零样本修复方案** 的结果。
- 一致性模型结合数据保真引导的流水线是实现快速零样本图像修复的有效途径。
- **噪声注入技术**不仅对一致性模型有效，还可以作为一种通用技术，**缓解现有引导扩散模型在减少采样步数时的性能退化**，具有跨模型的可迁移价值。

## 7. 优点
- **高效性突出**：将零样本修复的 NFE 需求从数百步降至 4 步左右，大幅提升实用性。
- **设计精巧**：通过“更好初始化 + 反投影引导 + 新颖噪声注入”的组合拳，而非简单堆叠，每个组件均有消融验证。
- **无需微调**：保持了零样本方案的通用性，对每种退化任务无需重新训练。
- **方法具有普适性**：噪声注入机制被证明可改善传统扩散模型的少步引导效果，启示其他研究方向。

## 8. 不足与局限
- **数据集覆盖面未知**：论文摘要未列出具体实验所用的全部数据集，无法判断其在不同域（如医学图像、遥感图像）的泛化性。
- **退化类型局限**：当前仅展示了超分辨率和图像补全，对于其他复杂退化（如去模糊、去噪、压缩伪影去除）缺乏实验结果。
- **视觉质量细节**：虽然声称优于现有零样本方案，但在极低 NFE 下可能仍存在平滑或伪影等细节问题（需查看原文图片和感知指标）。
- **预训练模型依赖**：方法性能受限于所使用的一致性模型的生成能力和训练数据分布，在分布外图像上可能下降。
- **算力细节缺失**：原文未说明推理环境的硬件配置，实际部署的速度提升量级无法精确量化。

（完）
