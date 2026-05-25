---
title: Compressed Image Generation with Denoising Diffusion Codebook Models
title_zh: 基于去噪扩散码本模型的压缩图像生成
authors: "Guy Ohayon, Hila Manor, Tomer Michaeli, Michael Elad"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=cQHwUckohW"
tags: ["query:real-ir"]
score: 5.0
evidence: 利用去噪扩散模型进行图像生成与压缩，引入基于码本的噪声采样
tldr: 本文提出去噪扩散码本模型，通过在逆向扩散中用预定义码本中的高斯向量替代标准噪声采样，同时生成高质量图像及其无损压缩比特流。该方法在极小的码本下仍保持样本质量和多样性，并可转化为高效的感知有损图像编解码器，达到最先进的感知性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1770, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 897, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1750, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1753, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1759, \"height\": 1838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1521, \"height\": 2175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1605, \"height\": 2183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1764, \"height\": 1525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1776, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1603, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1767, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1623, \"height\": 2156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1741, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1746, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1745, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1488, \"height\": 1547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1771, \"height\": 1348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1773, \"height\": 1332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 852, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cqhwuckohw/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1770, \"height\": 1812, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1723, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 764, \"height\": 1564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 911, \"height\": 1390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 911, \"height\": 1526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 911, \"height\": 1267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 909, \"height\": 1267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 909, \"height\": 1136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cqhwuckohw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1035, \"height\": 234, \"label\": \"Table\"}]"
motivation: 扩散模型生成高质量图像，但通常不产生压缩表示。
method: 将逆向扩散中的高斯噪声替换为从固定码本中选择的噪声样本。
result: 在极小码本下保持生成质量，并转化为高效的感知有损图像编码。
conclusion: 扩散模型可同时实现图像生成与压缩，扩展了生成模型的应用。
---

## Abstract
We present a novel generative approach based on Denoising Diffusion Models (DDMs), which produces high-quality image samples *along* with their losslessly compressed bit-stream representations. This is obtained by replacing the standard Gaussian noise sampling in the reverse diffusion with a selection of noise samples from pre-defined codebooks of fixed iid Gaussian vectors. Surprisingly, we find that our method, termed *Denoising Diffusion Codebook Model* (DDCM), retains sample quality and diversity of standard DDMs, even for extremely small codebooks. We leverage DDCM and pick the noises from the codebooks that best match a given image, converting our generative model into a highly effective lossy image codec achieving state-of-the-art perceptual image compression results.
More generally, by setting other noise selections rules, we extend our compression method to any conditional image generation task (e.g., image restoration), where the generated images are produced jointly with their condensed bit-stream representations.
Our work is accompanied by a mathematical interpretation of the proposed compressed conditional generation schemes, establishing a connection with score-based approximations of posterior samplers for the tasks considered.
Code and demo are available on our project's [website](https://ddcm-2025.github.io/).

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：去噪扩散模型（DDM）已成为图像生成的主流方法，但其采样过程依赖于从连续高斯分布中抽取噪声，导致表示空间无界且高度冗余。
- **核心问题**：能否在保持生成质量的前提下，将扩散模型的无限表示空间压缩为离散、有限的码本空间，从而自然地同时完成生成与无损压缩？
- **整体含义**：提出“去噪扩散码本模型”（DDCM），通过用预定义码本中的固定噪声替换随机高斯噪声，使每张生成图像都对应一组码本索引，实现生成与压缩的一体化，并可扩展至条件生成任务（如压缩、复原）。

### 2. 论文提出的方法论

- **核心思想**：
  - 在 DDPM 的逆向采样过程中，将每一步添加的噪声 \( z_i \sim \mathcal{N}(0,I) \) 替换为从预先生成且固定的码本 \( C_i \) 中选取的噪声向量 \( C_i(k_i) \)。
  - 每张生成图像由索引序列 \( k_{T+1},\dots,k_2 \) 唯一决定，从而可视为无损压缩的比特流表示。

- **关键技术细节**：
  - **码本构建**：对每个采样步骤 \( i \) 独立采样 \( K \) 个标准高斯噪声向量作为码本条目，码本在模型整个生命周期内固定。
  - **无条件生成**：随机选取索引，生成过程变为 \( x_{i-1} = \mu_i(x_i) + \sigma_i C_i(k_i) \)，初始化 \( x_T = C_{T+1}(k_{T+1}) \)。
  - **图像压缩**：基于残差匹配选择索引 \( k_i = \arg\max_k \langle C_i(k), x_0 - \hat{x}_{0|i} \rangle \)，其中 \( \hat{x}_{0|i} \) 为去噪器对 \( x_0 \) 的预测。
  - **可变码率**：通过调整码本大小 \( K \)、采样步数 \( T \) 以及采用匹配追踪（MP）策略（多噪声加权组合）来控制比特率。
  - **压缩条件生成**：推广至一般条件任务，索引选择准则为 \( k_i = \arg\min_k \mathcal{L}(y, x_i, C_i, k) \)。当损失函数选为 \( \mathcal{L}_P = \|C_i(k) - \sigma_i \nabla_{x_i}\!\log p_i(y|x_i)\|^2 \) 时，\( K\to\infty \) 下该过程收敛于后验概率流 ODE。
  - **图像复原应用**：针对逆问题 \( y = A x_0 \)，使用损失 \( \mathcal{L} = \|y - A(\mu_i(x_i)+\sigma_i C_i(k))\|^2 \)，实现零样本压缩复原。
  - **无参考质量优化**：对真实人脸复原，交替选择促进高感知质量和高保真的索引，并用无参考图像质量评价（NR‑IQA）指标在采样轨迹上贪心优化。

- **算法流程（文字描述）**：
  1. 预生成 \( T \) 个码本，每个包含 \( K \) 个标准高斯噪声向量。
  2. **压缩**：对目标图像从 \( x_T \) 开始，每一步根据预测残差选择最匹配的码本索引，并记录该索引。
  3. **解压/生成**：按记录索引从码本中取噪声，执行 DDCM 逆向采样即可重建图像。

### 3. 实验设计

- **数据集与场景**：
  - **图像压缩**：Kodak24、DIV2K、ImageNet 1K 256×256、CLIC2020，图像尺寸多为 512×512 或 256×256。
  - **零样本逆问题复原**：ImageNet 256×256，任务为 4× 超分辨率（bicubic）和着色。
  - **真实人脸复原**：CelebA‑Test、LFW‑Test、WebPhoto‑Test、WIDER‑Test，采用 512×512 的 FFHQ 预训练模型。
  - **无条件/条件生成评估**：ImageNet 256×256（类别条件）、MS‑COCO 描述（文本条件），使用 SD 2.1。

- **对比方法**：
  - 压缩：BPG、HiFiC、IPIC、PSC‑D/PSC‑P、PerCo (SD)、ILLM、CRDR‑R/CRDR‑D。
  - 逆问题复原：DPS、DDNM，并进一步比较其输出经 DDCM 压缩后的版本。
  - 人脸复原：PMRF、DifFace、BFRffusion，同样包含压缩版本。
  - 生成质量：标准 DDPM 采样。

- **评价指标**：
  - 感知质量：FID、KID、FD DINOv2、NIQE、CLIP‑IQA⁺、TOPIQ‑FACE。
  - 失真：PSNR、LPIPS、ProxPSNR。
  - 比特率：BPP（Bits Per Pixel）。

### 4. 资源与算力

- 论文中未明确报告训练或实验所使用的 GPU 型号、数量及总用时。
- 实验基于公开预训练模型（如 Stable Diffusion 2.1、ImageNet 256×256 DDPM、FFHQ 512×512 DDM），因此主要计算开销在于推理过程中的噪声选择和采样。
- 推断所需算力相对可控，因为 DDCM 仅改变噪声选取方式，不增加额外训练负担，但具体硬件配置未给出。

### 5. 实验数量与充分性

- **实验数量**：
  - 至少涵盖 4 个压缩数据集、2 种逆问题、4 个人脸评测集，以及额外的无条件/条件生成实验。
  - 对比了大量最新方法，且对压缩、复原等方法均提供了压缩版本的对比。
  - 消融实验包括不同码本大小 \( K \)（2～64 甚至更大）、不同采样步数 \( T \) 及其子采样策略、匹配追踪的 \( M \) 与 \( C \) 参数等。
  - 还分析了文本提示对压缩的影响、压缩后的条件生成（分类器和无分类器引导）以及图像编辑。

- **充分性与客观性**：
  - 实验设计较全面，覆盖生成、压缩、复原等多个任务，并与主流方法公平比较。
  - 对比方法均使用官方实现与推荐超参数，并在相同的预训练模型基础上评估。
  - 对于压缩，部分方法也采用与本文相同的扩散模型（如 PSC、PerCo），可比性较好。
  - 部分感知评价（如 FID）在较小数据集上采用补丁方式计算，符合惯例。
  - 总体实验较为充分，能够支撑论文结论。

### 6. 论文的主要结论与发现

- DDCM 在仅使用极小的码本（如 \( K=64 \)）时即可实现与标准 DDPM 相当的生成质量（FID 接近）。
- 基于 DDCM 的无损索引表示可将扩散模型转化为高效的感知有损图像编解码器，在低码率下同时取得最优的 FID 和优于感知导向方法的 PSNR/LPIPS。
- 将噪声选择策略推广至条件生成任务，可在生成压缩输出的同时实现图像复原、真实人脸恢复等，且平衡感知‑失真权衡。
- 数学上证明了当码本足够大时，基于特定损失的索引选择等价于后验概率流 ODE 的离散化。

### 7. 优点

- **创新性**：首次将扩散模型的噪声采样替换为离散码本选择，实现了生成与压缩的自然统一。
- **简单高效**：无须重新训练任何扩散模型，即插即用地应用于各种预训练 DDM，且比特流形成和压缩过程并不增加额外训练开销。
- **高压缩性能**：在极低码率下获得优异的感知质量和较低失真，尤其在感知‑失真权衡上显著优于同类方法。
- **通用性强**：同样的码本选择框架可拓展至多种条件生成任务，且支持梯度自由的感知指标优化。
- **理论支撑**：给出了压缩条件生成与后验采样之间的数学联系，增强了方法的可解释性。

### 8. 不足与局限

- **高码率性能瓶颈**：在较高码率时，受限于潜在空间 VAE 的编解码失真，压缩性能难以进一步提升；匹配追踪方案虽有改进，但仍弱于专门设计的压缩方法。
- **实验覆盖局限**：压缩实验主要针对特定模型（如 SD 2.1、ImageNet 256×256 无条件模型），未在更多样化的扩散模型（如基于 Transformer 的扩散模型）或更高分辨率上进行广泛验证。
- **未使用熵编码**：文中指出未对选定的索引序列进行熵编码，可能导致比特率偏高，未来可进一步压缩。
- **理论解释不足**：虽然证明了极限情况下的等价性，但对有限 \( K \) 时为什么简单的内积或损失最小化策略能够有效工作，缺乏深入的理论分析。
- **计算开销**：尽管无需训练，但编码过程需要对所有码本条目计算内积或损失，当 \( K \) 较大时计算量会增加。
- **编辑能力有限**：初步的图像编辑实验显示结构保持能力弱于某些专用方法。

（完）
