---
title: Image Generation Diversity Issues and How to Tame Them
title_zh: 图像生成多样性问题及其驯服方法
authors: "Dombrowski, Mischa, Zhang, Weitong, Cechnicka, Sarah, Reynaud, Hadrien, Kainz, Bernhard"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Dombrowski_Image_Generation_Diversity_Issues_and_How_to_Tame_Them_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 6.0
evidence: 将生成模型多样性问题框架化为图像检索问题以进行测量
tldr: 指出生成模型存在多样性不足且常见指标难以检测的问题，提出将多样性度量视为图像检索问题，通过合成样本查询真实图像数量来评估分布覆盖，并给出了缓解多样性不足的策略，为生成模型评估提供了新工具。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 754, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 679, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 831, \"height\": 546, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1793, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-dombrowski-image-generation-diversity-issues-and-how-to-tame-them-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1814, \"height\": 610, \"label\": \"Table\"}]"
motivation: 生成模型在覆盖数据分布上存在局限，现有指标无法有效度量。
method: 将多样性定义为图像检索问题，用合成数据作查询统计检索真实图像数量。
result: 所提指标能揭示模型多样性缺失，并给出改进策略。
conclusion: 多样性评估对提升生成模型分布覆盖至关重要，提供了有效的度量框架。
---

## Abstract
Generative methods have reached a level of quality that is almost indistinguishable from real data. However, while individual samples may appear unique, generative models often exhibit limitations in covering the full data distribution. Unlike quality issues, diversity problems within generative models are not easily detected by simply observing single images or generated datasets, which means we need a specific measure to assess the diversity of these models. In this paper, we draw attention to the current lack of diversity in generative models and the inability of common metrics to measure this. We achieve this by framing diversity as an image retrieval problem, where we measure how many real images can be retrieved using synthetic data as queries. This yields the Image Retrieval Score (IRS), an interpretable, hyperparameter-free metric that quantifies the diversity of a generative model's output. IRS requires only a subset of synthetic samples and provides a statistical measure of confidence. Our experiments indicate that current feature extractors commonly used in generative model assessment are inadequate for evaluating diversity effectively. Consequently, we perform an extensive search for the best feature extractors to assess diversity. Evaluation reveals that current diffusion models converge to limited subsets of the real distribution, with no current state-of-the-art models superpassing 77% of the diversity of the training data. To address this limitation, we introduce Diversity-Aware Diffusion Models (DiADM), a novel approach that improves diversity of unconditional diffusion models without loss of image quality. We do this by disentangling diversity from image quality by using a diversity aware module that uses pseudo-unconditional features as input. We provide a Python package offering unified feature extraction and metric computation to further facilitate the evaluation of generative models https://github.com/MischaD/beyondfid.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **背景**：生成模型（特别是扩散模型）生成的单张图像质量已接近真实，但模型覆盖完整数据分布的能力（即**多样性**）常被忽视。多样性不足难以通过肉眼直接判断，且现有评估指标（如FID、Precision/Recall）无法有效衡量。
- **核心问题**：当前生成模型普遍存在**多样性缺失**，现有特征提取器在评估多样性时存在**测量鸿沟**（measurement gap），导致常用指标严重低估或失真。论文旨在提出一种可解释、无超参数、能统计置信的多样性度量工具，并以此诊断和改善扩散模型的多样性。

## 2. 论文提出的方法论

### 2.1 图像检索分数（Image Retrieval Score, IRS）
- **核心思想**：将多样性定义为**图像检索问题**：以合成图像为查询，在真实训练集中检索最相似的样本，统计有多少个**不同的**真实样本被至少一个合成图像检索到。该比例即为多样性分数。
- **数学建模**：基于优惠券收集问题（Coupon Collector Problem），将合成图像的生成视为从离散的真实样本集中有放回抽取，推导出恰好检索到k个不同真实样本的概率公式，并据此给出IRS的最大似然估计和置信区间。
- **超参数自由与调整**：IRS仅依赖少量合成样本即可得到统计推断。为消除特征提取器造成的“测量鸿沟”，采用**调整IRS**（adjusted IRS）：先将IRS应用于真实数据获得参考值，再将合成数据的IRS除以该参考值，得到相对于真实数据多样性的比率。

### 2.2 多样性感知扩散模型（DiADM）
- **动机**：现有无条件扩散模型通过占位标签实现无条件生成，导致多样性受限。
- **方法**：利用预训练特征提取器（如Inception v3）提取训练图像的**伪无条件特征**，直接作为条件输入扩散模型，从而将多样性（由伪标签覆盖）与保真度（由扩散模型本身保证）解耦。训练时使用EDM-2架构，将标签维度改为特征维度。该方法称为**DiADM**。

## 3. 实验设计

### 3.1 数据集与场景
- **主要数据集**：ImageNet-512（通用物体）、FFHQ（人脸）、ChestX-ray14（医学X光）、CelebV-HQ（人脸视频帧）、Dynamic（心脏超声视频帧）。
- **评估对象**：涵盖多种主流扩散模型：ADM、LDM、DiT、MAR、EDM-2（多种尺度），以及DeepFloyd作为文生图示例。

### 3.2 基准与对比方法
- **多样性指标**：IRS（调整后）与Precision、Recall、Density、Coverage、Vendi Score、FID等对比。
- **特征提取器搜索**：为降低测量鸿沟，对BYOL、CLIP、ConvNeXt、data2vec、DINOv2、Inception、MAE、SwAV、Random共9种提取器进行检索一致性评估，最终选用与集成共识一致性最高的**SwAV**作为默认特征提取器。
- **文本-图像公平性实验**：使用DeepFloyd生成特定职业词汇图像，构造性别平衡的参考集，评估性别多样性。

### 3.3 主要对比模型
- 表2中对比了Pixel diffusion (ADM)、Transformer (DiT)、MAR、Latent diffusion (LDM、EDM-2系列) 共计12个配置，分别报告条件与无条件生成下的FID、Precision、Recall等及IRS。

## 4. 资源与算力

- 论文明确提到：**DiADM训练固定使用574 A40 GPU小时**，仅相当于原始EDM训练时长的十分之一。
- 其他实验使用的是预训练模型（直接评估），未额外描述算力。

## 5. 实验数量与充分性

- 实验覆盖了**5个不同领域的数据集**，**12种以上生成模型**（包括不同大小架构），**9种特征提取器**的对比，以及文本-图像的性别多样性分析。
- 消融实验：通过人工剔除ImageNet类别构造已知多样性水平的测试集，验证IRS与真实多样性线性相关，并与其他指标对比（图5）。
- 提供了 DiADM 与 EDM-2 在多个数据集上的生成多样性对比（表3）。
- 总体实验**较为充分**，多维度验证了IRS的有效性和现有模型的多样性短板。对比公平：所有模型均使用统一采样设置，特征提取器基于共识选择，调整步骤消除测量偏差。

## 6. 主要结论与发现

- **测量鸿沟存在**：所有常用特征提取器在真实数据上的检索能力远低于理论值，导致现有指标无法有效衡量多样性（图4）。
- **SOTA模型多样性严重不足**：在ImageNet上，条件生成的最佳模型（EDM-2-XXL）仅覆盖77%的训练多样性，部分模型低至21%。
- **IRS可作为有效诊断工具**：它能早期发现多样性缺失，且与真实多样性线性相关，可解释性强。
- **DiADM有效解耦多样性与质量**：在多个数据集上，DiADM在相同计算预算下显著提升调整IRS（甚至超过1.0），同时改善FID。
- **文本-图像模型存在显著性别偏差**：例如“人”只生成女性，IRS预测多样性仅达50%。

## 7. 优点

- **问题新颖且重要**：将多样性评估形式化为图像检索，提供概率论解释和置信区间，弥补了现有指标的不足。
- **指标设计优点**：无超参数、无需大量样本（ω=0.1即可获得可靠估计）、可统计推断，且通过调整步骤消除了特征提取器的偏差。
- **实验设计严谨**：特征提取器的系统搜索、多数据集多模型覆盖、通过类剔除构造可控多样性的验证，增强了结论可信度。
- **实用性**：提出DiADM模块简单有效，代码开源，便于社区评估和改善多样性。

## 8. 不足与局限

- **特征提取器依赖**：IRS性能仍受所选特征提取器影响，论文推荐通用SwAV，但更优的特征提取器可能进一步提升准确性；测量鸿沟仅通过归一化缓解，未根本解决。
- **实验局限**：DiADM训练仅在EDM-2 XS架构上测试，计算预算有限（1/10原始时长），未探索更大模型或更长时间训练后对FID-多样性平衡的影响。
- **条件生成拓展不完整**：虽然文本-图像示例展示了IRS对公平性的评估能力，但DiADM专注于无条件生成，未给出条件生成下多样性的改善方法。
- **随机性影响**：样本量很少时，IRS估计变化大（但置信区间提供了信息），不易区分细微差异。

（完）
