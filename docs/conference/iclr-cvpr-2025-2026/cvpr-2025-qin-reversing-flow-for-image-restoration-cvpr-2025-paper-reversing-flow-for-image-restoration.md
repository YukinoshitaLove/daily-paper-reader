---
title: Reversing Flow for Image Restoration
title_zh: 反向流用于图像恢复
authors: "Qin, Haina, Luo, Wenyang, Wang, Libin, Zheng, Dandan, Chen, Jingdong, Yang, Ming, Li, Bing, Hu, Weiming"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Qin_Reversing_Flow_for_Image_Restoration_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出基于流的生成模型用于图像恢复，直接应对图像恢复任务
tldr: 针对现有生成式图像恢复方法将退化视为随机过程导致的低效与复杂性问题，提出ResFlow框架，利用连续标准化流将退化建模为确定性路径，并通过辅助增广过程实现可逆建模。实验展示了该方法在图像恢复中的高效性和优越性能，为流模型在恢复领域的应用开辟新途径。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1805, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1822, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1804, \"height\": 366, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1816, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1820, \"height\": 688, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qin-reversing-flow-for-image-restoration-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 520, \"label\": \"Table\"}]"
motivation: 现有生成式恢复模型将退化视为随机过程，效率低且复杂。
method: 提出ResFlow框架，用连续标准化流将退化建模为确定性路径，并增广辅助过程确保可逆性。
result: 在图像恢复任务中实现高效、高质量的恢复结果。
conclusion: 确定性流建模为图像恢复提供了高效替代方案。
---

## Abstract
Image restoration aims to recover high-quality (HQ) images from degraded low-quality (LQ) ones by reversing the effects of degradation. Existing generative models for image restoration, including diffusion and score-based models, often treat the degradation process as a stochastic transformation, which introduces inefficiency and complexity. In this work, we propose ResFlow, a novel image restoration framework that models the degradation process as a deterministic path using continuous normalizing flows. ResFlow augments the degradation process with an auxiliary process that disambiguates the uncertainty in HQ prediction to enable reversible modeling of the degradation process. ResFlow adopts entropy-preserving flow paths and learns the augmented degradation flow by matching the velocity field. ResFlow significantly improves the performance and speed of image restoration, completing the task in fewer than four sampling steps. Extensive experiments demonstrate that ResFlow achieves state-of-the-art results across various image restoration benchmarks, offering a practical and efficient solution for real-world applications.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：图像恢复（去雪、去雨、去雾、去噪、JPEG压缩伪影消除等）旨在从低质量（LQ）图像中恢复高质量（HQ）图像。由于退化过程会丢失信息，一个LQ图像可能对应多个可能的HQ图像，因此该逆问题具有严重的不适定性。  
- **现有方法局限**：基于扩散、分数匹配等生成式模型通常将退化过程建模为从HQ到噪声的**随机过程**。这种随机性虽然提供了自然图像先验，但反向恢复需从纯噪声开始，逐步重建图像结构，既低效（需要大量采样步数）又增加复杂性，且忽略了LQ图像中已有的结构信息。  
- **本文动机与含义**：作者提出 **ResFlow**，将退化过程重新定义为从HQ到LQ的**确定性、可逆的连续标准化流（Continuous Normalizing Flow）**，从而恢复时可直接从LQ开始反转，极大提升效率。通过引入辅助变量消解不确定性，使整个增广退化流完全可逆，在极少采样步数（<4步）内实现高质量恢复。

### 2. 方法论
- **核心思想**  
  - 将图像退化视作一个确定性常微分方程（ODE）描述的连续标准化流：  
    \( \frac{d z_t}{dt} = v(z_t, t) \)，其中 \( z_0 = [x_{HQ}; y_0] \)，\( z_1 = [x_{LQ}; y_1] \)。  
  - 由于原始退化过程损失互信息，导致 HQ→LQ 不可逆。为此，在状态中加入**辅助变量 \( y_t \)**，其任务是在反向过程中提供缺失信息以消除速度场的不确定性范围（uncertainty scope）。\( y_1 \) 设为高斯噪声（最大熵），\( y_0 \equiv 0 \)。
- **正向路径参数化**  
  - 正向路径采用欧氏空间的测地线插值：  
    \( z_t = \alpha_t z_0 + \sigma_t z_1 \)，满足 \( \alpha_0 = \sigma_1 = 1 \)，\( \alpha_1 = \sigma_0 = 0 \)。  
  - 提出**熵保持退化调度**：  
    - 数据部分：\( \alpha_t^x = 1 - t, \; \sigma_t^x = t \)（直线路径）；  
    - 辅助部分：\( \alpha_t^y = 1 - \sigma_t^y, \; \sigma_t^y = \beta(1 - t + \beta)^{-1}, \beta = 10 \)（保持整个 \( z_t \) 熵恒定）。
- **训练与推理**  
  - 通过**速度场匹配**优化神经网络 \( v_\theta \)：  
    \( \min_\theta \mathbb{E}_{x_0,x_1,y_0,y_1} \int_0^1 \lambda(t) \| v_\theta(x_t,y_t,t) - \dot{z}_t \|^2 dt \)，  
    其中 \( \dot{z}_t \) 由调度函数的导数计算，避免模拟 ODE。  
  - 损失加权 \( \lambda(t) \) 强调靠近 \( t=1 \) 的时刻（\( \lambda(t) = [\cos(\frac{\pi}{2}(t-2)) + 1]^\gamma \)），以应对退化后期速度预测困难。  
  - 推理时：从 LQ 图像 \( x_1 \) 和采样的 \( y_1 \sim \mathcal{N}(0,I) \) 出发，数值求解 ODE 至 \( t=0 \)，取 \( \hat{x}_0 \) 作为恢复结果。

### 3. 实验设计
- **数据集与任务**  
  - 去雪：合成 Snow100K，真实 RealSnow。  
  - 去雨：合成 Outdoor‑Rain，真实 LHP。  
  - 去雾：合成 Dense‑Haze，真实 NH‑HAZE。  
  - 真实去噪：SIDD。  
  - 散焦去模糊：DPDD（室内/室外/综合）。  
  - JPEG 压缩伪影去除：LIVE1、BSD500。
- **对比方法**  
  涵盖单步回归方法（NAFNet、Restormer）、Transformer方法（FocalNet、SCD‑Former）、扩散/分数匹配方法（SnowDiff、RainHazeDiff、DTPM）、以及经典GAN/VAE方法，具体见论文各表格。  
- **评估指标**  
  PSNR、SSIM、MAE、LPIPS。  
- **模型与训练**  
  采用UNet架构预测速度场，时间步 t 通过自适应层归一化注入。在 256×256 裁剪图像上训练，全分辨率测试，统一使用4个采样步数。

### 4. 资源与算力
- 论文全文**未明确说明**训练使用的 GPU 型号、数量、批次大小、单次训练时长等算力细节。仅提及使用 Adam 优化器，详细超参数放在附录。

### 5. 实验数量与充分性
- **实验覆盖广**：涉及6类图像恢复任务，11个不同数据集（合成与真实）。  
- **对比充分**：每项任务均与当时的主流及 SOTA 方法对比，包含回归式、生成式、扩散式等代表性工作。  
- **消融实验**：  
  - 逆向过程步数对性能的影响曲线。  
  - 辅助变量的分布（高斯 vs 常数）、调度（熵保持 vs 常数）及注入方式（Adapter、加和、通道拼接）的对比。  
- 实验设计客观，各方法在统一指标下比较，且论文提供了丰富的视觉对比。

### 6. 主要结论与发现
- ResFlow 将图像退化重新建模为确定性、可逆的连续标准化流，通过辅助变量消解不确定性，实现了极高效的恢复（≤4步）。  
- 在去雪、去雨、去雾、去噪、去模糊、JPEG伪影去除等多项基准上，**均取得新的最优定量结果**，且视觉质量优于对比方法。  
- 证明确定性流建模不仅能克服扩散模型低效的缺点，还能更好地保留图像细节，避免模糊和伪影。

### 7. 优点
- **理论创新**：首次将连续标准化流应用于一般图像恢复，用辅助过程处理信息丢失带来的不确定性，实现完全可逆的退化流。  
- **高效性**：仅需 4 步采样即达到 SOTA，推理速度远快于需要数十至上千步的扩散模型。  
- **设计优雅**：熵保持调度、时间相关损失加权等设计简单有效，无需繁琐的随机过程模拟。  
- **全面验证**：横跨多种任务、合成与真实数据、全指标评估，论证充分。

### 8. 不足与局限
- **算力信息缺失**：未提供训练所需的 GPU 类型、数量及训练时间，难以直接评估实际部署成本。  
- **退化类型覆盖**：主要针对噪声、雾、雨、雪、压缩伪影、散焦模糊，未涉及运动模糊、低光增强、超分辨率等其他重要退化。  
- **辅助变量设计**：虽然消融证明了当前设计的优越性，但更优的动态耦合方式仍有探索空间。  
- **极端退化**：在极度退化场景（如极低信噪比）下的鲁棒性未深入分析；且“确定性”假设可能在某些真实退化中不成立。  
- **对比公平性**：扩散类方法可能通过调整采样步数在效率与质量间平衡，论文未详细比较同等计算量下的性能。

（完）
