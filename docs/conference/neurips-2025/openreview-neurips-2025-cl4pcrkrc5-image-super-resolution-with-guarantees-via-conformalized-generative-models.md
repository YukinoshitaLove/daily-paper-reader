---
title: Image Super-Resolution with Guarantees via Conformalized Generative Models
title_zh: 带有保证的图像超分辨率：基于共形化生成模型
authors: "Eduardo Adame, Daniel Csillag, Guilherme Tegoni Goedert"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cl4PCrKrc5"
tags: ["query:real-ir"]
score: 9.0
evidence: 基于共形化生成模型的图像超分辨率
tldr: 生成模型用于超分辨时缺乏不确定性量化，该文提出基于共形预测的置信掩码方法，适用于任意黑盒生成模型，提供保真度误差的理论保证，用户可通过掩码判断生成图像的可靠区域。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 1037, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 887, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cl4pcrkrc5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 1527, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cl4pcrkrc5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1390, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cl4pcrkrc5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 796, \"height\": 359, \"label\": \"Table\"}]"
motivation: 生成模型超分辨结果缺乏可解释的置信度，用户无法信任哪些区域可靠。
method: 利用共形预测技术，在生成模型后处理中生成置信掩码，并给出保真度误差控制的理论保证。
result: 在超分辨数据集上验证了方法的有效性和理论保证。
conclusion: 为生成模型应用于图像恢复提供了可靠的置信度评估工具。
---

## Abstract
The increasing use of generative ML foundation models for image restoration tasks such as super-resolution calls for robust and interpretable uncertainty quantification methods. We address this need by presenting a novel approach based on conformal prediction techniques to create a `confidence mask' capable of reliably and intuitively communicating where the generated image can be trusted. Our method is adaptable to any black-box generative model, including those locked behind an opaque API, requires only easily attainable data for calibration, and is highly customizable via the choice of a local image similarity metric. We prove strong theoretical guarantees for our method that span fidelity error control (according to our local image similarity metric), reconstruction quality, and robustness in the face of data leakage. Finally, we empirically evaluate these results and establish our method's solid performance.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：生成式机器学习基础模型（如扩散模型）在图像超分辨率任务中取得了巨大成功，但模型生成的图像是否真实可信、是否存在幻觉（hallucination）一直缺乏有效的量化手段。用户需要一种可解释、有统计保证的方法来判断生成图像的哪些区域是可靠的。
- **现有不足**：以往工作要么产生像素级区间（不直观），要么输出连续置信分数但缺乏概率保证（如 Kutiel et al. 2023），要么只适用于特定模型、需要额外标注或无法处理黑盒 API。
- **本文目标**：提出一种基于共形预测（conformal prediction）和共形风险控制（conformal risk control）的方法，为任何黑盒生成模型输出的超分辨率图像生成“置信掩码”（confidence mask），不仅能直观标识可信区域，还提供严格的保真度误差控制、PSNR 保证以及对数据泄露的鲁棒性。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用少量无标注高分辨率图像作为校准数据，通过共形风险控制选择阈值 \(t_\alpha\)，然后对每个测试低分辨率图像，根据模型不确定度估计 \(\sigma(X)\) 生成二进制掩码 \(M_\alpha(X)\)，表示像素级信任区域（mask 内像素保真度误差受控）。
- **关键步骤**：
  1. 给定任意生成超分辨率模型 \(\mu\) 和不确定度函数 \(\sigma\)（例如多生成图像像素方差，或经低通滤波的方差）。
  2. 定义局部保真度误差度量 \(D_p(Y, \hat{Y})\)（如 L1 距离、邻域平均差或语义差异），要求值域在 \([0,3]\)。
  3. 使用校准集 \((X_i, Y_i)_{i=1}^n\)，计算阈值：
     \[
     t_\alpha = \sup\left\{ t \in \mathbb{R}\cup\{+\infty\} : \frac{1}{n+1}\sum_{i=1}^n \sup_{p:[\sigma(X_i)]_p \le t} D_p(Y_i, \mu(X_i)) + \frac{3}{n+1} \le \alpha \right\}
     \]
  4. 对测试图像 \(X\)，生成掩码：
     \[
     M_\alpha(X) = \{ p \in \mathbb{Z}\times\mathbb{Z} : [\sigma(X)]_p \le t_\alpha \}
     \]
- **算法效率**：通过动态规划将阈值计算复杂度从 \(O(n^2 d^2)\) 降至 \(O(nd \log d)\)（\(n\) 为校准图像数，\(d\) 为每图像素数）。
- **模型不确定度 \(\sigma\) 的改进**：提出“核方差”（kernel variance）方法，先对生成图像做低通滤波再计算方差，避免边缘伪影，得到更平滑、更准确的置信图。
- **保真度度量 \(D_p\) 的可选类型**：点对点 L1、邻域平均（低通滤波后 L1）、基于语义标注的指标（需人工标注校准集）。

### 3. 实验设计：数据集、基准与对比方法
- **数据集**：Liu4K 数据集（1600 张 4K 训练图像用于校准，400 张验证/测试图像用于评估）。所有图像在 Lab 色彩空间处理（感知均匀）。
- **基模型**：SinSR（一种单步扩散超分辨率模型）。
- **对比方法**：
  - 无不确定性量化（直接信任整张图）。
  - Angelopoulos et al. 2022b：产生像素区间图像，保证区间覆盖真实值的期望比例。
  - Kutiel et al. 2023：产生连续置信分数，但无概率保证。
- **评估指标**：保真度误差（期望最大值）、平均 PSNR、平均掩码大小（不可信区域比例）。

### 4. 资源与算力
- **硬件**：Intel Xeon E5-2696 v2 CPU（2.5GHz，18 线程，40GB RAM）+ NVIDIA RTX 6000 Ada Generation 48GB GPU。
- **计算瓶颈**：主要是基模型 SinSR 的推理过程；共形校准步骤在 CPU 上运行非常快。
- **未明确说明**：总推理耗时、GPU 小时数等具体数值未给出，但代码已开源以便复现。

### 5. 实验数量与充分性
- **实验组数**：较充分——包括不同 α 值（0.075、0.1、0.2、0.3）下的语义/非语义 \(D_p\) 性能对比（表 1）、PSNR 控制验证（图 4 左）、数据泄露鲁棒性（图 4 右）、模糊核影响（图 6）、分布偏移测试（表 2）、以及对 baseline 的定性比较（图 5）。另外还在图像染色任务上展示了可迁移性（附录 F）。
- **公正性与客观性**：实验设计合理，理论预言（保真度 ≤ α、PSNR ≥ -20logα）与实验吻合。但对比方法（Angelopoulos 等、Kutiel 等）由于输出模态不同，只做了定性比较，未提供定量公平对比，这在一定程度上降低了直接可比性。

### 6. 主要结论与发现
- 所提方法能 **紧密控制保真度误差**（实际误差 ≤ α），且掩码大小随 α 增大而减小，在大多数 α 下保持信息量。
- 方法 **理论保证得到实证支持**：PSNR 下限成立（图 4 左），数据泄露时上界有效（图 4 右）。
- **语义 \(D_p\) 比非语义 \(D_p\) 表现更好**：在相同 α 下，语义指标产生更高的 PSNR 和更小的掩码（表 1）。
- 加入低通滤波（kernel variance 和模糊 Dp）可显著提升掩码质量和连续度（图 6）。
- 方法可推广至其他图像恢复任务（如染色，附录 F）。

### 7. 优点
- **模型无关**：适用于任意黑盒生成模型（包括仅 API 访问），只需少量无标注校准数据。
- **强理论保证**：控制保真度误差期望、PSNR 下界、数据泄露下的鲁棒上界。
- **可解释性好**：输出二进制掩码，用户能直观理解哪些区域可信。
- **高度可定制**：通过选择不同的局部相似度度量 \(D_p\)（点对点、邻域、语义）适应具体应用需求。
- **校准高效**：动态规划算法使计算复杂度可控。

### 8. 不足与局限
- **分布漂移风险**：核心假设是校准-测试数据可交换（即分布内），若测试分布发生较大偏移，理论保证可能失效。
- **计算开销**：需要生成多幅高分辨率图像以获得不确定度 \(\sigma\)，对于大模型可能成本较高。
- **数据泄露容忍度有限**：虽然理论给出上界，但严重泄露时上界变松，实际性能下降（图 4 右）。
- **对比方法公平性不足**：与 Angelopoulos 和 Kutiel 的定量对比缺失，仅做定性展示，结论的全面性受一定限制。
- **语义 \(D_p\) 依赖人工标注**：若使用语义度量，需在校准集上提供人工标注，增加了应用门槛。

（完）
