---
title: "Outsourced Diffusion Sampling: Efficient Posterior Inference in Latent Spaces of Generative Models"
title_zh: 外部扩散采样：生成模型潜空间中的高效后验推断
authors: "Siddarth Venkatraman, Mohsin Hasan, Minsu Kim, Luca Scimeca, Marcin Sendera, Yoshua Bengio, Glen Berseth, Nikolay Malkin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=94c9hu6Fsv"
tags: ["query:real-ir"]
score: 7.0
evidence: 提出用扩散模型摊销生成模型的后验采样
tldr: 本文针对生成模型中后验分布采样难解的问题，提出在外部噪声空间训练扩散模型，以实现对约束后验的高效采样，并通过摊销方式处理不同观测。该方法适用于VAE、GAN等常见生成模型，为求解含辅助变量的后验分布提供了通用框架，在多个任务上验证了其高效性与准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1055, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 970, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 826, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1089, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 872, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1228, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1751, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1755, \"height\": 166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1751, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1750, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1753, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1753, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1755, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1753, \"height\": 170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1756, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1756, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1752, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1753, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1753, \"height\": 170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1753, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1752, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1755, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1752, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1752, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1753, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1753, \"height\": 166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1756, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1752, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1753, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1746, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1751, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1751, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1753, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1746, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1757, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1762, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-94c9hu6fsv/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1725, \"height\": 1597, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 698, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1080, \"height\": 655, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1363, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1071, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1551, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1562, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1780, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 857, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-94c9hu6fsv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 308, \"height\": 255, \"label\": \"Table\"}]"
motivation: 生成模型的后验采样通常难解。
method: 在外部噪声空间训练扩散模型来采样约束后验。
result: 实现了对不同观测的摊销后验采样。
conclusion: 扩散模型可作为通用后验推断工具。
---

## Abstract
Any well-behaved generative model over a variable $\mathbf{x}$ can be expressed as a deterministic transformation of an exogenous (‘*outsourced'*) Gaussian noise variable $\mathbf{z}$: $\mathbf{x}=f_\theta(\mathbf{z})$. 
In such a model (*eg*, a VAE, GAN, or continuous-time flow-based model), sampling of the target variable $\mathbf{x} \sim p_\theta(\mathbf{x})$ is straightforward, but sampling from a posterior distribution of the form $p(\mathbf{x}\mid\mathbf{y}) \propto p_\theta(\mathbf{x})r(\mathbf{x},\mathbf{y})$, where $r$ is a constraint function depending on an auxiliary variable $\mathbf{y}$, is generally intractable.
We propose to amortize the cost of sampling from such posterior distributions with diffusion models that sample a distribution in the noise space ($\mathbf{z}$). These diffusion samplers are trained by reinforcement learning algorithms to enforce that the transformed samples $f_\theta(\mathbf{z})$ are distributed according to the posterior in the data space ($\mathbf{x}$). 
For many models and constraints, the posterior in noise space is smoother than in data space, making it more suitable for amortized inference. Our method enables conditional sampling under unconditional GAN, (H)VAE, and flow-based priors, comparing favorably with other inference methods. We demonstrate the proposed ___outsourced diffusion sampling___ in several experiments with large pretrained prior models: conditional image generation, reinforcement learning with human feedback, and protein structure generation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：在生成模型中，直接从先验分布 $p_\theta(\mathbf{x})$ 采样是容易的，但很多现实应用需要从形式为 $p(\mathbf{x}|\mathbf{y}) \propto p_\theta(\mathbf{x}) r(\mathbf{x}, \mathbf{y})$ 的后验分布中采样。这类后验分布通常难以直接处理（intractable）。
- **研究动机**：现有的后验推断方法（如MCMC、近似引导、变分推断）存在计算成本高、难以处理多模态、或只能用于特定模型等局限。
- **整体含义**：本文提出利用生成模型“外部化”的噪声变量 $\mathbf{z}$ （满足 $\mathbf{x}=f_\theta(\mathbf{z})$）进行后验推断。由于噪声空间的后验分布往往比数据空间更平滑、更低维，能在其中更高效地进行摊销采样（amortized sampling）。

### 2. 方法论
- **核心思想**：将生成模型视为从噪声变量 $\mathbf{z}$ 到数据 $\mathbf{x}$ 的确定性变换 $f_\theta$。后验分布可“拉回”（pullback）到噪声空间，其未归一化密度为 $R(\mathbf{z}|\mathbf{y}) = p(\mathbf{z}) r(f_\theta(\mathbf{z}), \mathbf{y})$。通过在噪声空间训练一个扩散模型来逼近此分布，实现高效的后验采样。
- **关键技术——外部扩散采样（Outsourced Diffusion Sampling）**：
    - **扩散采样器训练**：使用**离线策略（off-policy）的轨迹平衡（Trajectory Balance, TB）目标**训练扩散模型。该目标不需要目标分布的得分（score）信息，也不要求 $f_\theta$ 可逆或平滑。
    - **目标函数**：$L_\text{TB}(\tau; \mathbf{y}, \phi) = \left(\log \frac{Z_\phi(\mathbf{y}) p_\phi^F(\tau|\mathbf{y})}{R(\mathbf{z}_1|\mathbf{y}) p_B(\tau|\mathbf{z}_1)}\right)^2$，其中 $p_\phi^F$ 和 $p_B$ 分别是生成（去噪）和加噪过程的分布，$Z_\phi$ 是学习到的配分函数估计量。
    - **训练流程**：交替地从当前模型采样轨迹和从经验回放缓冲区采样，利用上述损失函数优化模型参数 $\phi$ 和 $Z_\phi$。
- **适用范围**：该方法对变换 $f_\theta$ 的形式不敏感，可统一应用于VAE、GAN、归一化流（NF）、连续归一化流（CNF）等多种生成模型（见表1）。

### 3. 实验设计
- **实验场景与先验模型**：
    - **CIFAR-10 类别条件生成**：使用无条件 Image-CFM (CNF) 和 SN-GAN 作为先验，约束为分类器概率。
    - **高分辨率人脸条件生成 (FFHQ)**：使用 StyleGAN3 (GAN) 和 NVAE (HVAE) 作为先验，约束为大语言模型奖励 ImageReward。
    - **文本到图像 RLHF**：使用 Stable Diffusion 3 (CNF) 作为先验，约束为 ImageReward。
    - **蛋白质二级结构多样性生成**：使用 FoldFlow 2 (Riemannian CNF) 作为先验，约束为结构多样性奖励。
- **对比方法**：
    - **针对特定模型的微调方法**：如针对I-CFM的Adjoint Matching。
    - **通用MCMC方法**：如应用于噪声空间的哈密顿蒙特卡洛（HMC）和随机游走。
    - **启发式方法**：如无分类器引导（CFG）调参。
- **评价指标**：根据任务不同，使用了对数奖励（log-reward）、FID分数、CLIP多样性、TM-Score等。

### 4. 资源与算力
- **硬件**：实验主要使用**NVIDIA A100 GPU**。
- **训练时长示例**：
    - **CIFAR-10实验**：Oursourced Diffusion 训练约**5小时**，对比的 Adjoint Matching 约**12小时**。
    - **蛋白质实验**：扩散模型训练约**4 A100 GPU小时**，对比的MCMC Baseline运行了**8 A100 GPU小时**。

### 5. 实验数量与充分性
- **实验规模**：论文在**四个不同领域**（图像分类生成、高分辨率人脸、大语言模型文本对齐、蛋白质结构）的**五种不同的生成模型先验**上进行了验证。
- **对比充分性**：对比了**多种基线方法**，包括专门为特定模型设计的（如Adjoint Matching）、通用的MCMC方法、以及启发式方法。
- **消融与分析**：虽无严格消融实验，但附录中包含了对CIFAR-10各子类别的详细结果、HMC采样链的可视化分析，以及将扩散采样器**蒸馏为单步生成器**的有效性验证，证明了方法的效率和灵活性。

### 6. 主要结论与发现
1.  **通用性**：外部扩散采样是一种**与先验模型类型无关**的后验推断方法，可有效应用于GAN、VAE、CNF等多种模型。
2.  **有效性**：在多个复杂的高维生成任务中，该方法在生成质量和奖励对齐方面，均显著优于HMC等通用MCMC基线，并在某些场景下媲美了专用的微调方法（如Adjoint Matching）。
3.  **高效性**：噪声空间的后验更易于采样，使得该方法训练快、生成快，且可被蒸馏为单步模型。同时，它不依赖目标的梯度信息，属于黑箱方法，适用性更广。

### 7. 优点
- **方法通用灵活**：将后验推断统一到噪声空间采样，适用于几乎所有能表示为确定性噪声变换的生成模型。
- **训练高效稳定**：使用离线策略训练，不依赖目标分布的得分（score）或梯度，允许结合重放缓冲区等技术来促进模式发现和稳定训练。
- **应用场景广泛**：成功在条件生成、RLHF、科学发现（蛋白质设计）等多个前沿问题上验证了有效性。
- **可蒸馏性**：训练好的外部扩散采样器可被蒸馏为单步生成器，在不牺牲性能的前提下极大提升采样速度。

### 8. 不足与局限
- **噪声空间维度**：在某些模型中，噪声空间维度可能很高（如扩散模型先验的噪声维度为$d_{data} \cdot (T+1)$），增加了采样器的训练难度。
- **对奖励函数的依赖**：训练依赖于一个足够好的约束/奖励函数 $r$，若奖励函数质量差或稀疏，可能难以训练。
- **先验模型的定式**：方法假设生成模型是噪声的确定性变换，可能不完全适用于所有类型的生成模型。
- **超参数敏感性**：如蛋白质实验所示，训练可能不稳定，需要根据奖励函数调整温度参数、重放缓冲区采样策略等超参数。

（完）
