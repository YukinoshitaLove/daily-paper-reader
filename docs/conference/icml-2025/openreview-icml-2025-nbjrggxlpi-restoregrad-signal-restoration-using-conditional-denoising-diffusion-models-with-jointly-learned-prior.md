---
title: "RestoreGrad: Signal Restoration Using Conditional Denoising Diffusion Models with Jointly Learned Prior"
title_zh: RestoreGrad：使用条件去噪扩散模型与联合学习先验的信号恢复
authors: "Ching-Hua Lee, Chouchang Yang, Jaejin Cho, Yashas Malur Saidutta, Rakshith Sharma Srinivasa, Yilin Shen, Hongxia Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NbjrGgxLPi"
tags: ["query:real-ir"]
score: 10.0
evidence: 使用条件扩散模型与联合学习先验进行信号恢复
tldr: 本文针对条件扩散模型在信号恢复中先验信息利用不足的问题，提出联合学习数据相关先验的新框架。该方法使扩散模型能更充分利用退化观测中的有用信息，在图像恢复任务上取得优于标准高斯先验的性能。该框架可灵活嵌入现有条件扩散恢复模型中，为信号恢复提供了新的设计维度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 851, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1511, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1517, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1599, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1412, \"height\": 1442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1246, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1726, \"height\": 2021, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1610, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1776, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1778, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1769, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1773, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1777, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1777, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nbjrggxlpi/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1771, \"height\": 693, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1599, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 901, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1288, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1070, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1168, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 898, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1250, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nbjrggxlpi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1241, \"height\": 199, \"label\": \"Table\"}]"
motivation: 标准高斯先验丢弃了退化信号中的有用信息。
method: 联合学习数据相关先验与扩散模型。
result: 在恢复任务上性能优于常规条件扩散模型。
conclusion: 有效利用退化信息可显著提升扩散恢复效果。
---

## Abstract
Denoising diffusion probabilistic models (DDPMs) can be utilized to recover a clean signal from its degraded observation(s) by conditioning the model on the degraded signal. The degraded signals are themselves contaminated versions of the clean signals; due to this correlation, they may encompass certain useful information about the target clean data distribution. However, existing adoption of the standard Gaussian as the prior distribution in turn discards such information when shaping the prior, resulting in sub-optimal performance. In this paper, we propose to improve conditional DDPMs for signal restoration by leveraging a more informative prior that is jointly learned with the diffusion model. The proposed framework, called RestoreGrad, seamlessly integrates DDPMs into the variational autoencoder (VAE) framework, taking advantage of the correlation between the degraded and clean signals to encode a better diffusion prior. On speech and image restoration tasks, we show that RestoreGrad demonstrates faster convergence (5-10 times fewer training steps) to achieve better quality of restored signals over existing DDPM baselines and improved robustness to using fewer sampling steps in inference time (2-2.5 times fewer), advocating the advantages of leveraging jointly learned prior for efficiency improvements in the diffusion process.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在信号恢复（如语音增强、图像去雨雪）任务中，现有条件去噪扩散概率模型大多采用**标准高斯分布作为先验**。然而，输入的退化信号（如带噪语音）本身与干净信号存在相关性，蕴含着关于目标数据分布的有用信息，而标准高斯先验完全丢弃了这些信息，导致扩散模型的**训练收敛慢、推理采样步数多**。
- **整体含义**：本文旨在系统性地解决这一效率瓶颈，提出一种**学习驱动的扩散先验**框架，通过自动挖掘退化信号中的有用信息来构造更富信息的先验，从而显著提升条件扩散模型的训练与推理效率，以及恢复质量。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将**条件去噪扩散模型无缝集成到变分自编码器框架**中，利用退化信号与干净信号的关联性，通过联合学习一个由“先验网络”和“后验网络”构成的编码器，为扩散模型的逆向过程提供**数据自适应的、更具信息量的高斯先验**（其协方差由网络预测），取代固定的标准高斯先验。
- **关键技术细节**：
    - **框架整合**：以最大化条件数据对数似然为目标，推导出一个新的**证据下界**，它由三个损失项构成：
        - **潜在正则化项**：约束后验协方差的大小，防止其任意膨胀。
        - **去噪匹配项**：在**马氏距离**（由后验协方差加权）度量下，训练扩散模型预测噪声。
        - **先验匹配项**：通过 KL 散度最小化，使由**“先验网络”** 估计的分布接近由**“后验网络”** 估计的分布。
    - **双编码器设计**：训练时使用双编码器，而后验网络同时输入干净信号和退化信号，能比仅使用退化信号的方案提供更丰富的目标信息，从而引导先验网络学得更好；推理时仅需先验网络。
    - **算法流程**：训练时联合优化扩散模型、先验网络、后验网络；推理时，从先验网络采样的噪声出发，通过条件扩散模型的逆向过程生成恢复信号。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **数据集与场景**：
    - **语音增强**：VoiceBank+DEMAND 数据集。
    - **图像恢复（恶劣天气）**：RainDrop（雨滴）、AllWeather（多天气，含雪、雨、雨滴）数据集。
    - **图像恢复（其他任务）**：RealBlur 数据集（真实去模糊）、DIV2K 数据集（超分辨率）。
    - **泛化性测试**：使用 CHiME-3 数据集（OOD语音）、RainDS-Real 和 Snow100K-Real 数据集（真实世界图像）。
- **核心对比方法**：
    - **语音基线**：CDiffuSE（标准高斯先验）、PriorGrad（手工设计先验）。
    - **图像基线**：RainDropDiff 和 WeatherDiff（均为标准高斯先验），以及更广泛的 SOTA 模型（如 TransWeather, DTPM 等）。
- **评估指标**：覆盖全面，包括 PESQ、SI-SNR、SSNR、CSIG/CBAK/COVL（语音），以及 PSNR、SSIM、LPIPS、FID（图像）。

### 4. 资源与算力
- **语音增强任务**：训练 96 轮次，在 1 张 32GB 显存的 NVIDIA Tesla V100 GPU 上用时**1 天**完成。
- **图像恢复任务**：训练均采用 2 张 NVIDIA Tesla V100 GPU。
    - RainDrop 数据集：训练 9,261 轮次，用时**12 天**。
    - AllWeather 数据集：训练 887 轮次，用时**21 天**。
    - RealBlur 数据集：训练 853 轮次，每个子集用时**5 天**。
    - DIV2K 数据集：训练 2000 轮次，每个子集用时**3 天**。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平
- **实验数量**：作者进行了非常全面且充分的实验，覆盖了**语音和图像两大模态、多种任务、多个数据集**。
- **消融研究**：包括对**后验网络的作用**以及潜在正则化权重等关键超参数的影响进行了详细分析，表明设计是有效的。
- **鲁棒性分析**：测试了**不同推理采样步数**下的性能，证明 RestoreGrad 在步数减少时仍能保持高性能。
- **复杂度分析**：对比了**不同编码器大小**与性能、延迟、显存占用的关系，证明其轻量高效。
- **公平性**：所有对比均基于统一的开源基线模型（CDiffuSE, WeatherDiff），并采用与原论文相同的标准配置进行复现或对比，实验设置公平客观。

### 6. 论文的主要结论与发现
- **效率显著提升**：提出的 RestoreGrad 方法在训练时收敛速度比基线快 **5-10 倍**，推理时对采样步数的鲁棒性提高 **2-2.5 倍**。
- **性能更优**：在更少的训练轮次和推理步数下，RestoreGrad 仍能在语音和图像恢复任务中取得优于或媲美全量训练基线模型的信号质量。
- **先验有效性**：可视化结果表明，联合学习到的先验方差能够捕捉到信号的结构和层级变化，比各向同性的标准高斯先验更接近真实数据分布，从而简化了扩散轨迹。
- **方法通用性强**：该框架成功应用于语音增强、多种天气下的图像恢复、去模糊和超分辨率等广泛任务，展示了其作为通用信号恢复框架的潜力。

### 7. 优点：方法或实验设计上有哪些亮点
- **问题切入点新颖**：系统性地提出从“学习数据相关先验”角度解决扩散模型效率问题，理论推导扎实，将扩散模型与变分推理优雅地结合。
- **方法设计巧妙**：通过后验网络在训练阶段引入干净信号信息来辅助先验网络学习，巧妙地利用了信号恢复任务中退化版本与真实版本的相关性。
- **计算开销小**：所需的先验/后验编码器网络参数极少（仅为扩散模型的0.3% 至 2%），计算延迟和显存增加极低，性价比高。
- **实验详实严谨**：
    - **多模态、多任务**：在语音和图像两大类信号上进行了验证。
    - **对比全面**：既包括标准扩散基线，也包括同类型改进方法。
    - **分析深入**：包含了收敛性、鲁棒性、超参数、模型复杂度、泛化性能、生成多样性等多维度分析。
    - **可视化辅助**：对学习到的先验分布和扩散过程进行了可视化，增强了可解释性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **先验形式假设较简单**：目前仅将先验建模为**零均值高斯分布**，且协方差限定为对角阵。对于分布更为复杂的数据，这种简单假设可能不是最优的。
- **信号恢复任务限定**：方法专注于信号恢复场景，利用了x与y之间的特定关联，其应用范围不如无条件生成任务广泛。
- **超参数引入**：方法引入了潜在正则化权重和先验匹配权重等新的超参数，可能需要针对不同任务进行调整。
- **长尾分布泛化**：论文虽测试了在未见过的合成数据（OOD）和真实世界数据上的泛化性，但对于极端噪声或退化模式下的恢复效果可能仍有局限。

（完）
