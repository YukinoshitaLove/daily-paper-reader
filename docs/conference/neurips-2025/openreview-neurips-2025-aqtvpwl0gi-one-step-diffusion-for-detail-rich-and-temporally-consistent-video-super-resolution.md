---
title: One-Step Diffusion for Detail-Rich and Temporally Consistent Video Super-Resolution
title_zh: 一步扩散实现细节丰富且时间一致的视频超分辨率
authors: "Yujing Sun, Lingchen Sun, Shuaizheng Liu, Rongyuan Wu, Zhengqiang ZHANG, Lei Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=aqtVpWl0gI"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于一步扩散的视频超分辨率，保持时间一致性和细节丰富性
tldr: 针对视频超分辨率中空间细节与时间一致性难以兼顾的问题，尤其在使用预训练扩散模型时，本文提出双LoRA学习范式（DLoRAL）。该方法通过提取低质量视频中鲁棒的时间一致性先验，并在保持该先验的同时增强细节，实现了基于稳定扩散的一步式视频超分。实验表明，该方法在细节丰富度和时间一致性上均优于现有方案，且推理效率高。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-aqtvpwl0gi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1396, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aqtvpwl0gi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aqtvpwl0gi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aqtvpwl0gi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aqtvpwl0gi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 510, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-aqtvpwl0gi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 1400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aqtvpwl0gi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1297, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aqtvpwl0gi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1145, \"height\": 318, \"label\": \"Table\"}]"
motivation: 现有扩散视频超分方法在细节和时间一致性之间权衡，效果不佳。
method: 提出双LoRA学习范式，提取退化鲁棒的时间先验并增强细节，实现一步扩散。
result: 在真实视频超分任务上取得了更优的视觉质量和时间一致性。
conclusion: 双LoRA学习有效解决了视频超分中细节与一致性的矛盾。
---

## Abstract
It is a challenging problem to reproduce rich spatial details while maintaining temporal consistency in real-world video super-resolution (Real-VSR), especially when we leverage pre-trained generative models such as stable diffusion (SD) for realistic details synthesis. Existing SD-based Real-VSR methods often compromise spatial details for temporal coherence, resulting in suboptimal visual quality. 
We argue that the key lies in how to effectively extract the degradation-robust temporal consistency priors from the low-quality (LQ) input video and enhance the video details while maintaining the extracted consistency priors.
To achieve this, we propose a Dual LoRA Learning (DLoRAL) paradigm to train an effective SD-based one-step diffusion model, achieving realistic frame details and temporal consistency simultaneously.
Specifically, we introduce a Cross-Frame Retrieval (CFR) module to aggregate complementary information across frames, and train a Consistency-LoRA (C-LoRA) to learn robust temporal representations from degraded inputs.
After consistency learning, we fix the CFR and C-LoRA modules and train a Detail-LoRA (D-LoRA) to enhance spatial details while aligning with the temporal space defined by C-LoRA to keep temporal coherence. 
The two phases alternate iteratively for optimization, collaboratively delivering consistent and detail-rich outputs. During inference, the two LoRA branches are merged into the SD model, allowing efficient and high-quality video restoration in a single diffusion step. Experiments show that DLoRAL achieves strong performance in both accuracy and speed. Code and models will be released.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文文本，生成一份结构化、深入且客观的中文总结。

### 论文总结：一步扩散实现细节丰富且时间一致的视频超分辨率

#### 1. 核心问题与整体含义（研究动机和背景）

-   **研究问题：** 视频超分辨率（Video Super-Resolution, VSR）的核心挑战在于**同时重建丰富的空间细节并保持跨帧的时间一致性**。尤其是在利用预训练的生成式模型（如Stable Diffusion, SD）合成逼真细节时，这个问题变得尤为棘手。
-   **现有方法的局限：**
    *   现有基于SD的VSR方法通常为了追求时间连贯性而牺牲空间细节，导致视觉质量不佳。
    *   传统方法（如CNN、Transformer）倾向于产生过平滑的结果；GAN方法可能产生不自然的伪影，且难以泛化到真实场景。
    *   当前主流VSR方法将细节优化和时间一致性优化联合在一个模型中进行，导致它们相互冲突，难以达到最佳平衡。
-   **核心动机：** 论文认为，关键在于如何从低质量（LQ）输入视频中有效提取**对退化鲁棒的时间一致性先验**，并在**保持该先验的同时增强视频细节**。旨在解决细节与一致性之间的根本矛盾，实现高效、高质量的视频恢复。

#### 2. 方法论：核心思想、关键技术细节

-   **核心思想：提出一种双LoRA学习（Dual LoRA Learning, DLoRAL）范式**。将时间一致性学习和空间细节学习**解耦**到两个独立的LoRA模块中，通过**交替迭代训练**来协同优化，最终合并到一步扩散模型中进行高效推理。

-   **关键技术细节：**

    1.  **Cross-Frame Retrieval (CFR) 模块**：用于从退化的LQ视频帧中提取结构对齐的、对退化鲁棒的中间表示。它通过一个受注意力机制启发的操作，从相邻帧中聚合互补信息，并引入**可学习的阈值**和**top-k筛选**机制，避免无关噪声的干扰，为后续的细节增强提供稳定的“锚点”。

    2.  **双LoRA解耦架构**:
        *   **Consistency-LoRA (C-LoRA)**：在**时间一致性训练阶段**训练，负责从CFR提供的信息中学习鲁棒的时间表示，并强化时间对齐。
        *   **Detail-LoRA (D-LoRA)**：在**细节增强训练阶段**训练，负责在冻结C-LoRA和CFR模块的情况下，专注于提升空间细节。通过引入Classifier Score Distillation (CSD)损失来生成更丰富的细节。

    3.  **交替迭代训练（Dual-Stage Training）**：
        *   训练从**一致性阶段**开始，只更新CFR和C-LoRA，使用包含像素级、感知级和光流损失的一致性损失函数，先建立鲁棒的时间一致性基础。
        *   然后切换到**细节增强阶段**，冻结CFR和C-LoRA，只更新D-LoRA，使用包含CSD损失的增强损失函数，在保持时间一致性的前提下精炼细节。
        *   如此反复迭代，使模型均衡地收敛于兼顾时间连贯性和视觉保真度的解。在两个阶段之间，使用**渐进式重加权策略**（插值损失函数）进行平滑过渡，避免学习目标突变导致不稳定性。

    4.  **一步扩散推理**：在推理时，C-LoRA和D-LoRA均被激活并合并到冻结的扩散UNet中，只需**一步扩散**即可将LQ输入增强为高质量（HQ）视频帧，极大提升了推理效率。

#### 3. 实验设计

-   **数据集:**
    *   **训练数据：**
        *   **一致性阶段：** 使用REDS数据集（44,162帧，含丰富运动）和从Pexels精选的视频（外观和时序平滑）。
        *   **细节增强阶段：** 使用LSDIR图像数据集（纹理丰富）。为模拟视频序列，对每张图像应用随机像素级平移生成伪视频序列，以支持光流约束。所有数据均使用RealESRGAN退化流水线进行合成退化。
    *   **测试数据：**
        *   **合成数据集：** UDM10（10个序列，每序列32帧）、SPMCS（30个序列，每序列31帧）。
        *   **真实世界数据集：** RealVSR（50个序列，每序列50帧）、VideoLQ（50个序列，具有复杂退化）。

-   **Benchmark/对比方法：**
    *   **Real-ISR方法：** RealESRGAN, StableSR, OSEDiff (一步去噪扩散)。
    *   **判别式VSR方法：** RealBasicVSR。
    *   **扩散VSR方法：** Upscale-A-Video, MGLD-VSR, STAR。

-   **评估指标：**
    *   **全参考指标：** PSNR, SSIM（像素精度）；LPIPS, DISTS（感知质量）。
    *   **无参考指标：** MUSIQ, MANIQA, CLIPIQA, BRISQUE（图像质量）；DOVER（视频质量）。
    *   **时间一致性指标：** 平均扭曲误差 E*_warp（量化时序稳定性）。

#### 4. 资源与算力

-   **硬件环境：** 4 张 NVIDIA A100 GPU。
-   **训练批次与分辨率：** Batch size为16，序列长度为3，视频分辨率为 512×512。
-   **优化器与学习率：** Adam优化器，初始学习率 5×10^{-5}。
-   **推理时间：** 在A100 GPU上处理50帧 512×512 LQ输入进行4倍VSR，DLoRAL的推理时间为346秒，是Upscale-A-Video (3640s)、MGLD (4146s) 和 STAR (2830s) 的约8-12倍。
-   **总体参数量：** DLoRAL 为1300M，与其他方法相比适中且高效。
-   **未明确的训练时长：** 论文未明确报告单个训练阶段的总体训练时长（如epoch数或总步数），只提及使用46000张/步的一致性阶段数据和LSDIR图像用于细节阶段。

#### 5. 实验数量与充分性

-   **实验组数：** 实验较为充分。
    *   **主要定量对比：** 在4个主要的公开数据集（UDM10, SPMCS, RealVSR, VideoLQ）上，对7种对比方法和DLoRAL进行了多达11种指标的评估。
    *   **定性对比：** 提供了与多种方法在真实视频上的视觉效果对比（图3）以及高度体现时间一致性的时序剖面图对比（图4），直观展示了DLoRAL的优势。
    *   **消融实验：** 在VideoLQ4子集上对CFR、C-LoRA、D-LoRA三个关键模块进行了消融分析，验证了每个组件的有效性。
    *   **效率对比：** 直接对比了不同方法的推理步数、模型参数量和实际推理时间（表2），证明了方法的效率提升。
    *   **用户研究：** 邀请10位志愿者对12个真实LQ视频进行主观比较，DLoRAL获得了压倒性的偏好（77.5%的得票率），进一步证明了方法的实际效果。

-   **评估是否充分、客观、公平：**
    *   **充分性：** 实验覆盖了多种类型的数据集（合成与真实）、多种类型的评估指标（全参考、无参考、时序一致性）以及定性和定量、甚至主观评估，较为全面。
    *   **客观性：** 评估指标多样，且使用了公认的标准。用户研究虽然规模不大，但提供了一种主观验证方式。
    *   **公平性：** 与当前该领域最先进的方法（包括最新的STAR）进行了直接比较，且对比了Real-ISR方法以凸显VSR方法的时序特性，设计是公平的。
    *   **潜在偏差：** 消融实验仅在VideoLQ4一个小子集上进行，虽然代表性较强，但其结果可能不完全适用于所有场景。用户研究的参与者数量（10人）有限。

#### 6. 论文的主要结论与发现

-   DLoRAL **成功解决了VSR中细节和一致性不可兼得的矛盾**，能产生既细节丰富又时间稳定的结果。
-   **双LoRA解耦和交替训练策略是有效的**，允许每个分支专注于其特定的目标（时间一致性或细节增强），避免了联合优化带来的冲突。
-   **CFR模块能有效从退化视频中提取鲁棒的、结构一致的特征**，为后续的细节生成提供了坚实的“锚点”。
-   **性能卓越：** 在几乎所有感知质量指标（如CLIPIQA, MUSIQ, MANIQA, DOVER）上取得了**最优或次优**的成绩，尤其是在真实视频数据集上表现突出，同时保持了较低的推理误差E*_warp。
-   **效率极高：** 在**一步扩散**的框架下，DLoRAL在保持最佳视觉质量的同时，推理速度比现有扩散型VSR方法**快约10倍**。

#### 7. 优点

-   **方法论创新：** 首次将解耦式双LoRA学习范式引入Real-VSR，精准地解决了核心矛盾，思路清晰、巧妙。
-   **CFR模块的设计巧妙：** 通过可学习阈值和top-k机制，从退化帧中精准提取鲁棒的时间先验，是一个亮点。
-   **交替训练与平滑过渡策略：** 动态的双阶段训练及渐进式损失切换，保证了模型训练的稳定性和最终性能，考虑周全。
-   **高效实用：** 采用一步扩散设计，使得模型在获得顶级质量的同时，推理速度远超其他扩散方法，极具实用价值。
-   **实验设计全面：** 不仅包含全面的定量、定量对比和消融实验，还特别加入了**用户研究**和**效率对比**，使得结论的说服力大大增强。

#### 8. 不足与局限

-   **VAE的局限：** 模型继承了Stable Diffusion的8倍下采样VAE，导致其在恢复**非常精细的细节**（如小文字）时仍有困难。此外，这种高压缩率的VAE也可能**干扰时间一致性**的提取。
-   **量化指标的局限性：** 论文也指出，虽然E*_warp广泛用于评估时间一致性，但它与人类感知可能并不完全相关（过于平滑的结果有时反而能得到更低的E*_warp值），这暗示了现有时间一致性指标的改进空间。
-   **训练数据为合成：** 尽管使用了复杂的退化管线，但训练数据依然是合成的（即使是真实视频也经过了相同的退化处理），这可能导致模型在应对某些未在合成数据中建模的真实、罕见退化时性能受限。
-   **用户研究规模：** 用户研究的参与者和样本数量都比较有限，虽然结果具有倾向性，但严谨性上仍有提升空间。
-   **泛化性讨论不足：** 论文未对不同退化类型、运动速度跨度更大、分辨率更低等极端场景下的泛化能力进行深入探讨。

（完）
