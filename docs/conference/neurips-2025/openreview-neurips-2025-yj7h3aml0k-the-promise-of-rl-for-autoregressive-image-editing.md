---
title: The Promise of RL for Autoregressive Image Editing
title_zh: 强化学习在自回归图像编辑中的前景
authors: "Saba Ahmadi, Rabiul Awal, Ankur Sikarwar, Amirhossein Kazemnejad, Ge Ya Luo, Juan A. Rodriguez, Sai Rajeswar, Siva Reddy, Christopher Pal, Benno Krojer, Aishwarya Agrawal"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=YJ7H3amL0k"
tags: ["query:real-ir"]
score: 7.0
evidence: 利用强化学习和思维链增强的自回归图像编辑
tldr: 针对文本引导图像编辑任务执行准确性不足的问题，本文探索了监督微调、强化学习和思维链推理三种策略在自回归多模态模型框架下的效果。研究表明，结合大型多模态LLM验证器的强化学习是最有效的策略，并发布了EARL模型。该方法统一处理文本和视觉token，在多种编辑任务上取得了显著提升，展示了强化学习在图像编辑中的潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 1085, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 1642, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1397, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1284, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1450, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1110, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1272, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 766, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 727, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1444, \"height\": 431, \"label\": \"Table\"}]"
motivation: 文本引导图像编辑难以准确执行编辑指令。
method: 在统一的自回归多模态框架下比较监督微调、强化学习和思维链，发现强化学习且用多模态LLM验证器最有效。
result: 强化学习策略在多个图像编辑任务上显著优于其他方法。
conclusion: 强化学习是提升自回归图像编辑准确性的有效途径。
---

## Abstract
While image generation techniques are now capable of producing high-quality images that respect prompts which span multiple sentences, the task of text-guided image editing remains a challenge. Even edit requests that consist of only a few words often fail to be executed correctly. We explore three strategies to enhance performance on a wide range of image editing tasks: supervised fine-tuning (SFT), reinforcement learning (RL), and Chain-of-Thought (CoT) reasoning. In order to study all these components in one consistent framework, we adopt an autoregressive multimodal model that processes textual and visual tokens in a unified manner.
We find RL combined with a large multi-modal LLM verifier to be the most effective of these strategies.
As a result, we release **EARL**: **E**diting with **A**utoregression and **RL**, a strong RL-based image editing model that performs competitively on a diverse range of edits compared to strong baselines, despite using much less training data. Thus, EARL pushes the frontier of autoregressive multimodal models on image editing. We release our code, training data, and trained models at [https://github.com/mair-lab/EARL](https://github.com/mair-lab/EARL).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究背景**：文本到图像生成技术已能生成高质量图像，但文本引导的图像编辑（text-guided image editing）仍存在挑战：即使编辑指令只有几个词，模型也常常无法正确执行。现有扩散模型在简单编辑（对象/属性替换）上表现尚可，但在复杂编辑（空间关系、计数、动作理解等）上远不足。
- **整体含义**：本文目标是探索如何用**统一端到端模型**同时处理简单和复杂编辑，系统比较三种学习范式——监督微调（SFT）、强化学习（RL）和思维链推理（CoT）——在自回归（AR）多模态框架下的效果，最终提出**EARL**（Editing with Autoregression and RL），证明AR模型结合RL可以达到甚至超越强扩散基线，推动了AR模型在图像编辑中的前沿。

## 2. 方法论

- **核心思想**：采用**统一自回归多模态模型**，将文本和视觉token联合建模，在同一个框架下对比三种训练策略。
- **基础模型**：Emu3-8B，一个全自回归的图文联合生成模型，输入为原图vision tokens + 编辑指令语言tokens，输出为编辑后图像的vision tokens。

- **三种训练范式**：
  - **SFT**：标准下一个token预测，最小化交叉熵损失。
  - **RL后训练**：使用**GRPO**（Group Relative Policy Optimization）进行在线RL优化。对于每个输入，模型生成G个候选编辑，用**大MLLM验证器**（Qwen2.5-VL-72B）根据VIEScore四个维度（编辑成功、过度编辑、自然感、伪影）计算总分作为奖励，再通过组相对优势估计更新策略。KL散度项保持稳定性。
  - **CoT推理**：在SFT阶段，先用MLLM生成结构化推理链（描述输入图像、目标边界框、编辑步骤等）作为输出前缀，监督模型学习逐步推理后再生成图像。

- **关键技术细节**：
  - 数据集分为**简单编辑（S）**（OmniEdit 750K）和**复杂编辑（C）**（Aurora、VisMin、MagicBrush等，共171K，上采样至300K）。
  - SFT learning rate 1e-4，RL learning rate 3e-6，KL系数3e-4，batch size 128，8个rollout per instruction。
  - 图像分辨率256×256，采用完全在线策略梯度（每步单次梯度更新）。

## 3. 实验设计

- **评估基准**（6个）：
  - **简单编辑**：OmniEdit、EmuEdit（OOD）
  - **复杂编辑**：MagicBrush、AURORA（含子集）、VisMin（从caption生成指令）、I2EBench（OOD）
- **评估指标**：**VIEScore**（GPT-4o-mini作为评估模型），从0-10分，综合四个子指标（可解释性好）。另补充CLIP相似度、FID等。
- **对比方法**：MagicBrush、InstructPix2Pix、Aurora（扩散模型）、EditAR（AR模型）、Omnigen（SOTA扩散模型，训练数据~5×更多）。
- **实验分组**：
  - 消融SFT阶段：SFT(S)、SFT(S+C)、SFT(S+C) two-stage
  - 消融RL阶段：从不同SFT基座出发，用RL(S)、RL(C)、RL(S+C)
  - 缩放训练：将最佳配置SFT(S)→RL(S+C)扩至2000步、32K样本，称为EARL
  - CoT变体：SFT think (S)、SFT think (S+C) two-stage，以及在其上叠加RL
  - 附加：Best-of-N采样、不同验证器比较（Qwen2.5-VL-72B vs Qwen-7B）

## 4. 资源与算力

- **SFT训练**：4×A100L GPU，batch size 128，约60小时
- **RL训练**：4×NVIDIA H100 GPU，2000步，约48小时；推理时使用vLLM
- **验证器**：Qwen2.5-VL-72B 运行在4×H100推理服务器
- **总数据使用**：约752K样本（SFT 750K，RL 32K），远少于Omnigen的4M+
- **训练时长**：合计约108小时

## 5. 实验数量与充分性

- **实验数量**：
  - 主表格（Table 2）列出17种模型/训练变体的结果，覆盖6个基准。
  - 消融实验包括：不同SFT组成、不同RL数据组合、不同基座（S vs S+C）、不同验证器规模、CoT变体（Table 3）、Best-of-N（Table 11）、细粒度子任务分析（Table 12-17）。
  - 额外评估：CLIP/FID（Table 8-9）、PIEBench对比（Table 10）、推理速度（Appendix F.3）。
- **充分性与公平性**：
  - **充分**：覆盖简单、复杂、IID、OOD场景，对比最强扩散和AR基线，做了大量消融。
  - **客观**：评估指标采用VIEScore（基于GPT-4o-mini，与人类相关），并验证与人类判断一致（Table 4、5）。RL奖励与评估使用不同MLLM，减少过拟合。
  - **不足**：未报告误差棒（error bars），可能存在随机性影响。另外，某些复杂编辑（如大规模计数变化）验证器仍不可靠（见Fig 6）。

## 6. 主要结论与发现

1. **RL后训练最有效**：从SFT(S)基座经过RL(S+C)训练，平均VIEScore从3.88提升至4.57，进一步缩放至EARL后达到4.80，超过所有基线（包括用5倍数据的Omnigen）。
2. **复杂编辑在SFT阶段无益，但在RL阶段有益**：SFT混合复杂数据会损害简单编辑性能（SFT(S+C)平均3.32 < SFT(S) 3.88），但RL(C)能保持简单编辑性能同时提升复杂编辑。
3. **CoT推理未带来一致改进**：无论是SFT还是RL叠加，CoT变体均低于无推理对应模型。可能因为Emu3未预训练于交错图文生成，且CoT引入伪影。
4. **验证器规模至关重要**：Qwen2.5-VL-72B作为验证器有效，而7B版本导致RL性能下降至2.81（Table 6）。
5. **数据效率**：EARL以远少于SOTA的数据获得可比甚至更优性能，证明AR+RL范式的潜力。

## 7. 优点

- **统一框架**：首次在同一AR模型内系统比较SFT、RL、CoT，控制变量。
- **方法简洁有效**：RL（GRPO）+强大MLLM验证器，无需人工偏好标注或掩码条件，端到端训练。
- **数据高效**：仅用开源合成数据集，750K SFT + 32K RL即达到SOTA，而Omnigen需4M+。
- **推理速度快**：相比Omnigen（扩散模型）快4倍（256×256下），同时保持质量。
- **评估全面**：6个基准、多种指标、人类相关性验证，并公开代码、数据、模型。

## 8. 不足与局限

- **验证器依赖**：RL性能高度依赖Qwen2.5-VL-72B的准确性，复杂编辑（如大规模计数、细微空间关系）验证仍不可靠（Fig 6），且验证器可能继承其预训练偏差。
- **CoT失败**：尽管尝试多种设置（S、C、two-stage），CoT均未提升甚至降低性能。作者推测因基础模型缺乏交错图文预训练，但未深入诊断，未来需更强AR基座。
- **训练数据噪声**：合成数据（扩散生成+自动过滤）仍含变形、未能反映指令的样本，可能引入噪声。
- **公平性偏差**：如果基座模型或验证器存在人口统计偏差，RL可能放大这些偏差。代码发布但未提供额外安全过滤。
- **实验未报告误差棒**：缺乏多次运行置信度，部分结论稳定性待验证。
- **仅限单一基座**：所有实验基于Emu3-8B，结论能否泛化到其他AR模型（如LlamaGen）未知。
- **应用限制**：模型主要面向研究，直接部署于真实场景可能带来伪造、误导风险。

（完）
