---
title: Ultra Lowrate Image Compression with Semantic Residual Coding and Compression-aware Diffusion
title_zh: 基于语义残差编码与压缩感知扩散的超低码率图像压缩
authors: "Anle Ke, Xu Zhang, Tong Chen, Ming Lu, Chao Zhou, Jiawen Gu, Zhan Ma"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=xiVuqZZ59O"
tags: ["query:real-ir"]
score: 8.0
evidence: 利用扩散模型与残差编码进行图像压缩与重建
tldr: 针对现有多模态大模型图像压缩框架碎片化、重建质量受限的问题，提出残差引导的超低码率压缩方法ResULIC。引入语义残差编码捕获压缩失真，并利用压缩感知扩散过程生成高质量重建图像，在极低码率下显著提升感知质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1693, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1674, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 840, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 854, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 818, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 835, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 529, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1336, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1250, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1222, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 887, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1561, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1255, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 816, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1596, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1572, \"height\": 1290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1546, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1565, \"height\": 1126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1562, \"height\": 1693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xivuqzz59o/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1344, \"height\": 2189, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 883, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1339, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1620, \"height\": 525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xivuqzz59o/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 759, \"height\": 336, \"label\": \"Table\"}]"
motivation: 低码率下图像压缩重建质量差，现有框架集成碎片化。
method: 设计语义残差编码与压缩感知扩散相结合的两阶段压缩框架。
result: 在超低码率下取得优越的重建保真度。
conclusion: ResULIC为超低码率图像压缩提供了生成式解决方案。
---

## Abstract
Existing multimodal large model-based image compression frameworks often rely on a fragmented integration of semantic retrieval, latent compression, and generative models, resulting in suboptimal performance in both reconstruction fidelity and coding efficiency. To address these challenges, we propose a residual-guided ultra lowrate image compression named ResULIC, which incorporates residual signals into both semantic retrieval and the diffusion-based generation process. Specifically, we introduce Semantic Residual Coding (SRC) to capture the semantic disparity between the original image and its compressed latent representation. A perceptual fidelity optimizer is further applied for superior reconstruction quality. Additionally, we present the Compression-aware Diffusion Model (CDM), which establishes an optimal alignment between bitrates and diffusion time steps, improving compression-reconstruction synergy. Extensive experiments demonstrate the effectiveness of ResULIC, achieving superior objective and subjective performance compared to state-of-the-art diffusion-based methods with -80.7\%, -66.3\% BD-rate saving in terms of LPIPS and FID.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容，生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机：** 在极低码率（<0.01 bpp）图像压缩场景下，传统及基于学习的压缩方法会产生过度平滑的纹理或丢失精细细节。现有集成多模态大模型（MLLM）、潜在空间压缩和生成模型的框架存在碎片化整合问题，导致重建保真度和编码效率的次优。
*   **核心问题：**
    1.  **多模态语义整合问题：** 如何有效整合多模态语义信息，在极低码率下最小化冗余并保持高感知保真度。
    2.  **压缩与生成对齐问题：** 如何对压缩比率与扩散模型中的噪声尺度进行建模，以实现跨不同压缩级别的高效、一致的重建。
*   **整体含义：** 论文旨在解决现有方法中语义冗余和压缩-生成过程协同不佳的问题，提出一种统一的、残差引导的超低码率图像压缩框架，以在保持高感知质量的同时，显著提升编码效率和重建保真度。

### 2. 论文提出的方法论

论文提出了名为 **ResULIC** 的残差引导的超低码率图像压缩框架，其核心方法论包括两大部分：

*   **语义残差编码（SRC）**：旨在以最少的比特率捕获和补偿压缩过程中的语义损失。
    *   **核心思想：** 摒弃直接传输原始图像完整的文本描述，改为编码原始图像与压缩后图像之间的“语义残差”。
    *   **语义残差检索（Srr）**：
        1.  使用 MLLM 分别获取原始图像 `x` 的全部文本描述 `fmllm(x)` 和解码压缩图像 `x'` 的文本描述 `fmllm(x')`。
        2.  将两个文本描述输入大语言模型（LLM），通过 `fmllm(x) ⊖mllm fmllm(x')` 的过程提取出仅存在于原始图像但压缩图像中缺失或不匹配的紧凑语义信息 `cres`。
        3.  **优势：** 这种方法能够根据潜在特征码率 `Rzc` 自适应地调整文本码率 `Rc`。当潜在码率很低时，`x'` 信息较少，`cres` 会包含更多信息，反之亦然，从而优化码率分配。
    *   **感知保真度优化器（Pfo）**：旨在进一步细化文本提示，提升重建图像与原始图像的细节一致性。
        1.  将 `cres` 初始化为可学习的连续嵌入 `P`。
        2.  在优化过程中，每次迭代将 `P` 投影到 CLIP 词表空间中最接近的离散词嵌入 `P'`。
        3.  计算一种损失函数 `Lpfo`，它结合了扩散模型的去噪损失和一个辅助 CLIP 相似度损失，并计算其关于 `P'` 的梯度。
        4.  利用梯度更新连续嵌入 `P`，经过多轮迭代，找到感知保真度最优的离散化文本提示。最终的文本提示通过高效的索引编码进一步压缩比特率。

*   **压缩感知扩散模型（CDM）**：旨在建立压缩比与扩散步骤之间的最优对齐，以提升重建效率和保真度。
    *   **核心思想：** 不再是传统的从纯噪声开始去噪，而是根据压缩图像的失真程度（由压缩比决定），从扩散过程的中间步骤 `Nr` (`Nr < T`) 开始，以压缩后的潜在特征作为基础进行加噪和去噪。
    *   **建模扩散步数与压缩级别：**
        1.  观察到比特率（bpp）、扩散步数（`Nr`）和重建质量之间存在强相关性。较低比特率的压缩图像失真较大，等效于扩散模型中更高噪声水平，因此需要使用更大的 `Nr` 来恢复。
        2.  提出比特率自适应的 `Nr` 选择策略，而非固定的扩散步数。
    *   **加噪过程（非马尔可夫前向过程）：**
        公式定义为 `zn = sqrt(bar_alpha_n) * z0 + sqrt(1 - bar_alpha_n) * (gamma_n * rho_res + epsilon_n)`。
        其中，`rho_res = zc - z0` 是压缩带来的潜在残差，`gamma_n` 是与最终步 `Nr` 相关的固定缩放因子。该过程确保起点不是纯噪声，而是包含压缩图像信息的噪声图像。
    *   **逆向采样过程：**
        基于前向过程的定义，推导出条件概率 `q(zn-1 | zn, z0, zc)` 的参数形式，`sigma_n` 参数可通过设为 0 实现确定性采样（DDIM）。采样时，根据预测的 `z_hat_0` 和公式 `zn-1 = iota_n * zn + zeta_n * z_hat_0 + sigma_n * epsilon` 逐步恢复图像。

### 3. 实验设计

*   **数据集**：
    *   **训练集**：使用 LSDIR 和 Flicker2w 数据集进行训练。
    *   **测试集**：在多个公开基准数据集上进行评估，包括 CLIC-2020（主要）、Kodak、DIV2K、Tecnick 和 MS-COCO 3K。
*   **基准方法**：与多种先进的编解码器进行比较，覆盖了传统、GAN和扩散模型等方法：
    *   **传统编解码器**：VTM。
    *   **基于 GAN 的压缩方法**：HiFiC, MS-ILLM。
    *   **基于扩散模型的压缩方法**：Text-Sketch, DiffEIC, CDC, PerCo (包括复现版和论文原版)。
*   **评估指标**：
    *   **感知保真度**：LPIPS, DISTS。
    *   **感知真实感**：FID, KID。
    *   **失真度**：PSNR, MS-SSIM。
    *   **率失真性能**：BD-Rate。
    *   **复杂度**：编码/解码时间。

### 4. 资源与算力

*   论文中**未明确提及**完整的训练所用的具体 GPU 型号、数量及总训练时长。
*   论文在复杂度分析部分提到，所有方法的推理时间测试是在一张 **RTX 4090 GPU** 上进行的。

### 5. 实验数量与充分性

实验设计相对全面且充分，具有较强的说服力。
*   **对比实验**：在 5 个不同数据集上，与 7 种以上的基线方法进行了全面的定量和定性（可视化）比较，覆盖了多种指标维度和比特率范围。
*   **消融实验**：系统性地验证了各个核心模块的有效性。
    *   **模块对比**：对比了 `+CDM`、`+Index Coding`、`+Srr`、`+Pfo` 等模块在 PerCo 和 ResULIC 框架下逐步叠加带来的 BD-Rate 收益。
    *   **CDM 有效性**：对比了固定/自适应扩散步数、从纯噪声开始（ANS方式）与使用论文提出的 CDM 方案，证明了 CDM 在性能和速度上的优势。
    *   **SRC 有效性**：验证了 Srr 模块在极低码率下带来的提升，特别展示了不同码率下文本比特占比的自适应变化，直观体现了其减少冗余的能力。
    *   **Pfo 模块**：对比了不使用优化器、使用 PEZ 方法与使用论文提出的 Pfo 方法的效果。
    *   **MLL M 的选择**：对比了使用 GPT-4o、Llama-3.2-11B 等多种在线/离线 MLLM 模型的性能，证明了框架的鲁棒性。
*   **公平性**：对于开源方法，使用其公开的预训练模型进行测试；对于非开源方法，使用论文汇报结果。同时，提供了对 PerCo 进行精细复现（适配 SD2.1）后的对比，确保了比较的公平和深度。

### 6. 论文的主要结论与发现

*   ResULIC 框架在超低码率下，无论是客观还是主观重建质量，均显著优于现有最先进的扩散模型压缩方法。
*   在 CLIC-2020 数据集上，相比 PerCo，ResULIC 在 LPIPS 上实现了 -80.7% 的 BD-Rate 节省，在 FID 上实现了 -66.3% 的 BD-Rate 节省。
*   **语义残差编码（SRC）** 能有效消除语义冗余，实现高效的文本与潜在特征联合比特率降低。
*   **压缩感知扩散模型（CDM）** 通过对压缩比和扩散步数的对齐建模，不仅显著提升了重建保真度（尤其在低码率下），还大幅减少了解码所需的去噪步骤数，降低了延迟。

### 7. 优点

*   **创新性框架**：提出了从传统“分离式”设计到“联合”框架的转变，通过残差信号将语义提取和生成过程有机统一。
*   **码率自适应性**：Srr 和 CDM 两个核心模块均具备根据真实码率动态调整的能力，使得框架在不同压缩比下都能高效工作。
*   **兼容性与灵活性**：CDM 保留了预训练 Stable Diffusion 的原始噪声调度，无需重新训练即可适配，大大降低了计算开销。Pfo 模块被设计为即插即用。
*   **效率提升显著**：CDM 大幅减少了扩散模型的推理步数，并将解码时间控制在具有竞争力的水平（如 0.43s/3步）。
*   **细致的实验验证**：消融实验设计扎实，清晰展示了每个模块的增益，并通过多 MLLM 验证证明了方法的鲁棒性。

### 8. 不足与局限

*   **编码复杂度较高**：虽然解码快，但编码端若开启 Pfo 优化（如每张 Kodak 图像需约 175 秒），会显著增加编码时间，限制了其在实时或高吞吐量场景的应用。
*   **对 MLLM 的依赖**：SRC 模块的效果依赖于外部 MLLM（如 GPT-4o）的性能，且使用在线商业 API 可能存在成本、稳定性和隐私问题。
*   **训练细节缺失**：论文未报告整体的训练算力消耗（如 GPU 类型、数量和时间），这使得复现的成本评估不完全透明。
*   **潜在偏差风险**：扩散模型作为生成模型，可能从训练数据中继承偏见，虽然论文声明其伦理上无虞，但在极端或有偏数据集下的生成结果可能存在不确定性。
*   **评估指标侧重**：虽然 FID/KID 表现优异，但 PSNR 等纯像素失真指标相比传统编解码器不占优。该方法更适合对感知质量要求高于像素保真度的应用。

（完）
