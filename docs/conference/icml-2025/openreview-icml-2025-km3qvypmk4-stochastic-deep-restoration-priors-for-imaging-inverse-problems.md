---
title: Stochastic Deep Restoration Priors for Imaging Inverse Problems
title_zh: 适用于成像逆问题的随机深度恢复先验
authors: "Yuyang Hu, Albert Peng, Weijie Gan, Peyman Milanfar, Mauricio Delbracio, Ulugbek S. Kamilov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Km3QvYPmK4"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用深度恢复模型集合作为成像逆问题的先验
tldr: 本文提出ShaRP框架，随机利用在广泛退化上训练的深度恢复模型集合作为逆问题先验，有效应对结构化伪影，并支持无全采样数据的自监督训练。理论证明了其等价于基于恢复算子得分函数的正则项最小化。ShaRP在多种成像逆问题上取得优异效果，为学习先验方法提供了新的范本。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1215, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1524, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1753, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1398, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1398, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1603, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1243, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1474, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1469, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1183, \"height\": 1246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1182, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 751, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1538, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-km3qvypmk4/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 923, \"height\": 412, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 758, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 743, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1305, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1304, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1322, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1114, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 514, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 420, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 755, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-km3qvypmk4/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1309, \"height\": 267, \"label\": \"Table\"}]"
motivation: 现有去噪器先验难以处理结构化退化。
method: 构建多恢复模型集合作为随机先验，实现自监督。
result: 有效去除结构化伪影，无需全采样数据。
conclusion: 扩展了学习先验的适用范围和鲁棒性。
---

## Abstract
Deep neural networks trained as image denoisers are widely used as priors for solving imaging inverse problems. We introduce Stochastic deep Restoration Priors (ShaRP), a novel framework that stochastically leverages an ensemble of deep restoration models beyond denoisers to regularize inverse problems. By using generalized restoration models trained on a broad range of degradations beyond simple Gaussian noise, ShaRP effectively addresses structured artifacts and enables self-supervised training without fully sampled data. We prove that ShaRP minimizes an objective function involving a regularizer derived from the score functions of minimum mean square error (MMSE) restoration operators. We also provide theoretical guarantees for learning restoration operators from incomplete measurements. ShaRP achieves state-of-the-art performance on tasks such as magnetic resonance imaging reconstruction and single-image super-resolution,  surpassing both denoiser- and diffusion-model-based methods without requiring retraining.

---

## 论文详细总结（自动生成）

好的，我将根据您提供的论文内容，生成一份结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

-   **研究动机**：成像逆问题旨在从退化的测量值中恢复出清晰图像，这本质上是病态的，需要引入先验信息进行正则化。当前主流方法是使用**深度高斯去噪器**作为图像先验（如PnP、RED、扩散模型），但这些方法存在局限。
-   **核心问题**：现有的方法过度依赖只能处理单一、特定类型退化（如高斯噪声）的模型作为先验。当测试时面临**结构化伪影**或模型训练数据与测试环境**不匹配**时，性能会下降。此外，训练这些高斯去噪器通常需要完全采样的高质量数据，这在很多场景下难以获取。
-   **整体含义**：本文提出**随机深度恢复先验（Stochastic deep Restoration Priors, ShaRP）**框架。其核心思想是将**先验的来源，从单一的高斯去噪器扩展到一个由处理多种退化类型的深度恢复模型构成的集合**。这使得ShaRP能更有效地处理结构化伪影，并能在不需要完全采样数据的情况下进行自监督训练，从而作为一种更通用、更强大的图像正则化方法。

### 2. 论文提出的方法论

-   **核心思想**：ShaRP的核心是随机地调用一个**恢复模型集合**中的不同模型来引导逆问题的求解。该集合中的每个模型对应于一种特定的图像退化（如不同模糊核、不同MRI欠采样模式），ShaRP在迭代优化中随机选择一种退化模式，利用对应的恢复模型计算更新方向。
-   **关键技术细节与公式**：
    -   **先验训练**：一个恢复网络$R(s, H)$被训练以求解一系列恢复问题$s = Hx + n$，其中$H$是从退化分布$p(H)$中随机采样的退化算子（如$H_\alpha = (1-\alpha)I + \alpha M$，通过改变$\alpha$控制退化程度）。
    -   **算法流程（ShaRP）**：在求解目标逆问题（测量算子为A）的第$k$次迭代中：
        1.  随机采样一个退化算子 $H \sim p(H)$。
        2.  对当前估计 $x_{k-1}$ 施加退化并加噪，得到模拟退化图像 $s = Hx_{k-1} + n$。
        3.  使用预训练的恢复网络对其进行恢复，得到恢复残差。
        4.  沿着由**数据保真项梯度$\nabla g_A(x)$** 和**基于恢复残差的正则化项梯度**$\hat{\nabla}h(x) = \frac{\tau}{\sigma^2} H^T H(x - R(s, H))$组成的合成梯度方向更新图像。
    -   **理论贡献**：
        -   证明了ShaRP的更新方向等价于最小化一个特定目标函数的随机梯度，该目标函数包含一个新颖的正则化项$h(x) = \tau \mathbb{E}_{s, H} [-\log p(s|H)]$，该正则项鼓励解的多种退化版本与真实退化图像的分布一致。
        -   提供了在恢复模型非理想的MMSE估计器时，ShaRP作为有偏SGD的收敛性分析。
        -   证明了在特定条件下（如MRI中的傅里叶变换基是正交的），可以从欠采样测量值中以自监督方式学习到与监督学习等价的MMSE恢复算子。

### 3. 实验设计

-   **数据集与场景**：
    -   **压缩感知磁共振成像 (CS-MRI)**：使用公开的**fastMRI**脑部T2加权数据集，模拟多线圈、不同加速倍数（4x, 6x）和采样模式（均匀、随机）的欠采样重建，并加入不同等级的高斯噪声。
    -   **单图像超分辨率 (SISR)**：使用**ImageNet测试集**中的100张图像，进行2倍超分辨率，模拟两种不同标准差的高斯模糊核和噪声水平。
-   **Benchmark 与方法对比**：
    -   **CS-MRI**：与去噪器先验方法 (**PnP-FISTA, PnP-ADMM**)、扩散模型方法 (**DPS, DDS**)、单恢复先验方法 (**DRP**) 以及两种监督/自监督方法 (**E2E-VarNet, SPICER, TV, GRAPPA**) 进行对比。
    -   **SISR**：与去噪器先验方法 (**DPIR**)、扩散模型方法 (**DPS, DDNM, DiffPIR, DDRM, DiffIR**) 以及单恢复先验方法 (**DRP**) 进行对比。

### 4. 资源与算力

-   论文正文及附录中**未明确提及**用于训练和推理的具体算力信息（如GPU型号、数量、训练时长等）。这属于文本中缺失的信息。

### 5. 实验数量与充分性

-   **实验数量**：实验覆盖了**两个核心任务**（CS-MRI, SISR），每个任务下测试了**多种退化参数**（不同加速比、掩膜类型、噪声水平、模糊核），并对比了当时**最先进的多种基线方法**。
-   **消融研究**：进行了充分的消融实验来验证设计选择的有效性，包括：
    -   集合中**恢复先验数量**的影响。
    -   **自监督 vs. 监督**训练先验的性能与收敛性对比。
    -   **超参数$\alpha$** 的影响。
    -   使用**跨任务的先验**（用超分辨率网络作为CS-MRI的先验）来证明框架的灵活性。
    -   与任务特定、但测试环境不匹配的模型的**泛化能力对比**。
-   **充分性与公平性**：实验设计**全面且公平**。对比了多个类别的强基线方法，并确保了所有数据驱动模型（包括基线）都使用**相同的数据集进行训练**，对于扩散模型甚至使用了**相同的网络骨架**。所有方法的超参数均在验证集上调整至最佳PSNR，确保了比较的公平性。

### 6. 论文的主要结论与发现

1.  **性能优越**：ShaRP在CS-MRI和SISR任务中均取得了**最先进的性能**，超越了基于单一高斯去噪器或扩散模型的现有方法。
2.  **集合先验有效**：随机集成多个退化特定的恢复模型作为先验，其性能**显著优于使用单一固定先验**的方法。
3.  **自监督可行**：理论证明并通过实验验证了，在无法获得完全采样数据时，ShaRP可以使用**自监督训练**的恢复网络作为有效先验，性能甚至超越了使用完全采样数据训练的高斯去噪器方法。
4.  **灵活性强**：ShaRP框架可以灵活接入不同类型的恢复模型（如去模糊、超分辨率模型）作为先验，来解决不相关的目标逆问题，展现了很强的通用性。

### 7. 优点

-   **方法论创新**：首次提出并理论化地证明了，可以使用一个随机集成的、超越高斯去噪的**通用恢复模型集合**作为逆问题正则化项的统一框架。
-   **强大的理论基础**：为所提出的正则化项提供了明确、可解释的公式，并给出了在非理想模型下的收敛性保证以及自监督学习的理论支持。
-   **广泛的适用性与灵活性**：ShaRP不局限于特定任务或特定类型的先验，具有即插即用的潜力，并能适应无全监督数据的训练场景。
-   **实验严谨且全面**：在两个重要的成像任务上进行了全面评估，对比了大量基线，并进行了丰富的消融研究，有力地支撑了提出的观点。

### 8. 不足与局限

-   **计算开销**：每次迭代都需要对随机选择的退化进行恢复推理，相比于使用单模型先验的方法，整体的**推理计算成本可能更高**。虽然作者提及与单模型方法可比，但未提供具体的时间对比。
-   **感知质量**：虽然PSNR/SSIM指标领先，但在SISR任务中，其**感知质量指标(LPIPS)次于某些扩散模型**。作者也承认该方法受限于优化求解的“感知-失真权衡”，采样扩展是未来方向。
-   **理论与实现的差距**：自监督学习的理论证明依赖于正交测量算子等较强假设，这**限制了其直接应用到更广泛逆问题**的普适性。
-   **实验覆盖范围**：实验主要在MRI和SISR上进行，在其他更复杂的成像逆问题（如去雨、去雾、相位恢复）上的表现有待验证。
-   **资源说明缺失**：**未提供任何算力资源信息**，这不利于评估方法的实际应用成本和复现可行性。

（完）
