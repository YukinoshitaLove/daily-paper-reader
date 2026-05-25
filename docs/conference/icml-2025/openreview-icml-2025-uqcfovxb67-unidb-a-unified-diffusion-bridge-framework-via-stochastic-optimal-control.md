---
title: "UniDB: A Unified Diffusion Bridge Framework via Stochastic Optimal Control"
title_zh: UniDB：基于随机最优控制的统一扩散桥框架
authors: "Kaizhen Zhu, Mokai Pan, Yuexin Ma, Yanwei Fu, Jingyi Yu, Jingya Wang, Ye Shi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=uqCfoVXb67"
tags: ["query:real-ir"]
score: 10.0
evidence: 用于图像翻译和修复的统一扩散桥框架
tldr: UniDB 针对现有扩散桥模型在图像翻译与修复中细节模糊、理论基础薄弱的局限，提出基于随机最优控制的统一框架。通过推导最优控制器的闭式解，统一并泛化了现有扩散桥方法，在多个图像恢复与翻译任务上展现了更清晰的细节还原能力，为扩散桥模型提供了坚实的理论支撑。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1717, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1698, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1753, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1714, \"height\": 883, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 939, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1734, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1733, \"height\": 886, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1756, \"height\": 1139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uqcfovxb67/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1516, \"height\": 2130, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 1013, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1747, \"height\": 699, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1412, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1378, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 550, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uqcfovxb67/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 851, \"height\": 293, \"label\": \"Table\"}]"
motivation: 现有扩散桥方法常导致图像细节模糊，且缺乏统一的理论解释。
method: 提出基于随机最优控制的 UniDB 框架，导出最优控制闭式解并统一现有扩散桥模型。
result: 在图像翻译与恢复任务上显著改善了细节清晰度，超越了已有扩散桥方法。
conclusion: UniDB 为扩散桥模型提供了理论扎实且性能更优的统一方案。
---

## Abstract
Recent advances in diffusion bridge models leverage Doob’s $h$-transform to establish fixed endpoints between distributions, demonstrating promising results in image translation and restoration tasks. However, these approaches frequently produce blurred or excessively smoothed image details and lack a comprehensive theoretical foundation to explain these shortcomings. To address these limitations, we propose UniDB, a unified framework for diffusion bridges based on Stochastic Optimal Control (SOC). UniDB formulates the problem through an SOC-based optimization and derives a closed-form solution for the optimal controller, thereby unifying and generalizing existing diffusion bridge models. We demonstrate that existing diffusion bridges employing Doob’s $h$-transform constitute a special case of our framework, emerging when the terminal penalty coefficient in the SOC cost function tends to infinity. By incorporating a tunable terminal penalty coefficient, UniDB achieves an optimal balance between control costs and terminal penalties, substantially improving detail preservation and output quality. Notably, UniDB seamlessly integrates with existing diffusion bridge models, requiring only minimal code modifications. Extensive experiments across diverse image restoration tasks validate the superiority and adaptability of the proposed framework. Our code is available at https://github.com/UniDB-SOC/UniDB/.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- 现有扩散桥模型（如 DDBMs、GOUB）利用 Doob’s h‑变换建立分布间的固定端点，在图像翻译与修复任务中效果良好。
- 但这些方法存在两个根本问题：① Doob’s h‑变换如何控制桥接过程的理论机制不清晰，缺乏统一的解释框架；② 生成图像容易出现高频细节模糊或过度平滑，感知保真度不足。
- 本文旨在从随机最优控制（SOC）的视角，为扩散桥提供统一的理论基础，并通过引入可调的终端惩罚系数改善细节生成质量，使得框架能够兼容并泛化现有扩散桥模型。

## 方法论
- **统一 SOC 建模**  
  将扩散桥的前向过程构建为一个线性二次 SOC 问题，在一般线性 SDE 约束下最小化控制代价与终端偏离的加权和。目标函数为：
  \[
  \min_{u_{t,\gamma}} \ \mathbb{E}\!\left[\int_0^T \frac{1}{2}\|u_{t,\gamma}\|_2^2\,dt + \frac{\gamma}{2}\|x_u^T - x_T\|_2^2\right]
  \]
  - 漂移项采用统一形式 \(f(x_t,t)=f_t x_t + h_t m\)，可退化到 DDBMs(VE/VP) 和 GOUB。
- **闭式最优控制器**  
  利用庞特里亚金极大值原理推导出最优控制 \(u^*_{t,\gamma}\) 及对应的前向转移均值，并引入随机插值项构造完整的高斯转移概率 \(p(x_t|x_0,x_T)\)。
- **与 Doob’s h‑变换的等价关系**  
  证明当终端惩罚系数 \(\gamma \to \infty\) 时，最优控制退化为 \(g_t\nabla_{x_t}\log p(x_T|x_t)\)，即 Doob’s h‑变换是 UniDB 的特例。同时给出定理：有限 \(\gamma\) 的系统总代价低于 \(\gamma\to\infty\) 的情形。
- **训练与采样**  
  基于条件得分匹配与 \(l_1\) 损失，推导训练目标，并给出 UniDB‑GOU 等实例的训练/采样算法。核心改动仅在于将原方法中部分系数替换为含有 \(\gamma\) 的表达式，代码修改量小。

## 实验设计
- **数据集与任务**
  - 图像 4× 超分辨率：DIV2K 数据集（800 训练/100 测试），低分图像经 bicubic 放大至同尺寸。
  - 图像去雨：Rain100H 数据集（1800 训练/100 测试），指标在 Y 通道计算。
  - 图像修复（Inpainting）：CelebA‑HQ 256×256 数据集（27000 训练/3000 测试），使用 thin mask（附录含 thick mask 实验及 FFHQ 超分实验）。
- **基准方法**  
  超分：Bicubic、DDRM、IR‑SDE、GOUB (SDE/ODE)；去雨：MAXIM、MHNet、IR‑SDE、GOUB (SDE/ODE)；修复：DDRM、PromptIR、IR‑SDE、GOUB (SDE/ODE)。同时对比 DDBMs (VE)、DDBMs (VP) 及对应 UniDB 版本。
- **评价指标**  
  PSNR、SSIM、LPIPS、FID，兼顾信号保真度和感知质量。

## 资源与算力
- 模型在一张 NVIDIA H20 GPU（96 GB 显存）上训练，训练约 2 天。
- 训练参数：U‑Net 结构，总步数 120 万，初始学习率 \(10^{-4}\)，在 300k/500k/600k/700k 步衰减，batch size 8，patch size 128，扩散步数 \(T=100\)。

## 实验数量与充分性
- 在**3 个核心任务**上，与 5‑9 个基线方法进行系统对比，覆盖 SDE 和 ODE 采样。
- 针对关键超参数 \(\gamma\) 进行了多组消融实验（\(\gamma = 5\times 10^5, 1\times 10^6, 1\times 10^7, 1\times 10^8, \infty\)），分析对 PSNR/SSIM/LPIPS/FID 的影响。
- 附录补充了 UniDB‑VE、UniDB‑VP 与 DDBMs 的比较，CelebA‑HQ 超分、FFHQ 超分及 thick mask 修复实验。
- 实验设置与 GOUB 等基线一致，对比公平，结果充分验证了框架的优越性和适应性。

## 主要结论与发现
- UniDB 基于随机最优控制首次为扩散桥提供了统一且可解释的理论框架，Doob’s h‑变换仅为 \(\gamma\to\infty\) 的特例。
- 有限 \(\gamma\) 可以在控制代价与终端匹配之间取得更优平衡，显著改善图像细节、减少模糊与扭曲。
- 在超分辨率、去雨、修复等多任务上均取得 SOTA 或极具竞争力的结果，尤其在 LPIPS 和 FID 等感知指标上提升明显。
- 该方法可作为即插即用模块，只需少量代码修改即可增强现有扩散桥模型。

## 优点
- **理论统一与深化**：用 SOC 统一了 Doob’s h‑变换，并揭示其并非最优，为后续研究提供新的优化方向。
- **简单高效**：仅需调节一个标量系数 \(\gamma\)，算法与现有扩散桥高度兼容，训练和采样开销几乎不变。
- **实验扎实全面**：多任务、多数据集、多指标对比，消融实验充分，体现方法的泛化性和鲁棒性。
- **生成质量提升明显**：视觉结果（放大细节）和感知指标均优于 GOUB 等基线。

## 不足与局限
- **采样效率受限**：和一般扩散桥模型类似，采样仍需多步迭代，高分辨率或实时场景部署困难。
- **超参数敏感**：最优 \(\gamma\) 依赖任务和数据，需人工调参，缺乏自动选择机制。
- **范围限定**：目前仅针对线性 SDE 形式的扩散桥，尚未涵盖非线性漂移或更一般的扩散过程。
- **任务覆盖**：实验聚焦于图像恢复，在文本到图像等生成式任务上的表现有待验证。

（完）
