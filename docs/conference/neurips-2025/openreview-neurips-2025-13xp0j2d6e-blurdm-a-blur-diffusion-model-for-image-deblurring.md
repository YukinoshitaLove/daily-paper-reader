---
title: "BlurDM: A Blur Diffusion Model for Image Deblurring"
title_zh: "BlurDM: 用于图像去模糊的模糊扩散模型"
authors: "Jin-Ting He, Fu-Jen Tsai, Yan-Tsung Peng, Min-Hung Chen, Chia-Wen Lin, Yen-Yu Lin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=13xP0J2d6E"
tags: ["query:real-ir"]
score: 9.0
evidence: 扩散模型用于图像去模糊
tldr: 现有扩散模型用于去模糊时未充分利用模糊形成过程，BlurDM通过双扩散前向过程将噪声和模糊同时扩散到清晰图像，反向过程同时去噪和去模糊，显著提升动态场景去模糊性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1434, \"height\": 185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 590, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1074, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1398, \"height\": 1340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1410, \"height\": 1406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1403, \"height\": 1423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1403, \"height\": 1423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13xp0j2d6e/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1399, \"height\": 1406, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 678, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 743, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 702, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 775, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 704, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1457, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13xp0j2d6e/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 212, \"label\": \"Table\"}]"
motivation: 扩散模型在动态场景去模糊中的潜力未充分发挥，未利用模糊形成的物理过程。
method: 设计双扩散前向过程，同时扩散噪声和模糊；反向过程联合去噪和去模糊。
result: 在动态场景去模糊数据集上取得最优结果。
conclusion: 将物理模糊模型融入扩散过程能有效提升去模糊效果。
---

## Abstract
Diffusion models show promise for dynamic scene deblurring; however, existing studies often fail to leverage the intrinsic nature of the blurring process within diffusion models, limiting their full potential. To address it, we present a Blur Diffusion Model (BlurDM), which seamlessly integrates the blur formation process into diffusion for image deblurring. Observing that motion blur stems from continuous exposure, BlurDM implicitly models the blur formation process through a dual-diffusion forward scheme, diffusing both noise and blur onto a sharp image. During the reverse generation process, we derive a dual denoising and deblurring formulation, enabling BlurDM to recover the sharp image by simultaneously denoising and deblurring, given pure Gaussian noise conditioned on the blurred image as input. Additionally, to efficiently integrate BlurDM into deblurring networks, we perform BlurDM in the latent space, forming a flexible prior generation network for deblurring. Extensive experiments demonstrate that BlurDM significantly and consistently enhances existing deblurring methods on four benchmark datasets. The project page is available at https://jin-ting-he.github.io/BlurDM/.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：动态场景图像去模糊是一个高度病态问题，现有基于深度学习的去模糊方法（CNN、Transformer）受限于回归损失，常产生过平滑结果，缺乏高频细节。
- **背景**：扩散模型在图像生成中展现出卓越能力，但现有将扩散模型用于去模糊的工作（如HI-Diff、RDDM）未能有效利用模糊形成的物理本质——运动模糊源于连续曝光过程中光的累积，具有结构性和方向性，而非随机噪声。
- **动机**：弥合标准扩散过程与运动模糊形成过程之间的根本差异，通过将模糊形成过程的归纳偏置融入扩散框架，提升去模糊性能。为此提出 BlurDM（Blur Diffusion Model）。

## 2. 论文提出的方法论

### 核心思想
- 设计**双扩散前向过程**：同时在清晰图像上添加噪声和模糊（通过曝光时间递增模拟模糊累积）；**双去噪和去模糊反向过程**：联合估计并去除噪声残差和模糊残差，从而恢复清晰图像。
- 在潜在空间执行 BlurDM，作为灵活的先验生成网络，可即插即用地增强现有任何去模糊网络。

### 关键技术细节
1. **双噪声与模糊扩散过程**：
   - 定义清晰图像 \(I_0\)（短曝光）、模糊图像 \(B\)（全曝光）。前向过程在每个时间步 \(t\) 添加模糊残差 \(e_t\)（曝光区间 \([ \alpha_{t-1}, \alpha_t ]\) 的积分）和高斯噪声 \(\epsilon_t\)，状态更新公式：
     \[
     I_t = \frac{\alpha_{t-1}}{\alpha_t} I_{t-1} + \frac{1}{\alpha_t} e_t + \beta_t \epsilon_t.
     \]
   - 通过累积可一步得到最终状态：\(I_T = B + \bar{\beta}_T \epsilon\)，即完全模糊图像加噪声。

2. **双去噪与去模糊反向过程**：
   - 使用两个估计器：模糊残差估计器 \(e_\theta(I_t, t, B)\) 和噪声估计器 \(\epsilon_\theta(I_t, t, B)\)。
   - 基于 DDIM 确定性采样，反向更新：
     \[
     I_{t-1} = \frac{\alpha_t}{\alpha_{t-1}} I_t - \frac{1}{\alpha_{t-1}} e_\theta - \left(\frac{\alpha_t \bar{\beta}_t}{\alpha_{t-1}} - \bar{\beta}_{t-1}\right) \epsilon_\theta.
     \]

3. **三阶段训练策略**：
   - **第一阶段**：预训练 Sharp Encoder (SE)、Prior Fusion Module (PFM) 和去模糊网络，使用清晰图像 S 获得清晰先验 \(Z_S\)，通过 PFM 调制解码器特征。
   - **第二阶段**：训练 Blur Encoder (BE) 和 BlurDM，从模糊图像 B 生成扩散先验 \(Z_B^0\)，使用潜在-先验损失 \(\mathcal{L}_{\text{prior}} = \|Z_B^0 - Z_S\|_1\) 监督。
   - **第三阶段**：联合优化 BE、BlurDM、PFM 和去模糊网络，使用原去模糊网络的损失函数进行端到端训练。

4. **网络架构**：
   - SE 和 BE 结构相同：6 个残差块 + 4 个 CNN 层 + 2 个 MLP 层。
   - BlurDM 中两个估计器各包含 6 个 MLP 层。
   - PFM 为 1 个 MLP 层。
   - 扩散步数 \(T=5\)，\(\beta_{1:T}\) 从 0 均匀增加到 0.02，\(\alpha_{0:T}\) 从 0 均匀增加到 1。

5. **理论推导**：提供了 ELBO 变分下界、优化目标、确定性采样以及潜在空间 BlurDM 的理论合理性（泰勒展开证明）详见附录。

## 3. 实验设计

- **数据集**：GoPro（2103 训练 / 1111 测试）、HIDE（2025 测试）、RealBlur-J（3758 训练 / 980 测试，JPEG 格式）、RealBlur-R（相同分割，RAW 格式）。
- **基准模型**：MIMO-UNet、Stripformer、FFTformer、LoFormer 四个主流去模糊模型。
- **对比方法**：
  - 每个基线与其 BlurDM 增强版本对比。
  - 在先验生成方法比较中，对比 MLP、DDPM、RDDM。
  - 与其他扩散方法 HI-Diff、RDDM 直接比较。
- **评估指标**：PSNR ↑、SSIM ↑、LPIPS ↓。
- **消融实验**：
  - 噪声/模糊估计器有效性（表 2）
  - 不同先验生成方法（表 3）
  - 潜在空间残差建模可视化（图 6）
  - 迭代步数影响（图 7、表 8）
  - 各训练阶段贡献（表 6）
  - 计算开销（表 4）
  - 训练时间成本（表 7）

## 4. 资源与算力

- 论文中明确说明：FLOPs、参数量和推理时间在 “Analysis of BlurDM’s Computational Overhead” 中给出。BlurDM 平均仅增加 4.16 G FLOPs、3.33 M 参数和约 9 ms（256×256 图像，RTX 3090）。
- 训练时间：以 MIMO-UNet 为例，Baseline 需 66.7 小时（3000 epoch），BlurDM 完整三阶段（Stage1 3000 + Stage2 500 + Stage3 3000）需 141.4 小时，增加约 8%。
- **未明确说明**：训练所用的 GPU 型号和数量（推理时为 RTX 3090，但训练部分未注明具体型号和并行数量）。

## 5. 实验数量与充分性

- **实验数量充分**：共进行了 8 张主表、1 张图（图 7）和 4 张附录表格，涵盖 4 个数据集、4 个基线模型、多种消融设置（估计器、先验方法、迭代步数、训练阶段、计算开销、训练成本），还额外对比了不同扩散步数下 RDDM 与 BlurDM 的性能。
- **客观性与公平性**：
  - 所有对比均在相同训练配置下进行（学习率、epoch、batch size、优化器等）。
  - Baseline 使用各自默认设置，BlurDM 仅作为附加模块，未改动原网络参数。
  - 性能增益统计为多次实验平均值，尽管未给出误差条，但结果稳定一致。
- **充分性评价**：实验设计较为全面，覆盖了合成和真实数据集、多种指标、多种骨干网络、多种消融，结论具有说服力。

## 6. 论文的主要结论与发现

- BlurDM 在四个数据集上一致显著提升四个去模糊基线模型：平均 PSNR +0.53 dB，SSIM +0.004，LPIPS -0.0028。
- 双扩散（噪声+模糊）优于仅噪声或仅模糊扩散，验证了物理建模的有效性。
- BlurDM 作为先验生成网络比标准 DDPM 和 RDDM 更有效，体现了模糊形成归纳偏置的价值。
- 仅需 5 次迭代即可达到峰值性能，计算开销小，适合实际部署。
- 潜在空间 BlurDM 能够学习从模糊到清晰的渐进表示，具有可解释性。

## 7. 优点

- **物理启发式设计**：将连续曝光积累的物理过程直接编码进扩散框架，具有强可解释性。
- **即插即用**：作为通用先验生成模块，仅增加少量计算即可显著提升各种现有去模糊网络性能。
- **训练策略有效**：三阶段训练充分利用清晰先验的监督信息，避免了对逐步模糊残差标签的依赖（仅需 blur-sharp 对）。
- **高效迭代**：T=5 步就能达到最佳，远少于传统扩散模型（数百步）。
- **实验全面**：在合成和真实数据集、多种架构、多种指标上验证，消融充分。

## 8. 不足与局限

- **应用范围有限**：论文明确指出 BlurDM 针对运动模糊设计，不适用于散焦模糊（defocus blur），因为散焦模糊是深度依赖且非时间累积。
- **训练时间增加**：完整三阶段训练时间相比 baseline 增加约 8%（以 MIMO-UNet 为例），但性能增益显著。
- **未讨论极端情况**：如剧烈运动、严重噪声、低光照等条件下的表现未单独分析。
- **未提供误差条**：表 1 等结果未报告多次实验的方差或置信区间，虽然增益稳定，但缺乏统计显著性检验。
- **资源细节缺失**：训练 GPU 型号和数量未说明，可能影响复现性。
- **潜在偏差风险**：若被用于恢复故意模糊的敏感内容（如人脸、车牌），可能带来隐私风险，论文在 Broader Impacts 中有所提及但未提供具体缓解措施。

（完）
