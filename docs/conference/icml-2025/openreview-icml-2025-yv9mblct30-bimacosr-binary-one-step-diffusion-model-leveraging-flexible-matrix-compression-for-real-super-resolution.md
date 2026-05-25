---
title: "BiMaCoSR: Binary One-Step Diffusion Model Leveraging Flexible Matrix Compression for Real Super-Resolution"
title_zh: BiMaCoSR：利用灵活矩阵压缩的二值一步扩散模型实现真实超分辨率
authors: "Kai Liu, Kaicheng Yang, Zheng Chen, Zhiteng Li, Yong Guo, Wenbo Li, Linghe Kong, Yulun Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yV9MbLCt30"
tags: ["query:real-ir"]
score: 10.0
evidence: 提出二值化一步扩散模型用于真实超分辨率，结合二值化和蒸馏
tldr: 针对扩散模型超分辨率方法内存和计算需求大的问题，本文提出BiMaCoSR，将模型二值化与一步蒸馏结合，实现极度压缩和加速，同时利用灵活矩阵压缩防止灾难性遗忘，使扩散模型能够在资源受限的边缘设备上部署，并保持优秀的超分辨率性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yv9mblct30/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 714, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yv9mblct30/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1693, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yv9mblct30/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 830, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yv9mblct30/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 1221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yv9mblct30/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 511, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 991, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1747, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 970, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 877, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yv9mblct30/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 746, \"height\": 202, \"label\": \"Table\"}]"
motivation: 扩散超分模型部署受限于高内存和高计算需求。
method: 结合二值化和一步蒸馏，并采用灵活矩阵压缩防止灾难性遗忘。
result: 在真实超分任务上实现了极致的压缩和加速，性能可部署于边缘设备。
conclusion: BiMaCoSR为扩散超分模型的实际应用开辟了新途径。
---

## Abstract
While super-resolution (SR) methods based on diffusion models (DM) have demonstrated inspiring performance, their deployment is impeded due to the heavy request of memory and computation. Recent researchers apply two kinds of methods to compress or fasten the DM. One is to compress the DM into 1-bit, aka binarization, alleviating the storage and computation pressure. The other distills the multi-step DM into only one step, significantly speeding up inference process. Nonetheless, it remains impossible to deploy DM to resource-limited edge devices. To address this problem, we propose BiMaCoSR, which combines binarization and one-step distillation to obtain extreme compression and acceleration. To prevent the catastrophic collapse of the model caused by binarization, we proposed sparse matrix branch (SMB) and low rank matrix branch (LRM). Both auxiliary branches pass the full-precision (FP) information but in different ways. SMB absorbs the extreme values and its output is high rank, carrying abundant FP information. Whereas, the design of LRMB is inspired by LoRA and is initialized with the top r SVD components, outputting low rank representation. The computation and storage overhead of our proposed branches can be safely ignored. Comprehensive comparison experiments are conducted to exhibit BiMaCoSR outperforms current state-of-the-art binarization methods and gains competitive performance compared with FP one-step model. Moreover, we achieve excellent compression and acceleration. BiMaCoSR achieves a 23.8x compression ratio and a 27.4x speedup ratio compared to FP counterpart. Our code and model are available at https://github.com/Kai-Liu001/BiMaCoSR

---

## 论文详细总结（自动生成）

# BiMaCoSR：利用灵活矩阵压缩的二值一步扩散模型实现真实超分辨率

## 1. 研究动机与背景
- **核心问题**：基于扩散模型（DM）的超分辨率（SR）方法虽然性能出色，但因高内存、高计算开销难以部署到边缘设备。
- **现有努力**：一方面通过二值化（1-bit量化）压缩模型，减少存储与计算；另一方面通过知识蒸馏将多步扩散模型压缩为一步推理，加速生成。但两种技术尚未有效结合，且二值化会导致模型灾难性崩溃。
- **整体含义**：本文旨在将二值化与一步蒸馏结合，实现极致压缩与加速，使扩散SR模型可在资源受限设备上运行，同时保持高感知质量。

## 2. 方法论
- **整体架构**：以一步扩散模型SinSR为骨架，对其所有卷积层和线性层（除首尾）进行二值化，得到**二值矩阵分支（BMB）**；同时补充两个全精度辅助分支——**低秩矩阵分支（LRMB）**和**稀疏矩阵分支（SMB）**，以补偿二值化导致的信息损失。
- **低秩矩阵分支（LRMB）**：
  - 思想：将原始权重矩阵W近似为两个低秩矩阵的乘积 $W \approx BA$，其中 $B \in \mathbb{R}^{m \times r}, A \in \mathbb{R}^{r \times n}$，rank $r \ll \min(m,n)$。
  - 初始化：对预训练权重矩阵W进行奇异值分解（SVD），取前r个奇异值分量构造 $W \approx B A$，并将这部分从待二值化权重中减去（$W'_{BMB} := W - BA$），使BMB专注于高频细节，LRMB传递低频信息。
  - 前向：$x_{LRMB} = x_{in} BA$。
- **稀疏矩阵分支（SMB）**：
  - 思想：利用稀疏矩阵高效传递高秩信息。选取 $W'_{BMB}$ 中绝对值最大的k个元素构成稀疏矩阵 $W_{sparse}$，其余位置置零。
  - 初始化：同样从待二值化权重中减去这k个极端值（$W_{BMB} := W'_{BMB} - W_{sparse}$），进一步解耦。
  - 前向：$x_{SMB} = x_{in} W_{sparse}$。
- **二值矩阵分支（BMB）**：
  - 权重与激活经Sign函数二值化为±1，卷积/线性层转为XNOR与bit-count运算，再通过通道级缩放因子（激活平均×权重平均）补偿精度损失。
- **最终输出**：$x_{out} = x_{BMB} + x_{LRMB} + x_{SMB}$。
- **可忽略的开销**：LRMB和SMB的额外参数与计算量极小，仅带来可忽略的存储和运算负担。

## 3. 实验设计
- **数据集**：
  - 训练：ImageNet训练集，低分辨率图像由RealESRGAN的退化管线生成。
  - 测试：三个基准——RealSR、DRealSR（真实世界）、DIV2K-Val（双三次下采样，×4放大）。
- **评估指标**：
  - 全参考：PSNR、SSIM、LPIPS。
  - 无参考感知指标：DISTS、FID、NIQE、MANIQA、MUSIQ、CLIPIQA+。
  - 压缩与加速：参数总量（Params）、运算量（OPs），按二值化部分1bit权重计为全精度的1/32，计算量为1/64的等效方式统计。
- **对比方法**：
  - 全精度模型：SinSR（一步），ResShift（多步教师模型）。
  - 二值化SR方法：XNOR、ReActNet、BBCU、ReSTE、BiDM（均在SinSR基础上实现，统一训练设置）。

## 4. 资源与算力
- **硬件**：所有训练和测试在**单张NVIDIA RTX A6000**上完成。
- **训练配置**：Adam优化器（$\beta_1=0.9, \beta_2=0.99$），学习率 $2\times10^{-5}$，批量大小8，输入裁切为64×64，共训练**100K迭代**。
- **效率对比**：BiMaCoSR的FLOPs为1.83 G（单步），全精度SinSR为50.23 G，常规二值化方法为5.83~11.60 G不等；参数量仅4.98 M，SinSR为118.59 M，直接二值化版本约4.95 M。

## 5. 实验数量与充分性
- **主要结果表1**：包含三种数据集下与6种对比方法的9个指标全面比较，实验覆盖充分。
- **效率对比表2**：FLOPs、参数量、推理步数、PSNR/LPIPS。
- **消融实验**：共5组：
  1. 分支有效性（BMB、+LRMB、+LRMB+SMB）——表格3a。
  2. 损失函数（仅蒸馏损失 vs. SinSR完整损失）——表格3b。
  3. LRMB的秩（r=4,8,12,16）——表格3d，复杂度与性能权衡。
  4. LRMB初始化（零+随机 vs. SVD）——表格3c。
  5. SMB初始化（零初始化、Uni-shortcut、稀疏跳跃）——表格3e。
- **可视化分析**：图5展示各层三种分支输出的高频信息占比，验证分支分工假设。
- 总体来看，实验设计**公平、客观**，统一训练环境与评测流程，消融研究细致，验证了所提模块的有效性。

## 6. 主要结论与发现
- BiMaCoSR首次实现了**二值化 + 一步扩散模型**的SR，压缩比23.8×，加速27.4×。
- 在真实世界与合成基准上，性能显著超越现有二值化SR方法，部分指标（如RealSR的PSNR 26.84 dB、LPIPS 0.3375）甚至优于全精度一步模型SinSR。
- 通过**矩阵解耦**：BMB负责高频纹理生成，LRMB传递低频结构，SMB携带极端值高秩信息，极大缓解二值化带来的信息崩溃。
- 与全精度模型相比，感知质量下降极小，边缘设备部署成为可能。

## 7. 优点
- **创新性组合**：首次将极端量化（二值化）与一步蒸馏结合，兼顾速度与质量。
- **双分支设计巧妙**：低秩与稀疏矩阵分支有效补偿二值化信息损失，存储/计算开销近乎为零。
- **理论支持的初始化**：基于SVD的解耦初始化和极端值抓取使训练更稳定、性能更优。
- **实验扎实**：多个数据集、全面指标、公平对比、详尽消融，验证可靠。
- **实用性突出**：资源需求极低，真正将扩散SR推向边缘端。

## 8. 不足与局限
- **骨干固定**：仅基于SinSR一种一步扩散模型，通用性未在其他一步SR（如OSEDiff）或不同层次结构上验证。
- **特定退化**：训练数据退化管线固定为RealESRGAN，对多样真实退化（如不同噪声、模糊组合）的泛化性未深入探索。
- **极端值选择的固定性**：SMB在训练期间坐标固定，可能限制适应性；超参k的选取依赖经验公式，缺乏自适应机制。
- **全精度首尾层保留**：为保持质量，输入输出层保留全精度，牺牲了部分压缩潜力。
- **未与其他压缩技术结合**：仅二值化，未探索剪枝、INT8量化等混合策略，压缩比可能存在空间。
- **感知指标虽好但PSNR/SSIM在部分数据集略降**：与全精度模型相比仍有少量畸变指标下降，某些场景细节可能丢失。

（完）
