---
title: "Transition Matching: Scalable and Flexible Generative Modeling"
title_zh: 过渡匹配：可扩展且灵活的生成建模
authors: "Neta Shaul, Uriel Singer, Itai Gat, Yaron Lipman"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=An0ePypuOJ"
tags: ["query:real-ir"]
score: 7.0
evidence: 统一扩散与自回归生成的新范式
tldr: 现有扩散/流模型与连续自回归模型各有优缺点，Transition Matching提出一种离散时间连续状态生成范式，将复杂生成任务分解为马尔可夫转移，允许非确定性转移核和任意非连续监督过程。该方法在媒体生成任务上表现优越，同时简化了设计和扩展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1413, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 400, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 629, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 318, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1410, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 671, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1435, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1517, \"height\": 1171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1403, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1399, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1355, \"height\": 1762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1354, \"height\": 1405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1356, \"height\": 1982, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1357, \"height\": 1081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1374, \"height\": 1433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1369, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1268, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1267, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1262, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1271, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1272, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1269, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1269, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1266, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1270, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1276, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1269, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1267, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1265, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1266, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1272, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1268, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1268, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1271, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1277, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1398, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1429, \"height\": 1599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1424, \"height\": 1699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1369, \"height\": 1731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-an0epypuoj/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1424, \"height\": 1793, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 707, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 705, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1357, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1131, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1270, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1362, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1392, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 734, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 516, \"height\": 117, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1440, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1444, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1444, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 933, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-an0epypuoj/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1466, \"height\": 502, \"label\": \"Table\"}]"
motivation: 扩散/流模型设计空间受限，自回归模型在统一文本与媒体生成上表现更好但范式不同。
method: 提出Transition Matching，将生成过程建模为离散时间马尔可夫转移，支持非确定性核和非连续监督。
result: 在媒体生成任务上取得竞争力性能，统一了扩散/流与自回归生成。
conclusion: Transition Matching为生成建模提供了更灵活通用的框架。
---

## Abstract
Diffusion and flow matching models have significantly advanced media generation, yet their design space is well-explored, somewhat limiting further improvements. Concurrently, autoregressive (AR) models, particularly those generating continuous tokens, have emerged as a promising direction for unifying text and media generation, showing improved performance at scale. This paper introduces Transition Matching (TM), a novel discrete-time, continuous-state generative paradigm that unifies and advances both diffusion/flow models and continuous AR generation. TM decomposes complex generation tasks into simpler Markov transitions, allowing for expressive non-deterministic probability transition kernels and arbitrary non-continuous supervision processes, thereby unlocking new flexible design avenues. We explore these choices through three TM variants: (i) Difference Transition Matching (DTM), which generalizes flow matching to discrete-time  by directly learning transition probabilities, yielding state-of-the-art image quality and text adherence. (ii) Autoregressive Transition Matching (ARTM) and (iii) Full History Transition Matching (FHTM) are partially and fully causal models, respectively, that generalize continuous AR methods. They achieve continuous causal AR generation quality comparable to non-causal approaches and potentially enable seamless integration with existing AR text generation techniques. Notably, FHTM is the first fully causal model to match or surpass the performance of flow-based methods on text-to-image task in continuous domains. 
  We demonstrate these contributions through a rigorous large-scale comparison of TM variants and relevant baselines, maintaining a fixed architecture, training data, and hyperparameters.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：扩散模型和流匹配（flow matching）在媒体生成（图像、视频、音频）中取得了显著进展，但其设计空间已被广泛探索，进一步改进受限。同时，自回归（AR）模型，特别是生成连续token的AR模型，成为统一文本和媒体生成的有前途方向，并在大规模下表现出更好的性能。
- **核心问题**：如何设计一个更灵活、统一的生成范式，既能继承扩散/流模型的优势（逐步去噪），又能融合连续AR模型的因果建模能力，从而解锁新的设计空间，实现更优的生成质量和采样效率。
- **核心含义**：Transition Matching（TM）是一个离散时间、连续状态的生成范式，它统一了扩散/流模型和连续AR生成。通过将复杂生成任务分解为更简单的马尔可夫转移，并允许非确定性的概率转移核和任意非连续监督过程，TM提供了新的灵活设计方向。

## 2. 方法论

### 2.1 核心思想
- 定义一个马尔可夫过程，从简单分布 p0（如标准正态）逐步过渡到目标分布 pT（数据分布）。
- 利用一个“监督过程” (X0, X1, ..., XT) 来训练转移核 pθ_{t+1|t}，使得模型学习从 Xt 到 Xt+1 的转移。
- 损失函数基于分布之间的散度，并通过经验形式（单样本损失）实现可训练。

### 2.2 关键技术细节
- **框架**：设 X0 ~ p0, Xt+1 ~ pθ_{t+1|t}(·|Xt)。监督过程 q 满足 q0 = p0，且联合分布可分解为 q0,...,T|T × pT。
- **损失函数**：L(θ) = E_{t,X_t} D(q_{t+1|t}(·|Xt), pθ_{t+1|t}(·|Xt))，其中 D 可选KL散度、MSE等。文中使用流匹配（FM）损失，即条件流匹配损失，用于建模转移核。
- **核参数化**：引入隐变量 Y，通过 q_{t+1|t,Y} 和 pθ_{Y|t} 来参数化转移核。训练时学习 pθ_{Y|t}，采样时先采样 Y 再根据 qt+1|t,Y 得到 Xt+1。
- **三个变体**：
  - **DTM**（Difference Transition Matching）：
    - 监督过程：线性过程（条件最优传输），Xt = (1 - t/T) X0 + (t/T) XT，其中 X0 ~ N(0,I)。
    - 参数化：Y = XT - X0。
    - 建模：使用流匹配学习 Y|(t, Xt)，采用 backbone-head 架构（backbone 是大模型，head 是小 MLP），每个 token 独立生成。
    - 特点：与流匹配的关系——DTM 的期望等于流匹配的边际速度；随着步数增加（T→∞），DTM 趋近于 Euler 步的流匹配。
  - **ARTM**（Autoregressive Transition Matching）：
    - 监督过程：独立线性过程，每个时间步的 X0,t 独立采样，使得转移核更灵活。
    - 参数化：Y = Xt+1（直接预测下一状态）。
    - 建模：自回归方式，每个 token 的生成依赖于之前 token（X_{t+1}^{<i}）和 Xt，使用流匹配学习。
    - 特点：部分因果模型；需要 backbone 逐 token 推理，但 patch 可并行。
  - **FHTM**（Full History Transition Matching）：
    - 监督过程：独立线性过程，使用全历史 X0,…,Xt。
    - 参数化：Y = Xt+1。
    - 建模：完全因果，依赖所有历史状态，使用完全因果的 backbone（如 LLM 架构）。
    - 特点：第一个在连续域中达到或超越流匹配性能的完全因果模型。

### 2.3 公式/算法流程（文字描述）
- 训练算法（通用）：
  1. 采样数据 XT，时间 t，以及条件样本 (Xt, Y) 来自监督过程。
  2. 通过 backbone 提取特征，head 预测速度场 uθs。
  3. 计算条件流匹配损失 L = E[||uθs - (Y - Y0)||²]。
- 采样算法：
  1. 从 p0 采样 X0。
  2. 对 t=0..T-1：通过 head 生成 Y（ODE求解），然后根据过程（如 Xt+1 = Xt + (1/T)Y）得到 Xt+1。
  3. 输出 XT。

## 3. 实验设计

- **数据集**：
  - 训练：350M 许可的 Shutterstock 图像-描述对，图像 256×256，描述长度1-128 token（CLIP tokenizer）。
  - 评估：PartiPrompts、MS-COCO、GenEval、T2I-CompBench。
- **基准与对比方法**：
  - 基线包括：FM（流匹配）、MAR（连续token掩码自回归）、MAR-Fluid（连续cosine调度）、MAR-discrete（离散token）、AR（连续token自回归）、AR-discrete（离散token自回归）。
  - 额外对比：Restart 采样、MARTM等。
- **架构与设置**：
  - backbone：DiT（1.7B参数，24层自注意力+交叉注意力，hidden=2048，head=16）和 LLM 架构（1.7B，34层，无交叉注意力，文本作为前缀）。
  - head：6层MLP，hidden=1024，约40M参数。
  - 所有模型使用相同架构、数据、超参数（500K迭代，batch size 2048，lr 1e-4，warmup 2K）。
  - 分类器无引导（CFG）尺度6.5，文本丢弃概率0.15。

## 4. 资源与算力

- 论文**明确提及**：所有模型使用相同大小的 DiT 或 LLM 架构（1.7B参数），训练 500K 迭代，batch size 2048，但**未给出具体GPU型号、数量、总训练时间或功耗**。仅在采样效率部分提到使用单张 H100 GPU 计算推理时间（如 DTM 1.6秒 vs FM 10.8秒），但未提供训练时的资源细节。

## 5. 实验数量与充分性

- **实验数量**：论文进行了大量实验：
  - 主要结果：PartiPrompts、MS-COCO、GenEval、T2I-CompBench 四组基准，共27个指标。
  - 消融实验：DTM 步数与 head NFE 组合（8×8网格）、FM 步数、AR 依赖vs独立线性过程、DTM 核表达性（patch大小）、AR 调度器（均匀vs指数）、CFG 尺度敏感性、不同 head NFE 等。
  - 对比方法：6个TM变体 + 6个基线 = 12个模型，每个模型在多个基准上评测。
  - 额外扩展：MARTM、Restart 采样等。
- **充分性**：实验设计相对充分，固定架构、数据、超参数，确保了公平比较。但是：
  - 仅报告了点估计，**未给出误差棒或置信区间**（论文注明遵循标准实践）。
  - 没有使用CIFAR-10等小规模数据集验证一般性。
  - 重点在图像生成，并未涉及视频、音频等其他媒体。

## 6. 主要结论与发现

- **DTM**：在所有基线中取得最佳结果，尤其在文本对齐（PickScore、ImageReward、UnifiedReward）和图像质量（Aesthetic、DeQA）上显著超越FM和MAR。CLIPScore 在 PartiPrompts 上仅次于 ARTM-3 和 FHTM-3，但在 MS-COCO 上领先。
- **ARTM/FHTM**（3步）：在图像质量上大幅优于基线AR/MAR，CLIPScore 与 MAR 接近，但其他指标显著提升。FHTM-3 是首个在连续域达到或超越流匹配的**完全因果**模型。
- **采样效率**：DTM 仅需少量 backbone 步骤（如16步）即可达到 SOTA，比 FM 快约7倍；AR 变体则因逐token推理而较慢。
- **监督过程**：独立线性过程对于 AR 核至关重要，而依赖线性过程会导致低质量生成。
- **全局排名**：DTM 排名第一，其次 FHTM-3/ARTM-3，然后 MAR。

## 7. 优点

1. **理论创新**：统一了扩散/流与连续AR生成，提供了更通用的框架，并揭示了 DTM 与流匹配的极限关系。
2. **灵活性**：允许非确定转移核和非连续监督过程，解锁新设计空间。
3. **性能优秀**：DTM 在多个指标上达到 SOTA，FHTM 首次使完全因果模型在连续域匹敌非因果方法。
4. **公平比较**：固定架构、数据、超参数进行大规模对比，结果可靠。
5. **采样加速**：DTM 实现近7倍加速，同时保持高质量。
6. **可扩展性**：FHTM 易于与 LLM 集成，为多模态 AR 模型提供基础。

## 8. 不足与局限

1. **实验覆盖有限**：没有在视频、音频、3D等其他媒体模态上验证，仅聚焦图像生成。
2. **缺乏不确定性量化**：所有指标仅报告点估计，未给出方差或置信区间。
3. **计算开销**：AR/FHTM 的采样成本高（NFE = 步骤数 × token数），仅 DTM 加速明显。
4. **消融不完整**：对监督过程的非连续性（如跳变）未充分探索；核表达性实验仅限 patch 大小，未尝试更复杂的依赖关系。
5. **架构依赖**：Head 设计（独立 token）可能限制 DTM 核的表达能力，作者也承认这一点。
6. **资源报告缺失**：未提供训练所使用的具体GPU数量、时长、功耗等，影响可重复性。
7. **适用性**：假设数据在欧氏空间，对于离散或结构化数据需额外适配。

（完）
