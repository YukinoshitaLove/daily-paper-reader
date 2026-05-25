---
title: Decomposition of Graphic Design with Unified Multimodal Model
title_zh: 利用统一多模态模型分解平面设计
authors: "Hui Nie, Zhao Zhang, Yutao Cheng, Maoke Yang, Gonglei Shi, Qingsong Xie, Jie Shao, Xinglong Wu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=7SG4s8d8AQ"
tags: ["query:real-ir"]
score: 9.0
evidence: 将复合设计分解为图层以促进精确图像编辑
tldr: 该论文提出图形设计层分解任务（LDGD），将复杂平面设计（如海报）转化为有序的RGBA图层及元数据。通过大型统一多模态模型DeaM解决属性预测和遮挡区域恢复挑战，实现精确图像编辑和高保真重建，为数字内容创作提供结构化方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7sg4s8d8aq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 796, \"height\": 842, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-7sg4s8d8aq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7sg4s8d8aq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 835, \"height\": 159, \"label\": \"Table\"}]"
motivation: 平面设计编辑需要结构化表示，但现有方法缺乏层分解能力。
method: 提出DeaM模型，集成视觉编码器、语言模型实现层分解。
result: 模型能准确预测图层属性并恢复遮挡区域，支持高保真重建。
conclusion: 层分解为图形设计提供灵活的编辑能力，促进内容管理与重用。
---

## Abstract
We propose Layer Decomposition of Graphic Designs (LDGD), a novel vision task that converts composite graphic design (e.g., posters) into structured representations comprising ordered RGB-A layers and metadata. By transforming visual content into structured data, LDGD facilitates precise image editing and offers significant advantages for digital content creation, management, and reuse. This task presents two core challenges: (1) predicting the attribute information (metadata) of each layer, and (2) recovering the occluded regions within overlapping layers to enable high-fidelity image reconstruction. To address this, we present the Decompose Layer Model (DeaM), a large unified multimodal model that integrates a conjoined visual encoder, a language model, and a condition-aware RGB-A decoder. DeaM adopts a two-stage processing pipeline: first generates layer-specific metadata containing information such as spatial coordinates and quantized encodings, and then reconstructs pixel-accurate layer images using a condition-aware RGB-A decoder. Beyond full decomposition, the model supports interactive decomposition via textual or point-based prompts.  Extensive experiments  demonstrate the effectiveness of the proposed method. The code is accessed at https://github.com/witnessai/DeaM.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机**：在数字媒体创作中，多层复合图像（如海报）是基本结构，但自动将一张合并后的平面设计分解为独立的、可编辑的图层（包含 RGBA 图像和元数据）依然是一个尚未解决的难题。
*   **核心问题**：论文形式化了一项新任务——**图形设计层分解（Layer Decomposition of Graphic Designs, LDGD）**，旨在将一张复合图像（如海报）转换成一组有序、带透明度的图层（RGB‑A）及其结构化元数据（位置、大小、字体、颜色等）。其本质是实现从“扁平像素”到“结构化图层”的逆向拆解。
*   **整体含义**：该任务可直接服务于精确图像编辑、素材归档、数字资产管理等应用，为图形设计的智能化理解与重用提供新的范式。

### 2. 论文提出的方法论

*   **核心思想**：利用大型统一多模态模型（Unified Multimodal Model）同时理解图像语义并生成结构化输出，将层分解建模为“先预测元数据（含视觉码本索引），再根据索引解码 RGBA 图层”的两阶段过程。
*   **关键技术细节**：
    *   **模型架构（DeaM）**：包含三个关键组件：
        *   **联合视觉编码器（Conjoined Visual Encoder）**：融合 CLIP ViT（高阶语义）与 DINO v2（低阶纹理）的特征，拼接后送入语言模型，以增强对不同语义层级元素（物体、装饰、文字）的感知。
        *   **语言模型骨干（LLM Backbone）**：InternLM2‑7B，扩展词表以容纳 VQ‑GAN 码本的特殊 token（`<vt‑xxxxx>`）。
        *   **条件感知的 RGBA 解码器（Condition‑Aware RGB‑A Decoder）**：以原始图像的对应裁剪区域作为条件，并预测一个遮挡掩码（Occlusion Mask），引导解码器重点修复被遮挡的部分，从而提升重建清晰度。
    *   **训练流程（三阶段）**：
        1.  **RGBA VQ‑GAN 训练**：将普通 VQ‑GAN 改为 4 通道（RGB + Alpha），并用不同权重优化 RGB 与 Alpha 重建损失，避免编码歧义。下采样率 \(f=16\)，每张图层被压缩为 12×12 或 8×8 的码本索引序列。
        2.  **指令微调（Instruction Tuning）**：在自然图像上训练模型自回归生成 JSON 元数据（包括类别、位置、层级顺序、码本索引等）。引入可学习的换行 token 增强二维序列的规律性，降低预测难度。
        3.  **解码器训练**：冻结 VQ 编码器，仅用 ResNet 作为条件编码器，与 VQ 解码器联合训练，使生成图像更清晰。
    *   **交互范式**：除全自动分解外，模型支持文本提示（“分解包含文字的图层”）和点指点（用户提供坐标）的交互式分解。
*   **公式或算法流程**：整体流程为：输入图像 → 联合视觉编码 → LLM 预测包含 `<vt‑...>` token 的 JSON 元数据 → 将 token 序列重排为二维矩阵，从码本取出嵌入 → 条件感知解码器结合原图对应区域及预测的遮挡掩码 → 输出清晰的 RGBA 图层。重建损失沿用 VQ‑GAN 的损失。

### 3. 实验设计

*   **数据集**：
    *   **训练数据**：自建数据集 **CreatiLD**，包含超过 22.4 万张多层海报，平均每张 10.3 个图层，同时补充了图像描述、文本内容、字体、颜色等标注。
    *   **测试数据**：公开学术数据集 **Crello（VistaCreate）**，包含约 2000 张平面设计作品，附有图层顺序、位置等真值。
*   **Baseline 与对比方法**：
    *   **自建 Baseline**：结合 OCR 提取文字、图像抠图（matting）与火山引擎 API 进行区域修复，仅能分解为背景、主体、文字三个图层。
    *   **其他对比**：与指令式图像编辑方法 **MGIE**（仅展示定性结果）以及矢量图分解方法 **LIVE**（针对 Logo 及复杂自然图像）进行比较。
*   **评估指标**：
    *   **重建质量**：将所有图层按预测顺序重渲染后，与原始图像计算 **FID**（Fréchet Inception Distance）。
    *   **定位精度**：对核心主体等元素，采用匈牙利匹配计算预测框与真实框的 **平均 IoU（Loc α）**。

### 4. 资源与算力

*   论文明确提到使用 **16 块 NVIDIA A800 GPU** 进行训练，但未披露具体训练时长。

### 5. 实验数量与充分性

*   **实验组数**：论文主要进行了消融实验和与 Baseline 的对比。
    *   **消融实验**：针对联合视觉编码器、增强预测规律性、条件感知解码器三个关键组件，在 Crello 数据集上以 FID 为指标进行 4 组实验（见表1）。
    *   **主对比实验**：与自建 Baseline 在 Crello 上对比 FID 和 IoU（见表2）。
    *   **定性分析**：展示了全自动分解、Baseline 对比、文本/点指令分解、与 LIVE 的对比等大量定性结果（图 4‑7）。
*   **充分性与公平性**：
    *   **优点**：消融实验清晰地验证了各个模块的有效性；定量指标（FID + IoU）与可视化结果相互印证，对比公平。
    *   **局限**：对比方法较少，仅与一个简易 Baseline 和少数其他领域的代表性方法比较，缺乏针对该任务的特有模型对比（因该任务为首次提出）。实验全部集中于 Crello 一个公开测试集，缺乏跨数据集的泛化性验证。

### 6. 论文的主要结论与发现

*   所提出的 LDGD 任务框架可行且实用，能够将复杂海报分解为结构合理的多图层。
*   DeaM 模型在图像重建质量（FID 70.63 vs. Baseline 99.60）和定位精度（Loc α 0.71 vs. 0.71，定位略优）上显著优于传统 OCR+抠图+修复的流水线方法。
*   三个关键设计（联合视觉编码、换行 token 增强预测规律、条件感知解码器）均对性能有正向贡献，其中条件感知解码器带来的提升最为显著。
*   模型具备拓展交互能力，能够根据文本或空间点指令选择性地输出指定图层，展示出对图像多粒度语义的理解。
*   与图像矢量法 LIVE 相比，DeaM 在处理含复杂自然图像的海报时鲁棒性更强。

### 7. 优点

*   **问题新颖**：首次明确定义图形设计的图层分解任务，并构建了大规模专用数据集。
*   **方法统一**：采用单一多模态模型同时完成“理解”与“生成”，将元数据预测和图像重建有机融合。
*   **技术精巧**：RGBA VQ‑GAN、换行 token 增强二维规律性、条件感知解码器等设计环环相扣，有效解决了训练和生成中的具体难点。
*   **交互灵活**：支持全自动分解及文本、点指令的交互式分解，提升了实用性。
*   **可复现**：开源代码，有利于后续研究。

### 8. 不足与局限

*   **对比基准薄弱**：仅与一个自建的传统流程 Baseline 进行定量对比，未与其他可能的分解策略（如分割+补全）或最新多模态生成模型进行深度比较。
*   **测试范围有限**：所有定量实验仅在 Crello 一个数据集上完成，缺乏在其他类型设计图（如网页、杂志）或真实用户数据上的泛化性验证。
*   **字体预测不足**：论文承认字体识别的准确度仍有提升空间，这会影响文字图层的完美重建和二次编辑。
*   **图像生成质量有待提高**：定性结果中解码图像存在一定模糊，论文也指出需要更强大的图像 tokenizer 来改善。
*   **算力需求**：使用 16 块 A800 GPU，模型规模较大，可能对资源受限环境不友好。
*   **层级歧义处理**：对装饰性元素，模型可能将本可分开的多个图层预测为同一层，层级粒度的合理性仍有优化空间。

（完）
