---
title: "AddSR: Accelerating Diffusion-based Blind Super-Resolution with Adversarial Diffusion Distillation"
title_zh: AddSR：利用对抗扩散蒸馏加速基于扩散的盲超分辨率
authors: "Rui Xie, Ying Tai, Chen Zhao, Kai Zhang, Zhenyu Zhang, Jun Zhou, Xiaoqian Ye, qian Wang, Jian Yang"
date: 2024-09-26
pdf: "https://openreview.net/pdf?id=BpKbKeY0La"
tags: ["query:real-ir"]
score: 10.0
evidence: 使用对抗扩散蒸馏加速盲超分辨率
tldr: 该论文针对基于稳定扩散的盲超分方法推理效率低的问题，引入对抗扩散蒸馏(ADD)来加速。通过改进训练策略平衡感知与失真，并增强条件输入鲁棒性，显著减少了采样步数。实验表明AddSR在保持生成质量的同时大幅提升速度，为扩散超分的实用化迈进重要一步。
source: ICLR-2025-Public
selection_source: conference_retrieval
motivation: 现有扩散盲超分方法需数百步采样，效率低下，无法实际应用。
method: 引入对抗扩散蒸馏，优化感知-失真平衡并增强条件输入质量，大幅减少采样步数。
result: 在多个基准上以少量步骤取得与多步方法相当甚至更优的超分效果。
conclusion: AddSR成功将扩散盲超分加速至实用水平，同时保持高质量生成。
---

## Abstract
Blind super-resolution methods based on Stable Diffusion (SD) demonstrate impressive generative capabilities in reconstructing clear, high-resolution (HR) images with intricate details from low-resolution (LR) inputs. However, their practical applicability is often limited by poor efficiency, as they require hundreds to thousands of sampling steps.
Inspired by Adversarial Diffusion Distillation (ADD), we incorporate this approach to design a highly effective and efficient blind super-resolution method. Nonetheless, two challenges arise: First, the original ADD significantly reduces result fidelity, leading to a perception-distortion imbalance. Second, SD-based methods are sensitive to the quality of the conditioning input, while LR images often have complex degradation, which further hinders effectiveness.
To address these issues, we introduce a Timestep-Adaptive ADD (TA-ADD) to mitigate the perception-distortion imbalance caused by the original ADD. Furthermore, we propose a prediction-based self-refinement strategy to estimate HR, which allows for the provision of more high-frequency information without the need for additional modules.
Extensive experiments show that our method,~\name, generates superior restoration results while being significantly faster than previous SD-based state-of-the-art models (e.g., $7\times$ faster than SeeSR).

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：基于 Stable Diffusion（SD）的盲超分辨率方法虽能生成清晰、细节丰富的高分辨率图像，但需数百乃至数千步采样，推理效率极低，严重阻碍实际应用。
- **研究动机**：受对抗扩散蒸馏（Adversarial Diffusion Distillation, ADD）启发，希望将该蒸馏技术引入盲超分任务，极大减少采样步数，同时保持高质量的生成效果。
- **整体含义**：论文试图在“速度”与“质量”之间找到更优的平衡，使扩散模型在超分任务中真正走向实用化。

### 2. 论文提出的方法论
- **核心思想**：以 ADD 为基础框架加速 SD 盲超分，并针对该场景下的两大挑战进行针对性改进。
- **关键技术细节**：
  - **挑战一**：原始 ADD 会明显降低结果保真度，造成“感知–失真”不平衡。为此提出 **Timestep-Adaptive ADD (TA-ADD)**，通过时间步自适应的策略来缓解这种不平衡。
  - **挑战二**：SD 方法对条件输入质量敏感，而低分辨率图像往往退化复杂、信息严重缺失。为此提出 **基于预测的自精炼策略 (prediction-based self-refinement strategy)**，旨在估计出高质量的高分辨率图像，以此为模型提供更丰富的高频信息，且无需额外模块。
- **算法流程**：整体可理解为，利用 TA-ADD 在少量步数内完成“扩散采样→高分辨率估计”的过程，并用自精炼策略提升条件输入质量，从而在加速的同时保证还原效果。
- **命名**：方法最终定名为 **AddSR**。

### 3. 实验设计
- **数据集 / 场景**：论文未在摘要中列出具体数据集名称，通常盲超分领域会使用 DIV2K、Flickr2K、RealSR、DRealSR 等合成或真实退化数据集。
- **对比方法**：明确与基于 SD 的先前领先模型 **SeeSR** 进行对比，并以“比 SeeSR 快 7 倍”量化加速效果。此外，摘要提到与“previous SD-based state-of-the-art models”进行对比，暗示可能包含其他扩散类盲超分方法。
- **评估基准**：从“生成优越的复原结果”并实现显著加速来看，评估维度应同时涵盖图像质量指标（如 PSNR、SSIM、LPIPS、FID 等）和推理效率（采样步数、运行时间）。

### 4. 资源与算力
- **摘要未提供**任何关于 GPU 型号、数量、训练时长、内存开销等算力信息。需要查看正文才能获得具体配置。

### 5. 实验数量与充分性
- **摘要信息有限**，但可推断至少包含以下实验组：
  - 与当前领先方法（如 SeeSR）的对比实验，验证速度与质量的综合优势。
  - 消融实验以验证 TA-ADD 和自精炼策略各自的有效性（摘要中提出的两个改进点通常会被单独消融）。
- **充分性判断**：仅凭摘要无法确认是否在多个数据集、多种退化类型下进行测试，但从“extensive experiments show”的表述来看，作者自述实验较为广泛。是否充分需结合实际评测才能最终判断。
- **客观性与公平性**：声称比 SeeSR 快 7 倍，同时在视觉质量上生成更优结果，对比时若使用相同的评估协议和官方的复现或预训练模型，则具备一定公平性。

### 6. 论文的主要结论与发现
- AddSR 成功将扩散盲超分加速至实用水平，仅需极少量采样步数就能生成高质量结果。
- 所提出的 TA-ADD 能有效缓解原始 ADD 带来的感知–失真失衡问题。
- 基于预测的自精炼策略可在不增加模块的情况下，显著增强条件输入中的高频信息，提升最终复原效果。
- 该方法在速度上远超现有基于 SD 的先进方法（如比 SeeSR 快 7 倍），同时保持甚至超越其生成质量，向扩散超分的实用化迈出了重要一步。

### 7. 优点
- **效率大幅提升**：成功将数百步采样减少至极少步数，推理速度显著提高，增强了实用性。
- **创新性改进**：TA-ADD 针对盲超分特点修复了 ADD 的失真问题，自精炼策略则在没有额外参数负担的前提下增强条件信息，设计精巧。
- **性能优越**：以少步数取得与多步数 SD 方法相当或更优的效果，在速度和质量之间取得良好平衡。

### 8. 不足与局限
- **摘要信息缺失**：未提供具体数据集、退化方式、训练配置、算力开销等细节，外部读者难以评估其复现门槛和适用范围。
- **可能存在的偏差**：依赖 SD 先验，可能对训练时未见过的重度或特殊退化不鲁棒；对抗蒸馏训练本身可能不稳定。
- **实验覆盖风险**：文中仅能确认与 SeeSR 及部分 SD SOTA 对比，是否包含基于 GAN 或纯回归的盲超分方法（如 BSRGAN、Real-ESRGAN 等）未知。若缺少这些对比，速度与质量的综合优势可能被高估。
- **应用限制**：虽然速度提升，但仍可能无法满足视频超分等实时性要求极高的场景；方法对预训练的 SD 模型依赖性强，可能继承其潜在的偏见与生成伪影。

（完）
