---
title: Bio-Inspired Image Restoration
title_zh: 生物启发的图像恢复
authors: "Yuning Cui, Wenqi Ren, Alois Knoll"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=UhvD08xpBO"
tags: ["query:real-ir"]
score: 9.0
evidence: 生物启发的通用图像恢复框架
tldr: 图像恢复方法在追求通用性的同时面临计算效率瓶颈。本文受人类视觉系统启发，提出BioIR框架，设计了外围到中央（P2F）和中央到外围（F2P）模块，模拟视觉感知交互，在多种退化任务上实现了高效且高质量的恢复，兼顾了效率与性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 948, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1413, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1424, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1429, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 2165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhvd08xpbo/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 2201, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1464, \"height\": 1002, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 554, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 464, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 418, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1263, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1425, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 900, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 904, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhvd08xpbo/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1446, \"height\": 381, \"label\": \"Table\"}]"
motivation: 现有图像恢复方法计算效率低。
method: 设计P2F和F2P模块模拟人类视觉系统的中央-外围交互。
result: 在多种退化任务上实现高效高质量恢复。
conclusion: 生物启发的设计提升了图像恢复的效率和通用性。
---

## Abstract
Image restoration aims to recover sharp, high-quality images from degraded, low-quality inputs. Existing methods have progressively advanced from task-specific designs to general architectures, all-in-one frameworks, and composite degradation handling. Despite these advances, computational efficiency remains a critical factor for practical deployment. In this work, we present BioIR, an efficient and universal image restoration framework inspired by the human visual system. Specifically, we design two bio-inspired modules, Peripheral-to-Foveal (P2F) and Foveal-to-Peripheral (F2P), to emulate the perceptual processes of human vision, with a particular focus on the functional interplay between foveal and peripheral pathways. P2F delivers large-field contextual signals to foveal regions based on pixel-to-region affinity, while F2P propagates fine-grained spatial details through a static-to-dynamic two-stage integration strategy. Leveraging the biologically motivated design, BioIR achieves state-of-the-art performance across three representative image restoration settings: single-degradation, all-in-one, and composite degradation. Moreover, BioIR maintains high computational efficiency and fast inference speed, making it highly suitable for real-world applications.

---

## 论文详细总结（自动生成）

## 论文《Bio-Inspired Image Restoration》详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：图像恢复（去雪、去雾、去雨、低光增强等）在深度学习中已从任务特定模型发展到通用架构、全合一框架及复合退化处理方法。然而，现有方法在追求通用性的同时，往往牺牲了计算效率，难以在真实场景中高效部署。此外，不同恢复场景（单一退化、多任务、复合退化）缺乏统一高效的解决方案。
- **整体含义**：受人类视觉系统中中央凹（fovea）与周边（periphery）协同感知机制的启发，论文提出一种**高效且通用的图像恢复框架 BioIR**，旨在同时兼顾性能、通用性与效率，统一处理三大主流恢复设置。

### 2. 论文提出的方法论
- **核心思想**：模拟人眼中锥体细胞（密集于中央凹）与杆体细胞（密集于周边）的功能分工与交互。中央凹负责高精度细节，周边提供大范围上下文。BioIR 通过两个专用模块模拟这种交互：
  - **P2F（Peripheral-to-Foveal）**：将大视野上下文信号传递至局部区域，通过像素-区域亲和度动态生成卷积核，增强局部特征。
  - **F2P（Foveal-to-Peripheral）**：将精细空间细节传播至周边，采用“静态调制 + 动态卷积”的两阶段集成策略（先逐元素相乘，再通过动态卷积进一步细化）。
- **关键技术细节**：
  - 整体网络采用**简单 U 型架构**（编码器-解码器-精修），核心构件为 **BioBlock**，每个 BioBlock 包含归一化层、BioModule 和前馈网络。
  - BioModule 将输入特征沿通道分为两部分（P 和 F），分别输入 P2F 和 F2P，其输出通过逐元素乘法进行重新校准（recalibration），再经 1×1 卷积生成最终特征。
  - 具体计算：输入 X → 1×1 卷积 → 3×3 深度可分离卷积 → 切分为 P、F → P2F、F2P 各处理 → 对应特征相乘 → 1×1 卷积输出。
- **算法流程（文字说明）**：给定退化图像，先经 3×3 卷积嵌入特征，再经编码器逐步下采样扩展通道，解码器恢复分辨率并利用跳跃连接，最后经精修阶段和 3×3 卷积输出残差，与输入相加得到恢复结果。各阶段由不同数量的 BioBlock 堆叠。

### 3. 实验设计
- **数据集与场景**：覆盖三大恢复设置：
  1. **单一退化**：4 个任务共 9 个数据集（去雪：Snow100K、SRRS、CSD；去雾：SOTS-Indoor、Haze4K；低光增强：LOLv2-s；去雨：AGAN-Data、DID-Data、SPA-Data）。
  2. **全合一（All-in-One）**：三任务（去雾、去雨、去噪）和五任务（额外增加去运动模糊、低光增强），测试集包括 SOTS、Rain100L、BSD68、GoPro、LOLv1 等。
  3. **复合退化（Composite Degradation）**：LOLBlur（低光+模糊）、CDD11（最多三种退化组合）。
- **对比方法**：
  - 单一退化：对比 FocalNet、IRNeXt、MBTF-L V2、Restormer、NAFNet、MambaIR 等近年代表方法。
  - 全合一：对比 PromptIR、AdaIR、MoCE-IR、InstructIR-5D、IDR 等。
  - 复合退化：对比 OneRestore、MoCE-IR-S、DarkIR 系列、WGWSNet 等。
- **评价指标**：PSNR、SSIM，部分也报告了 LPIPS（感知指标）和推理时间（FLOPs、参数量、运行时间）。

### 4. 资源与算力
- 论文明确说明：所有实验**使用 PyTorch 在 NVIDIA Tesla A100 80G GPU 上运行**。具体训练轮次：单一退化/复合退化训练 300K 次迭代；全合一三任务训练 100 epoch，五任务训练 150 epoch。批大小统一为 32（全合一），Patch 尺寸 128×128。未提及 GPU 数量及总耗时（小时级），但给出了各模型的 FLOPs（如 Tiny 版本 16.65G）和参数（1.32M~15.85M），以及推理速度（如表 2 所示，在 RTX 4090 上单张图 0.038~0.133 秒）。

### 5. 实验数量与充分性
- **实验数量**：非常丰富。
  - 4 个单一退化任务 × 9 个数据集，每个任务均与多个 SOTA 对比。
  - 全合一设置下两个子设置（3 任务、5 任务），每个子设置包含 5~6 个对比方法，并额外进行了跨数据集泛化测试（在未见的 Urban100、Kodak24 上测试去噪）。
  - 复合退化在 LOLBlur（四类对比）和 CDD11（11 个退化类别）上全面对比。
  - 详细消融实验：验证各组件（P2F、F2P、重校准）、外围视野尺度 S、中央凹卷积核大小、动态卷积核大小（K、G）等。
  - 提供了视觉对比图和 L1 误差图。
- **充分性与公平性**：
  - 对比方法均为近年顶会/顶刊工作，且基本为官方版本，使用相同训练/测试协议。
  - 消融实验在同一设置（RESIDE-Indoor 100K 次迭代）下进行，控制变量，结论清晰。
  - 报告了 FLOPs、参数量、推理时间，公平对比复杂度。
  - 总体上实验设计客观、全面、可复现。

### 6. 论文的主要结论与发现
- **BioIR 在所有三个恢复设置上均达到当前最优**，并在多个数据集上显著超越以往方法。
  - 单一退化：如去雾 SOTS-Indoor 达 40.50 dB PSNR，比 MaIR 高 1.05 dB，参数仅为其 1.32M vs 3.40M。
  - 全合一：五任务平均 30.99 dB PSNR，比 MoCE-IR 高 0.41 dB，参数更少（16M vs 25M）。
  - 复合退化：CDD11 上 BioIR-B 平均 30.54 dB，比 MoCE-IR-S 高 1.49 dB。
- **强泛化能力**：无需显式退化先验，仅靠生物启发的模块捕获隐式上下文，即可处理多种退化类型。
- **高效率**：推理速度快、参数量小、FLOPs 低，适合实际部署。

### 7. 优点
- **设计新颖且高效**：将生物视觉的中央-外周交互机制转化为两个轻量级模块（P2F、F2P），在几乎没有额外开销下显著提升性能。
- **通用性强**：单一网络架构即可覆盖单一、全合一、复合三种主流设置，无需针对不同场景修改结构。
- **实验扎实**：多场景、多数据集、多指标、多消融，对比方法全面，结果一致优于基线。
- **模型可伸缩**：提供 Tiny、Base、Large 三个版本，适应不同算力需求。

### 8. 不足与局限
- **生物模拟仍较初步**：论文自身也承认，人眼视觉处理极其复杂，当前模块仅模拟了粗略的交互，更精细的机制（如自适应重校准）未探索。
- **重校准机制简单**：目前仅使用逐元素乘法，论文认为设计更复杂的校准方式可能进一步提升性能。
- **未在超高清或视频恢复上测试**：实验图像尺寸多为 256×256 或 patch，未涉及 4K/8K 或视频帧序列。
- **训练细节略简**：仅提及优化器、学习率计划，未提供完整的超参数网格搜索，可能存在未公开的最佳配置。
- **潜在隐私风险**：在增强敏感内容（如人脸、证件）时可能引发隐私泄露，文中建议用户自行添加隐私保护技术，但未提供具体防护机制。

（完）
