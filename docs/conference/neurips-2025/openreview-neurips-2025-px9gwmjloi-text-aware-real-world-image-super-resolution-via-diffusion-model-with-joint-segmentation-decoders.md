---
title: Text-Aware Real-World Image Super-Resolution via Diffusion Model with Joint Segmentation Decoders
title_zh: 基于扩散模型与联合分割解码器的文本感知真实图像超分辨率
authors: "Qiming Hu, Linlong Fan, luoyiyan, Yuhang Yu, Xiaojie Guo, Qingnan Fan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=px9GwMjloi"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用扩散模型进行文本感知的真实图像超分辨率
tldr: 生成模型在图像超分辨率中常扭曲文本结构。TADiSR提出文本感知注意力与联合分割解码器，在扩散超分辨率框架中同时恢复自然细节和文本区域的保真度，并设计了合成高质量文本掩码图像的完整流程。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1373, \"height\": 1151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1421, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1416, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 1143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1419, \"height\": 954, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1417, \"height\": 1014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1422, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1418, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1419, \"height\": 1096, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-px9gwmjloi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1419, \"height\": 1051, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-px9gwmjloi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-px9gwmjloi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1012, \"height\": 248, \"label\": \"Table\"}]"
motivation: 真实图像超分辨率中文本结构保真度不足。
method: 集成文本感知注意力和联合分割解码器的扩散超分辨率框架。
result: 在恢复自然细节和文本结构方面均取得优异性能。
conclusion: 文本感知机制可有效提升超分辨率中的结构保真度。
---

## Abstract
The introduction of generative models has significantly advanced image super-resolution (SR) in handling real-world degradations. However, they often incur fidelity-related issues, particularly distorting textual structures. 
In this paper, we introduce a novel diffusion-based SR framework, namely TADiSR, which integrates text-aware attention and joint segmentation decoders to recover not only natural details but also the structural fidelity of text regions in degraded real-world images. Moreover, we propose a complete pipeline for synthesizing high-quality images with fine-grained full-image text masks, combining realistic foreground text regions with detailed background content. Extensive experiments demonstrate that our approach substantially enhances text legibility in super-resolved images, achieving state-of-the-art performance across multiple evaluation metrics and exhibiting strong generalization to real-world scenarios. Our code is available at [here](https://github.com/mingcv/TADiSR).

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义
- **研究动机**：真实图像超分辨率（Real-SR）中，生成模型（GAN、扩散模型）能生成逼真图像，但常牺牲结构保真度，尤其严重扭曲文本结构（如复杂笔画的中文字符）。现有方法缺乏对文本区域的感知能力，导致笔画畸形、字符错误，影响用户体验和下游OCR应用。
- **整体含义**：本文旨在解决生成模型在超分辨率中文本结构失真的问题，提出一个统一、端到端的文本感知扩散超分辨率框架，同时保持自然细节和文本保真度。

## 2. 论文提出的方法论
### 核心思想
- 基于潜在扩散模型（LDM），引入文本感知交叉注意力（TACA）和联合分割解码器（JSD），实现图像超分辨率与文本分割的多任务学习，通过交叉注意力定位文本区域并引导结构恢复。

### 关键技术细节
- **文本感知交叉注意力（TACA）**：在U-Net中提取与提示词“text”对应的交叉注意力图，跨层拼接后线性投影，生成文本感知特征`a_tex`，与去噪潜变量`ˆz_H`一同输入解码器。
- **联合分割解码器（JSD）**：包含原始VAE图像解码器和对称的文本分割解码器，两者通过交叉解码器交互块（CDIB）进行多尺度、双流特征交互（类似GLU结构），同时输出超分辨率图像和文本分割掩码。
- **LoRA微调**：对U-Net和VAE解码器应用LoRA，高效引导交叉注意力聚焦文本区域，实现文本感知。
- **损失函数**：图像重建损失（MSE+LPIPS+改进焦点损失ℓ_mf），其中ℓ_mf利用分割掩码对边缘像素加权，强调困难文本结构；分割损失（MSE+Focal Loss+Dice Loss）。
- **数据合成流程**：构建FTSR数据集——从CTR数据集提取文本块，经SR、OCR质量筛选、SAM-TS分割得到高质量文本-掩码对，再随机粘贴到高质量背景（LSDIR，经OCR过滤文本）上，最后通过Real-ESRGAN退化生成LR-HR-Mask三元组。

### 公式/算法流程（文字说明）
1. 退化LR图像`x_L`经VAE编码得到`z_L`，提示词由文本编码器得到`c_y`，提取`c_tex`（对应“text”）。
2. U-Net一步去噪：`ˆz_H = (z_L - β_t * ˆn)/α_t`，其中`ˆn = U_ϕ(z_L; t, c_y)`。
3. 从所有交叉注意力层提取对应`c_tex`的切片，拼接后线性投影得到`a_tex`。
4. 联合解码器：`ˆx_H = Dv_ϕ(ˆz_H)`，`ˆs = Ds_φ(a_tex)`，两者通过CDIB交互。
5. 总损失`ℓ_tot = ℓ_img + ℓ_seg`联合优化。

## 3. 实验设计
### 数据集
- **训练集**：自建FTSR（50,000三元组，45,000训练/5,000测试）+ Real-CE（手动过滤后337训练对/189测试对）。
- **测试集**：FTSR测试集（FTSR-TE）和Real-CE验证集（Real-CE-val，对齐后）。
- **真实场景**：额外使用数字相机拍摄的多样真实世界样本（过曝霓虹灯、长文本、竖排文本、手写文本等）。

### Benchmark
- 4×超分辨率设置。
- 对比方法：GAN-based（R-ESRGAN, HAT）、扩散based（SeeSR, SupIR, OSEDiff）、文本专用SR（MARCONet, DiffTSR）。对后两者采用OCR检测+裁剪+SR+融合策略以适应全图。

### 评价指标
- PSNR、SSIM、LPIPS、FID、OCR识别准确率（OCR-A，基于Levenshtein比率）。

## 4. 资源与算力
- **明确说明**：训练采用4张H20 GPU（H20为NVIDIA高性能计算卡），每GPU batch size=1，迭代200,000步，使用PyTorch框架、AdamW优化器、固定学习率5×10⁻⁵。基于Kolors（LDM变体）实现，推理采用tile-based策略（类似SupIR）。

## 5. 实验数量与充分性
- **定量实验**：两个测试集（FTSR-TE和Real-CE-val）上对比8种方法，5个指标，结果全面。在FTSR上PSNR/SSIM/LPIPS/FID/OCR-A均最优；在Real-CE上OCR-A比第二名HAT提升18.7%。
- **消融实验**：3个变体（w/o JSD、w/o TACA、w/o MF Loss），在FTSR测试集上对比定量与定性，验证各组件有效性（OCR-A下降11.4%~3.3%，视觉上结构失真）。
- **真实场景定性**：包含5大类（过曝霓虹灯、长水平文本、竖排刻字、手写文本、Real-CE样张）共约15张图对比，展示方法优势。
- **分割效果对比**：与Hi-SAM比较，TADiSR分割更精细（图8）。
- **局限性分析**：提供一个高笔画密度字符失败案例，指出未来方向。
- **充分性与公平性**：所有对比方法使用官方代码并在相同训练集上微调（若提供）；文本SR方法采用OCR裁剪+后处理以保证全图输出，避免不公平比较。实验设计规范、全面。

## 6. 论文的主要结论与发现
- TADiSR在合成和真实场景下均显著优于现有方法，尤其在文本结构保真度（OCR-A大幅领先）和视觉质量（清晰笔画、无粘连）上。
- 文本感知交叉注意力（TACA）和联合分割解码器（JSD）是提升文本恢复性能的关键：TACA引导模型关注文本区域，JSD提供显式结构监督并促进双任务互益。
- 自建FTSR数据集有效支撑端到端训练，其合成流程可扩展。
- 该方法自然克服了垂直文本、长文本等场景下现有文本SR方法的局限。

## 7. 优点
- **创新性**：首次将扩散模型与文本分割任务联合，通过交叉注意力引导实现端到端全图文本感知超分辨率，无需复杂的检测-裁剪-融合流程。
- **实用性**：统一框架，推理单次完成；对多语言（中英文）、复杂布局（竖排、多行）鲁棒。
- **数据贡献**：提出可扩展的FTSR数据合成流程，解决了缺乏全图文本分割标注超分辨率数据的瓶颈。
- **实验严谨**：定量+定性+消融+真实场景，对比充分，且对文本SR方法做了公平适配（OCR裁剪+融合）。
- **性能提升显著**：Real-CE上OCR-A比第二名HAT提升18.7%，视觉上笔画重建明显更清晰。

## 8. 不足与局限
- **极端退化**：对于高笔画密度、笔画严重融合的字符（如某些汉字），仍可能产生结构偏差（图15所示案例）。人类肉眼也难以辨认，说明该极端情况未完全克服。
- **依赖合成数据**：训练主要基于FTSR合成数据（背景-文本粘贴），虽保证三元组强对应，但真实场景中文本与背景的融合、光照、模糊等可能有差异，需进一步在真实数据上微调。
- **分割标签来源**：部分训练标签来自Hi-SAM（SAM-TS）推理+OCR过滤，可能存在少量噪声，但实验表明整体有效。
- **额外计算开销**：同时训练两个解码器及交互模块，相比基线模型有额外参数和计算成本，但未量化FLOPS比较。
- **场景覆盖**：真实世界测试样本数量有限（数百张），虽然多样化但可能存在偏差，需更大规模真实场景验证。
- **未提供error bar**：该方法未报告多次运行的误差棒（但领域常规如此）。

（完）
