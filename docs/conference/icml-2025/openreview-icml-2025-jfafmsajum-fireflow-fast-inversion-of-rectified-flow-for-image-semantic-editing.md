---
title: "FireFlow: Fast Inversion of Rectified Flow for Image Semantic Editing"
title_zh: FireFlow：面向图像语义编辑的修正流快速反演
authors: "Yingying Deng, Xiangyu He, Changwang Mei, Peisong Wang, Fan Tang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JFafMSAjUm"
tags: ["query:real-ir"]
score: 10.0
evidence: 实现修正流的快速反演，用于8步内精确图像语义编辑
tldr: 本文针对修正流模型快速反演难的问题，提出FireFlow零样本方法，通过精巧设计的数值求解器实现精确反演与重建，以二阶精度保持一阶效率。在8步内即可完成高质量图像语义编辑，显著优于现有方法。FireFlow是简单有效的零样本编辑方案，为修正流模型的实用化铺平了道路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1488, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 836, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1882, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1713, \"height\": 1527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1742, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1777, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1784, \"height\": 1164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1771, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jfafmsajum/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 361, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1800, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 909, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jfafmsajum/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1702, \"height\": 471, \"label\": \"Table\"}]"
motivation: 修正流反演慢且不精确，影响编辑应用。
method: 设计二阶精度但一阶效率的数值求解器用于反演。
result: 8步内实现精确反演与高质量语义编辑。
conclusion: 大幅提升了修正流模型在编辑中的实用化。
---

## Abstract
Though Rectified Flows (ReFlows) with distillation offer a promising way for fast sampling, its fast inversion transforms images back to structured noise for recovery and following editing remains unsolved. This paper introduces FireFlow, an embarrassingly simple yet effective zero-shot approach that inherits the startling capacity of ReFlow-based models (such as FLUX) in generation while extending its capabilities to accurate inversion and editing in **8** steps. 
We first demonstrate that a carefully designed numerical solver is pivotal for ReFlow inversion, enabling accurate inversion and reconstruction with the precision of a second-order solver while maintaining the practical efficiency of a first-order Euler method. This solver achieves a $3\times$ runtime speedup compared to state-of-the-art ReFlow inversion and editing techniques while delivering smaller reconstruction errors and superior editing results in a training-free mode. The code is available at [this-URL](https://github.com/HolmesShuan/FireFlow-Fast-Inversion-of-Rectified-Flow-for-Image-Semantic-Editing).

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，以Markdown形式为您生成一份结构化、深入、客观的中文总结。

### **1. 论文的核心问题与整体背景（研究动机）**

*   **核心问题**：修正流模型虽然在快速采样上很有前景，但其**快速反演**技术尚不成熟。现有的反演方法难以在计算效率、数值精度和编辑质量间取得平衡。
*   **研究背景**：
    *   图像反演是将图像映射回模型隐空间的过程，是实现精确图像语义编辑的基础。
    *   扩散模型的反演常用随机微分方程求解，但其非线性特性易引入误差。
    *   基于普通微分方程的修正流模型为更高效、稳定的反演提供了新思路，但目前的方法（如 RF-Solver、RF-Inversion）未能充分利用其“学习到近乎恒定速度场”的特性，导致反演步骤多、耗时长或精度不高。
*   **研究动机**：设计一种能**完全利用**修正流模型恒定速度属性、同时实现**高数值精度（二阶）**与**高计算效率（一阶成本）** 的零样本反演求解器，以在极少数步骤内完成高质量的图像重建与编辑。

### **2. 论文提出的方法论**

论文的核心是设计了一个用于求解修正流ODEs的新型数值求解器“FireFlow”，其关键思想与流程如下：

*   **核心思想**：
    *   **加速运动的视角**：将修正流的线性运动扩展为加速运动（`Xt+1 = Xt + vt*Δt + 1/2*at*Δt^2`），这与高阶ODE求解器（如二阶Runge-Kutta中点法）的原理相通，能实现更高的精度。
    *   **速度场重用**：对于一个训练良好的修正流模型，其预测的速度场v(t) 在不同时刻应近似相等（`v(Xt, t) ≈ X1 - X0`）。FireFlow利用这一特性，用**上一时间步计算并储存的中点速度**来替代当前时间步的速度，从而避免额外的模型前向计算。

*   **关键技术细节与流程（Midpoint Method with Velocity Reuse）**：
    1.  **初始化（t=0）**：模型需要前向计算两次，得到初始速度`v0`和在`t+Δt/2`时刻的“中点速度”`v_{0+Δt/2}`并进行储存。
    2.  **迭代步骤（从t=1到t=T-1）**：
        *   **重用速度**：从内存中读取上一个时间步储存的`v_{(t-1)+Δt/2}`，将其作为当前时刻的近似速度 `ŷ(Xt, t)`。这一步**不消耗额外的NFE**。
        *   **计算中点位置**：使用近似速度 `ŷ(Xt, t)`，计算时间步中点的图像潜变量 `Ť = Xt + (Δt/2) * ŷ(Xt, t)`。
        *   **计算中点速度**：对中点位置运行一次模型前向，得到精确的中点速度 `v_{t+Δt/2}`。
        *   **更新潜变量 & 储存**：使用该精确的中点速度完成当前步的完整更新 `Xt+1 = Xt + Δt * v_{t+Δt/2}`，并将这个`v_{t+Δt/2}`存储到内存，供下一时间步重用。
    *   **理论保证**：论文通过定理（**Theorem 4.2**）证明，在满足重用速度误差`||ŵθ - vθ|| ≤ O(Δt)`的条件下，该方案能达到与标准中点法相同的全局截断误差（`O(Δt^2)`），即二阶精度。同时，除初始化外，每步仅需一次模型评估，计算量与一阶欧拉法相当。

*   **图像语义编辑流程**：
    *   **反演阶段**：使用FireFlow求解器将源图像反演为结构化噪声，同时**存储**反演过程中自注意力层的**Value (V) 特征**。
    *   **编辑阶段**：使用FireFlow求解器从噪声开始进行去噪生成，但在自注意力层中，用反演阶段存储的**V特征替换**当前生成的V特征，从而在保留源图像结构的同时，根据新的编辑提示词修改内容。

### **3. 实验设计**

*   **数据集与场景**：
    *   **无条件生成**：CIFAR-10数据集。
    *   **文本到图像生成 (T2I)**：MSCOCO Caption 2014验证集（随机10K子集）。
    *   **反演与重建**：Densely Captioned Images (DCI) 数据集（前1K张图片）。
    *   **语义图像编辑**：PIE-Bench数据集（包含700张图像、10种编辑类型，如添加/删除物体、改变风格、替换内容）。
*   **对比基准方法**：
    *   **基于扩散模型**：Prompt-to-Prompt、MasaCtrl、Pix2Pix-Zero、Plug-and-Play、DiffEdit、DirectInversion。
    *   **基于修正流模型**：RF-Inversion、RF-Solver。
    *   **基线模型**：原生的FLUX-dev（一阶欧拉法）。
*   **评估指标**：
    *   **生成质量与文本对齐**：FID、Inception Score (IS)、CLIP Score。
    *   **重建保真度**：LPIPS、SSIM、PSNR。
    *   **编辑质量**：结构距离、PSNR、SSIM（衡量背景保留能力）、整体和编辑区域的CLIP相似度。

### **4. 资源与算力**

*   **推理测速**：论文在表6中报告了在单块**RTX 3090**显卡上的推理时间对比，这是为了展示方法的实际加速效果。
*   **训练**：本文提出的FireFlow是一个**零样本、免训练**方法，因此不涉及任何训练算力开销。论文中未提及训练所需的GPU型号、数量或训练时长，这是该方法的一个重要优势。

### **5. 实验数量与充分性评估**

论文的实验设计较为全面，涵盖了约**7组以上**不同维度的对比实验，充分性很高：

*   **任务覆盖广**：从基本的无条件和文本条件生成，到反演重建，再到最终的语义编辑应用，构成了一个完整的验证链条。
*   **对比方法丰富且公平**：既对比了传统的扩散模型编辑方法，也重点对比了同为修正流框架下最新的直接竞争对手（RF-Solver, RF-Inversion）。在对比时，尽量统一了总函数评估次数或总步数，确保了公平性。
*   **定量与定性分析结合**：不仅有详尽的数值指标表格，还提供了大量的视觉对比图，直观展示了重建误差和编辑效果。
*   **包含深入分析**：不仅展示了最终结果，还通过2D合成数据实验、速度场误差分析、收敛速度对比图等方式，验证了理论假设和方法的优越性。
*   **消融实验**：对关键超参数“编辑步数”和不同的“注意力操控策略”进行了消融研究，明确了方法的最佳设置与局限性。

### **6. 论文的主要结论与发现**

*   FireFlow成功地将二阶数值求解精度与一阶方法的计算成本相结合，是首个在修正流模型上实现该突破的训练无关求解器。
*   该方法能够在**仅8个步骤**内完成精确的图像反演和高质量的语义编辑，相比现有最先进的修正流反演方法，实现了约**3倍推理速度提升**。
*   实验证明，FireFlow在重建误差、编辑保真度和背景保持能力上均显著优于或等同于现有方法，尤其是在CLIP相似度（编辑-文本对齐）上表现突出。

### **7. 优点（亮点）**

*   **算法简洁高效**：“Embarassingly simple yet effective”，仅通过重用中间速度场就实现了质的飞跃，思路巧妙，易于实现和复现。
*   **零样本、免训练**：无需任何额外训练或微调，可直接应用于现成的预训练修正流模型（如FLUX），通用性强。
*   **理论与实践结合紧密**：提供了严谨的误差分析和命题证明，理论指导了方法设计，实验结果又反过来验证了理论假设。
*   **极致加速**：在极低NFE（8步18次函数评估）下就达到了SOTA编辑水平，极大地推动了修正流模型在交互式应用中的实用性。

### **8. 不足与局限**

*   **特定编辑类型失败**：论文坦诚地指出，该方法在修改物体**颜色**或处理包含不常见/不完整对象（如看不到头的人像、罕见概念组合）的场景时，编辑效果不佳。
*   **编辑策略简单**：将失败归因于只进行V特征替换的编辑策略可能过于简单。虽然探索了K/Q特征操作能改善某些情况，但会牺牲背景保持能力，表明该编辑框架仍有待完善。
*   **实验范围**：由于是零样本方法，其性能很大程度上受限于底层FLUX模型的能力边界。对于FLUX生成的失败案例，FireFlow也无法解决。
*   **泛化性未深入探讨**：虽然实验覆盖了常见编辑任务，但未系统评估其在更多样化、更复杂的开放式世界编辑或极高分辨率图像上的鲁棒性。

（完）
