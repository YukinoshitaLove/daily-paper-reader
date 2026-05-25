---
title: "Epsilon-VAE: Denoising as Visual Decoding"
title_zh: Epsilon-VAE：去噪即视觉解码
authors: "Long Zhao, Sanghyun Woo, Ziyu Wan, YANDONG LI, Han Zhang, Boqing Gong, Hartwig Adam, Xuhui Jia, Ting Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oK4ot2wAJU"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出扩散过程作为视觉标记化中的解码器
tldr: 视觉标记化在高效生成模型中至关重要，但现有方法依赖自编码器的单步解码可能限制重建质量。受扩散模型启发，本文提出Epsilon-VAE框架，创新性地以扩散过程替代传统解码器，将图像重建转化为迭代去噪任务。具体地，编码器产生潜在表示，条件扩散模型据此逐步从噪声中恢复图像。实验结果显示，Epsilon-VAE在图像生成质量上显著超越标准自编码器，为视觉标记化开辟了新的设计范式，并证明了扩散机制在表示学习中的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1750, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 1291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1775, \"height\": 1400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ok4ot2waju/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1775, \"height\": 2184, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1601, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1138, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1353, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1250, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ok4ot2waju/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 725, \"height\": 224, \"label\": \"Table\"}]"
motivation: 克服传统自编码器单步解码在图像重建质量上的局限性。
method: 用扩散过程替换解码器，将去噪作为视觉解码机制。
result: 在图像生成质量上显著超过标准自编码器方法。
conclusion: 扩散过程可作为有效的解码策略，推动视觉标记化新范式。
---

## Abstract
In generative modeling, tokenization simplifies complex data into compact, structured representations, creating a more efficient, learnable space. For high-dimensional visual data, it reduces redundancy and emphasizes key features for high-quality generation. Current visual tokenization methods rely on a traditional autoencoder framework, where the encoder compresses data into latent representations, and the decoder reconstructs the original input. In this work, we offer a new perspective by proposing denoising as decoding, shifting from single-step reconstruction to iterative refinement. Specifically, we replace the decoder with a diffusion process that iteratively refines noise to recover the original image, guided by the latents provided by the encoder. We evaluate our approach by assessing both reconstruction (rFID) and generation quality (FID), comparing it to state-of-the-art autoencoding approaches. By adopting iterative reconstruction through diffusion, our autoencoder, namely Epsilon-VAE, achieves high reconstruction quality, which in turn enhances downstream generation quality by 22% at the same compression rates or provides 2.3x inference speedup through increasing compression rates. We hope this work offers new insights into integrating iterative generation and autoencoding for improved compression and generation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 当前视觉生成模型（自回归、扩散）严重依赖标记化（tokenization）将高维图像压缩为紧凑的潜在表示，主流框架采用自编码器：编码器压缩、解码器单步重建。
- 单步确定性解码在极端压缩下难以同时保持高重建精度与生成质量，且在速率-失真-感知三角权衡中存在局限。
- 受扩散模型迭代去噪机制启发，本文核心动机：**将“解码”重新定义为一种去噪过程**，用条件扩散模型取代传统单步解码器，通过渐进式精炼提升重建与后续生成的质量。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：保留自编码器的编码器 E，将解码器 G 替换为一个条件扩散模型。编码器输出 z = E(x) 作为条件引导去噪过程，从纯噪声 x_T 迭代恢复原始图像 x_0，即 p(x_{0:T} | z)。

- **建模与参数化**：
  - 采用 **Rectified Flow（直线流）** 参数化：`x_t = (1 − t)·x_0 + t·ϵ`，模型预测速度 `v_Θ(x_t, t, z) = ϵ − x`，训练目标为速度匹配损失 L_score。
  - 解码器架构以 **ADM UNet** 为主（也对比了 DiT），条件 z 经最近邻上采样后与 x_t 按通道拼接注入网络。
  - 推理时使用欧拉求解器沿概率流 ODE 迭代更新，默认采用 1~3 步，通过逆向对数时间步调度保证低步数下的稳定性。

- **训练目标组合**：
  - 将标准 VAE 的像素重建损失替换为 **分数匹配损失**（速度预测）。
  - **感知匹配**：利用预测速度估计一步重建 `x̂_t^0 = x_t − t·v_Θ(...)`，再计算其与真实图像 x 的 LPIPS 损失。
  - **去噪轨迹匹配（对抗性）**：设计时间相关的判别器，匹配真实轨迹 `(x_0, x_t)` 与模型生成轨迹 `(x̂_t^0, x_t)` 的分布，采用非饱和 GAN 损失加 R1 梯度惩罚。

- **噪声与时间调度**：
  - 对中间状态 x_t 乘以缩放因子 γ（如 0.6）降低信噪比，并做方差归一化。
  - 训练时从 logit-normal 分布采样时间步 t，侧重中间噪声水平。
  - 推理时采用逆向对数映射 (ρ_log) 安排时间步，在噪声较大区域布下更多步数，确保 1~3 步下的高质量采样。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - ImageNet（128×128、256×256、512×512）用于重建与生成评估。
  - COCO-2017 验证集用于重建泛化性评估。

- **Benchmark 设置**：
  - 轻量配置 **ϵ-VAE-lite**（编码器 6M 参数，下采样×16，潜通道 8）用于受控变量分析。
  - 标准配置 **ϵ-VAE-SD**（编码器 34M 参数，下采样×8，潜通道 4，与 Stable Diffusion 对齐）用于与 SOTA 比较。

- **对比方法**：
  - 自编码类：SD-VAE、SDXL-VAE、LiteVAE、VQGAN、ViT-VQGAN、Asym-VAE、Omni-VAE。
  - 离散标记化：MaskGIT、LlamaGen 等。

- **生成评估**：对所有自编码器抽取的潜在表示，固定使用 **DiT-XL/2** 作为下游潜在扩散模型，报告类别条件生成的 FID、IS、Precision/Recall。

### 4. 资源与算力
- 论文指出所有模型使用 **JAX/Flax** 实现，并在 **TPU-v5lite pod** 上训练。
- 推理吞吐量（images/sec）在 **Tesla H100 GPU** 上测量。
- 未明确提及 TPU 具体数量、训练总时长或显存消耗，也未给出不同模型配置下训练计算量的详细对比。

### 5. 实验数量与充分性：大概做了多少组实验，是否充分、客观、公平

- **实验规模较大，覆盖充分**：
  - 核心消融 7 阶段逐步改进（表 5），清晰展示架构、参数化、损失项、噪声/时间调度各自增益。
  - 架构对比：ADM 与 DiT 不同规模 8 种配置（图 2 左）。
  - 压缩率分析：潜通道维度 4/8/16/32，下采样因子 4/8/16/32（图 2 中右）。
  - 模型缩放：5 种解码器规模（B→H），并与参数匹配的 VAE 分组比较（表 8）。
  - 分辨率泛化：跨 128/256/512 分辨率，含微调策略（表 1）。
  - 与 SOTA 全面比较（表 2/3/4/10）：覆盖离散/连续标记化，带/不带引导的生成，多种分辨率。
  - 生成任务中验证了推理吞吐加速和不同下采样率的影响。

- **公平性**：
  - 几乎所有对比实验在相同编码器、相同超参下进行，解码器参数量近似时也做了对照。
  - 下游生成模型固定为 DiT-XL/2，仅改自编码器，突出潜在表示的影响。
  - 消融采用逐步叠加策略，归因明确。

### 6. 论文的主要结论与发现
- **去噪解码可行且高效**：用条件扩散替代单步解码，即便 1 步重建也优于同参数量 VAE（表 3）。
- **重建质量大幅领先**：标准 SD-VAE 配置下，ϵ-VAE-SD (H) 的 rFID 降低 35~50% 不等；在更高压缩率下优势更明显。
- **下游生成受益显著**：相同下采样率时，FID 相对提升约 22%（如 8×8 下从 11.63 降至 8.85）；可将下采样率提高 2 倍（8×8→16×16）且 FID 仍更优，带来 **2.3 倍**推理加速。
- **关键设计相辅相成**：直线流参数化 + 感知匹配损失 + 轨迹对抗损失 + 噪声/时间调度共同将最佳 NFE 缩至 1~3 步，实现高质量与效率的平衡。
- **分辨率泛化力强**：仅在 128² 训练的 ϵ-VAE 可直接重建 512² 图像，且继续保持对 SD-VAE 的优势。

### 7. 优点：方法或实验设计上有哪些亮点
- **新颖的解码范式**：将扩散过程嵌入自编码器，开创性地将“去噪”作为解码机制，为视觉标记化提供新方向。
- **损失协同设计精巧**：不仅是简单替换，而是将 LPIPS 和 GAN 损失适配到扩散轨迹域，使生成式训练目标与扩散目标互补，显著提升低步数下的性能。
- **推理灵活可控**：可通过调整采样步数（1~3）在质量和速度间按需权衡，适应不同延迟要求。
- **优秀的压缩-质量权衡**：在相同重建质量下能承受更高压缩比，直接加速下游潜在扩散模型。
- **实验全面且系统**：逐层消融揭示各组件贡献，多配置多维度的对比验证了方法的鲁棒性和普适性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **高分辨率下的计算瓶颈**：解码器仍为 UNet，处理 512² 以上图像时内存和吞吐开销较大，论文仅在讨论中展望了分块扩散方案，并未实现优化。
- **最佳步数范围窄**：实验表明推理 NFE 超过 3 步后重建质量反而下降（图 3 右），其原因与模型对非高斯轨迹拟合的假设有关，限制了进一步以增加步数换取质量的途径。
- **随机性可能引入“幻觉”**：尽管实验显示重建整体保真，但在极高压缩下（如 ×32），扩散的随机性可能导致恢复出原图中不存在的纹理细节，论文承认这一特性，但未提供定量控制其“分布外”程度的机制。
- **训练成本未量化对比**：相比标准 VAE，扩散解码器训练涉及额外的前向/反向计算及对抗训练，论文没有给出训练时间或能耗的对比数据。
- **局限于连续标记化**：当前工作针对潜在扩散模型所需的连续潜在表示，虽提及未来可扩展到离散 tokens，但未做验证，通用性有待延伸。

（完）
