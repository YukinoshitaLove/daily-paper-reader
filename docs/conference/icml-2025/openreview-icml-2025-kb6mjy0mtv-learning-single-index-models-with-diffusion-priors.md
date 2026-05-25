---
title: Learning Single Index Models with Diffusion Priors
title_zh: 利用扩散先验学习单指数模型
authors: "Anqi Tang, Youming Chen, Shuchen Xue, Zhaoqiang Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kB6mJY0MTV"
tags: ["query:real-ir"]
score: 10.0
evidence: 利用扩散模型作为生成先验从单指数模型中恢复信号
tldr: 扩散模型在信号恢复中已取得显著成效，但在面对具有不连续或未知链接函数的单指数模型时，现有方法往往失效。本文提出一种扩散先验驱动的恢复框架，通过精巧的变分推断或优化策略，无需知晓链接函数即可从非线性测量中精确重建信号。在图像去噪、修复和稀疏重建等任务上，该方法均表现出优于传统方法的鲁棒性和精度，展示了扩散模型作为通用生成先验在复杂逆问题中的强大潜力，为图像复原和超分辨率等应用提供了新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 805, \"height\": 164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1730, \"height\": 831, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1758, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1691, \"height\": 1601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kb6mjy0mtv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 642, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 901, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1403, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1243, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1830, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1828, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1026, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kb6mjy0mtv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 711, \"height\": 360, \"label\": \"Table\"}]"
motivation: 解决扩散模型在非线性、不连续观测模型下信号恢复的难题。
method: 提出利用扩散先验对单指数模型进行高效信号恢复的算法。
result: 在图像去噪、修复等任务中取得领先的恢复精度与鲁棒性。
conclusion: 扩散先验可有效推广到复杂逆问题，为图像复原提供新范式。
---

## Abstract
Diffusion models (DMs) have demonstrated remarkable ability to generate diverse and high-quality images by efficiently modeling complex data distributions. They have also been explored as powerful generative priors for signal recovery, resulting in a substantial improvement in the quality of reconstructed signals. However, existing research on signal recovery with diffusion models either focuses on specific reconstruction problems or is unable to handle nonlinear measurement models with discontinuous or unknown link functions. In this work, we focus on using DMs to achieve accurate recovery from semi-parametric single index models, which encompass a variety of popular nonlinear models that may have {\em discontinuous} and {\em unknown} link functions. We propose an efficient reconstruction method that only requires one round of unconditional sampling and (partial) inversion of DMs. Theoretical analysis on the effectiveness of the proposed methods has been established under appropriate conditions. We perform numerical experiments on image datasets for different nonlinear measurement models. We observe that compared to competing methods, our approach can yield more accurate reconstructions while utilizing significantly fewer neural function evaluations.

---

## 论文详细总结（自动生成）

好的，以下是根据提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义
*   **研究问题**：如何利用扩散模型（DMs）作为生成先验，从半参数单指数模型（SIM）这种非线性观测中准确恢复信号。
*   **研究动机**：压缩感知等领域常用线性测量模型，但真实世界问题常涉及非线性测量，如1比特压缩感知。SIM是一种应用广泛的非线性模型，其特点是观测值由一个未知、可能不连续（如符号函数）的链接函数对线性投影结果进行逐元素变换得到。现有的扩散模型信号恢复方法大多限于线性模型或已知链接函数的非线性模型，无法有效处理SIM这类链接函数未知或非线性的情况。
*   **研究目标**：提出一种高效、无需知晓链接函数具体形式的扩散模型信号恢复方法，能够从SIM观测中精确重建原始信号。

### 2. 论文提出的方法论
*   **核心思想**：利用扩散模型的采样和反演过程来重建信号。关键洞察在于，某些统计量（如 \( \frac{1}{m}A^T y \)）可以看作是原始信号的一个带噪版本。通过理论分析确定噪声水平，并找到扩散模型的中间时间步，使得该时间步的信号-噪声比与带噪统计量相匹配。
*   **关键技术细节与算法流程（SIM-DMIS方法）**：
    1.  **统计量计算**：基于测量矩阵 \( A \) 和观测向量 \( y \)，计算统计量 \( \frac{1}{m}A^T y \)。理论分析表明，该统计量高概率地近似于 \( \mu x^* \)，其中 \( x^* \) 是待恢复信号，\( \mu \) 是一个由未知链接函数决定的非零常数，同时该统计量还包含一个噪声项。
    2.  **中间时间步确定**：通过比较统计量中噪声的理论水平与扩散模型前向过程中的噪声水平（\( \sigma_t / \alpha_t \)），找到一个中间时间步 \( t^* \)，使得两者相匹配。这一步避免了对链接函数知识的依赖，只需要调节一个超参数。
    3.  **部分反演与采样**：
        *   将缩放后的统计量 \( \alpha_{t^*} \cdot C'_s \cdot (A^T y / m) \) 作为输入，从时间 \( t^* \) 开始执行扩散模型的反演过程，直至达到时间 \( T \)。
        *   然后，再从时间 \( T \) 执行标准的扩散模型采样过程，生成最终的重建信号 \( \hat{x} = G \circ G^\dagger_{t^*}(\cdot) \)。
    4.  **理论保证**：论文在数据预测网络满足利普希茨连续性等假设下，证明了该方法的有效性，并给出了重建误差的上界。定理表明，重建误差取决于数值方法的离散步长（\( h_{max} \)）和生成器的利普希茨常数。

### 3. 实验设计
*   **数据集**：
    *   **FFHQ 256×256**
    *   **ImageNet 256×256**
*   **测量模型（非线性场景）**：
    *   **1比特测量**：\( y = sign(Ax^* + e) \)，链接函数不连续。
    *   **立方测量**：\( y = (Ax^*)^3 + e \)，链接函数连续但非线性极强。
*   **对比方法**：
    *   **QCS-SGM**：用于量化压缩感知的扩散模型方法（特定于1比特测量）。
    *   **DPS (后验采样) 变体**：
        *   **DPS-N**: 知道真实非线性链接函数的DPS。
        *   **DPS-L**: 不知道链接函数，将测量模型视为线性。
    *   **DAPS (退火后验采样) 变体**：
        *   **DAPS-N**: 知道真实非线性链接函数的DAPS。
        *   **DAPS-L**: 不知道链接函数，将测量模型视为线性的DAPS。
    *   **消融实验变体**：
        *   **SIM-DMFIS**: 执行完整反演和采样的方法。
        *   **SIM-DMS**: 仅执行部分采样的方法。

### 4. 资源与算力
*   论文在测量重建速度时提到，推理实验在单块NVIDIA GeForce RTX 4090 GPU上执行。对于FFHQ数据集上的10张验证图像，**SIM-DMIS**（150次网络函数评估）的推理时间为5.66秒，而**DAPS-N**（1000次评估）为160秒。
*   论文未明确提及模型本身的训练算力（如GPU型号和训练时长）。所使用的基础扩散模型均引用自现有工作（如DPS使用的FFHQ预训练模型、ADM的ImageNet模型），因此其训练是依赖前人工作完成的。

### 5. 实验数量与充分性
*   **实验组数量**：论文设计并实施了多维度对比实验，覆盖：
    *   **2个数据集** (FFHQ, ImageNet)。
    *   **2种非线性测量模型** (1比特，立方)。
    *   **7种对比方法/变体** (QCS-SGM, DPS-N, DPS-L, DAPS-N, DAPS-L, SIM-DMFIS, SIM-DMS)。
    *   **消融研究**：在CIFAR-10数据集上，对关键超参数（\( C_s \), \( C'_s \)）及NFE进行了详尽的消融实验。还补充了FFHQ上不同NFE的对比。
*   **充分性评价**：实验设计较为充分。它不仅与多种强基线方法对比，还通过自身方法的两种变体（SIM-DMFIS, SIM-DMS）清晰地展示了部分反演策略的必要性和优越性。在1比特测量这类极端非线性场景下，与利用真实链接函数的DPS-N/DAPS-N对比，充分证明了该方法在处理未知链接函数时的鲁棒性。
*   **公平性评价**：对比公平。对DPS/DAPS给出了“知晓真实链接函数”和“不知晓”的两种设定，清晰地划分了能力边界。所有方法都使用了预训练模型，并在标准测试集上报告了相同的评估指标（PSNR, SSIM, LPIPS）。

### 6. 论文的主要结论与发现
*   **方法有效**：提出的**SIM-DMIS**方法能在非线性测量模型下准确重建信号，尤其擅长处理链接函数未知或不连续的情况。
*   **性能优越**：在1比特和立方测量的实验中，**SIM-DMIS**在PSNR、SSIM和LPIPS指标上均显著优于所有对比方法。
*   **效率极高**：**SIM-DMIS**仅需150次网络函数评估（NFE）即可取得顶尖性能，远低于QCS-SGM（数万次）和DPS/DAPS变体（通常1000次），实现了极高的计算效率。
*   **策略优势**：实验证明，起始于中间时间的“部分反演”策略（SIM-DMIS）远优于“全反演”（SIM-DMFIS）和“直接部分采样”（SIM-DMS），是其成功的关键。

### 7. 优点
*   **无需链接函数知识**：这是与DPS-N等方法的根本区别，也是其处理现实世界未知非线性问题的核心优势。
*   **理论与实践的桥梁**：通过严谨的数学分析（引理2）推导出噪声水平，并将其直接用于指导算法设计（确定中间时间\( t^* \)），理论扎实，算法简洁。
*   **计算效率**：相比同类方法，其NFE需求数量级更小，重建速度快，具有很好的实用性。
*   **通用性强**：方法框架不限于特定测量模型，可灵活应用于满足特定条件的各种非线性问题。

### 8. 不足与局限
*   **链接函数的限制性假设**：理论推导依赖于链接函数满足两个特定条件（公式(20)和(21)）。这使得该方法无法直接处理诸如相位恢复（\( f(x)=x^2 \)）等重要问题，限制了其应用范围。
*   **对预训练扩散模型的依赖**：方法依赖于一个能够完美代表目标数据分布的预训练扩散模型。模型的偏见可能影响重建质量。
*   **超参数敏感性**：算法中引入了可调超参数（如 \( C_s \) 和 \( C'_s \)），尽管消融实验表明性能相对稳定，但在新任务中可能仍需要一定调整。
*   **实验覆盖的局限性**：实验主要关注图像域和特定非线性，其结论向其他数据类型（如音频、视频）和更复杂的连续非线性模型的推广性尚有疑问。同时，缺少对测量矩阵扰动或更复杂噪声模型的鲁棒性分析。

（完）
