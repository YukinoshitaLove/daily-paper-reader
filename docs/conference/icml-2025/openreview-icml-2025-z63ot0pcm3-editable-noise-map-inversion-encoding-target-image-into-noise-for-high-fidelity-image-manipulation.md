---
title: "Editable Noise Map Inversion: Encoding Target-image into Noise For High-Fidelity Image Manipulation"
title_zh: 可编辑噪声图反演：将目标图像编码为噪声以实现高保真图像操作
authors: "Mingyu Kang, Yong Suk Choi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=z63Ot0pcM3"
tags: ["query:real-ir"]
score: 9.0
evidence: 提出用于基于扩散的文本引导图像编辑的反演方法
tldr: 针对现有扩散反演方法难以兼顾源图重建与目标提示遵从的问题，提出可编辑噪声图反演（ENM Inversion），直接编码目标图像为噪声图，增强编辑灵活性。在保持高重建质量的同时，更好地执行文本引导编辑，为扩散模型的高保真图像操作提供了新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1780, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1780, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 849, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1693, \"height\": 1595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1116, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1119, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1114, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 847, \"height\": 1366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z63ot0pcm3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1780, \"height\": 1032, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 800, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1715, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 325, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1689, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 845, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1583, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1614, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z63ot0pcm3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1213, \"height\": 253, \"label\": \"Table\"}]"
motivation: 现有反演方法在遵从目标提示与重建源图之间失衡。
method: 提出ENM反演，将目标图像直接编码为可编辑噪声图。
result: 实现了高保真重建和更精准的文本编辑对齐。
conclusion: ENM反演提升了扩散模型的图像编辑可控性与质量。
---

## Abstract
Text-to-image diffusion models have achieved remarkable success in generating high-quality and diverse images. Building on these advancements, diffusion models have also demonstrated exceptional performance in text-guided image editing. A key strategy for effective image editing involves inverting the source image into editable noise maps associated with the target image. However, previous inversion methods face challenges in adhering closely to the target text prompt. The limitation arises because inverted noise maps, while enabling faithful reconstruction of the source image, restrict the flexibility needed for desired edits. To overcome this issue, we propose Editable Noise Map Inversion (ENM Inversion), a novel inversion technique that searches for optimal noise maps to ensure both content preservation and editability. We analyze the properties of noise maps for enhanced editability. Based on this analysis, our method introduces an editable noise refinement that aligns with the desired edits by minimizing the difference between the reconstructed and edited noise maps. Extensive experiments demonstrate that ENM Inversion outperforms existing approaches across a wide range of image editing tasks in both preservation and edit fidelity with target prompts. Our approach can also be easily applied to video editing, enabling temporal consistency and content manipulation across frames.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义
- **研究动机**：基于文本到图像扩散模型的图像编辑通常需要先将源图像反演（invert）为一组可编辑的噪声图。现有反演方法（如DDIM inversion及其改进）主要关注源图像的精确重建，导致得到的噪声图缺乏足够的编辑灵活性，难以严格遵循目标文本提示，常出现编辑失败、内容残留或伪影。
- **核心问题**：如何获得既能忠实重建源图像（内容保留）又能灵活适应目标编辑（高编辑性）的噪声图。
- **整体含义**：该文提出了一种新的反演范式，不再仅为重建而反演，而是将目标图像“烙印”到噪声图中，从而同时保证内容一致性和编辑逼真度。

## 2. 方法论
- **核心思想**：可编辑噪声图反演（ENM Inversion）通过主动缩小“重建路径”和“编辑路径”产生的噪声图之间的差异，将目标图像信息直接编码到噪声图中，提升编辑性；同时添加重建误差损失以保持源图像内容。
- **关键技术细节**：
  - **观察基础**：分析与编辑成功/失败案例中重建噪声图和编辑噪声图的差异，发现差异越小编辑性能越好。
  - **可编辑噪声精炼（Editable Noise Refinement）**：
    - 定义编辑对齐损失：\( L_{\text{edit}} = \| f(z_t, t, C_{\text{src}}) - f(z_t, t, C_{\text{tgt}}) \|^2 \)，其中 \( f \) 为去噪函数，\( C_{\text{src}}, C_{\text{tgt}} \) 分别为源和目标文本嵌入。
    - 定义重建损失：\( L_{\text{prev}} = \| z_{t-1} - f(z_t, t, C_{\text{src}}) \|^2 \)。
    - 总损失：\( L = L_{\text{prev}} + \lambda L_{\text{edit}} \)，在每一步迭代优化 \( z_t \) 以最小化该损失，直至收敛或低于阈值 \( \tau \)。
  - **算法流程**（Algorithm 1）：对每个时间步 \( t \)，先进行常规DDIM反演得到初始 \( z_t \)，然后通过多次迭代梯度更新 \( z_t \)，同时平衡重建和编辑。
  - **扩展到视频编辑**：先微调图像扩散模型用于视频，再利用ENM反演对每一帧进行反演，最后通过跨帧注意力控制保证时序一致性。

## 3. 实验设计
- **数据集/场景**：
  - 图像编辑：PIE‑Bench（高分辨率图像，每张图像附有9种不同的编辑任务，涵盖语义和结构修改）。
  - 视频编辑：DAVIS数据集及网络采集视频，配有源和目标提示及区域蒙版。
- **Benchmark 与对比方法**：
  - 反演方法对比：DDIM Inversion、Null‑Text Inversion (NTI)、StyleDiffusion (StyleD)、Noise Map Guidance (NMG)、Edit‑Friendly DDPM Inversion (EF)、PnP Inversion (PNPInv) 以及固定点迭代法 (AIDI, FPI, ReNoise)。
  - 编辑管线组合：分别与 Prompt‑to‑Prompt (P2P)、MasaCtrl、Plug‑and‑Play (PnP) 结合测试；视频编辑则与 Tune‑A‑Video (TAV) 和 Video‑P2P 结合对比。
- **评价指标**：
  - 结构相似性：DINO score
  - 背景保留：PSNR, LPIPS, MSE, SSIM（基于未编辑区域）
  - 文本‑图像一致性：CLIP Similarity（全图及编辑区域）
  - 视频额外指标：TEMP（时序一致性）
  - 编辑性能分析：交叉注意力图与目标区域的对齐曲线。

## 4. 资源与算力
- 论文明确提到：“We perform all experiments on a single RTX3090.”（所有实验在单张RTX3090显卡上完成）。
- 未给出具体训练时长，但提供了反演方法的推理时间对比表（Table 2），ENM Inversion 用时约38.87秒，远快于NTI（148.48秒）和StyleD（382.98秒），但比DDIM（18.22秒）和PNPInv（28.17秒）略慢。

## 5. 实验数量与充分性
- 实验覆盖范围广：
  - 图像编辑定量对比表（Table 1,3,6,7）：至少3个主流编辑框架（P2P、MasaCtrl、PnP）与多种反演方法组合，数十个指标。
  - 视频编辑定量表（Table 4）：2种基线方法对比。
  - 消融实验（Table 5）：分析超参数 \( \lambda \)（编辑对齐权重）和 \( T \)（总步数）的影响，观察到 \( \lambda \) 增大编辑性提升但背景保留下降，步数多相似分数高。
  - 噪声图差异分析实验（Figure 3,7）：验证编辑性能与噪声图差异的反比关系。
  - 交叉注意力对齐实验（Figure 6）：展示ENM反演的编辑步数内对齐更稳定且更高。
  - 与固定点迭代法比较（Table 3）：证明固定点方法虽提升重建但降低编辑性，而ENM同时优化两者。
  - 源提示鲁棒性实验（Table 7）：使用空提示反演对重建质量无明显影响。
  - 扩展至流模型实验（Table 6）：与Rectified Flow结合同样提升效果。
- **充分性评价**：实验设计全面，对比方法覆盖主流基线，评估指标既有结构保留又有语义一致性，消融和鲁棒性分析完备，定性结果丰富（多张编辑结果图），整体客观且公平。

## 6. 主要结论与发现
- ENM Inversion通过最小化重建与编辑噪声图的差异，能够将目标图像特性编码进反演噪声中，大幅提升了文本引导图像编辑的灵活性和逼真度，同时保证了源图像内容的保留。
- 该方法与多种注意力控制编辑技术（P2P、MasaCtrl、PnP）兼容，在结构和背景保留、文本‑图像对齐等方面均优于现有反演方法。
- 可轻松扩展至视频编辑，获得时序一致且编辑精准的视频结果。
- 相比固定点迭代法，ENM Inversion在追求高编辑性时不会牺牲编辑能力，优于单纯追求精确重建的策略。

## 7. 优点
- **创新性强**：从噪声图差异最小化这一新颖角度解决编辑性的难题。
- **方法简洁有效**：通过添加一个编辑对齐损失并迭代优化，与现有编辑管线无缝集成。
- **编辑、保留双赢**：实验证明其在不降低甚至提升内容保真度的前提下，显著增强了编辑响应度。
- **广泛适用性**：支持多种编辑模式（对象变换、属性修改、背景替换等）和视频编辑；与流模型也可结合。
- **实验扎实**：大量定量与定性实验，多角度验证方法的有效性和鲁棒性。

## 8. 不足与局限
- **对基础模型依赖**：编辑能力受限于Stable Diffusion的生成边界，目标图像超出模型知识范围时可能失效。
- **计算效率问题**：每个目标提示需单独进行一次反演，无法复用源图像反演结果；多编辑场景下推理成本增加。
- **实时性不足**：虽然较NTI等快，但38秒的单次反演仍难以满足实时应用需求。
- **超参数敏感**：编辑对齐权重 \( \lambda \) 和总步数 \( T \) 需权衡，不同任务可能需要调参。
- **未涉及极端编辑**：实验中没有特别展示大姿态变化或全场景替换等极端情况，可能存在未知局限性。

（完）
