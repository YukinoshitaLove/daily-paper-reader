---
title: "Instruct-CLIP: Improving Instruction-Guided Image Editing with Automated Data Refinement Using Contrastive Learning"
title_zh: Instruct-CLIP：利用对比学习自动细化数据改进指令引导图像编辑
authors: "Chen, Sherry X., Sra, Misha, Sen, Pradeep"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_Instruct-CLIP_Improving_Instruction-Guided_Image_Editing_with_Automated_Data_Refinement_Using_CVPR_2025_paper.pdf"
tags: ["query:real-ir"]
score: 9.0
evidence: 通过对比学习自动细化训练数据改进指令引导图像编辑
tldr: 针对图像编辑训练数据中指令与图像不匹配的问题，提出Instruct-CLIP自监督方法，通过对比学习自动筛选和细化编辑对，构建高质量数据集。实验表明该方法显著提升了指令引导图像编辑模型的性能，为数据驱动编辑提供了可靠基础。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 798, \"height\": 211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 807, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 806, \"height\": 165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 809, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 732, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 652, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 871, \"height\": 218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1615, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 870, \"height\": 218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 865, \"height\": 184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 850, \"height\": 345, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-instruct-clip-improving-instruction-guided-image-editing-with-automated-data-refinement-using-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 276, \"label\": \"Table\"}]"
motivation: 现有图像编辑训练数据集质量低，合成对常与指令不匹配。
method: 提出自监督方法Instruct-CLIP，用对比学习自动筛选和细化编辑指令与图像对。
result: 构建高质量数据集，显著提升编辑模型性能。
conclusion: 自动化数据细化是提升图像编辑模型的有效途径。
---

## Abstract
Although natural language instructions offer an intuitive way to guide automated image editing, deep-learning models often struggle to achieve high-quality results, largely due to the difficulty of creating large, high-quality training datasets. To do this, previous approaches have typically relied on text-to-image (T2I) generative models to produce pairs of original and edited images that simulate the input/output of an instruction-guided image- editing model. However, these image pairs often fail to align with the specified edit instructions due to the limitations of T2I models, which negatively impacts models trained on such datasets. To address this, we present Instruct-CLIP (I-CLIP), a selfsupervised method that learns the semantic changes between original and edited images to refine and better align the instructions in existing datasets. Furthermore, we adapt Instruct-CLIP to handle noisy latent images and diffusion timesteps so that it can be used to train latent diffusion models (LDMs) and efficiently enforce alignment between the edit instruction and the image changes in latent space at any step of the diffusion pipeline. We use Instruct-CLIP to correct the InstructPix2Pix dataset and get over 120K refined samples we then use to fine-tune their model, guided by our novel I- CLIP-based loss function. The resulting model can produce edits that are more aligned with the given instructions. Our code and dataset are available at https://github.com/SherryXTChen/Instruct-CLIP.git.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：指令引导的图像编辑模型（如 InstructPix2Pix）高度依赖高质量的训练数据。现有数据生成流程通常借助文本‑到‑图像模型模拟编辑前后的图像对，并利用大语言模型生成编辑指令，但生成的图像对往往与指令**语义不一致**（如图像变化与指令描述不匹配），严重限制了模型性能。
- **整体含义**：论文提出一种自监督方法，通过自动精炼现有数据集中的错误或模糊指令，提升数据质量，从而以较小的代价增强编辑模型对齐指令的能力，不需要人工标注或重新构建整个数据流水线。

### 2. 方法论
- **核心思想**：借鉴 CLIP 的对比学习框架，将“原始→编辑图像的视觉变化”与“编辑指令”映射到同一语义空间，并通过一个解码器生成更准确的精炼指令。该方法既可用于离线数据集清洗，又可作为训练时的语义对齐损失。
- **关键技术细节**：
  - **Instruct‑CLIP 架构**：
    - 视觉编码器 `I-CLIP_vis`：两个共享权重的 DINOv2 分别提取原图 `Io` 和编辑图 `Ie` 的特征，计算特征差并与中层特征跳跃连接后送入 CLIP 视觉编码器，得到视觉变化嵌入 `zvis`。
    - 文本编码器 `I-CLIP_txt`：沿用 CLIP 文本编码器，将编辑指令 `p` 映射为 `ztxt`。
    - 训练采用对比损失（式 2），使匹配的 `(zvis, ztxt)` 对相似度最大。
  - **指令精炼**：
    - 使用 DeCap 策略，以交叉熵损失训练一个文本解码器将 `ztxt` 重建为原指令。
    - 推理时，为缩小 `zvis` 与文本特征的分布差距，计算 `zvis` 与训练集中所有 `ztxt_i` 的余弦相似度，经 softmax 加权求和得到 `(zvis)'`（式 6），再解码出新指令 `p'`。
  - **扩散潜在空间适配**：
    - 训练一个“潜在‑扩散 DINOv2”（LD‑DINOv2），输入噪声潜在图像 `L~k` 和时间步 `tk`，输出与原始 DINOv2 对齐的特征（式 7）。
    - 在潜在扩散模型（LDM）训练中，用 LD‑DINOv2 替换原 DINOv2，使 I‑CLIP 能在任意扩散时间步计算 `zvis`。
  - **编辑模型训练**：在 InstructPix2Pix 的标准 MSE 损失基础上，添加 I‑CLIP 引导损失 `L_I-CLIP`（式 12），强制中间去噪结果与精炼指令 `p'` 语义对齐。
- **整体流程**：先利用 Instruct‑CLIP 精炼已有数据集，得到 120K+ 高质量样本；再用精炼数据和 I‑CLIP 损失微调编辑模型。

### 3. 实验设计
- **数据集与基准**：
  - 数据精炼和训练基于 InstructPix2Pix 数据集。
  - 评估主要在 MagicBrush 和 ZONE 两个指令编辑基准上进行（含单轮与多轮编辑）。
- **对比方法**：Inst-Inpaint、MagicBrush、HIVE、InstructPix2Pix、Watch Your Steps、ZONE。
- **评估指标**：CLIP‑T（语义对齐）、CLIP‑I 和 DINO‑I（视觉保真度），并进行了 104 人参与的用户研究（对比 IP2P 和 MagicBrush）。
- **消融实验**：分别移除了精炼数据（用原始 IP2P 数据训练但保留 I‑CLIP 损失）和移除了 I‑CLIP 引导损失（用精炼数据但仅 MSE 训练），以考察各部件贡献。

### 4. 资源与算力
- 论文明确提及：在**指令精炼**阶段，使用 **两台 A6000 GPU**，耗时约 **10 小时**生成了超过 120K 个精炼样本。
- 对于后续编辑模型的微调训练，未给出具体的 GPU 数量、训练时长等算力明细。

### 5. 实验数量与充分性
- **实验规模**：包含在 2 个基准（MagicBrush 单/多轮、ZONE）上的定量比较（含 6 个基线）、消融实验（3 个变体）、大量定性可视化案例以及一次 104 人的用户研究（约 33 组对比 × 参与者）。
- **充分性评估**：实验设计较为全面，覆盖了客观指标、主观评价和部件有效性验证；对比方法均为同期先进工作，比较较为公平。
- **潜在局限**：指标上 CLIP‑T 等分数不一定反映真实编辑质量（论文自身也指出这一点），评估仍以 MagicBrush 等小型学术基准为主，真实场景的泛化实验缺位。

### 6. 主要结论与发现
- Instruct‑CLIP 能有效捕获图像间的语义变化，纠正数据集中大量错误的编辑指令（如“make the waves into a hurricane”→“add a lightning storm to the sky”）。
- 使用精炼后的数据集训练，并辅以 I‑CLIP 对齐损失，得到的图像编辑模型在指令‑图像对齐程度上显著优于原始 InstructPix2Pix、MagicBrush 等方法。
- 消融实验表明，数据精炼和训练时的对比损失均对性能提升有独立贡献，且视觉保真（CLIP‑I、DINO‑I）提升尤为明显。
- 用户研究显示参与者更偏好本文方法输出（胜出 IP2P 约 17.8%，胜出 MagicBrush 约 24.4%）。

### 7. 优点
- **自监督数据净化**：无需人工改写指令，利用对比学习即可修正数据中的对齐错误，具有高扩展性。
- **双重用途**：I‑CLIP 既能离线精炼数据集，又能作为在线语义损失融入扩散模型训练，实用性强。
- **扩散适配**：LD‑DINOv2 设计使 I‑CLIP 能直接处理噪声潜在图，可在任意扩散步计算对齐损失，设计巧妙。
- **实验扎实**：同时包含定量、定性、消融和用户研究，论证链完整。

### 8. 不足与局限
- **训练图像固有缺陷**：精炼后的数据仍来源于 Prompt‑to‑Prompt 等生成方法，其图像编辑本身的瑕疵（如颜色溢出、物体移除不彻底）无法通过指令精炼消除，限制了性能上限。
- **指标敏感度有限**：CLIP‑T 等自动指标有时与视觉质量不一致，论文虽加以指出，但评估体系依然部分倚赖此类指标。
- **应用范围**：只在基于 InstructPix2Pix 的扩散编辑框架上验证，未在更多样化的编辑模型结构上测试。精炼流程也仅针对一个数据集（IP2P），其到其他数据集的迁移效果未知。
- **训练算力未完整公开**：编辑模型微调的资源需求未说明，难以评估实际训练开销。

（完）
