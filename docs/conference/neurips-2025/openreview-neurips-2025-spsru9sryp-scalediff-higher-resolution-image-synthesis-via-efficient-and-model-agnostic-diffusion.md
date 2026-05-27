---
title: "ScaleDiff: Higher-Resolution Image Synthesis via Efficient and Model-Agnostic Diffusion"
title_zh: "ScaleDiff: 通过高效且模型无关的扩散实现高分辨率图像合成"
authors: "Sungho Koh, SeungJu Cha, Hyunwoo Oh, Kwanyoung Lee, Dong-Jin Kim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SpSru9SRyp"
tags: ["query:real-ir"]
score: 7.0
evidence: 模型无关的高效扩散框架实现高分辨率图像生成
tldr: 针对预训练扩散模型在生成超出训练分辨率图像时性能退化的问题，本文提出ScaleDiff框架。该框架无需额外训练，通过引入邻域块注意力（NPA）减少自注意力计算冗余，并集成到SDEdit流程中，同时提出隐空间频率混合（LFM）策略。ScaleDiff是模型无关的，兼容多种扩散架构，高效地生成了高分辨率且高质量的图像，扩展了扩散模型的分辨率能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1221, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 656, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1235, \"height\": 1005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1380, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1156, \"height\": 1615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1296, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1162, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1317, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1299, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1236, \"height\": 1345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1419, \"height\": 2164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1420, \"height\": 2192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-spsru9sryp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1420, \"height\": 2178, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-spsru9sryp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1310, \"height\": 951, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-spsru9sryp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1271, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-spsru9sryp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-spsru9sryp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 1046, \"label\": \"Table\"}]"
motivation: 预训练扩散模型在生成高于训练分辨率的图像时性能退化，现有方法计算量大或兼容性差。
method: 提出模型无关的ScaleDiff，使用邻域块注意力和隐空间频率混合，无需训练。
result: 在多种扩散模型架构上成功生成高分辨率图像，且效率高、质量好。
conclusion: 模型无关的训练自由方法有效扩展了扩散模型的分辨率上限。
---

## Abstract
Text-to-image diffusion models often exhibit degraded performance when generating images beyond their training resolution.
Recent training-free methods can mitigate this limitation, but they often require substantial computation or are incompatible with recent Diffusion Transformer models.
In this paper, we propose ScaleDiff, a model-agnostic and highly efficient framework for extending the resolution of pretrained diffusion models without any additional training.
A core component of our framework is Neighborhood Patch Attention (NPA), an efficient mechanism that reduces computational redundancy in the self-attention layer with non-overlapping patches.
We integrate NPA into an SDEdit pipeline and introduce Latent Frequency Mixing (LFM) to better generate fine details.
Furthermore, we apply Structure Guidance to enhance global structure during the denoising process.
Experimental results demonstrate that ScaleDiff achieves state-of-the-art performance among training-free methods in terms of both image quality and inference speed on both U-Net and Diffusion Transformer architectures.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：预训练的文本到图像扩散模型（如 SDXL、FLUX）在生成超出其训练分辨率（例如 1024²）的高分辨率图像（如 2048² 或 4096²）时，性能显著下降，产生重复伪影和结构扭曲。直接在高分辨率数据集上训练这些模型成本极高，因此需要一种无需额外训练、通用且高效的方法来扩展其分辨率能力。
- **核心目标**：提出一个**模型无关**（同时适用于 U-Net 和 Diffusion Transformer 架构）且**计算高效**的无训练框架 ScaleDiff，实现高质量、高分辨率的图像合成。

## 2. 论文提出的方法论

- **总体范式**：基于 SDEdit（升采样–扩散–去噪）管道重新生成高分辨率图像。
- **核心组件**：
  - **邻域块注意力（Neighborhood Patch Attention, NPA）**：针对自注意力层的计算冗余，将查询（Query）划分为**非重叠**的小块，每个查询块从对应**重叠**的邻域窗口中提取键（Key）和值（Value），从而避免传统逐块方法中所有层（如线性、卷积）的冗余计算。这使得非自注意力层可直接在完整潜特征上运行，自注意力计算量从 \((2s-1)^2 h^2 w^2 d\) 降低至 \(s^2 h^2 w^2 d\)（\(s\) 为分辨率缩放因子）。
  - **隐空间频率混合（Latent Frequency Mixing, LFM）**：将 RGB 空间升采样后经 VAE 编码的潜特征中的高频成分（Z_RU 的高频部分）与直接在潜空间升采样得到的低频成分（Z_LU 的低频部分）线性组合，获得参考潜变量 Z_ref。此举避免了 RGB 升采样导致的过平滑偏置，同时保留了稳定解码所需的高频细节。
  - **结构引导（Structure Guidance, SG）**：在每个去噪时间步，将模型预测的干净潜变量 Z_{0|t} 的低频成分与参考潜变量 Z_ref 的低频成分进行加权融合（权重 γ_t），从而维持全局结构一致性。
- **管道流程**：首先生成低分辨率潜变量，再通过 LFM 获得参考潜变量 Z_ref，然后向 Z_ref 添加噪声至中间时间步 τ，最后利用集成了 NPA 的扩散网络逐步去噪，并在去噪过程中应用 SG 引导。

## 3. 实验设计

- **数据集与场景**：从 LAION-5B 中随机抽取 1000 对图像-文本对作为测试集。
- **基准方法对比**（无训练方法为主）：
  - **训练无关方法**：ScaleCrafter、HiDiffusion、DiffuseHigh、FreeScale、DemoFusion、AccDiffusion v2、MultiDiffusion
  - **超分辨率模型**：BSRGAN、OSEDiff
  - **训练型方法**：UltraPixel
  - 直接推理基线：SDXL Direct、FLUX Direct
- **评估指标**：FID、KID、Inception Score（全局及 patch 级：FID_p、KID_p、IS_p）、CLIP Score。
- **生成分辨率**：2048² 和 4096²；管道采用 1024² → 2048² → 4096² 的迭代升采样。

## 4. 资源与算力

- 论文明确说明：“All experiments are conducted on a single NVIDIA A6000 GPU.”
- 未提及训练时长（方法无需训练），但给出了各方法的推理时间（秒）作为效率指标。

## 5. 实验数量与充分性

- **定量实验**：在 SDXL 和 FLUX 两个架构上，分别在 2048² 和 4096² 分辨率下与 10+ 种基线方法进行对比，报告了多组指标（表 2）。
- **定性实验**：提供了多幅 4096² 图像的视觉对比（图 5、图 6），以及针对不同模型（SDXL、FLUX、Lumina-T2X）的更多结果（附录 C）。
- **消融实验**：
  - NPA vs. 直接推理 vs. MultiDiffusion（图 6、表 3）。
  - LFM 和 SG 的分别消融（表 3、图 7）。
  - 噪声时间步 τ 的消融（表 4）。
- **其他分析**：不同分辨率下的推理时间对比（附录 B.2）、全景生成（附录 B.3）、裁剪策略变体（附录 B.1）。
- **充分性评价**：实验覆盖了主流 U-Net 和 DiT 模型，对比了最先进的训练无关方法和部分训练型方法，消融验证了各组件的必要性。实验设计客观、公平，指标多样，定量与定性结合，充分支持了核心主张。唯一不足是未提供错误条或统计显著性分析，但推理时间等已直接给出。

## 6. 论文的主要结论与发现

- ScaleDiff 在训练无关方法中达到了**最先进的性能**，在图像质量和推理速度上均优于对比方法。
- NPA 在保持与 MultiDiffusion 相近生成质量的同时，实现了 **2.8× 速度提升**（FLUX 4096²）。
- LFM 有效缓解了 RGB 空间升采样导致的过平滑问题，SG 成功抑制了块处理带来的重复伪影。
- 该方法对 U-Net（SDXL）和 Transformer（FLUX、Lumina-T2X）均适用，验证了其模型无关性。

## 7. 优点

- **高效性**：NPA 显著降低了自注意力计算量，使推理速度大幅提升（4096² 下 SDXL 仅需 113 秒，而 DemoFusion 需 1005 秒）。
- **模型无关**：可无缝应用于 U-Net 和 DiT 架构，无需修改模型权重。
- **无需训练**：完全零训练，降低了高分辨率生成的门槛。
- **综合性能**：在定量指标（FID、IS、CLIP Score）和视觉质量上均表现优异，细节丰富且结构一致。
- **技术创意**：隐空间频率混合是新颖的预处理策略，有效利用了不同升采样路径的优点。

## 8. 不足与局限

- **依赖基础模型能力**：作为无训练框架，最终质量受限于预训练模型本身的先验知识。
- **块处理固有缺陷**：patch-based 方法可能在某些场景下产生不一致的局部内容或背景重复伪影（论文附录 D 已承认）。
- **超参数敏感**：噪声时间步 τ 和引导强度 γ_t 需针对不同模型手动调节（论文提供了经验值但未深入分析敏感性）。
- **实验覆盖范围**：仅测试了 1K→2K→4K 的升采样场景，未评估更高分辨率（如 8K）或不同缩放因子下的泛化能力；未进行跨数据集或真实世界低分辨率输入的评估。
- **统计显著性**：未报告误差棒或置信区间，可能影响结果的可重复性判断。

（完）
