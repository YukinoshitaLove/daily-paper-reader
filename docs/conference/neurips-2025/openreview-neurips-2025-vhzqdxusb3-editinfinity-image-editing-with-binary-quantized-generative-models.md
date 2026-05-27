---
title: "EditInfinity: Image Editing with Binary-Quantized Generative Models"
title_zh: EditInfinity：基于二值量化生成模型的图像编辑
authors: "Jiahuan Wang, Yuxin Chen, Jun Yu, Guangming Lu, Wenjie Pei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vhzqdxuSB3"
tags: ["query:real-ir"]
score: 8.0
evidence: 使用二值量化生成模型进行图像编辑
tldr: 现有扩散模型在图像反演过程中因缺少精确监督而产生近似误差，限制了图像编辑性能。EditInfinity通过参数高效地适应二值量化生成模型，在保持生成能力的同时减少反演误差，实现高质量文本驱动图像编辑。实验表明，该方法在多个基准上达到先进水平，且计算开销极低。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 294, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 1237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 725, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 722, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1435, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 873, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1391, \"height\": 1803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhzqdxusb3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1406, \"height\": 1616, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 736, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 783, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1453, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhzqdxusb3/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 234, \"label\": \"Table\"}]"
motivation: 图像反演中的近似误差严重限制了扩散模型的编辑性能。
method: 提出参数高效地适应二值量化扩散模型，减少反演误差。
result: 在多个编辑任务上取得高质量结果，计算开销显著降低。
conclusion: 二值量化生成模型为高效图像编辑提供了新途径。
---

## Abstract
Adapting pretrained diffusion-based generative models for text-driven image editing with negligible tuning overhead has demonstrated remarkable potential. A classical adaptation paradigm, as followed by these methods, first infers the generative trajectory inversely for a given source image by image inversion, then performs image editing along the inferred trajectory guided by the target text prompts. However, the performance of image editing is heavily limited by the approximation errors introduced during image inversion by diffusion models, which arise from the absence of exact supervision in the intermediate generative steps. To circumvent this issue, we investigate the parameter-efficient adaptation of binary-quantized generative models for image editing, and leverage their inherent characteristic that the exact intermediate quantized representations of a source image are attainable, enabling more effective supervision for precise image inversion. Specifically, we propose EditInfinity, which adapts Infinity, a binary-quantized generative model, for image editing. We propose an efficient yet effective image inversion mechanism that integrates text prompting rectification and image style preservation, enabling precise image inversion. Furthermore, we devise a holistic smoothing strategy which allows our EditInfinity to perform image editing with high fidelity to source images and precise semantic alignment to the text prompts. Extensive experiments on the PIE-Bench benchmark across add, change, and delete editing operations, demonstrate the superior performance of our model compared to state-of-the-art diffusion-based baselines. Code available at: https://github.com/yx-chen-ust/EditInfinity.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于扩散模型的文本驱动图像编辑方法（如NTI、P2P、RF-Edit等）在“图像反演”步骤中，由于没有中间生成的精确监督信号，只能近似估计源图像的生成轨迹，导致反演误差，严重限制了编辑性能（背景保持不足、文本对齐不准确）。
- **研究动机**：二值量化生成模型（如Infinity）具有一个天然优势——对于任意图像，其精确的中间量化表示可以直接获得（通过token-wise量化），从而为反演提供精确监督，有望克服扩散模型的固有缺陷。
- **整体含义**：本文首次将经典的“反演-编辑”范式应用于二值量化生成模型，探索参数高效的自适应方法，实现高质量、高保真的文本驱动图像编辑。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 将图像编辑视为“精确反演 + 受控编辑”两步过程，利用二值量化模型的可精确监督特性，提升反演精度；再通过多尺度自回归平滑混合，实现局部编辑与全局保真。

### 关键技术细节

1. **图像反演（Image Inversion）**
   - 将反演建模为优化问题，损失函数为交叉熵：
     \[
     L_{inv} = -\frac{1}{K}\sum_{k=1}^{K} \left[ R^{sou}_k \cdot \log p(R^{inv}_k | R^{sou}_{<k}, \Psi(t)) \right]
     \]
     其中 \(R^{sou}_{1:K}\) 是源图像的精确量化token（通过Binary Spherical Quantization获得），作为真值监督。
   - **文本提示校正（Text Prompting Rectification）**：冻结Infinity全部参数，仅优化20个可学习提示token \(t_l\)，结合源提示 \(t_{sou}\) 和指令提示 \(t_{ins}\)，缩小语义差距。
   - **图像风格保持（Image Style Preservation）**：在文本校正后，使用LoRA（秩分解低秩矩阵）微调Infinity的FFN层，以保持源图像的整体结构和风格。

2. **图像编辑（Image Editing with Holistic Smoothing）**
   - **分段线性平滑核（Piecewise Linear Smoothing Kernel）**：
     \[
     G_{i,j} = \begin{cases}
     0, & d_{i,j} \le \tau_1 \\
     \frac{d_{i,j}-\tau_1}{\tau_2-\tau_1}, & \tau_1 < d_{i,j} < \tau_2 \\
     1, & d_{i,j} \ge \tau_2
     \end{cases}
     \]
     其中 \(d_{i,j}\) 是token位置到编辑掩码 \(M\) 的曼哈顿距离，\(\tau_1=1, \tau_2=4\)。
   - **多尺度自回归编辑**（Algorithm 1）：在每一尺度 \(k\)，生成目标token \(R^{tar}_k\)，然后与源token \(R^{sou}_k\) 按 \(G\) 加权混合得到编辑token \(E^{tar}_k\)，再下采样作为下一尺度的条件。最终解码得到编辑图像。

## 3. 实验设计

- **数据集/场景**：PIE-Bench（Prompt-based Image Editing Benchmark），包含700个测试用例，覆盖9种编辑类型（Add/Change/Delete Object、Change Content/Pose/Color/Background/Material/Style）。
- **对比方法**：
  - 开源方法：Diffusion UNet模型（P2P、MasaCtrl、P2P-Zero、NTI、PnP-Inv、NP），Diffusion Transformer模型（StableFlow、RF-Edit）。
  - 闭源方法：Gemini 2.0。
- **评价指标**：7个指标，分为两类：
  - 背景保持：PSNR、MSE、LPIPS、SSIM。
  - 文本对齐：Whole CLIP Score、Edited CLIP Score、IR（Image Reward）。
- **用户研究**：60名志愿者，从PIE-Bench“random class”中抽取140张图像，每人随机分配20个编辑任务，在五种方法（PNP-Inv、NTI、StableFlow、RF-Edit、EditInfinity）中匿名选择最佳结果。

## 4. 资源与算力

- 反演阶段：训练可学习提示和LoRA，使用2块NVIDIA L20 GPU。
- 编辑阶段：单块NVIDIA L20 GPU。
- 反演时间：107.06秒（平均）；每次编辑时间：3.64秒（比其他方法快7倍以上）。
- 未说明具体训练epoch数（LoRA训练20次迭代），但作者在消融实验中指出20次迭代为最优平衡点。

## 5. 实验数量与充分性

- **实验数量**：
  - 主表（Table 1）在PIE-Bench全量700个用例上，与9种方法对比，报告7个指标。
  - 图5给出任务级LPIPS和CLIP分数。
  - 消融实验：可学习提示+LoRA、平滑核（线性 vs 高斯）、自动掩码 vs 用户掩码、多尺度自回归 vs 非自回归、LoRA作用层（FFN vs Attn）。
  - 附加实验：人脸属性编辑（20张FFHQ图像）、复杂场景编辑（20张MagicBrush图像）。
- **充分性**：实验覆盖了所有主要编辑类型和主流基线，消融实验完整，用户研究增加了主观验证，公平性较好（各方法均使用其官方基础模型）。但未报告误差棒或统计显著性检验。

## 6. 主要结论与发现

- EditInfinity在所有7个指标上均优于所有对比方法，尤其在背景保持（PSNR=27.95, LPIPS=33.08×10⁻³, MSE=24.27×10⁻⁴, SSIM=92.12×10⁻²）和文本对齐（Whole CLIP=26.41, Edited CLIP=23.47, IR=5.88×10）上表现突出。
- 即使基础模型（Infinity-2B）在GenEval基准上与FLUX.1-dev相当或略逊，但其编辑性能仍大幅超越基于FLUX的方法，证明方法本身的有效性。
- 多次编辑场景下，编辑时间仅3.64秒（7倍于其他方法），适合迭代工作流。
- 用户研究中43.2%的结果被选为最佳，远高于其他方法。

## 7. 优点

1. **创新性**：首次将二值量化生成模型应用于图像编辑，利用精确量化token作为监督，解决了扩散模型反演误差的根本问题。
2. **效果卓越**：在所有指标上达到SOTA，尤其在背景保持和文本对齐的平衡上显著优于现有方法。
3. **高效性**：多次编辑场景下速度极快（3.64秒/次），且反演时间可复用。
4. **可解释性**：提出的分段线性平滑核和多尺度自回归编辑有清晰几何意义和算法流程。
5. **模块化设计**：文本提示校正、LoRA微调、平滑混合相互独立，消融实验验证各部分贡献。

## 8. 不足与局限

1. **实验覆盖有限**：主要在PIE-Bench上评估，未在更多样化的数据集（如ImagenEdits、COCO等）上验证。
2. **统计显著性缺失**：未提供误差棒或置信区间，结果的可重复性和稳定性未充分讨论。
3. **人脸/复杂场景实验样本少**：附加实验中人脸编辑仅20张，复杂场景仅20张，统计力不足。
4. **局限性声明**：在“风格改变”等极端任务中，背景无需保留时，结构保真度可能略有下降（虽然仍优于其他方法）。
5. **依赖用户掩码**：默认使用用户提供的掩码，虽可扩展为自动交叉注意力掩码，但准确性依赖于模型自身注意力质量。
6. **反演时间较长**：初始反演需107秒，比大多数扩散模型方法慢（虽然后续编辑快，但单次使用场景下总时间可能较长）。
7. **LoRA收敛问题**：需要控制LoRA训练迭代次数（20次最佳），否则过拟合会导致编辑意图丢失。

（完）
