---
title: "EditScore: Unlocking Online RL for Image Editing via High-Fidelity Reward Modeling"
title_zh: EditScore：通过高保真奖励建模解锁图像编辑的在线强化学习
authors: "Xin Luo, Jiahao Wang, Chenyuan Wu, Shitao Xiao, Xiyan Jiang, Defu Lian, Jiajun Zhang, Dong Liu, Zheng Liu"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=E7YpL4L4Xh"
tags: ["query:real-ir"]
score: 10.0
evidence: 通过高保真奖励模型解锁指令图像编辑的强化学习
tldr: 提出EditReward-Bench基准和EditScore奖励模型，为指令图像编辑提供可靠、高保真的评估信号，从而解锁在线强化学习，显著提升模型对复杂指令的编辑成功率和样本效率。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现编辑模型面对复杂指令效果不佳且需多次采样，强化学习因缺乏可靠奖励而难以应用。
method: 构建系统的评估基准EditReward-Bench，并据此开发高效评估编辑质量的专业奖励模型EditScore。
result: 所提奖励模型能有效指导RL训练，提升编辑模型对复杂指令的遵循能力和样本效率。
conclusion: 高保真奖励模型是推动RL在图像编辑中应用的关键，为编辑能力的持续提升铺路。
---

## Abstract
Instruction-guided image editing has achieved remarkable progress, yet current models still face challenges with complex instructions and often require multiple samples to produce a desired result. Reinforcement Learning (RL) offers a promising solution, but its adoption in image editing has been severely hindered by the lack of a high-fidelity, efficient reward signal. In this work, we present a comprehensive methodology to overcome this barrier, centered on the development of a state-of-the-art, specialized reward model. We first introduce $\textbf{EditReward-Bench}$, a comprehensive benchmark to systematically evaluate reward models on editing quality. Guided by this benchmark, we develop $\textbf{EditScore}$, an efficient model to evaluate the quality of instruction-guided editing. Through meticulous data curation and filtering, EditScore effectively matches the performance of learning proprietary VLMs. Furthermore, coupled with an effective self-ensemble strategy tailored for the generative nature of EditScore, our largest variant even surpasses GPT-5 in the benchmark. We then demonstrate that a high-fidelity reward model is the key to unlocking online RL for image editing. Our experiments show that, while even the largest open-source VLMs fail to provide an effective learning signal, EditScore enables efficient and robust policy optimization. Applying our framework to a strong base model, OmniGen2, results in a final model that shows a substantial and consistent performance uplift. Overall, this work provides the first systematic path from benchmarking to reward modeling to RL training in image editing, showing that a high-fidelity, domain-specialized reward model is the key to unlocking the full potential of RL in this domain. Our code, models, and benchmark will be released publicly.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

*   **研究背景**：指令引导的图像编辑（instruction-guided image editing）近年来进展显著，但现有模型在处理**复杂指令**时仍面临困难，往往需要多次采样才能生成符合要求的结果，效率低下且交互体验不佳。
*   **核心瓶颈**：强化学习（Reinforcement Learning, RL）被视为解决该问题的一种有前景的方案，然而其应用受到**严重制约**——缺乏一个**高保真、高效且可靠的奖励信号**。现有的通用视觉语言模型（VLMs）或简单的相似度度量无法准确评判编辑质量，导致 RL 训练难以有效开展。
*   **整体含义**：本文旨在**构建一套从基准设计到奖励建模再到 RL 训练的完整方法论**，核心是开发一个性能卓越的、领域专用的奖励模型（EditScore），以此**解锁在线 RL 在图像编辑领域的应用潜力**，使编辑模型能够高效地优化复杂指令的遵循能力，大幅提升样本效率与最终质量。

## 2. 论文提出的方法论

*   **核心思想**：以高质量奖励模型为中心，打通“评估→奖励建模→策略优化”的闭环。先定义何为好的奖励模型，再训练一个专业评判器，最后用这个评判器指导编辑策略的 RL 训练。
*   **关键技术细节**：
    *   **EditReward-Bench 基准**：系统构建一个用于评估奖励模型在编辑质量上表现的综合基准，为后续奖励模型的设计与筛选提供客观尺度。
    *   **EditScore 奖励模型**：开发一个高效、专用的模型来评价指令编辑的质量。通过**精细的数据策展与过滤**，使 EditScore 的性能足以媲美专有大型视觉语言模型（VLMs）。
    *   **自集成策略（Self-Ensemble）**：针对 EditScore 的生成式特性（可能指其输出具有随机性），设计了一种适配的自集成方法，进一步提升评分的稳健性。其最大变体在 EditReward-Bench 上**超越了 GPT-5**。
    *   **在线 RL 解锁**：明确指出，即使是最大的开源 VLM 也无法为 RL 策略优化提供有效学习信号，而 EditScore 则能驱动高效、稳健的策略优化。将整套框架应用于强基线模型 **OmniGen2**，得到最终编辑模型。
*   **算法流程简述**：首先在 EditReward-Bench 上指导奖励模型的迭代开发；然后利用 EditScore 对编辑结果进行高保真评分，该分数作为奖励信号输入在线 RL 流程（如策略梯度方法），直接优化编辑模型的参数，使其在复杂指令下的表现逐步提升。

## 3. 实验设计

*   **使用的基准与场景**：
    *   **EditReward-Bench**：专门构建的奖励模型评估基准，用于衡量不同奖励模型对编辑质量的评判能力。
    *   **指令图像编辑任务**：以复杂指令为输入，要求模型对给定图像进行相应编辑。
*   **对比的方法/模型**：
    *   **奖励模型层面**：将 EditScore 与**开源 VLM（包括最大的变体）** 以及**专有模型（如 GPT-5）** 在 EditReward-Bench 上进行比较。
    *   **策略优化层面**：对比使用不同奖励信号（如开源 VLM 的评分 vs. EditScore 的评分）进行在线 RL 训练的效果。
*   **基座编辑模型**：选用 **OmniGen2** 作为 RL 优化的初始策略，以验证 EditScore 对强大基线模型的进一步提升能力。

## 4. 资源与算力

*   论文目前提供的材料（仅摘要与元数据）**未明确提及任何算力信息**，包括 GPU 型号、数量、训练时长、批大小等。这些细节需要查阅完整论文或附录方可获知。

## 5. 实验数量与充分性

*   **实验组数量**：从摘要推测，至少包含以下几组关键实验：
    *   构建 EditReward-Bench 并评估多种奖励模型（含 EditScore 的不同变体）的性能；
    *   验证不同奖励信号（开源 VLM、EditScore 等）对 RL 训练的有效性；
    *   在 OmniGen2 等基线上进行 RL 优化，并展示最终模型在编辑任务上的提升。
    *   可能包含关于数据策展、自集成策略的消融实验（摘要未详细说明）。
*   **充分性与客观性**：
    *   **客观性**：通过独立构建的基准 EditReward-Bench 来衡量奖励模型，避免了自评偏差；对比对象涵盖了开源标杆和最新专有模型（GPT-5），具有较强说服力。
    *   **充分性**：摘要强调“substantial and consistent performance uplift”，暗示性能提升具有统计显著性。但**具体实验数量、统计检验、以及是否覆盖多类编辑场景尚无法从摘要判断**，需阅读全文确认。

## 6. 论文的主要结论与发现

*   **奖励模型是关键瓶颈**：在图像编辑中应用 RL 的核心障碍在于缺乏高保真的奖励信号，而非 RL 算法本身。
*   **EditScore 的有效性**：专门研发的奖励模型 EditScore 不仅能在编辑质量评估上匹配甚至超越顶尖专有模型（如 GPT-5），更重要的是，它能作为**有效的学习信号**，驱动成功的在线策略优化。
*   **RL 解锁**：实验表明，高保真的领域专用奖励模型是解锁 RL 在图像编辑领域潜力的钥匙。即使基于强大的基模型（如 OmniGen2），结合 EditScore 进行 RL 训练仍能带来**显著且一致**的性能提升，尤其体现在对复杂指令的遵循能力上。
*   **系统路径**：本文首次提供了从基准设计、奖励建模到 RL 训练的系统性解决路径，为今后在该方向的研究树立了范式。

## 7. 优点

*   **问题定位精准**：敏锐地识别出阻碍 RL 在图像编辑中应用的根本原因——奖励信号不可靠，而非方法本身不适用。
*   **方法论闭环**：完整覆盖“如何评价评价器 → 如何构建好评价器 → 如何使用评价器”，逻辑严谨，为后续工作提供了可复现的蓝图。
*   **评价先行**：花费大量精力构建专门的 EditReward-Bench，用以指导并验证奖励模型，体现了工程与科学的严谨性，避免了盲目的模型堆砌。
*   **效果突破**：EditScore 在基准上超越 GPT-5，且能直接驱动 RL 对强基线模型产生正收益，实证结果突出。

## 8. 不足与局限

*   **任务泛化性未知**：整个方案围绕**指令图像编辑**这一具体任务展开，所构建的基准、奖励模型及 RL 框架是否能平滑迁移至其他生成任务（如文生图、视频编辑）尚未得到验证。
*   **基座依赖**：RL 优化效果建立在 OmniGen2 这一强基线之上，对于更弱的编辑模型，该框架的增益幅度、稳定性以及是否需要调参尚不明确。
*   **奖励模型本身局限**：EditScore 作为评判模型，其性能上限会直接影响 RL 训练的天花板；一旦出现系统性评分偏差，可能导致策略被错误引导。其训练数据的覆盖广度与潜在偏见风险有待进一步披露。
*   **计算与资源成本**：即使 EditScore 被描述为“efficient”，训练一个高质量的奖励模型以及在线 RL 迭代所付出的总体算力代价、数据需求等并未在摘要中提及，可能限制其被社区快速复现。
*   **未提供实验细节**：因仅以摘要为依据，大量实验细节（如数据集组成、评估指标、对比方法的详细列表、消融实验设计）缺失，无法对这些实验设计的内部充分性做出最终评价。

（完）
