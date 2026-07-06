---
title: "SwiftEdit: Lightning Fast Text-Guided Image Editing via One-Step Diffusion"
title_zh: SwiftEdit：基于单步扩散的闪电般快速文本引导图像编辑
authors: "Nguyen, Trong-Tung, Nguyen, Quang, Nguyen, Khoi, Tran, Anh, Pham, Cuong"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Nguyen_SwiftEdit_Lightning_Fast_Text-Guided_Image_Editing_via_One-Step_Diffusion_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 10.0
evidence: 单步扩散实现即时文本驱动图像编辑
tldr: 该论文针对现有多步扩散编辑方法速度慢、难以满足实时应用的问题，提出SwiftEdit，通过单步反演框架实现一步图像重建，并结合掩码引导的注意力重缩放机制，将编辑时间缩短至0.23秒。实验表明其在保持编辑质量的同时大幅提升速度，为扩散模型在移动和实时场景的应用奠定基础。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1632, \"height\": 907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1801, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 843, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1403, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 857, \"height\": 164, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1643, \"height\": 761, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nguyen-swiftedit-lightning-fast-text-guided-image-editing-via-one-step-diffusion-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 794, \"height\": 322, \"label\": \"Table\"}]"
motivation: 现有多步扩散图像编辑速度慢，无法满足实时和移动端应用需求。
method: 提出单步反演框架实现一步图像重建，结合掩码引导的注意力重缩放机制加速编辑。
result: 编辑速度达0.23秒，同时保持较高的编辑质量，显著快于现有方法。
conclusion: SwiftEdit以极低延迟实现了高质量文本引导图像编辑，推动了扩散编辑的实际应用。
---

## Abstract
Recent advances in text-guided image editing enable users to perform image edits through simple text inputs, leveraging the extensive priors of multi-step diffusion-based text-to-image models. However, these methods often fall short of the speed demands required for real-world and on-device applications due to the costly multi-step inversion and sampling process involved. In response to this, we introduce SwiftEdit, a simple yet highly efficient editing tool that achieve instant text-guided image editing in 0.23s. The advancement of SwiftEdit lies in its two novel contributions: a one-step inversion framework that enables one-step image reconstruction via inversion and a mask-guided editing technique with our proposed attention rescaling mechanism to perform localized image editing. Extensive experiments are provided to demonstrate the effectiveness and efficiency of SwiftEdit. In particular, SwiftEdit enables instant text-guided image editing, which is extremely faster than previous multi-step methods (at least 50 times faster) while maintain a competitive performance in editing results. Our project is at https://swift-edit.github.io/.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
- **问题**：现有基于扩散模型的文本引导图像编辑方法依赖多步反演（inversion）与采样，速度慢（通常需数十秒以上），难以满足实时交互和移动端应用的需求。
- **目标**：实现极速（0.23秒）的文本引导图像编辑，同时保持编辑质量，缩小与多步方法的速度差距（快50倍以上）。
- **背景**：扩散模型蒸馏技术（如SwiftBrushv2）使得单步文本到图像生成成为可能，但将其用于图像编辑仍存在单步反演困难、编辑区域控制不足等挑战。

### 2. 方法论
#### 2.1 单步反演框架
- **核心思想**：训练一个反演网络 Fθ，将输入图像潜变量 z 直接映射为可编辑的倒置噪声 ˆϵ = Fθ(z, cy)，再通过单步生成器 G（SwiftBrushv2）重构图像，实现“一步反演 + 一步生成”。
- **引入IP‑Adapter分支**：在生成器中增加以输入图像特征为条件的交叉注意力层（GIP），减轻反演网络必须嵌入过多视觉细节的负担，既提升重构质量，又保持倒置噪声的可编辑性。
- **两阶段训练**：
  - **阶段1（合成数据）**：利用SBv2自身生成(ϵ, z)对，联合优化回归损失（||ˆϵ − ϵ||²）和像素重构损失（||z − ˆz||²），使倒置噪声服从高斯分布。
  - **阶段2（真实图片）**：采用感知损失（DISTS）替代像素损失；同时引入基于分数蒸馏采样（SDS）风格的正则化项，防止倒置噪声偏离𝒩(0, I)而破坏可编辑性。此时冻结IP‑Adapter，只微调反演网络。

#### 2.2 掩码引导的注意力重缩放编辑（ARaM）
- **自引导编辑掩码**：将源图像潜变量分别以源提示和编辑提示输入Fθ，得到两个噪声图，其差异图经归一化后即可高亮编辑区域，无需人工标注。
- **注意力重缩放**：在生成器的交叉注意力中，对编辑区域（掩码M）和非编辑区域分别设置缩放系数 sedit、snon‑edit，控制图像条件 cx 的影响，从而在编辑区域提升语义对齐，在非编辑区域保持背景不变。同时引入 sy 进一步调节编辑区域的文本对齐强度。
- **公式概括**：  
  `hl = sy·M·Attn(Q,Ky,Vy) + sedit·M·Attn(Q,Kx,Vx) + snon‑edit·(1−M)·Attn(Q,Kx,Vx)`

### 3. 实验设计
- **数据集**：PieBench（700样本，10种编辑类型），提供源提示、编辑提示、源图像和手动标注的编辑掩码。
- **评估指标**：背景保留（PSNR↑、MSE×10⁴↓）、语义对齐（CLIP‑Whole↑、CLIP‑Edited↑）及运行时间。
- **对比方法**：
  - 多步（50步）：DDIM + Prompt‑to‑Prompt、Null‑text Inversion + P2P、DDIM + MasaCtrl、Direct Inversion + MasaCtrl、Plug‑and‑Play等。
  - 少步（4步）：ReNoise（SDXL‑Turbo）、TurboEdit、ICD（SD1.5）。
  - 自身变体：使用人工标注掩码（GT masks）的版本。
- **用户研究**：140名参与者，对比SwiftEdit、Null‑text Inversion和TurboEdit在20个随机编辑上的偏好。

### 4. 资源与算力
- 训练硬件：单块NVIDIA A100 40 GB GPU。
- 训练配置：
  - 阶段1：批次大小4，Adam优化器（lr=1e‑5，权重衰减1e‑4），训练10万次迭代，使用合成图文对（图像由SBv2生成，文本来自JourneyDB 4万条描述）。
  - 阶段2：批次大小1，训练18万次迭代，使用CommonCanvas数据集中5千张真实图像及其描述。
  - 采用指数移动平均（EMA）更新参数。
- 推理速度：单次编辑0.23秒（A100）。

### 5. 实验数量与充分性
- **主要对比**：定量表（Tab. 1）涵盖10种组合方法（多步+少步）与4项指标，并单独给出使用人工掩码的结果，比较全面。
- **消融实验**：
  - 反演框架设计：先后移除阶段1、阶段2、IP‑Adapter，观察对真实图像重构的影响（Tab. 2），清晰验证各组件的必要性。
  - 损失函数：逐步删除回归损失和正则化损失，通过CLIP语义得分体现对编辑灵活性的影响（Tab. 3）。
- **定性分析**：提供多场景编辑对比图（Fig. 6）、掩码可视化（Fig. 5）及用户研究（Fig. 7）。
- **公平性**：所有方法在相同数据集、相同指标下评估；运行时间均报告于A100；对比方法包括当前主流，且使用了标准基准PieBench，具备客观性与可比性。

### 6. 主要结论与发现
- SwiftEdit首次实现了基于单步扩散模型的即时文本引导图像编辑，编辑耗时仅0.23秒，比多步方法快50倍以上，比少步方法快约5–7倍。
- 在PieBench上取得与多步方法有竞争力的背景保留和语义对齐得分；结合自引导掩码，质量接近使用人工掩码的版本。
- 两阶段训练和SDS风格正则化对于保持倒置噪声的可编辑性至关重要；IP‑Adapter明显提升重构质量。
- 掩码引导的注意力重缩放能够灵活调控编辑强度，实现局部编辑的同时保持背景不变。

### 7. 优点
- **速度突破**：完全省去迭代反演与采样，将编辑时延降至毫秒级，极具实用价值。
- **无需人工掩码**：反演网络可自感知语义变化区域，自动提供编辑掩码。
- **可控编辑**：ARaM机制允许通过多个缩放因子精细分离编辑与保留区域，甚至控制编辑强度。
- **训练高效**：利用合成数据预训练，仅需少量真实数据微调，成本可控。
- **全面验证**：定量、定性、用户研究多位一体，消融实验扎实，代码与项目页面公开。

### 8. 不足与局限
- **依赖生成模型质量**：整体性能受SwiftBrushv2的制约，数据偏差可能传递至编辑结果（如生成模型固有的种族、性别等偏见）。
- **速度仍非“实时”**：0.23秒虽已极快，但相较于视频会议、直播等场景要求的实时（< 0.1秒）仍有微小差距。
- **真实数据微调规模有限**：阶段2仅使用5千张真实图片，可能对广泛的开域真实图像泛化不足。
- **没有细粒度形状或姿态编辑评估**：实验主要围绕语义替换和背景保留，对复杂结构变化的编辑能力分析较少。
- **掩码自动提取在复杂场景可能不准**：当编辑语义差异细微或背景干扰严重时，自引导掩码可能失效，文中未量化其准确率。

（完）
