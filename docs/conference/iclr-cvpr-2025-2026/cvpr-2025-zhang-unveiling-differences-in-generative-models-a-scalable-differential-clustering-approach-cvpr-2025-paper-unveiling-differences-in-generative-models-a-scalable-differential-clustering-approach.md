---
title: "Unveiling Differences in Generative Models: A Scalable Differential Clustering Approach"
title_zh: 揭示生成模型的差异：一种可扩展的微分聚类方法
authors: "Zhang, Jingwei, Jalali, Mohammad, Li, Cheuk Ting, Farnia, Farzan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Unveiling_Differences_in_Generative_Models_A_Scalable_Differential_Clustering_Approach_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 7.0
evidence: 通过微分聚类识别两个生成模型产生差异的样本类型
tldr: 针对简单评分无法揭示生成模型间细微差异的问题，提出解决微分聚类问题，开发基于傅里叶的新颖聚类识别方法FINC，以检测两个生成模型产生频率更高的模式，实现可扩展的细粒度模型对比，为生成模型的深入分析提供了新工具。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 332, \"height\": 213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 317, \"height\": 109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1527, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1117, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1460, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1458, \"height\": 682, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-unveiling-differences-in-generative-models-a-scalable-differential-clustering-approach-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 572, \"label\": \"Table\"}]"
motivation: 现有评分排序无法揭示生成模型在产生不同样本类型时的细微差异。
method: 提出微分聚类问题，并用谱方法FINC识别生成模型产生频率更高的模式。
result: 可扩展地检测两个生成模型的差异模式，实现细粒度对比。
conclusion: FINC提供了一种可扩展且有效的生成模型差异分析方法。
---

## Abstract
A fine-grained comparison of generative models requires the identification of sample types generated differently by each of the involved models. While quantitative scores have been proposed in the literature to rank different generative models, score-based evaluation and ranking do not reveal the nuanced differences between the generative models in producing different sample types. In this work, we propose solving a differential clustering problem to detect sample types generated differently by two generative models. To solve the differential clustering problem, we develop a spectral method called Fourier-based Identification of Novel Clusters (FINC) to identify modes produced by a generative model with a higher frequency in comparison to a reference distribution. FINC provides a scalable algorithm based on random Fourier features to estimate the eigenspace of kernel covariance matrices of two generative models and utilize the principal eigendirections to detect the sample types present more dominantly in each model. We demonstrate the application of the FINC method to large-scale computer vision datasets and generative modeling frameworks. Our numerical results suggest the scalability of the developed Fourier-based method in highlighting the sample types produced with different frequencies by generative models. The project code is available at https://github.com/buyeah1109/FINC

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有的生成模型评估指标（如 IS、FID）只能给出生成分数，无法揭示两个模型在**生成不同样本类型（模式）时存在的细微差异**。例如，无法回答“模型 G₁ 在生成哪类图像上明显优于或劣于模型 G₂”这类细粒度对比问题。
- **研究动机**：
  - 分数排名可能与人评估不一致，需要更可解释的对比方法。
  - 识别生成模型中出现频率更高或更低的样本簇（模式），有助于发现模型的**优势模式、次优模式、高记忆化模式**等，从而指导模型改进。
- **整体含义**：提出一种**可扩展的微分聚类方法**，从样本类型层面比较两个生成模型（或一个模型与参考数据集），不再仅仅输出一个数字，而是输出“哪些样本类型在两个分布中出现的频率差异显著”。

### 2. 论文提出的方法论
- **核心思路**：将模型对比形式化为**微分聚类（differential clustering）问题**：给定测试模型生成的样本集 \(X\) 和参考分布样本集 \(Y\)，找出在测试模型中频率显著高于参考分布中频率的样本簇（模式）。
- **谱方法背景**：基于核协方差矩阵差 \(\Lambda_{X|\rho Y} = \widehat{C}_X - \rho \widehat{C}_Y\)（\(\rho \ge 1\) 为新颖性阈值），该矩阵的正特征值对应的特征向量能够揭示测试分布中频率达参考分布 \(\rho\) 倍以上的模式。
- **FINC（Fourier-based Identification of Novel Clusters）算法**：
  - **可扩展设计**：传统核方法需要对 \((n+m)\times(n+m)\) 的核矩阵做特征分解，复杂度高。FINC 利用 **随机傅里叶特征（RFF）** 近似高斯核，将问题转化为对一个 **\(2r\times 2r\) 小矩阵**的特征分解，其中 \(r\) 是傅里叶特征数量。
  - **关键步骤**：
    1. 从 \(\mathcal{N}(0, \frac{1}{\sigma^2}\mathbf{I}_d)\) 采样 \(r\) 个频率向量 \(\omega_1,\dots,\omega_r\)，构造特征映射 \(\widetilde{\phi}_r(x) = \frac{1}{\sqrt{r}}[\cos(\omega_1^\top x),\sin(\omega_1^\top x),\dots,\cos(\omega_r^\top x),\sin(\omega_r^\top x)]\)。
    2. 分别计算测试和参考样本的 \(2r\times 2r\) 经验协方差矩阵 \(\widetilde{C}_X, \widetilde{C}_Y\)。
    3. 计算差分矩阵 \(\widetilde{\Lambda}_{X|\rho Y} = \widetilde{C}_X - \rho \widetilde{C}_Y\)，并对其进行特征分解。
    4. 正特征值对应的特征向量即代表测试分布中出现频率更高的模式。通过特征向量可计算任意样本的模式相似度分数 \(s_{\mathbf{u}}(x) = \sum_{i=1}^r [u_{2i-1}\cos(\omega_i^\top x) + u_{2i}\sin(\omega_i^\top x)]\)。
  - **理论保证**（定理 1）：仅需 \(r = O\left(\frac{\log (m+n)}{\epsilon^4}\right)\) 个傅里叶特征，即可保证近似特征值与特征向量的误差被控制在 \(\epsilon\) 以内，复杂度与样本数呈对数关系，因此具有很好的扩展性。

### 3. 实验设计
- **数据集**：ImageNet-1K（含子集 ImageNet-dogs）、CelebA、FFHQ、AFHQ、Colored MNIST、Fashion-MNIST 等。
- **场景与任务**：
  - **可控验证**：在 Colored MNIST 上人为引入已知新颖模式（彩色数字），验证 FINC 能否准确检出。
  - **跨数据集新颖模式发现**：例如 AFHQ vs. ImageNet-dogs，展示模型能发现数据集间的差异模式。
  - **生成模型与参考数据集比较**：找出生成模型相对于 ImageNet 训练集的高频（overrepresented）模式。
  - **生成模型间比较**：对比 BigGAN、StyleGAN-XL、DiT-XL、LDM、GigaGAN、RQ-Transformer 等模型，找出一个模型相对于另一个模型更频繁生成的模式。
  - **高记忆化模式检测**：用 FLD 记忆化分数将样本分为高/低记忆化两组，用 FINC 找出高记忆化组中更频繁出现的样本类型。
  - **CLIPScore 对齐模式检测**：对文本到图像模型，按 CLIPScore 高低分组，用 FINC 发现对齐好/差的视觉模式。
- **对比方法**：
  - Rarity score + 后聚类
  - FLD score + 后聚类
  - KEN（核熵新颖性，直接特征分解/Cholesky 分解）
  - 本文提出的 FINC（\(r=2000\)）
- **评测指标**：运行时间（可扩展性）、定性可视化（模式的一致性、语义合理性）。

### 4. 资源与算力
- 文中**未明确说明所使用的 GPU 型号、数量或训练时长**。
- 表 1 记录了不同方法在 CPU 和 GPU 上的运行时间（秒），并提到在示例大小超过 10k 和 50k 时，基线方法会出现内存溢出，而 FINC 成功运行到 250k 样本。从运算环境可推测使用了商用级 GPU，但精确硬件配置未提供。

### 5. 实验数量与充分性
- **实验组数**：
  - 涉及 **6 个以上**的生成模型框架（GAN、扩散、VAE 等）。
  - 覆盖 **4 个主要任务**（模式发现、模型对比、记忆化模式、CLIP 对齐模式），每个任务至少展示 2 个代表性模式。
  - 可扩展性实验在 **8 个样本规模**（1k～250k）下测试了 FINC 及 3 种基线。
  - 可控实验在 MNIST 和 Fashion-MNIST 上验证了方法的基本正确性。
  - 定性展示了 ImageNet-dogs 与 AFHQ 间的模式差异。
- **充分性与公平性**：
  - 实验覆盖了较大尺度的数据集（ImageNet-1K）和多种生成范式，任务设计丰富。
  - 对比方法均采用原作者开源代码，公平性较好。
  - 但**缺乏定量指标**（如聚类纯度、NMI）直接评估模式检测质量，主要依赖可视化与语义合理性，可能会引入主观偏差。消融研究（如不同 \(r\)、\(\rho\)、带宽 \(\sigma\) 的影响）也未见详细报告，实验的客观量化程度有待加强。

### 6. 论文的主要结论与发现
- FINC 能有效识别出两个分布间频率差异显著的样本簇，且在可控实验下与真实新颖模式完美吻合。
- 与 Rarity、FLD、KEN 等基线相比，FINC 具有显著的可扩展性，能够在 100k 甚至 250k 样本规模下运行，而其他方法出现内存溢出或计算超时。
- 通过 FINC 可以发现生成模型在 ImageNet 上的**过度生成模式**以及相较其他模型的**高频生成模式**，为模型细粒度对比提供了可解释的见解。
- FINC 可成功用于**检测高记忆化模式**和**文本对齐好/差的模式**，拓展了生成模型分析和诊断的工具箱。

### 7. 优点
- **可扩展性强**：利用随机傅里叶特征将大核矩阵特征分解转换为小矩阵运算，复杂度与样本数对数增长，适用于大规模数据集。
- **理论坚实**：给出了近似误差界，证明所需傅里叶特征数仅随样本数对数增长。
- **提供模式级别的可解释性**：不仅输出分数，还能通过特征向量给出模式相似度分数，可对任意新样本分配模式标签，具有聚类和排序能力。
- **方法通用**：不限于特定生成模型或数据模态，可扩展至对比任意两个分布。
- **实验丰富**：涵盖了多个主流生成模型和任务场景，展示了方法的广泛适用性。

### 8. 不足与局限
- **缺乏定量聚类指标**：实验仅通过可视化主观判断模式质量，缺少与真实标签对比的聚类纯度等客观量化指标。
- **超参数敏感性未充分研究**：带宽 \(\sigma^2\)、阈值 \(\rho\)、特征数 \(r\) 的选择对结果的影响缺少消融分析。
- **依赖特征提取器**：实验统一使用 DINOv2 嵌入，若下游任务与该嵌入分布不匹配，可能引入偏差，但文中未探讨该影响。
- **模式分离假设**：理论分析基于模式在高斯核特征空间中良好分离的假设，复杂混合分布下可能失效。
- **对比方法有限**：虽与 Rarity、FLD、KEN 对比，但主要为可扩展性与定性，未与其他可能的降维或聚类策略（如在线聚类）进行系统定量比较。
- **算力信息缺失**：未提供 GPU 型号与详细资源消耗（如显存），缺乏对实际部署资源需求的透明度。

（完）
