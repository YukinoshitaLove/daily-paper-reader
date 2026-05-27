---
title: Fast constrained sampling in pre-trained diffusion models
title_zh: 预训练扩散模型中的快速约束采样
authors: "Alexandros Graikos, Nebojsa Jojic, Dimitris Samaras"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3kVM0m60Q5"
tags: ["query:real-ir"]
score: 8.0
evidence: 预训练扩散模型中的快速约束采样，可用于图像编辑
tldr: 现有预训练扩散模型在生成符合新约束的图像时效率低且不可靠。本文提出一种快速约束采样方法，无需反向传播，仅通过局部约束实现全局一致性，在图像修复和编辑任务上相比现有方法显著更快，且保持高质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1376, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 743, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1166, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1459, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 981, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1457, \"height\": 1301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1026, \"height\": 1792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1453, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1448, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1460, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1453, \"height\": 1122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1454, \"height\": 1122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1455, \"height\": 1124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1453, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1452, \"height\": 1127, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1432, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1414, \"height\": 1112, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3kvm0m60q5/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1451, \"height\": 916, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 712, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 722, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 759, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 679, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 681, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3kvm0m60q5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1056, \"height\": 362, \"label\": \"Table\"}]"
motivation: 预训练扩散模型在约束采样中反向传播慢且不可靠。
method: 提出一种无需反向传播的快速约束采样算法，仅局部约束传播。
result: 在图像修复和编辑任务上实现更快且可靠的生成。
conclusion: 该方法实现了高效且高质量的约束生成。
---

## Abstract
Large denoising diffusion models, such as Stable Diffusion, have been trained on billions of image-caption pairs to perform text-conditioned image generation. As a byproduct of this training, these models have acquired general knowledge about image statistics, which can be useful for other inference tasks. However, when confronted with sampling an image under new constraints, e.g. generating the
missing parts of an image, using large pre-trained text-to-image diffusion models is inefficient and often unreliable. Previous approaches either utilized backpropagation through the denoiser network, making them significantly slower and more memory-demanding than simple text-to-image generation, or only enforced the constraint locally, failing to capture critical long-range correlations in the sampled
image. In this work, we propose an algorithm that enables fast, high-quality generation under arbitrary constraints. We show that in denoising diffusion models, we can employ an approximation to Newton’s optimization method that allows us to speed up inference and avoid the expensive backpropagation operations. Our approach produces results that rival or surpass the state-of-the-art training-free
inference methods while requiring a fraction of the time. We demonstrate the effectiveness of our algorithm under both linear (inpainting, super-resolution) and non-linear (style-guided generation) constraints. An implementation is provided at https://github.com/cvlab-stonybrook/fast-constrained-sampling.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大规模预训练扩散模型（如 Stable Diffusion）通过学习海量图像-文本对获得了丰富的图像先验知识，可用于多种下游任务。然而，当需要在这些模型上施加新的约束（例如图像修复、超分辨率、风格引导）进行采样时，现有方法存在两大问题：一是利用反向传播通过去噪网络计算梯度，导致推理速度极慢且内存开销大；二是仅局部施加约束，无法捕获样本中的关键长程相关性，生成结果不一致。
- **背景**：此前工作如 LDPS、PSLD、FreeDoM 等通过反向传播梯度来优化样本，但时间成本高；MPGD 等不反向传播的方法则约束传播不足，尤其在需要长程依赖的任务（如大区域修复）上效果差。
- **整体目标**：提出一种快速、高质量的任意约束采样算法，避免昂贵反向传播，同时保持全局一致性。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：将约束优化视为寻找输入变化以使去噪输出更好满足条件的问题，引入牛顿优化方法的近似，用去噪器雅可比矩阵本身来近似其逆，从而避免反向传播。
- **关键技术细节**：
  - **问题定义**：在扩散采样每一步，优化目标为最小化约束代价 \(C(x_t) = (A\hat{x}_0(x_t) - y)^T (A\hat{x}_0(x_t) - y)\)（线性）或更一般形式 \(C(x_t) = (f(\hat{x}_0(x_t)) - y)^T (f(\hat{x}_0(x_t)) - y)\)（非线性）。
  - **传统梯度下降**：更新方向 \(e_t = J^T e\)，其中 \(J = \nabla_{x_t} \hat{x}_0(x_t)\)，\(e = A^T (A\hat{x}_0 - y)\)，需反向传播。
  - **牛顿方法方向**：理论上应求解 \(J e_t = e\)，即 \(e_t = J^{-1} e\)，但计算雅可比逆不现实。
  - **本文近似**：提出不精确牛顿步 \(e_t = J e\)（用雅可比本身代替逆），并利用有限差分近似计算：  
    \[
    e_t \approx \lambda \frac{\hat{x}_0(x_t + \delta e) - \hat{x}_0(x_t)}{\delta}
    \]
    仅需两次前向传播（一次计算 \(\hat{x}_0(x_t)\)，一次计算 \(\hat{x}_0(x_t + \delta e)\)），无需反向传播。
  - **合理性**：去噪器输入与输出高度相关，因此雅可比矩阵近似对称（理论最优解对称），且谱性质受控，选择合适的步长 \(\lambda\) 可保证残差单调递减。
  - **算法流程**（Algorithm 1）：初始化 \(x_T \sim \mathcal{N}(0, I)\)；对每个扩散时间步 \(t\)，迭代 \(K\) 次：计算误差方向 \(e\)（线性约束用伪逆，非线性约束用反向传播通过约束函数 \(f\)），再通过有限差分得到更新方向 \(e_t\)，更新 \(x_t = x_t - \lambda e_t\)；随后执行 DDIM 步下一步。支持线性与非线性约束。

### 3. 实验设计

- **数据集与场景**：
  - **线性约束**：Free-form inpainting（随机掩膜遮盖10-20%像素）和 8× super-resolution，使用 ImageNet 验证集前1000张（ctest10k 分割）；Box inpainting（遮盖25%的大区域）。
  - **非线性约束**：Style-guided generation（使用 CLIP/OpenCLIP 特征格拉姆矩阵匹配风格），参考 WikiArt 风格图与 PartiPrompts 文本提示共1000对；Mask-guided generation（使用人脸分割网络，约束分割图匹配），参考 FFHQ 验证集100张。
- **基准方法**：
  - LDPS、PSLD、FreeDoM（均需反向传播）、MPGD（无反向传播）、P2L（需额外视觉语言模型）、SD-Inpaint（微调模型作为上限）。
- **评价指标**：
  - Inpainting/Super-resolution：PSNR（↑）、LPIPS（↓）、FID（↓）。
  - Style：风格得分（Gram矩阵差，↓）、CLIP相似度（↑）。
  - Mask：mIoU（↑）、CLIP-FID（↓）。

### 4. 资源与算力

- **GPU**：NVIDIA RTX A5000 24GB GPU（单卡）。
- **运行时间**：Free-form inpainting 15秒（比 P2L 的30分钟快120倍）；Box inpainting 15秒；Super-resolution 1分钟；Style-guided 45秒（与 MPGD 相当）；Mask-guided 时间未明确列出，但计算量类似。
- **内存**：仅前向传播时约9GB，反向传播时约17GB。
- **未说明**：训练时长（论文不涉及训练）、总能耗等。

### 5. 实验数量与充分性

- **实验数量**：共3组主要实验（线性约束含两个子任务+大区域修复，非线性约束含风格和掩码引导），外加消融实验（优化步数 \(K\)、学习率 \(\lambda\)、有限差分步长 \(\delta\) 以及对比精确雅可比-向量乘积）。
- **充分性**：
  - 覆盖了常见线性和非线性约束场景，与多种基线方法对比，评价指标全面。
  - 消融实验验证了超参数影响，并展示了算法对不同设置的鲁棒性。
  - 在线性约束上报告了定量结果并给出定性示例；非线性约束上定量和定性均给出。
  - 对比了不同方法的运行时间，突出效率优势。
- **客观公平**：代码公开（GitHub），便于复现；基线结果引用原文或自行运行；对于没有公开代码的方法（如 P2L），直接引用论文数据并注明。

### 6. 主要结论与发现

- 提出的不精确牛顿近似方法在 Free-form inpainting 和 Box inpainting 上显著优于所有无训练基线，FID 指标大幅提升（例如 Box inpainting FID 42.01 vs. 最佳基线 FreeDoM 55.68），生成结果更接近微调模型（SD-Inpaint）。
- 在 8× super-resolution 上，结合文本提示（如自动生成 caption）可获得与最强方法 P2L 相当或更好的性能，同时时间仅为1分钟 vs. 30分钟。
- 在非线性约束（风格引导、掩码引导）上，风格得分最低（更匹配风格），且保持合理文本保真度；掩码引导的 mIoU 接近最优，图像质量优于 MPGD。
- 推理速度比需反向传播的方法快10倍以上，内存需求更小。

### 7. 优点

- **计算高效**：仅需两次前向传播，无需反向传播，推理时间缩短至秒级或分钟级，内存占用低。
- **全局一致性**：通过近似牛顿步，有效捕获长程像素相关性，尤其适合大区域修复等任务。
- **通用性**：支持线性与非线性（可微）约束，可部署于不同扩散模型（SD、Rectified Flow、一致性模型等），且易于与不同采样器（DDIM、PNDM）结合。
- **理论依据**：从牛顿优化方法出发，基于雅可比矩阵的对称性假设，给出不精确牛顿步的收敛条件，并用实验验证谱性质。
- **可复现**：提供代码和详细算法描述。

### 8. 不足与局限

- **高分类器无指导权重**：当使用高引导权重（\(w>10\)）时，需显著降低学习率，否则可能不稳定，限制了在某些任务（如多视图推理）中的应用。
- **蒸馏模型效果有限**：对少步数蒸馏模型（如 InstaFlow 仅5步），需要更多优化步数，抵消了快速推理优势；可能需要额外线搜索，增加时间。
- **非线性约束**：仍需通过约束函数 \(f\) 反向传播来计算误差方向 \(e\)（尽管不通过去噪器），对于非可微约束需人工定义局部梯度（如图15的量化约束）。
- **实验覆盖**：仅测试了图像域的约束（修复、超分、风格、掩码），未涉及时序数据、3D 或其他模态；未评估对生成多样性或模式坍塌的影响。
- **偏差风险**：使用预训练模型（如 Stable Diffusion）本身可能存在性别、种族等偏见，本文算法继承这些偏见；未讨论缓解措施。

（完）
