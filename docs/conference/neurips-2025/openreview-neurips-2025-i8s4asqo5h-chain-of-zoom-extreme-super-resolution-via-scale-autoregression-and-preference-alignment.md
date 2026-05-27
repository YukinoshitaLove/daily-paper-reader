---
title: "Chain-of-Zoom: Extreme Super-Resolution via Scale Autoregression and Preference Alignment"
title_zh: 缩放链：通过尺度自回归与偏好对齐实现极端超分辨率
authors: "Bryan Sangwoo Kim, Jeongsol Kim, Jong Chul Ye"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=I8S4ASqO5H"
tags: ["query:real-ir"]
score: 9.0
evidence: 通过自回归缩放实现极端超分辨率
tldr: 现有超分辨率模型在超出训练倍数时性能崩溃。本文提出Chain-of-Zoom框架，将极端放大分解为自回归中间缩放链，通过多尺度提示重新利用现有SR模型。无需额外训练即可实现前所未有的放大倍数，并保持高保真度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1377, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1306, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 992, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 978, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 936, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 1807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 2151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1445, \"height\": 2148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1445, \"height\": 2149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 2151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 573, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 573, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i8s4asqo5h/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 574, \"height\": 292, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1152, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 732, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i8s4asqo5h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1116, \"height\": 301, \"label\": \"Table\"}]"
motivation: 突破现有超分辨率模型在极端放大倍数下的性能瓶颈。
method: 将超分辨率分解为自回归的中间缩放链，并引入多尺度提示。
result: 实现远超训练倍数的高质量放大，无需重新训练模型。
conclusion: 提出了一种无需额外训练的极端超分辨率通用框架。
---

## Abstract
Modern single-image super-resolution (SISR) models deliver photo-realistic results at the scale factors on which they are trained, but collapse when asked to magnify far beyond that regime. We address this scalability bottleneck with Chain-of-Zoom (CoZ), a model-agnostic framework that factorizes SISR into an autoregressive chain of intermediate scale-states with multi-scale-aware prompts. CoZ repeatedly re-uses a backbone SR model, decomposing the conditional probability into tractable sub-problems to achieve extreme resolutions without additional training. Because visual cues diminish at high magnifications, we augment each zoom step with multi-scale-aware text prompts generated by a vision-language model (VLM). The prompt extractor itself is fine-tuned using  Generalized Reward Policy Optimization (GRPO) with a critic VLM, aligning text guidance towards human preference. Experiments show that a standard $4\times$ diffusion SR model wrapped in CoZ attains beyond $256\times$ enlargement with high perceptual quality and fidelity.

---

## 论文详细总结（自动生成）

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：现代单图像超分辨率（SISR）模型在它们被训练使用的放大倍数上能生成逼真的结果，但若要求放大倍数远超出该范围（例如从4×到256×），模型性能会急剧下降，产生模糊、伪影甚至完全失败。这种可扩展性瓶颈限制了模型的实际应用，因为用户可能希望灵活地放大至任意倍数，而直接训练极端放大倍数的模型在计算上非常昂贵（内存和时间成本高）。
- **核心问题**：如何有效利用已有的超分辨率模型（例如4× SR模型）来实现远超其训练配置的极端放大（如256×），而无需重新训练新模型。
- **整体含义**：提出一种模型无关的框架Chain-of-Zoom（CoZ），通过将极端超分辨率分解为一系列可处理的中间缩放状态和相应的多尺度感知文本提示，使得任何现有SR模型都能逐步放大到极高倍数，同时保持高感知质量和保真度。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：CoZ是一个尺度级别的自回归框架，将从低分辨率（LR）到高分辨率（HR）的映射分解为一个中间缩放状态链（scale-states），并引入多尺度感知文本提示作为潜在变量，以弥补极端放大时原始图像信号提供的视觉线索不足的问题。
- **关键技术细节**：
  - **AR-2建模**：假设图像生成过程服从二阶自回归（AR-2）结构，即当前缩放状态依赖于前两个缩放状态。引入文本提示变量\( c_i \)（由VLM基于前两个缩放状态生成），以捕获跨尺度的语义信息。
  - **联合分布分解**：将完整的条件概率\( p(x_H | x_L) \)分解为初始步骤和后续步骤，每个步骤包括图像生成和提示生成两个子目标，分别由参数化模型\( \theta \)（SR backbone）和\( \phi \)（VLM）优化。
  - **训练目标**：最大化对数似然\( \mathcal{L} = \mathcal{L}_{init} + \mathcal{L}_{SR} + \mathcal{L}_{VLM} \)，其中\( \mathcal{L}_{SR} \)通过MSE损失优化（等同于标准SR训练），\( \mathcal{L}_{VLM} \)通过交叉熵损失优化（等同于标准VLM预训练）。因此，CoZ可以直接复用预训练的SR backbone和VLM，无需重新训练。
  - **推理算法**：从LR输入\( x_0 \)开始，循环执行：根据当前和前一状态生成提示\( c_i \sim p_\phi(c_i | x_{i-1}, x_{i-2}) \)，然后用SR backbone生成下一状态\( x_i \sim p_\theta(x_i | x_{i-1}, c_i) \)。每次缩放后对图像进行裁剪和调整以满足backbone的输入尺寸要求。
  - **多尺度感知提示提取的RL对齐**：为了在极端放大时获得更符合人类偏好的提示，使用GRPO（Generalized Reward Policy Optimization）对提示提取VLM进行微调。奖励函数包括：批评家VLM得分（\( R_{critic} \)）、短语排除奖励（\( R_{phrase} \)，避免输出如“first image”等无意义短语）、重复惩罚（\( R_{rep} \)）。通过组级优势估计更新VLM参数。

#### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **使用数据集**：
  - 训练：LSDIR数据集 + FFHQ中的10K图像，用于训练SR backbone（OSEDiff）和VLM的GRPO微调。
  - 测试：DIV2K训练集（800张图像）和DIV8K训练集（1500张图像）。每张图像被调整并中心裁剪为512×512作为输入。
- **Benchmark**：由于256×放大不存在真实图像，采用无参考感知指标：NIQE（↓）、MUSIQ（↑）、MANIQA-pipal（↑）、CLIPIQA（↑）。
- **对比方法**：
  - 基线：最近邻插值、直接一步SR（OSEDiff backbone）。
  - 消融变体：CoZ + Null prompt（无文本）、CoZ + DAPE prompt（退化感知提示提取器）、CoZ + VLM prompt（本文提出的多尺度感知VLM）。
  - 额外对比：任意尺度SR方法LIIF、基于扩散的SR方法SeeSR、S3Diff，以及将CoZ应用于S3Diff的结果。
- **用户研究**：MOS（Mean Opinion Score）测试，25名参与者对图像生成和文本生成进行评估，比较仅使用LR输入、多尺度图像、GRPO微调后三种提示的质量。

#### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。
- **明确信息**：
  - SR backbone（OSEDiff with Stable Diffusion 3.0）训练：使用4块NVIDIA GeForce RTX 3090 GPU，采用粗到细训练策略：随机退化训练25K迭代，然后4×特定放大训练20K迭代。
  - VLM的GRPO微调：同样使用4块NVIDIA GeForce RTX 3090 GPU，训练10K全局步数，使用LoRA（Rank=8, Alpha=32, Dropout=0.05），每个提示生成2个候选。
- **未明确说明**：单次完整实验的总GPU时长、总能耗等细节未给出；但已提到SR训练迭代次数和VLM微调步数，可大致推算。

#### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平
- **实验组数**：
  - 主要实验：在DIV2K和DIV8K两个数据集上，对4×、16×、64×、256×四个放大倍数，分别测试了5种方法（NN插值、Direct SR、CoZ-Null、CoZ-DAPE、CoZ-VLM），共5×2×4=40组结果（表1）。
  - 额外对比表2：又与LIIF、SeeSR、S3Diff、S3Diff+CoZ对比，同样在四个倍数和两个数据集上进行，共4×2×4=32组结果。
  - GRPO训练曲线：两个不同批评家VLM（InternVL2.5-8B和Qwen2.5-VL-7B-Instruct）的训练奖励曲线，表明收敛性。
  - 用户研究：MOS测试，25人评分，统计显著性（t检验）。
  - 额外实验：使用开源OSEDiff（SD2.1 backbone）重复表1结果（附录E）；使用不同批评家VLM的量化结果（附录F）；重叠区域一致性测试（附录G）。
- **实验充分性**：实验覆盖多个放大倍数、多种基线、不同提示策略、两种评测数据集、两种SR backbone（SD3.0和SD2.1）、两种批评家VLM，并包含用户主观评价，较为全面。对比方法包括传统插值、一步SR、任意尺度SR、其他扩散SR，且CoZ方法本身做了消融，证明了VLM提示的必要性。实验设计客观、公平。

#### 6. 论文的主要结论与发现
- CoZ框架能够将任何现成的SR模型（例如仅训练于4×的模型）扩展到256×甚至更高倍数，无需重新训练，并保持高感知质量和内容保真度。
- 在极端放大时，多尺度感知的VLM文本提示显著优于无提示或DAPE提示，能减少幻觉并生成更逼真细节。
- 通过GRPO微调VLM使其提示与人类偏好对齐，进一步提升了图像质量和文本相关性，用户研究证实了这一点。
- 在无参考指标（NIQE、MUSIQ、MANIQA、CLIPIQA）上，CoZ-VLM在所有高放大倍数（16×, 64×, 256×）上均优于直接SR和其他基线，仅在4×时略低于直接SR（但差异很小）。
- 将CoZ应用于其他SR模型（如S3Diff）同样带来显著提升，验证了框架的泛化性。

#### 7. 优点：方法或实验设计上有哪些亮点
- **方法亮点**：
  - 模型无关：可直接套用任何训练好的SR backbone，无需修改或重训练，降低了计算成本。
  - 自回归缩放链：巧妙地分解问题，使逐步放大变得可行，且通过AR-2建模和文本提示弥补信息损失。
  - 首次将GRPO应用于超分辨率中的提示提取，利用批评家VLM进行偏好对齐，提升了提示质量。
  - 算法设计简洁：训练目标可分解为标准的MSE和交叉熵损失，易于实施。
- **实验设计亮点**：
  - 在多个极端放大倍数（16×~256×）上进行测试，并采用多种无参考指标，避免了因缺少真实HR的困境。
  - 广泛的消融：比较Null、DAPE、VLM三种提示，证明了VLM的必要性和有效性。
  - 用户研究提供了主观证据，增强了结论的可信度。
  - 额外实验验证了框架在不同backbone和不同批评家VLM下的鲁棒性。

#### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **错误累积**：CoZ需要多次递归执行SR和提示提取，每次误差可能累积，尤其在高倍数时。
- **计算成本**：虽然无需训练新模型，但推理时需多次调用VLM（每次缩放一次），VLM推理成为瓶颈。运行时分析表明，VLM提示提取时间远高于SR时间，限制了实时应用。
- **依赖VLM质量**：提示质量高度依赖于VLM的预训练能力和GRPO微调效果；若VLM产生误导性描述，可能导致图像内容错误。
- **潜在负面社会影响**：高保真超分辨率可能被用于篡改图像、伪造细节或未经授权重建敏感视觉信息，引发隐私和安全担忧。
- **实验覆盖有限**：主要测试了自然图像（DIV2K、DIV8K），未涉及医学、遥感等特殊领域；真实世界退化与训练时采用的合成退化可能存在差异。
- **评估指标局限**：所有指标均为无参考，缺乏客观配对比较（如PSNR/SSIM在极端倍数下不可用）。用户主观评价的样本量有限（25人）。
- **固定窗口策略**：当前使用固定512×512窗口进行递归放大，在全图超分辨率时需要多次运行，增加了复杂度且可能导致接缝伪影（虽然使用高斯加权缓解）。

（完）
