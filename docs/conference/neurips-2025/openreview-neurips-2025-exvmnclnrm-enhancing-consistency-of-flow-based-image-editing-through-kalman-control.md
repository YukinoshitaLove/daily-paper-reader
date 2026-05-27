---
title: Enhancing Consistency of Flow-Based Image Editing through Kalman Control
title_zh: 通过卡尔曼控制增强流模型图像编辑的一致性
authors: "Haozhe Chi, Zhicheng Sun, Yang Jin, Yi Ma, Jing Wang, Yadong MU"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ExVMnClnrM"
tags: ["query:real-ir"]
score: 8.0
evidence: 基于卡尔曼控制的流模型图像编辑，保证区域一致性
tldr: 针对基于指令的图像编辑中非目标区域一致性不足的问题，本文提出Kalman-Edit方法。该方法将图像编辑建模为控制问题，利用卡尔曼滤波器整合历史编辑轨迹，有效减少逐步骤误差累积。实验表明，该方法在保持编辑区域修改的同时显著提升了非目标区域的一致性，为流模型图像编辑提供了新的控制视角。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 1033, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 740, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 1503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 350, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 352, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 361, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 349, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1429, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1428, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 1087, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1417, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1445, \"height\": 1329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1307, \"height\": 1275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1302, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1451, \"height\": 924, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1430, \"height\": 1577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1433, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-exvmnclnrm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1455, \"height\": 706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 912, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 879, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 772, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-exvmnclnrm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 952, \"height\": 421, \"label\": \"Table\"}]"
motivation: 现有流模型图像编辑方法在非目标区域一致性上存在不足，归因于逐步骤误差累积。
method: 将图像编辑视为控制问题，引入卡尔曼滤波器整合历史编辑轨迹，提出Kalman-Edit算法。
result: 该方法在保持编辑区域修改的同时，显著提升了非目标区域的一致性，优于现有方法。
conclusion: 卡尔曼控制有效解决了流模型图像编辑中的累积误差问题，提升了编辑质量。
---

## Abstract
Flow-based generative models have gained popularity for image generation and editing. For instruction-based image editing, it is critical to ensure that modifications are confined to the targeted regions. Yet existing methods often fail to maintain consistency in non-targeted regions between the original / edited images. Our primary contribution is to identify the cause of this limitation as the error accumulation across individual editing steps and to address it by incorporating the historical editing trajectory. Specifically, we formulate image editing as a control problem and leverage the Kalman filter to integrate the historical editing trajectory. Our proposed algorithm, dubbed Kalman-Edit, reuses early-stage details from the historical trajectory to enhance the structural consistency of the editing results. To speed up editing, we introduce a shortcut technique based on approximate vector field velocity estimation. Extensive experiments on several datasets demonstrate its superior performance compared to previous state-of-the-art methods.

---

## 论文详细总结（自动生成）

# 论文总结：Enhancing Consistency of Flow-Based Image Editing through Kalman Control

## 1. 论文的核心问题与整体含义（研究动机和背景）

基于指令的图像编辑要求修改仅发生在目标区域，但现有流模型（Flow‑based）编辑方法在非目标区域难以保持一致性，常出现过度编辑或欠编辑，导致结构不一致。作者识别出根本原因在于逐编辑步骤的误差累积——微小不准确会逐步放大为显著偏离。为此，论文将图像编辑建模为控制问题，引入卡尔曼滤波器（Kalman Filter）整合历史编辑轨迹，提出 Kalman‑Edit 方法，以增强非目标区域的结构一致性，同时保持编辑质量。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将图像编辑视为线性二次高斯（LQG）控制问题，利用卡尔曼滤波器融合历史反转轨迹作为观测序列，在生成阶段校正噪声估计，减少误差累积。
- **关键技术细节**：
  - **两阶段编辑**：第一阶段生成一个同时包含原图语义和目标语义的中间潜变量 \(x_{mid}\)；第二阶段将该中间潜变量再次反转，并应用卡尔曼滤波生成最终结果。
  - **观测序列构建**：同时利用原图 \(x_s\) 和中间图 \(x_{mid}\) 的反转潜变量构成观测序列 \(\{y_k\}\)，分为两段分别捕获早期结构和后期细节。
  - **卡尔曼滤波应用**：在生成阶段的后期（精细细节阶段）应用卡尔曼滤波，计算卡尔曼增益并更新状态，公式化为：
    \[
    x_{t_{k+1}} = x_{t_k} + (t_{k+1} - t_k) v'_{t_k},
    \quad v'_{t_k} = \mu v_{t_k} + \lambda u_{t_k} + (1-\mu-\lambda) K_k(y_k - H x_{t_k})
    \]
    其中 \(v_{t_k}\) 是预测速度，\(u_{t_k}\) 是最优控制器，\(K_k\) 为卡尔曼增益。
  - **加速版本 Kalman‑Edit\***：利用平行四边形法则近似第二次反转，直接估计第二原始潜变量以避免二次反转，加速编辑过程。
- **算法流程**：
  1. 对原图 \(x_s\) 进行反转，得到第一原始潜变量 \(x_{orig1}\)。
  2. 用最优控制器从 \(x_{orig1}\) 生成中间潜变量 \(x_{mid}\)。
  3. （Kalman‑Edit）对 \(x_{mid}\) 进行第二次反转得到 \(x_{orig2}\)；或（Kalman‑Edit\*）用 shortcut 公式 \(x_{orig2}=x_{orig1}+(x_{mid}-x_s)\) 估计。
  4. 构建观测序列，并从 \(x_{orig2}\) 开始，在生成阶段使用卡尔曼滤波更新状态，得到最终编辑图像 \(x_t\)。

## 3. 实验设计

- **数据集**：SFHQ（人脸，约1,200张子集）、HQ（合成编辑基准，320张子集）、ZONE（物体插入/编辑/移除，105张）、DIV2K（真实世界，105张）。
- **评估场景**：SFHQ 上添加眼镜或胡须；HQ 上复杂指令编辑；ZONE 和 DIV2K 上多种任务（局部编辑、结构保持）。
- **评价指标**：
  - 编辑质量：CLIP‑T（语义对齐）、Face Rec.（人脸相似度）。
  - 编辑一致性：CLIP‑I、DINO（高级语义相似度）、LPIPS（低级像素细节）、DreamSim（中级布局）。
- **对比方法**：
  - 流模型方法：RF‑Edit、RF‑Inversion、FlowEdit、FlowChef。
  - 扩散模型方法：SDEdit、P2P、MasaCtrl、DDPM‑Inv。
- **实现细节**：流模型基座使用 FLUX.1 dev，步数28；扩散模型基座使用 Stable Diffusion 1.4，步数50。

## 4. 资源与算力

论文明确说明所有实验在**单个 NVIDIA A40 GPU** 上完成。未提及训练时长（因为方法是训练无关的，仅推理），也未给出具体推理总耗时，仅在图4中比较了各方法的运行时间（Kalman‑Edit\* 仅次于 RF‑Inversion 和 FlowChef，快于其他流模型基线）。

## 5. 实验数量与充分性

- **主要实验**：在4个数据集上进行定量比较，每种方法均报告6个指标，共给出7个主表（表1‑表6）以及多个消融、可视化结果。
- **消融实验**：
  - 不同卡尔曼强度与步数对 CLIP‑I 和 LPIPS 的影响（表4）。
  - 有无卡尔曼滤波的对比（表5）。
  - 控制器放置阶段的影响（附录图14）。
- **定性实验**：多组编辑结果对比（图2、图3、图5、图6‑15等），涵盖风格迁移、场景编辑、大面积修改。
- **充分性评价**：实验设计较为全面，覆盖多个类别、多个指标、多种任务，并进行了消融和效率对比。但缺少统计显著性检验（如误差条），且部分对比方法（扩散模型）的基座与流模型不同，公平性仅通过统一调度步骤和推荐默认参数保证。

## 6. 论文的主要结论与发现

- 卡尔曼控制能有效利用历史反转轨迹，减少逐步骤误差累积，在保持编辑区域修改质量的同时显著提升非目标区域的结构一致性。
- 两阶段编辑策略（先生成中间语义混合潜变量，再应用卡尔曼滤波）比直接单轮控制效果更好，避免了语义模糊和伪影。
- 加速版本 Kalman‑Edit\* 在多数指标上接近全版本，且速度更快，实现性能与效率的平衡。
- 在 SFHQ、HQ、ZONE、DIV2K 四个数据集上，Kalman‑Edit 在大多数指标上达到或超过当前最先进方法。

## 7. 优点

- **方法创新**：首次将卡尔曼滤波引入流模型图像编辑，为控制理论在生成模型中的应用提供了新视角。
- **训练无关**：无需微调或训练，可直接利用预训练流模型。
- **两阶段设计**：有效解决了控制器过度或不足的问题，兼顾结构保持与编辑灵活性。
- **加速方案合理**：利用平行四边形法则近似，显著减少计算开销。
- **实验全面**：多数据集、多指标、多场景（风格迁移、场景编辑、局部修改），消融实验清晰。

## 8. 不足与局限

- **参数敏感**：对物体移除等任务需要额外调节超参数（如控制强度、滤波步数），默认参数可能失败（论文给出失败案例，图15）。
- **逆过程两次反转**：全版本 Kalman‑Edit 需要两次反转，计算成本略高；加速版 Kalman‑Edit\* 在某些任务（如对人脸）上结构保持可能下降（表1、表2显示 LPIPS 更高）。
- **缺少统计显著性报告**：未提供误差条或置信区间，难以评估结果是否具有统计可重复性。
- **对比公平性**：流模型方法使用 FLUX，扩散模型方法使用 SD 1.4，模型能力差异可能影响比较的绝对公平性。
- **应用限制**：对于需要大幅改变语义（如物体删除）的任务，当前方法依赖历史信息可能残留原始内容，需要额外参数搜索。

（完）
