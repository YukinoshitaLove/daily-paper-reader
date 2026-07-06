---
title: Efficient High-Resolution Image Editing with Hallucination-Aware Loss and Adaptive Tiling
title_zh: 高效高分辨率图像编辑：幻觉感知损失与自适应平铺
authors: "Young D. Kwon, Abhinav Mehrotra, Malcolm Chadwick, Alberto Gil Couto Pimentel Ramos, Sourav Bhattacharya"
date: 2025-09-20
pdf: "https://openreview.net/pdf?id=OqZFfDks0Q"
tags: ["query:real-ir"]
score: 10.0
evidence: 扩散模型的高效高分辨率图像编辑
tldr: 该工作提出MobilePicasso系统，通过幻觉感知损失和自适应平铺技术，在资源受限设备上实现高分辨率图像编辑，兼顾计算效率与编辑质量。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有扩散模型在资源受限设备上进行高分辨率编辑时面临内存和图像质量挑战。
method: MobilePicasso分三阶段：标准分辨率编辑加幻觉感知损失，潜空间投影，以及自适应上下文保持平铺上采样。
result: 用户研究显示在移动设备上实现了高效高分辨率编辑。
conclusion: MobilePicasso为移动端高分辨率图像编辑提供了实用解决方案。
---

## Abstract
High-resolution (4K) image-to-image synthesis has become increasingly important for mobile applications. Existing diffusion models for image editing face significant challenges, in terms of memory and image quality, when deployed on resource-constrained devices. In this paper, we present MobilePicasso, a novel system that enables on-device image editing at high resolutions, while minimising computational cost and memory usage. MobilePicasso comprises three stages: (i) performing image editing at a standard resolution with hallucination-aware loss, (ii) applying latent projection to overcome going to the pixel space, and (iii) upscaling the edited image latent to a higher resolution with adaptive context-preserving tiling. Our user study with 46 participants reveals that MobilePicasso not only improves image quality by 18-48% but reduces hallucinations by 14-51% over existing methods. MobilePicasso demonstrates significantly lower latency, e.g., up to 55.8x speed-up, yet with a small increase in runtime memory, e.g., a mere 9% increase over prior work. Surprisingly, the on-device runtime of MobilePicasso is observed to be faster than a server-based high-resolution image editing model running on an A100 GPU.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：在移动设备上实现高分辨率（4K）图像编辑的需求日益增长，然而现有基于扩散模型的图像编辑方法在资源受限设备上部署时，面临严峻的内存消耗与图像质量挑战，如生成伪影（幻觉）严重。
- **整体含义**：为解决上述问题，论文提出 **MobilePicasso** 系统，旨在以极小的计算成本和内存占用，在设备端实现高质量、高效的高分辨率图像编辑，使移动端编辑速度甚至超越服务器端高端 GPU（A100）上的同类任务。

## 2. 论文提出的方法论
MobilePicasso 包含三个核心阶段，构成端到端的高效高分辨率编辑流程：
- **第一阶段：标准分辨率编辑 + 幻觉感知损失**
  - 在常规较低分辨率下执行图像编辑，但设计了一种**幻觉感知损失**，在训练/推理中抑制模型产生不真实内容（即幻觉），从而提高编辑结果的保真度。
- **第二阶段：潜空间投影**
  - 替代传统的将潜编码解码到像素空间的步骤，直接对编辑后的图像潜变量进行**潜空间投影**，以避免因解码造成的质量损失和额外计算，确保后续操作在高效的特征空间中完成。
- **第三阶段：自适应上下文保持平铺上采样**
  - 将编辑后的低分辨率潜编码上采样至高分辨率（4K），采用**自适应上下文保持平铺**策略，将大图像分块处理，同时保持块间的上下文一致性，从而在有限内存下完成高质量放大。

## 3. 实验设计
- **用户研究**：面向 **46 名参与者** 进行主观评价，对比 MobilePicasso 与现有方法。
- **对比基准**：摘要中未列出具体对比方法名称，但明确指出与现有方法（existing methods）进行比较，并量化了提升幅度。
- **评估指标/场景**：从摘要提取的关键指标包括：
  - 图像质量提升：**18%–48%**
  - 幻觉减少：**14%–51%**
  - 延迟加速比：最高 **55.8倍**
  - 运行时内存：仅比先前工作增加 **9%**
  - 设备端运行时甚至快于在 **A100 GPU** 上运行的服务器端高分辨率编辑模型。
- **数据集**：摘要未提及具体数据集名称。

## 4. 资源与算力
- **模型推理设备**：明确提及移动设备（on-device）与服务器端 **A100 GPU** 进行速度对比，表明系统部署于资源受限设备且超越 A100 的延迟表现。
- **训练算力**：摘要未说明训练阶段使用的 GPU 型号、数量、训练时长或其他计算资源细节。

## 5. 实验数量与充分性
- **已呈现实验**：
  - 一项 46 人参与的用户研究，用于测量图像质量与幻觉程度。
  - 延迟与内存的定量对比（与先前工作及 A100 服务器模型比较）。
- **未明确部分**：摘要中未提及消融实验、不同数据集上的泛化测试或自动化指标（如 FID、CLIP score）的全面实验。因此，从已有信息无法判断实验是否覆盖了充分的客观评估和消融分析，但给出的用户研究和资源对比对核心声明形成了一定支撑。

## 6. 论文的主要结论与发现
- MobilePicasso 成功在设备端实现高分辨率图像编辑，各项表现优于现有方法：
  - 图像质量大幅提升，幻觉现象显著减少。
  - 延迟极低（最高 55.8 倍加速），内存开销增加极其微小（仅 9%）。
  - 惊人发现：设备端运行速度快于同任务在服务器 A100 GPU 上的执行速度，显示出极致的效率优化。
- 结论是该系统为移动端高分辨率图像编辑提供了一套可行的实用解决方案。

## 7. 优点
- **三阶段流水线设计新颖**：通过幻觉感知损失、潜空间投影和自适应上下文平铺，系统性地解决了移动端编辑从质量、效率到分辨率的全链路挑战。
- **极端效率优化**：在资源极度受限的设备上实现了超越旗舰服务器 GPU 的延迟，同时内存增量几乎可忽略，具有很高的工程落地价值。
- **强实验说服力**：通过较大规模用户研究和与 A100 的对比，直观证明了方法在主观质量和系统性能上的双重优势。

## 8. 不足与局限
- **方法细节缺失**：摘要未给出幻觉感知损失、潜投影和自适应平铺的具体公式或实现原理，难以评估其技术普适性。
- **实验信息不完整**：未披露使用的数据集、对比的具体 baseline 方法、消融实验以及自动化定量指标，因此结论的泛化性和客观可比性存疑。
- **局限性未指明**：摘要未讨论方法可能存在的局限，例如对特殊编辑类型（如大尺度形变）的可靠性、在不同硬件平台上的可移植性等。

（完）
