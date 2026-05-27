---
title: "BitMark: Watermarking Bitwise Autoregressive Image Generative Models"
title_zh: "BitMark: 位自回归图像生成模型的水印"
authors: "Louis Kerner, Michel Meintz, Bihe Zhao, Franziska Boenisch, Adam Dziedzic"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=VSir0FzFnP"
tags: ["query:real-ir"]
score: 4.0
evidence: 生成模型的水印
tldr: 针对自回归图像生成模型在互联网上大量产出内容导致模型塌缩的问题，提出BitMark水印方法，嵌入人眼不可察觉的信号，防止模型被自身生成数据污染，保护模型长期训练稳定性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 676, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 726, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1428, \"height\": 1897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 1161, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 671, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1460, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 661, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 936, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1404, \"height\": 2022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1118, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1382, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 843, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1477, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1476, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1116, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 826, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 913, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 736, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 855, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1450, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 651, \"height\": 300, \"label\": \"Table\"}]"
motivation: 自回归生成模型输出大量充斥网络，可能被重新抓取训练导致模型塌缩。
method: 提出一种水印嵌入方法，在生成图像的比特级表示中嵌入不可见信号。
result: 实验表明该方法能有效防止模型塌缩且不影响生成质量。
conclusion: 水印是保证生成模型持续良性训练的重要手段。
---

## Abstract
State-of-the-art text-to-image models generate photorealistic images at an unprecedented speed. This work focuses on models that operate in a bitwise autoregressive manner over a discrete set of tokens that is practically infinite in size. However, their impressive generative power comes with a growing risk: as their outputs increasingly populate the Internet, they are likely to be scraped and reused as training data—potentially by the very same models. This phenomenon has been shown to lead to model collapse, where repeated training on generated content, especially from the models’ own previous versions, causes a gradual degradation in performance. A promising mitigation strategy is watermarking, which embeds human-imperceptible yet detectable signals into generated images—enabling the identification of generated content. In this work, we introduce BitMark, a robust bitwise watermarking framework. Our method embeds a watermark directly at the bit level of the token stream during the image generation process. Our bitwise watermark subtly influences the bits to preserve visual fidelity and generation speed while remaining robust against a spectrum of removal techniques. Furthermore, it exhibits high radioactivity, i.e., when watermarked generated images are used to train another image generative model, this second model’s outputs will also carry the watermark. The radioactive traces remain detectable even when only fine-tuning diffusion or image autoregressive models on images watermarked with our BitMark. Overall, our approach provides a principled step toward preventing model collapse in image generative models by enabling reliable detection of generated outputs. The code is available at https://github.com/sprintml/BitMark.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：当前最先进的文本到图像生成模型（如 Infinity、Instella）采用**逐位自回归**方式生成图像，输出大量逼真图像充斥网络。这些生成内容可能被模型本身或后续模型抓取并重新用作训练数据，导致**模型塌缩**——模型在自身生成数据上反复训练后性能逐渐退化，并放大原有偏差。
- **整体含义**：为防止模型塌缩，需要一种能够可靠识别生成内容并阻止其进入训练集的方法。水印技术可嵌入人眼不可察觉但可检测的信号，帮助模型所有者追踪和过滤自身生成的数据。然而，现有水印方法多针对扩散模型，缺乏对逐位自回归图像模型的专门方案，且扩散模型水印已被证明不具备**放射活性**（即无法在迁移训练后保持可检测性）。

### 论文提出的方法论

- **核心思想**：利用逐位自回归图像模型在比特级生成的特点，在生成过程中对**比特序列**进行软偏置，使生成的图像中包含更多预设的“绿色列表”中的比特模式，从而嵌入水印。检测时通过统计比特序列属于绿色列表的频率（green fraction）进行假设检验。
- **关键技术与流程**：
  - **嵌入**：将长度为 n 的所有可能比特序列划分为**绿色列表 G** 和**红色列表 R**（等大小）。对于每个待生成的比特 bj，若其与前面 n-1 个比特组成的前缀能构成绿色列表中的序列，则在 logit 中添加一个小偏置 δ，提高该比特被选中的概率。该过程对所有生成比特执行，最终使图像中绿色序列的比例显著高于自然图像的 50%。
    - 公式示意：pj = softmax(l(¬bj), l(bj)+δ) 或类似形式（取决于前缀是否在 G 中）。
  - **检测**：将图像通过模型自编码器重新编码为比特序列，统计所有长度 n 的比特窗口中属于绿色列表的个数 C，计算 z 值：`z = (C - γT) / sqrt(T * γ * (1-γ))`，其中 γ = |G|/2^n，T 为总序列数。若 z 超过阈值则判定为水印图像。
  - **关键设计点**：
    - **比特级优于令牌级**：由于图像自编码器在编码-解码过程中存在损失，令牌级水印的重叠率仅约 2.385%，而比特级重叠率可达 77.432%（见图 1），因此比特级水印更鲁棒。
    - **私有水印**：使用秘密密钥 K 和伪随机函数生成每步的绿/红列表，防止攻击者逆向。
- **算法流程**（文字描述）：
  1. 对于多尺度模型如 Infinity（算法 1）：对每个分辨率尺度 i，模型预测所有令牌的比特 logits；从第 n 比特开始，对每个比特根据其前缀是否在 G 中施加偏置 δ；采样得到比特值；最后解码为图像。
  2. 检测（算法 2）：对图像进行编码、量化、插值得到各尺度比特序列；计数所有绿序列；进行统计检验。

### 实验设计

- **数据集**：MS-COCO 2014 验证集（默认 10,000 张图像及对应 prompts）。
- **基准模型**：
  - 主模型：**Infinity-2B**、Infinity-8B、**Instella IAR**（均为逐位自回归模型）。
  - 扩展到扩散模型：**BiGR**（256x256 和 512x512）。
- **对比基线方法**：三种后处理水印方法——**RivaGAN**（消息长度 32）、**StegaStamp**（100）、**TrustMark**（100）。
- **攻击设置**：
  - 常规攻击：高斯噪声、高斯模糊、色彩抖动、随机裁剪、旋转（0°–180°）、JPEG 压缩（25%）、水平/垂直翻转。
  - 重建攻击：用 Stable Diffusion 2.1 VAE 编码-解码、**CtrlRegen+**（可控再生）。
  - 强攻击：**Watermarks in the Sand**（200 迭代，每轮 100 候选）、针对 BitMark 的 **Bit-Flipper 攻击**（假设攻击者知道所有细节，随机翻转绿序列中的比特）。
- **放射活性实验**：用 1,000 张水印图像微调相同架构（Infinity-2B）或跨架构（Stable Diffusion 2.1）模型，检测输出图像中的水印。
- **评估指标**：**TPR@1%FPR**（在 1% 假阳性率下的真阳性率）、FID、KID、CLIP Score，以及 z 值（均值和标准差）。

### 资源与算力

- 文中未明确说明训练从零开始所需的 GPU 型号、数量或时长。仅在附录 E.2 提及实验环境为：**Ubuntu 22.04，Intel(R) Xeon(R) Gold 6330 CPU + 单块 NVIDIA A40（40GB 显存）**。但未说明训练微调或大量生成所使用的 GPU 数量与时间。仅给出单张图像生成耗时约 2.58 秒（水印 vs 无 2.32 秒），检测耗时约 0.45 秒。

### 实验数量与充分性

- **实验数量**：论文提供了大量实验，具体包括：
  - 在 10,000 张图像上评估了不同 δ（1–5）对图像质量（FID、KID、CLIP）的影响。
  - 对 Infinity-2B、Infinity-8B、Instella IAR 各模型进行了至少 1,000 张图像的常规攻击与重建攻击测试（表 2）。
  - 单独对比了旋转角度对检测的影响（表 3、图 4）。
  - 对 Watermarks in the Sand 攻击在 1,000 张图像上测试（表 4）。
  - 对 Bit-Flipper 攻击进行了不同 ϕ 的消融（表 22）。
  - 放射活性实验：两个场景（同架构、跨架构），每种条件下 1,000 张水印图像用于微调；并测试了不同水印比例（5%、10%、25% 等）的检测效果（表 5、表 6）。
  - 扩展到 BiGR 扩散模型（5,000 张图像）的鲁棒性测试（表 21）。
  - 多组消融：红绿列表选择（表 7）、尺度选择（表 11）、自然图像假阳性率（表 18、表 19）。
- **充分性**：实验覆盖了多种攻击类型、多种模型、多种参数设置，并包含消融研究，设计较为全面。每个实验使用足够数量的样本（1,000–10,000 张），并报告均值和标准差。对比基线方法虽仅三种后处理方法，但已覆盖常见水印方案。整体实验设计客观、公平，符合 NeurIPS 标准。

### 论文主要结论与发现

1. **BitMark 在保持图像质量的前提下实现高检测率**：对于 Infinity-2B，δ=2 时 FID 从 33.36 降至 31.05，CLIP 得分基本不变；生成速度仅增加约 0.26 秒，检测仅需 0.45 秒。
2. **鲁棒性极强**：在大多数常规攻击下 TPR@1%FPR 接近 100%；对抗 CtrlRegen+ 攻击达到 91.6%（Infinity-2B）；对抗 Watermarks in the Sand 攻击达到 89.0% TPR@1%FPR（z 值仍高达 10.8）；对抗 Bit-Flipper 攻击即使最有效参数下 TPR 仍为 47.2%（但图像质量严重下降）。
3. **具有高放射活性**：无论是微调同架构 Infinity-2B 还是跨架构 Stable Diffusion 2.1，BitMark 在输出图像中均保持高检测率（>98% TPR@1%FPR）。即使仅有 5% 的水印数据，仍能产生显著分布偏移（Mann-Whitney U 检验 p < 1e-60）。
4. **比特级操作是关键**：比特级水印保留了比令牌级更高的编码一致性，是该方法成功的基础。

### 优点

- **创新性**：首次为逐位自回归图像模型设计生成时水印，填补了该领域空白。
- **实用性**：水印嵌入几乎不影响生成速度和图像质量，检测快速（<0.5s），易于部署。
- **鲁棒性全面**：不仅针对常规图像变换，还针对专门的水印去除攻击（CtrlRegen+、Watermarks in the Sand）及自适应 Bit-Flipper 攻击均表现良好。
- **放射活性**：水印可跨模型、跨架构传递，对防止模型塌缩具有实际应用价值。
- **设计简洁有效**：基于 KGW 思想但成功迁移至比特级，并通过实验验证了比特级优于令牌级。
- **实验充分**：涵盖多种攻击、多种模型、参数消融，并分析了自然图像假阳性率。

### 不足与局限

- **旋转鲁棒性有限**：对于大于 ±30° 的旋转，TPR 显著下降（±50° 时仅 56.8% TPR@1%FPR）。虽然可通过旋转校正预处理提升，但仍为实际应用的潜在瓶颈。
- **δ 需手动调节**：δ 超过 3 后图像质量急剧劣化（FID 从 29.61 升至 127.44），限制了最大水印强度。
- **仅适用于比特级自回归模型**：无法直接应用于传统扩散模型或非比特级自回归模型（如 VAR、RAR），虽在 BiGR 扩散模型上展示了可扩展性，但需额外处理（如添加噪声）。
- **对强攻击可能存在性能下降**：在 Bit-Flipper 攻击下，当 ϕ=2.2 时 TPR@1%FPR 降至 47.2%，虽图像质量严重损失，但理论上攻击者可能接受一定质量损失以移除水印。
- **False Positive 率在超大规模场景下可能成为问题**：虽然当前 1% FPR 在 1,000 张图像上可接受，但在万亿级数据中 1% 可能导致大量误检。作者提到需设置更严格的阈值或依赖模型所有者可承受的误报水平。
- **算力资源未充分披露**：未提供完整训练或大规模生成所需的 GPU 时间，仅给出单张图像生成和检测的耗时，难以评估整体部署成本。

（完）
