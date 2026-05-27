---
title: "NEP: Autoregressive Image Editing via Next Editing Token Prediction"
title_zh: NEP：基于下一编辑标记预测的自回归图像编辑
authors: "Huimin Wu, Xiaojian Ma, Haozhe Zhao, Yanpeng Zhao, Qing Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=42VDMzV7qm"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于下一标记预测的自回归图像编辑
tldr: 现有图像编辑方法整体生成图像，导致计算浪费和非编辑区域重建偏差。NEP将编辑视为下一编辑标记预测，仅生成需要修改的区域，保持其他部分不变。基于自回归图像生成实现，显著提高编辑质量和效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1302, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-42vdmzv7qm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 522, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1192, \"height\": 1262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1223, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1013, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 578, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 812, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 836, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 466, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-42vdmzv7qm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 457, \"height\": 229, \"label\": \"Table\"}]"
motivation: 全图生成浪费计算且破坏非编辑区域质量。
method: 将图像编辑建模为下一编辑标记预测，只对编辑区域进行自回归生成。
result: 在编辑任务上质量更高、速度更快，保持背景一致性。
conclusion: NEP为精准高效的图像编辑提供了新范式。
---

## Abstract
Text-guided image editing involves modifying a source image based on a language instruction and, typically, requires changes to only small local regions. However, existing approaches generate the entire target image rather than selectively regenerate only the intended editing areas. This results in (1) unnecessary computational costs and (2) a bias toward reconstructing non-editing regions, which compromises the quality of the intended edits. To resolve these limitations, we propose to formulate image editing as $\textbf{N}$ext $\textbf{E}$diting-token $\textbf{P}$rediction (NEP) based on autoregressive image generation, where only regions that need to be edited are regenerated, thus avoiding unintended modification to the non-editing areas. To enable any-region editing, we propose to pre-train an any-order autoregressive text-to-image (T2I) model. Once trained, it is capable of zero-shot image editing and can be easily adapted to NEP for image editing, which achieves a new state-of-the-art on widely used image editing benchmarks. Moreover, our model naturally supports test-time scaling (TTS) through iteratively refining its generation in a zero-shot manner.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
现有的文本引导图像编辑方法（特别是基于扩散模型的方法）通常需要生成整个目标图像，即使只有局部区域需要修改。这导致两个问题：
- **不必要的计算开销**：全图生成浪费大量计算资源。
- **非编辑区域的重建偏差**：模型倾向于优先重建未编辑区域，从而损害了真正需要修改的编辑区域的质量。

为了解决这些问题，本文提出将图像编辑重新建模为 **下一编辑标记预测（Next Editing-token Prediction, NEP）**，仅对需要编辑的局部区域进行自回归生成，而非编辑区域保持不变，从而避免全图生成的开销和重建偏差。

## 2. 论文提出的方法论

### 核心思想
- 将图像编辑视为 **自回归的标记预测任务**，输入包括文本指令、源图像标记以及编辑区域掩码标记，输出仅编辑区域的标记序列。
- 基于自回归文本到图像（T2I）模型，但标准自回归模型（如LlamaGen）使用固定的栅格扫描顺序生成，无法灵活地只生成任意编辑区域。为此，论文首先预训练了一个**任意顺序的自回归T2I模型 RLlamaGen**，支持在任意位置生成标记。

### 关键技术细节
1. **RLlamaGen 预训练**：
   - 在LlamaGen基础上引入**可学习的位置嵌入序列** \( PE_1, PE_2, ..., PE_L \)，并根据随机顺序打乱，使模型能够按任意顺序生成图像标记。
   - 生成概率定义为：\( p(I_O) = \prod_{i=1}^{L} p(I_{o_i} | I_{o_1} + PE_{o_2}, ..., I_{o_{i-1}} + PE_{o_i}; T) \)，其中 \( O \) 是随机顺序。
2. **NEP 编辑框架**：
   - 输入序列包含三部分：文本指令嵌入、源图像标记、编辑区域掩码标记（由编辑嵌入 \( E_{emb} \) 和非编辑嵌入 \( U_{emb} \) 组成）。
   - 模型仅预测编辑区域对应的标记（数量 \( L_E \)），生成顺序为编辑区域内按栅格扫描顺序。
   - 训练分两阶段：先预训练RLlamaGen，再在UltraEdit等编辑数据集上微调NEP。
3. **测试时缩放（Test-Time Scaling, TTS）**：
   - 将NEP集成到迭代精化循环中：首先计算图像质量奖励模型（如ImageReward）的Grad-CAM值，找出低质量区域作为修订区域；然后使用NEP重新生成该区域标记，并通过拒绝采样选择最优结果。

## 3. 实验设计

### 数据集与基准
- **文本到图像预训练**：约1600万文本-图像对，来自ALLaVA-LAION、CC12M、Kosmos-G、LAION-LVIS-220、LAION-COCO-AESTHETIC、LAION-COCO-17M、ShareGPT4V等开源数据集。
- **图像编辑微调**：UltraEdit数据集（400万图像对，其中13.1万有编辑区域标注）。
- **评估基准**：
  - **MagicBrush**：提供编辑区域掩码，评估单轮和多轮编辑，指标包括L1距离、L2距离、CLIP图像相似度（CLIP-I）、DINO特征相似度。
  - **Emu Edit**：无目标图像，评估自由形式编辑，使用CLIP文本-图像相似度（CLIPout）、CLIP方向相似度（CLIPdir）、L1距离、CLIP图像相似度、DINO相似度。

### 对比方法
- 全局描述型：SD-SDEdit、Null Text Inversion、GLIDE、Blended Diffusion。
- 指令引导型：HIVE、InstructPix2Pix（IP2P）、MagicBrush、UltraEdit、FireEdit、AnySD、EditAR、Emu Edit、MIGE等。
- 零样本编辑：aMUSEd。

## 4. 资源与算力
- **预训练阶段**：8张NVIDIA Tesla A100 GPU，训练60,000步，批量大小360，耗时39小时。
- **编辑微调阶段**：4张NVIDIA Tesla A100 GPU，训练390万步，批量大小100，学习率1e-4。并在512×512分辨率上额外微调2,000步。
- **模型规模**：基于LlamaGen-XL（775M参数），额外添加0.3M位置嵌入参数；编辑微调仅增加3.6K参数（两个可学习嵌入）。

## 5. 实验数量与充分性
本文进行了多组实验，覆盖不同任务和消融分析：
- **MagicBrush单轮与多轮编辑**：表1展示了与11种方法的对比，NEP在单轮设置下所有指标最优，多轮设置下也达到最好或相当水平。
- **Emu Edit自由形式编辑**：表2对比6种方法，NEP在CLIPout和CLIPimg上最优。
- **消融实验**：
  - 表3验证编辑区域条件（ERC）和NEP vs. NTP（全图生成）的重要性，移除ERC导致性能下降，NTP（生成所有标记）显著变差。
  - 表6验证零样本编辑中生成顺序（随机 vs. 栅格扫描）影响可忽略。
- **计算效率**：表4对比显存和推理时间，NEP推理最快（2.88秒/样本），但显存较高（13.25 GB）。
- **零样本编辑**：表5与aMUSEd对比，NEP在单轮和多轮上均更优。
- **预训练质量**：表7a证明RLlamaGen生成质量与LlamaGen相当，且TTS进一步改善CLIP和FID。
- **测试时缩放**：表7b展示多轮迭代精化持续提升，2轮后饱和。

总体实验充分，对比方法全面，消融实验验证了各设计点的有效性，结果可信。

## 6. 论文的主要结论与发现
- **NEP框架显著提升编辑质量和效率**：通过仅生成编辑区域标记，避免全图生成的计算浪费和重建偏差，在MagicBrush和Emu Edit上达到新SOTA。
- **任意顺序自回归T2I模型RLlamaGen有效**：预训练后不仅能用于NEP，还具备零样本局部编辑能力，且不牺牲T2I生成质量。
- **测试时缩放可行**：利用NEP进行迭代精化能够持续改善生成结果，验证了自回归模型的缩放潜力。

## 7. 优点
- **方法论创新**：首次将图像编辑明确建模为下一编辑标记预测，从根本上解决全图生成的问题。
- **高效性**：推理速度快于扩散模型和全图自回归方法，仅需编辑区域的计算量。
- **灵活性**：支持基于掩码的区域编辑和自由形式编辑；预训练模型RLlamaGen可零样本编辑，并适应不同任务。
- **测试时缩放能力**：无需额外微调即可通过迭代精化提升质量。

## 8. 不足与局限
- **依赖用户提供的掩码**：需要外部掩码（如来自SAM等分割模型）来指定编辑区域，增加了预处理开销或需要手动标注。论文指出将对自动掩码定位进行未来研究。
- **对掩码噪声的鲁棒性有限**：当掩码小于实际编辑区域时，模型可能遗漏部分修改；当掩码过大时，NEP表现出一定鲁棒性（自由形式编辑结果可证），但未专门优化。
- **显存需求较高**：由于输入序列中加入掩码嵌入，序列长度增加，导致注意力计算开销增大（显存13.25 GB，高于UltraEdit的4.04 GB）。
- **实验未提供统计显著性检验**（如误差线），仅报告单次运行结果，但遵循领域惯例。
- **社会影响**：图像编辑技术可能被滥用生成虚假内容，论文提出通过过滤训练图像和研究用途许可来缓解，但未给出具体安全机制细节。

（完）
