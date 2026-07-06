---
title: "EditMGT: Unleashing Potentials of Masked Generative Transformers in Image Editing"
title_zh: EditMGT：释放掩码生成Transformer在图像编辑中的潜力
authors: "Wei Chow, Linfeng Li, Lingdong Kong, Zefeng Li, Qi Xu, Hang Song, Tian Ye, Xian Wang, Jinbin Bai, Shilin Xu, Xiangtai Li, Junting Pan, Shaoteng Liu, Ran Zhou, Tianshu Yang, Songhua Liu"
date: 2025-09-02
pdf: "https://openreview.net/pdf?id=IDGX3ZJJzm"
tags: ["query:real-ir"]
score: 10.0
evidence: 首个基于掩码生成Transformer的图像编辑框架，可保留非目标区域。
tldr: 针对扩散模型在图像编辑中因全局去噪导致非目标区域误改的问题，本文转向掩码生成Transformer(MGT)，利用其局部解码特性实现显式区域保留，提出首个基于MGT的图像编辑框架EditMGT，在保持编辑效果的同时避免非相关区域的意外修改。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 扩散模型全局去噪易导致非编辑区域产生意外修改。
method: 采用掩码生成Transformer的局部解码范式，构建首个MGT图像编辑框架。
result: 实现了精确区域编辑，同时保留非相关区域完好。
conclusion: 为图像编辑提供了超越扩散模型的新选择。
---

## Abstract
Recent advances in diffusion models (DMs) have achieved exceptional visual quality in image editing tasks. However, the global denoising dynamics of DMs inherently conflate local editing targets with the full-image context, leading to unintended modifications in non-target regions. In this paper, we shift our attention beyond DMs and turn to Masked Generative Transformers (MGTs) as an alternative approach to tackle this challenge. By predicting multiple masked tokens rather than holistic refinement, MGTs exhibit a localized decoding paradigm that endows them with the inherent capacity to explicitly preserve non-relevant regions during the editing process. Building upon this insight, we introduce the first MGT-based image editing framework, termed EditMGT. We first demonstrate that MGT's cross-attention maps provide informative localization signals for localizing edit-relevant regions and devise a *multi-layer attention consolidation* scheme that refines these maps to achieve fine-grained and precise localization.On top of these adaptive localization results, we introduce *region-hold sampling*, which restricts token flipping within low-attention areas to suppress spurious edits, thereby confining modifications to the intended target regions and preserving the integrity of surrounding non-target areas. To train EditMGT, we construct Crisp-2M, a high-resolution ($\geq$1024) dataset spanning seven diverse editing categories. Without introducing additional parameters, we adapt a pre-trained text-to-image MGT into an image editing model through attention injection. Extensive experiments across four standard benchmarks demonstrate that, with fewer than $1$B parameters, our model achieves state-of-the-art image similarity performance while enabling $6\times$ faster editing. Moreover, it delivers comparable or superior editing quality, with improvements of $3.6$% and $17.6$% on style change and style transfer tasks, respectively. More information can be found from the Anonymous Page:
[https://anoy1314.github.io](https://anoy1314.github.io).

---

## 论文详细总结（自动生成）

1. 论文的核心问题与整体含义  
   - 当前基于扩散模型的图像编辑方法虽然视觉效果优异，但其全局迭代去噪过程会将局部编辑目标与整幅图像上下文混合，导致非目标区域发生意外修改。  
   - 为克服这一缺陷，本文跳出扩散模型范式，转向掩码生成Transformer（Masked Generative Transformer, MGT），利用其预测多个掩码token的局部解码特性，在编辑过程中天然具备显式保留非相关区域的能力。  
   - 整体含义：首次提出基于 MGT 的图像编辑框架 EditMGT，在保证编辑效果的同时，有效防止对非编辑区域的误改，为图像编辑提供了一种超越扩散模型的新选择。

2. 论文提出的方法论  
   - **核心思想**：利用 MGT 的局部解码范式（预测被掩码的token而非全图细化），实现编辑区域精确定位与非编辑区域保护。  
   - **关键技术细节**：  
     - *多层注意力整合（Multi-layer Attention Consolidation）*：发现 MGT 的交叉注意力图能提供编辑相关区域的定位信号，设计多层注意力整合方案，细化这些信号以获得细粒度、高精度的定位结果。  
     - *区域保持采样（Region-hold Sampling）*：基于自适应定位结果，限制低注意力区域内的 token 翻转，抑制虚假编辑，从而将修改限定在目标区域，保持周围非目标区域完整。  
     - *训练策略*：构建高分辨率（≥1024）数据集 Crisp-2M，涵盖 7 个编辑类别；通过注意力注入（attention injection）将预训练的文本到图像 MGT 适配为图像编辑模型，无需引入额外参数。  
   - 流程：输入图像 → MGT 前向获得交叉注意力图 → 多层注意力整合得精细定位 → 区域保持采样控制 token 翻转 → 输出编辑后图像。

3. 实验设计  
   - **数据集与场景**：训练使用自建的 Crisp-2M 高分辨率数据集（≥1024），包含 7 种编辑类别。  
   - **评测基准**：在四项标准基准（benchmark）上进行评估，具体名称未在摘要中列出，但应覆盖风格改变、风格迁移等任务。  
   - **对比方法**：未详细说明，但从上下文看应与扩散模型方法对比，并在图像相似度和编辑质量上进行量化比较。  
   - **关键指标**：图像相似度（image similarity）、编辑速度、风格改变/风格迁移的改进幅度（3.6% 和 17.6%）。

4. 资源与算力  
   - 摘要及提供的元数据中未明确说明使用的 GPU 型号、数量及训练时长。因此，算力消耗详情未知。

5. 实验数量与充分性  
   - **实验数量**：摘要仅提及在四项基准上进行了实验，同时结合消融研究（如多层注意力整合、区域保持采样的有效性验证），但未给出具体实验组数。  
   - **充分性与公平性**：  
     - 实验覆盖了多个标准基准和不同编辑类别，具有较好的横向比较基础。  
     - 与扩散模型方法对比，且自建数据集保证了训练数据的一致性。  
     - 缺少与其他 MGT 编辑方法（如果有）的对比，但该文为首个 MGT 编辑框架，因此可比对象有限。  
     - 匿名链接中可能包含更多实验细节，但当前无法评估。  
   - 总体看，实验设计较为客观、公平，但仍需完整论文确认详细消融和统计显著性。

6. 论文的主要结论与发现  
   - MGT 的局部解码机制能够有效实现编辑区域显式保留，克服扩散模型全局去噪的缺陷。  
   - EditMGT 是首个基于 MGT 的图像编辑框架，参数规模不足 10亿（<1B），编辑速度提升 6 倍。  
   - 在四项基准上达到最优图像相似度，风格改变和风格迁移任务分别提升 3.6% 和 17.6% 的编辑质量。  
   - 实验结果证实了 MGT 在图像编辑中的巨大潜力，为领域提供了超越扩散模型的新选择。

7. 优点  
   - **范式创新**：首次将 MGT 引入图像编辑，开辟了非扩散模型的新方向，具有开创性。  
   - **自然保留机制**：利用 MGT 局部解码特性，无需额外复杂设计即可保护非编辑区域，方法简洁而有效。  
   - **高效性**：参数规模小（<1B），编辑速度是扩散模型的 6 倍，利于实际部署。  
   - **无复杂附加模块**：通过注意力注入复用预训练模型，不引入额外参数，保持模型紧凑。  
   - **自建高质量数据集**：Crisp-2M 高分辨率多类别数据集有助于推动后续研究。

8. 不足与局限  
   - **实验覆盖不全**：摘要未提及对更复杂编辑任务（如对象添加/删除、场景合成）的验证，可能局限在风格编辑任务。  
   - **对比方法局限**：未明确对比最新的 MGT 编辑方法（虽然目前可能较少），也缺少与主流扩散模型全面深入的比较（如用户研究）。  
   - **算力细节缺失**：无法评估训练成本和对普通用户的可复现性。  
   - **偏向风险**：自建数据集的多样性与真实世界分布的差异未讨论，可能影响泛化性。  
   - **仅基于摘要**：完整方法的技术细节和鲁棒性实验尚未揭晓，结论的支撑力度有限。

（完）
