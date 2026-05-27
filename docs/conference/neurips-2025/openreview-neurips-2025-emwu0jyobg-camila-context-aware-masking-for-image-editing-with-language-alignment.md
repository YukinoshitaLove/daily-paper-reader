---
title: "CAMILA: Context-Aware Masking for Image Editing with Language Alignment"
title_zh: "CAMILA: 上下文感知掩码用于语言对齐的图像编辑"
authors: "Hyunseung Kim, Chiho Choi, Srikanth Malla, Sai Prahladh Padmanabhan, Saurabh Bagchi, Joon Hee Choi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Emwu0jyOBg"
tags: ["query:real-ir"]
score: 9.0
evidence: 文本引导图像编辑与上下文感知掩码
tldr: 现有文本编辑模型盲目遵从用户指令导致不合理输出，CAMILA提出上下文感知掩码方法，先验证指令与图像的一致性，只在相关区域应用编辑，忽略不可执行指令，提升了编辑的合理性和鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-emwu0jyobg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1359, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-emwu0jyobg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1378, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-emwu0jyobg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 563, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-emwu0jyobg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1335, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-emwu0jyobg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 331, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-emwu0jyobg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-emwu0jyobg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 581, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-emwu0jyobg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-emwu0jyobg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 824, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-emwu0jyobg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 658, \"height\": 166, \"label\": \"Table\"}]"
motivation: 现有图像编辑模型盲目执行所有指令，包括不可行或矛盾指令，导致不合理结果。
method: 设计上下文感知掩码机制，先评估指令与图像的一致性，再决定编辑区域和操作。
result: 在多个基准上展示了更合理的编辑结果。
conclusion: 上下文感知大大提升了文本驱动图像编辑的可靠性和实用性。
---

## Abstract
Text-guided image editing has been allowing users to transform and synthesize images through natural language instructions, offering considerable flexibility. However, most existing image editing models naively attempt to follow all user instructions, even if those instructions are inherently infeasible or contradictory, often resulting in nonsensical output. To address these challenges, we propose a context-aware method for image editing named as CAMILA (Context-Aware Masking for Image Editing with Language Alignment). CAMILA is designed to validate the contextual coherence between instructions and the image, ensuring that only relevant edits are applied to the designated regions while ignoring non-executable instructions. For comprehensive evaluation of this new method, we constructed datasets for both single- and multi-instruction image editing, incorporating the presence of infeasible requests. Our method achieves better performance and higher semantic alignment than state-of-the-art models, demonstrating its effectiveness in handling complex instruction challenges while preserving image integrity.

---

## 论文详细总结（自动生成）

# CAMILA 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：文本引导的图像编辑技术（如 InstructPix2Pix、MGIE、SmartEdit 等）允许用户通过自然语言指令修改图像，具有很高的灵活性。然而，现有模型往往不加区分地尝试执行所有用户指令，即使这些指令在视觉上不可行、逻辑矛盾或与图像内容不兼容，导致输出不合理、过度编辑甚至破坏图像完整性。
- **核心问题**：如何让模型具备**上下文感知**（Context-Aware）能力，即先验证指令与图像之间的语义一致性，仅对可执行的指令进行精确编辑，忽略不可行的指令，从而避免错误编辑。
- **整体含义**：论文提出 CAMILA，首次将指令可执行性评估引入图像编辑流程，从而提升编辑的鲁棒性、合理性和语义对齐效果，推动了文本驱动图像编辑从“盲目遵从”向“条件性执行”的转变。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：基于预训练的多模态大语言模型（MLLM）联合理解图像和文本指令，生成两类特殊 token——`[MASK]`（表示需修改的区域）和 `[NEG]`（表示需忽略的区域），并通过专门的广播和解码模块将 token 映射为二进制编辑掩码，最后利用扩散模型中的交叉注意力调制实现区域可控编辑。
- **关键技术细节**：
  1. **MLLM 联合编码**：将图像和文本指令同时输入 MLLM（基于 LLaVA），输出 token 序列。每个 token 被分类为 `[MASK]` 或 `[NEG]`。
  2. **Token Broadcaster（令牌广播器）**：将 MLLM 输出 token 与扩散模型的文本编码器输出的文本嵌入对齐。通过可训练的投影矩阵将两者映射到共享空间，计算余弦相似度并利用 softmax 得到对齐概率，最终每个文本嵌入映射到最匹配的 MLLM token（`[MASK]` 或 `[NEG]`）。
  3. **Token Decoder（令牌解码器）**：两层 Transformer 解码器。第一层对图像和文本特征进行交叉注意力提取；第二层引入 `[MASK]` token 作为 key/value 进行细化，最后经 sigmoid 阈值化输出二进制掩码。对于 `[NEG]` token 直接输出全黑掩码。
  4. **扩散模型中的注意力调制**：将生成的二进制掩码 `M` 与交叉注意力图结合，通过公式 `A' = softmax((X ⊙ M + Y ⊙ (1-M)) / sqrt(d))` 实现，其中 `X` 为含文本条件的注意力图，`Y` 为无文本条件的注意力图。掩码 `M` 保证仅对指定区域施加文本条件，其他区域保持原图特征。
  5. **代理模块（Surrogate Module）**：为解决难以从最终输出图像向 MLLM 反向传播的问题，训练一个轻量级单层 Transformer 来近似 CLIP-T 分数。训练后冻结代理模块，利用其预测分数微调 MLLM 和掩码生成模块，进一步提升掩码质量。
- **训练损失**：包含四部分加权损失：token 分类 CE 损失、广播对齐 CE 损失、掩码 Dice 损失和二进制 CE 损失。最终加入代理模块的 MSE 损失。

## 3. 实验设计

- **数据集**：
  - **单指令任务**：MagicBrush（包含单轮和多轮子集）以及 EMU 数据集。
  - **多指令与上下文感知指令任务**：由于缺乏标准基准，论文自行构建了数据集。具体做法是从 MagicBrush 的多轮任务中拼接可行指令得到多指令数据集；利用 ChatGPT-4V 生成与图像内容矛盾的不可执行指令，并与可行指令混合得到上下文感知指令数据集。
  - 评价指标：L1/L2 距离、CLIP-I、DINO、CLIP-T、CLIP-dir、PickScore 等。
- **对比方法**：InstructPix2Pix (IP2P)、MGIE、SmartEdit、FoI、EMILIE、Step1X-Edit。
- **主要实验规模**：
  - 单指令实验（MagicBrush 单轮/多轮）
  - 多指令实验（仅有可行指令）
  - 上下文感知指令实验（混合可行与不可行指令）
  - EMU 数据集上的 CLIP-T 和 CLIP-dir 对比
  - 与大规模模型 Step1X-Edit 的对比
  - 消融实验：代理模块训练前后性能对比、token 分类准确率（90.21%）、掩码分割指标（IoU=0.3819，Dice=0.4986）
  - 定性实验结果展示

## 4. 资源与算力

- 论文中未明确说明使用的 GPU 型号、数量以及训练时长等具体算力信息。仅在附录中提及训练细节（如学习率、优化器等），但未提供计算资源规格。因此，无法从公开内容中获知算力需求。

## 5. 实验数量与充分性

- **实验数量**：覆盖了四种主要任务（单指令、多指令、上下文感知指令、EMU），并设计了多种对比方法和多个指标（至少 5 个定量指标 + 定性对比 + 消融实验）。此外还包括与大规模模型的对比、代理模块有效性验证、掩码质量分析。总体实验组数大约 8-10 组（含表格）。
- **充分性与公平性**：
  - 论文构建了专门用于评估上下文感知能力的新数据集，弥补了领域空白，具有很强的针对性。
  - 对比方法包括当前最主流的多种图像编辑模型，且均在相同测试集下评估，保证了公平性。
  - 消融实验验证了关键模块（代理模块）的作用，并报告了 token 分类准确率和掩码质量，体现了方法的内在鲁棒性。
  - 不足之处：缺少对更多复杂场景（如长序列指令、罕见物体）的系统测试；未提供误差棒或统计显著性检验，结果均为单次确定性输出。

## 6. 主要结论与发现

- CAMILA 在几乎所有评价指标上均优于现有方法，尤其在**上下文感知指令任务**中提升显著（L1 降低 25.8%，CLIP-I 提升 4.5%，DINO 提升 9.0%），证明其有效区分可执行与不可执行指令。
- 通过 `[MASK]`/`[NEG]` token 和广播机制，模型能精确定位编辑区域并避免过度编辑，即使面对包含矛盾指令的输入也能保持图像完整性。
- 代理模块的引入进一步提升了 CLIP-T 分数以及整体的 L1/L2、CLIP-I、DINO 性能，说明优化掩码质量对最终编辑效果有正向作用。
- 即使使用较小的扩散模型（Stable Diffusion），CAMILA 仍优于使用更大扩散模型（DiT）的 Step1X-Edit，凸显了上下文感知设计的重要性。

## 7. 优点

1. **问题新颖且实用**：首次系统性关注指令可执行性，解决了实际应用中常见但未被充分研究的“无效指令”问题。
2. **模块化设计**：将上下文评估、掩码生成、注意力调制解耦，架构清晰，可解释性强。
3. **高效训练**：仅微调 MLLM 的 LoRA 部分和两个轻量模块（Token Broadcaster 和 Decoder），无需联合训练扩散模型，降低了计算成本。
4. **代理模块的巧妙应用**：利用代理近似 CLIP-T 分数来指导掩码生成，避免了扩散模型的反向传播困难，提升性能的同时保持训练可行性。
5. **新数据集构建**：为社区提供了首个包含不可执行指令的编辑基准，推动了公平评估。
6. **实验全面**：覆盖多种任务、多类指标、定性定量结合，并附有消融和大规模模型对比，说服力强。

## 8. 不足与局限

1. **算力信息缺失**：未透露具体 GPU 型号、训练时间等，不利于复现和成本评估。
2. **统计显著性缺失**：没有提供误差条或多次运行的标准差，结果可能受随机性影响（尽管扩散模型通常是确定性的）。
3. **掩码质量并非最优**：IoU 仅为 0.3819，说明生成的编辑掩码与真实编辑区域存在较大差异，可能影响精细编辑的准确性。
4. **复杂场景泛化性**：仅在有限的数据集上验证（MagicBrush、EMU），未测试真实用户生成的多样化场景或长序列指令。
5. **依赖 MLLM 质量**：模型性能受限于底层 MLLM（LLaVA）的分辨率和理解能力，对于非常细小的物体或抽象概念可能仍然失败（论文附录 E.3 讨论了一些失败案例）。
6. **实际应用限制**：推理时需要先生成掩码再运行扩散模型，增加了延迟；对实时性或低功耗场景可能不友好。

（完）
