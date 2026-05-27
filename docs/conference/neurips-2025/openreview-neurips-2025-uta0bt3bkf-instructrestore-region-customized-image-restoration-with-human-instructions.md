---
title: "InstructRestore: Region-Customized Image Restoration with Human Instructions"
title_zh: InstructRestore：基于人类指令的区域自定义图像恢复
authors: "Shuaizheng Liu, Jianqi Ma, Lingchen Sun, Xiangtao Kong, Lei Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=utA0BT3BKF"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于人类指令的区域定制图像恢复
tldr: "现有图像恢复方法对整个图像统一处理，无法按用户偏好进行区域定制。本文提出InstructRestore框架，根据人类指令对特定区域进行恢复。为此构建了一个包含536,945个三元组的大规模训练数据集，实验证明该方法在区域定制恢复任务上优于现有统一恢复方法。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1374, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1386, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1383, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1384, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 726, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 729, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uta0bt3bkf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1370, \"height\": 586, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-uta0bt3bkf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 729, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uta0bt3bkf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1422, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uta0bt3bkf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uta0bt3bkf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 728, \"height\": 290, \"label\": \"Table\"}]"
motivation: 现有图像恢复无法根据用户指令进行区域定制。
method: 提出数据生成引擎构建三元组数据集，训练扩散模型实现区域自定义恢复。
result: 在区域定制恢复任务上优于统一处理方法。
conclusion: 该框架实现了灵活的用户引导图像恢复。
---

## Abstract
Despite the significant progress in diffusion prior-based image restoration for real-world scenarios, most existing methods apply uniform processing to the entire image, lacking the capability to perform region-customized image restoration according to user preferences. In this work, we propose a new framework, namely InstructRestore, to perform region-adjustable image restoration following human instructions. To achieve this, we first develop a data generation engine to produce training triplets, each consisting of a high-quality image, the target region description, and the corresponding region mask. With this engine and careful data screening, we construct a comprehensive dataset comprising 536,945 triplets to support the training and evaluation of this task. We then examine how to integrate the low-quality image features under the ControlNet architecture to adjust the degree of image details enhancement. Consequently, we develop a ControlNet-like model to identify the target region and allocate different integration scales to the target and surrounding regions, enabling region-customized image restoration that aligns with user instructions. Experimental results demonstrate that our proposed InstructRestore approach enables effective human-instructed image restoration, including restoration with controllable bokeh blur effects and region-specific restoration with continuous intensity control. Our work advances the investigation of interactive image restoration and enhancement techniques.  Data, code, and models are publicly available at https://github.com/shuaizhengliu/InstructRestore.git.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有基于扩散先验的真实世界图像恢复方法（如DiffBIR、SUPIR等）对整个图像进行统一处理，无法根据用户偏好对不同区域进行差异化恢复。例如，用户可能希望保留或调整背景的散景（bokeh）模糊效果，或者对不规则纹理区域（如树叶）增强生成细节，而对结构区域（如建筑）保持高保真度。
- **整体含义**：本文首次提出**区域定制图像恢复**任务，即根据自然语言指令对图像中特定区域进行差异化恢复，同时保持其他区域不变。该工作为用户交互式图像恢复提供了新范式。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用ControlNet架构，将低质量（LQ）图像条件特征注入预训练Stable Diffusion（SD）模型，并通过在不同区域上使用不同的控制特征缩放系数，实现区域定制的恢复效果。用户指令包含目标区域描述和两个缩放系数（分别控制目标区域和其他区域的保真度/增强程度）。
- **关键技术细节**：
  - **数据集构建**：开发自动化数据生成管线，利用Semantic-SAM进行掩码提取，Osprey生成区域描述，再经Qwen大语言模型（LLM）反复迭代精炼得到最终三元组（高质量图像、区域描述、区域掩码）。构建了包含536,945个三元组的**Tri-IR**数据集，覆盖植物、建筑、动物等常见语义区域。
  - **模型架构**：基于ControlNet，包含预训练SD骨干（冻结）和可训练的ControlNet适配器，以及一个轻量级掩码解码器。掩码解码器利用ControlNet中文本-图像交叉注意力特征，以金字塔结构预测目标区域掩码。
  - **训练流程**：使用LQ图像（由Real-ESRGAN退化管线生成）和指令文本作为输入，SD文本提示使用区域描述。训练损失包括扩散损失和掩码交叉熵损失：
    \[
    \mathcal{L} = \mathbb{E}_{t,\epsilon} \left[ \| \epsilon - \epsilon_\theta(z_t, t, I_{LQ}, c_I, c_R) \|_2^2 \right] + \lambda \mathcal{L}_{mask}(\hat{M}, M)
    \]
  - **推理调制**：根据用户指令中的缩放系数 \(s_1\)（目标区域）和 \(s_2\)（其他区域），对各层控制特征进行调制：
    \[
    M_l = s_1 \cdot M_l + s_2 \cdot (1 - M_l), \quad F_{out}^l = F_{sd}^l + M_l \odot F_{cond}^l
    \]
    通过不同系数，可实现目标区域增强强度可调，其他区域保持原样或保留散景效果。

## 3. 实验设计

- **使用的数据集**：
  - **Instruct100Set**：100张真实世界图像，来源于RealSR、DRealSR、RAIM挑战赛，包含清晰语义区域。
  - **Bokeh测试集**：70张图像，来自EBB!数据集和Pixabay，具有明显前景和散景背景。
- **基准与对比方法**：与7种主流方法对比：RealESRGAN（GAN-based）、StableSR、DiffBIR、PASD、SeeSR、SUPIR、OSEDiff（均为扩散方法）。
- **评估指标**：
  - 参考指标：PSNR、SSIM（Y通道）、LPIPS。
  - 无参考指标：MANIQA、MUSIQ、CLIPIQA。
  - 额外对于散景任务，使用Bokeh IoU（通过D-DFFNet检测模糊背景）。
- **实验场景**：
  1. **局部增强**：在目标区域改变增强强度（\(s_1\)），保持其他区域强度不变（\(s_2=1\)），定量验证指令跟随能力（表2）。
  2. **与现有方法比较**：设置 \(s_1=0.8\)（目标区域增强）、\(s_2=1\)（其他区域高保真），在Instruct100Set上测试（表3）。
  3. **散景效果控制**：通过改变 \(s_2\) 调整背景模糊程度，或改变 \(s_1\) 调整前景细节，并与现有方法对比（表4）。
  4. 附录中还包含消融实验和指令变体鲁棒性测试。

## 4. 资源与算力

- 论文明确说明：训练在**2块A100 GPU**上进行，批次大小64，初始学习率5e-5，优化器AdamW。
- 训练过程分为两阶段：先在通用退化数据集上训练120k次迭代，再结合散景数据集训练14k次迭代（总计约134k次迭代）。
- 未明确报告训练总时长，但可合理推断为数十小时级别。

## 5. 实验数量与充分性

- 实验数量：共进行了**至少4组主要实验**（指令跟随定量、全方法比较、散景控制、视觉比较），以及附录中的消融和鲁棒性实验。
- 充分性评估：
  - **广泛性**：覆盖了两种核心应用场景（区域定制增强、散景保持/控制），且与7种对比方法进行公平比较。
  - **客观性**：使用了多种指标（参考+无参考），并在目标区域和全图分别计算，避免偏差。
  - **消融**：附录中对掩码解码器和特征调制机制进行了消融（文中提到但未提供具体数值，依赖读者参阅附录），整体设计较为充分。
  - 不足：未提供误差棒或统计显著性检验；Instruct100Set仅100张图像，规模中等，但论文使用了多个来源以提高多样性。

## 6. 主要结论与发现

- **结论**：InstructRestore实现了有效的**指令驱动区域定制图像恢复**，能够：
  - 按用户指令对指定区域进行连续增强强度控制（从高保真到高生成细节）。
  - 在恢复前景的同时，能够保留或调整背景散景效果，模拟不同景深。
  - 在定量和定性指标上，与统一恢复方法相比，在目标区域和全图质量上表现更优或相当，尤其在不破坏散景、避免区域过增强方面优势明显。
- **发现**：通过ControlNet特征缩放系数的区域差异化调制，可以在无需大量不同强度训练数据的情况下实现连续控制，是一种优雅且高效的解决方案。

## 7. 优点

- **任务创新**：首次定义并解决指令驱动的区域定制图像恢复问题，具有实际应用价值（如摄影后期、艺术创作）。
- **数据集贡献**：构建了大规模、高质量的三元组数据集Tri-IR（536,945样本），分辨率高（最长边>540px），图像质量好（MUSIQ>71），填补了该领域的空白。
- **方法巧妙**：利用ControlNet的特征缩放特性，仅需单一训练强度即可实现连续调节，无需对不同强度单独训练，降低了数据收集成本。
- **灵活可控**：支持两种主要模式（区域增强强度控制和散景效果控制），且用户可通过自然语言指令直观操作。
- **公开代码与模型**：承诺开源，有利于复现和后续研究。

## 8. 不足与局限

- **实例级支持缺失**：当前仅支持语义区域级（如“灌木丛”），不支持实例级（如“第二只狗”），需要实例分割和描述扩充。
- **指令格式限制**：用户需遵循固定模板（例如“make {region caption} clear with {s1}…”），虽然可用LLM转换自由输入，但增加了使用门槛。
- **全局质量优化不足**：框架侧重于局部定制，全图整体恢复质量仍有提升空间（如与其他方法相比某些指标略低）。
- **推理效率**：使用多步扩散采样，推理速度较慢，未探索单步或蒸馏方法。
- **实验覆盖**：
  - 测试集规模偏小（100/70张），泛化性需更大规模验证。
  - 未提供统计显著性分析（误差棒）。
  - 消融实验仅在附录中提及，主文未见具体数字，透明度不足。
- **潜在偏差**：数据集构建依赖自动管线（Semantic-SAM、Osprey、Qwen），可能存在错误标注或描述不准确，影响模型训练质量。
- **应用限制**：需用户提供明确区域描述和强度参数，对于非专业用户可能不够友好；掩码预测依赖于训练时见过的语义类别，对罕见或复杂区域可能失效。

（完）
