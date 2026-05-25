---
title: "LightningDrag: Lightning Fast and Accurate Drag-based Image Editing Emerging from Videos"
title_zh: LightningDrag：源自视频的闪电般快速准确拖拽式图像编辑
authors: "Yujun Shi, Jun Hao Liew, Hanshu Yan, Vincent Y. F. Tan, Jiashi Feng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=WFhQ9owxOH"
tags: ["query:real-ir"]
score: 9.0
evidence: 从视频中学得的闪电般快速的拖拽式图像编辑
tldr: LightningDrag 针对现有基于扩散的拖拽式编辑速度慢、成功率低的问题，将其重新定义为条件生成任务，利用大规模视频帧对模型进行训练，捕获多样运动模式。该方法省去了耗时的潜变量优化步骤，在约一秒内即可完成高质量编辑，显著提升了拖拽式交互的实用性和编辑效果。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1747, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 822, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 841, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1747, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1638, \"height\": 2105, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1473, \"height\": 1145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wfhq9owxoh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1470, \"height\": 946, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-wfhq9owxoh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 819, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wfhq9owxoh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wfhq9owxoh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 887, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-wfhq9owxoh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 831, \"height\": 336, \"label\": \"Table\"}]"
motivation: 现有拖拽编辑方法耗时超过一分钟且成功率低，无法满足实时交互需求。
method: 将拖拽编辑转化为条件生成任务，利用配对视频帧训练扩散模型，消除迭代优化。
result: 编辑速度提升至约1秒，同时准确性和一致性大幅优于以往方法。
conclusion: LightningDrag 使拖拽式图像编辑迈向实时高质，拓展了实际应用前景。
---

## Abstract
Accuracy and speed are critical in image editing tasks. Pan et al. introduced a drag-based framework using Generative Adversarial Networks, and subsequent studies have leveraged large-scale diffusion models. However, these methods often require over a minute per edit and exhibit low success rates. We present LightningDrag, which achieves high-quality drag-based editing in about one second on general images. By redefining drag-based editing as a conditional generation task, we eliminate the need for time-consuming latent optimization or gradient-based guidance. Our model is trained on large-scale paired video frames, capturing diverse motion (object translations, pose shifts, zooming, etc.) to significantly improve accuracy and consistency. Despite being trained only on videos, our model generalizes to local deformations beyond the training data (e.g., lengthening hair, twisting rainbows). Extensive evaluations confirm the superiority of our approach, and we will release both code and model.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：在交互式图像编辑中，拖拽式（drag‑based）编辑因其直观的空间控制能力而备受关注。然而，现有方法普遍存在两大瓶颈：
  - **速度慢**：基于GAN的方法（如DragGAN）需要耗时的反演步骤（1–2分钟）；基于扩散模型的方法（如DragDiffusion）在编辑过程中往往依赖潜变量优化或梯度引导，单次编辑仍需数十秒到上百秒。
  - **成功率低**：多数方法为零样本推理，缺乏显式监督，常常无法准确将语义内容从手柄点移动到目标点，或者不能保持源图像的纹理和身份。
- **整体含义**：本文旨在将拖拽式编辑推向实用化，通过重新定义问题范式、利用大规模视频数据学习运动先验，实现**亚秒级**、高保真、高准确性的通用图像拖拽编辑，大幅提升交互体验。

### 2. 论文提出的方法论

#### 2.1 核心思想：将拖拽编辑重新定义为条件生成

- 摒弃传统的潜变量优化或梯度引导过程，将拖拽操作视为**条件生成**任务：
  - 条件1：源图像（需要编辑的图像）
  - 条件2：拖拽指令（手柄点 → 目标点）
- 使用扩散模型一次性生成编辑结果，而不是在推理过程中反复迭代计算梯度，从而将延时降低到一次标准扩散采样的水平。

#### 2.2 模型架构

模型由三个主要组件构成（整体流程见图2）：

1. **修复（Inpainting）骨干网络**
   - 以Stable Diffusion Inpainting UNet为基础，输入为噪声潜变量、二值掩膜以及被掩膜遮盖的源图像潜变量。
   - 通过**IP‑Adapter**提取源图像的视觉特征，替代文本提示，使用户无需键入文本描述即能保持生成内容的语义一致性。

2. **外观编码器（Appearance Encoder）**
   - 采用“Reference‑only”架构，与骨干UNet结构相同但参数独立，输入为干净的源图像潜变量。
   - 将源图像的键（K）和值（V）特征注入到骨干UNet的自注意力层中，实现对**细粒度细节**（如面部、纹理）的精确保留。
   - 编码器只需运行一次，大幅减少了推理计算量。

3. **点嵌入网络与点跟随注意力（Point Embedding & Point‑Following Attention）**
   - 将手柄点和目标点分别编码为与图像同分辨率的点图，每个点对赋予一个唯一整数标签，其余位置置零。
   - 通过12层卷积+SiLU激活构成的**点嵌入网络**，生成多尺度嵌入 E_hdl、E_tgt（对应UNet的4个特征分辨率）。
   - 修改自注意力公式，将点嵌入直接参与查询‑键匹配：
     - 公式为：
       
       `Attn(Q, K, V, K_ref, V_ref, E_hdl, E_tgt) =`
       `softmax( ((Q+E_tgt)[K+E_tgt, K_ref+E_hdl]^T) / sqrt(d) ) [V, V_ref]`
   - 这种方式**显式增强**生成图像目标区域与参考图像手柄区域之间的相似性，使模型学会遵循拖拽指令。

#### 2.3 训练策略：从视频中自动构建监督

- 收集**大量静态相机下的视频**（内部数据集，220k样本），模拟仅局部运动、其余区域静止的拖拽场景。
- 对每一对源帧和目标帧，按**光流强度**采样手柄点（运动显著的位置），使用CoTracker2追踪这些点在目标帧中的对应位置，得到目标点。
- 自动提取运动区域的二值掩膜，最终构成 (I_src, I_tgt, P_hdl, P_tgt, M) 五元组用于训练。
- 视频中的多样运动模式（例如物体平移、姿态变化、缩放）为模型提供了丰富的变形与运动线索。

#### 2.4 推理时的增强技术

- **噪声先验（Noise Prior）**：
  - 摒弃随机高斯噪声，直接将源图像潜变量按照扩散公式加噪到终端时间步（t=999），缩小训练与测试的噪声分布差异，提升稳定性。
- **点跟随无分类器引导（PF‑CFG）**：
  - 在推理时施加CFG以强化点指令的作用：
    
    `ε̃_θ = ε_θ(z_t, c_appr, ∅) + ω(t) * [ ε_θ(z_t, c_appr, c_points) - ε_θ(z_t, c_appr, ∅) ]`
  - 采用**随时间衰减的引导权重**（逆平方函数，从 ω_max=3.0 衰减到1.0），在编辑前期强力遵循指令，后期保证图像自然度和色彩真实感。
- **可选的用户侧“拖拽工程”**：
  - **点增广**：增加辅助手柄‑目标点对来更清晰地传达编辑意图。
  - **序列化拖拽**：将长距离移动分解为多步短距拖拽，降低单步难度，且模型速度极快，不影响体验。

### 3. 实验设计

- **主要基准测试**：DragBench（Shi et al., 2023），包含205个样本，预定义拖拽点和掩膜。评估指标：
  - **Mean Distance (MD)** ↓：手柄点移动到目标的平均像素距离（越低表示跟随越精确）。
  - **Image Fidelity (IF)** ↑：1‑LPIPS，衡量编辑后图像对源图的视觉保真度。
- **对比方法**：
  - DragGAN (Pan et al., 2023)
  - DragDiffusion (Shi et al., 2023)
  - DiffEditor (Mou et al., 2024)
  - Readout Guidance (Luo et al., 2023a)
  - SDEDrag (Nie et al., 2023)
- **效率测试**：在DragBench的67张方形图像（512×512）上，于单块A100 GPU测量运行时间。
- **定性展示**：展示了多样化的拖拽类型（姿态变化、缩放、平移、局部变形）以及与基线的视觉对比。

### 4. 资源与算力

- **训练配置**：
  - 数据集：内部视频，采样220k训练样本。
  - 优化器：学习率5e‑5，批大小256。
  - 冻结模块：Inpainting UNet 和 IP‑Adapter；仅训练外观编码器和点嵌入网络（后者最后一层零初始化）。
  - 训练时随机采样1~20个点对，并将画面裁剪为512×512。
- **推理配置**：
  - 默认采样器：DDIM，25步。
  - 可与加速模块（LCM‑LoRA、PeRFlow）即插即用兼容，8步采样。
  - 单次编辑运行时间：默认约2.06±0.05秒，使用LCM‑LoRA后约0.92±0.02秒（A100）。
- **未明确说明**：具体训练总时长、GPU数量并未在文中报告；推断为单次训练，但资源消耗不透明。

### 5. 实验数量与充分性

- **定量实验**：
  - 主实验：在DragBench上的IF和MD对比（表3）。
  - 消融实验：
    - 噪声先验策略（纯噪声、混合噪声、复制粘贴、噪声源潜变量）对MD和IF的影响（表1）。
    - 不同CFG调度（无CFG、常数、平方、线性、逆平方）对MD和IF的影响（表2）。
  - 时间效率对比（表4）。
- **定性实验**：
  - 多轮拖拽示例，展示了迭代编辑能力（图9）。
  - 与5种基线的方法在多种场景下的视觉对比（图7）。
  - 点增广、序列拖拽的效果示意图（图5、图6）。
- **充分性与客观性**：
  - 实验覆盖了主要公开基准，与多个代表性方法进行了公平对比，指标标准化，消融设计合理。
  - 但是训练数据为内部视频，难以复现；且对比方法中部分方法（如SDEDrag）存在隐性身份映射问题，但文中已解释其高IF来自保真度伪像。

### 6. 论文的主要结论与发现

- **速度突破**：通过条件生成范式，将单次拖拽编辑延迟压缩至1秒左右，较先前方法实现数十倍的加速。
- **精度提升**：在DragBench上取得了最低的MD，显著优于所有对比方法，表明点跟随准确性极高。
- **强泛化能力**：仅用视频训练，却能够处理训练时未见过的局部非刚性变形（如拉长头发、扭曲彩虹）。作者认为这是由于视频运动成分的丰富性以及显式点跟随控制机制共同作用的结果。
- **实用性强**：支持即插即用的扩散加速模块，无需额外训练；并提供点增广、序列拖拽等轻量级修复策略。

### 7. 优点

- **方法设计新颖且高效**：首次系统性地利用大规模普通视频数据学习通用拖拽编辑，摒弃耗时的推理优化，架构解耦合理，性能提升显著。
- **工程化考虑周全**：推理阶段的噪声先验和动态CFG调度，有效平衡了编辑强度与画质，且模型可以无缝集成到已有的扩散加速框架中。
- **实验充分性较好**：定量与定性兼备，消融实验覆盖了关键设计选择，对速度、精度、保真度均有清晰评估。
- **可解释性讨论**：对域外泛化能力给出了有理有据的分析，增加了论文的深度。

### 8. 不足与局限

- **训练数据未公开**：使用的内部视频数据集无法复现，限制了公平性验证和社区扩展。
- **计算资源细节缺失**：未披露训练所用GPU数量、总训练时长，不利于评估方法的资源门槛。
- **泛化边界未严格量化**：虽然展示了非刚性变形案例，但缺乏系统性的域外编辑数据集和定量对比，可能对极端变形或复杂语义的场景仍有盲区。
- **对点数量和配置敏感**：点增广和序列拖拽虽然实用，但需要用户手动调整，影响了全自动化体验；CFG调度超参数 ω_max 的选择可能需要针对不同场景微调。
- **依赖外部模型**：训练基于CoTracker2进行点追踪，其准确度直接决定了监督信号质量，若点追踪失败会导致训练噪声。
- **长距离大变形**：序列拖拽虽然可以弥补单次编辑的不足，但累加多次仍可能引入微小形变，文中未讨论累积误差的上限。

（完）
