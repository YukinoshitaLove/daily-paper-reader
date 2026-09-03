<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-09-03
- 运行时间：2026-09-03 22:25:47 UTC
- 运行状态：成功
- 本次总论文数：15
- 精读区：6
- 速读区：9

### 今日简报（AI）
今日推荐15篇论文，其中6篇精读、9篇速读；最值得关注的是感知正则化扩散模型用于图像超分（10/10）和以一致性正则实现无监督阴影去除（9/10）。速读中，基于光谱谐波的全能天气恢复（8/10）也值得一看。建议普通读者优先追踪图像复原与生成模型结合的方向，后续可关注其效率提升与真实场景泛化。
- 详情：[/202609/03/README](/202609/03/README)

### 精读区论文标签
1. [Perceptually Regularized Diffusion Model for Image Super-Resolution](/202609/03/2609.02016v1-perceptually-regularized-diffusion-model-for-image-super-resolution)  
   标签：评分：10.0/10、query:real-ir
   evidence：将感知正则化引入图像超分辨率扩散模型
2. [Consistency as Regularization for Unsupervised Shadow Removal](/202609/03/2609.01806v1-consistency-as-regularization-for-unsupervised-shadow-removal)  
   标签：评分：9.0/10、query:real-ir
   evidence：提出基于跨观测一致性的无监督阴影去除，直接属于图像恢复任务。
3. [LaST-SR: Laplace-Inspired Steady-Transient Complex-Frequency Decomposition for Single Image Super-Resolution](/202609/03/2609.02063v1-last-sr-laplace-inspired-steady-transient-complex-frequency-decomposition-for-single-image-super-resolution)  
   标签：评分：9.0/10、query:real-ir
   evidence：论文聚焦单图像超分辨率，提出复频域稳态-瞬态分解，直接匹配图像恢复与超分辨率需求。
4. [SR-Edit: Region-Aware Image Editing via Self-Refinement](/202609/03/2609.02504v1-sr-edit-region-aware-image-editing-via-self-refinement)  
   标签：评分：9.0/10、query:real-ir
   evidence：提出基于自细化的区域感知图像编辑框架，精确修改目标区域并保持其余区域
5. [Uncertainty-Guided Adverse Weather Restoration via Gated Transformer Network](/202609/03/2609.02434v1-uncertainty-guided-adverse-weather-restoration-via-gated-transformer-network)  
   标签：评分：8.0/10、query:real-ir
   evidence：用门控Transformer做一体化恶劣天气图像恢复
6. [Benchmarking RAW and RGB Restoration in Image Signal Processors](/202609/03/2609.02831v1-benchmarking-raw-and-rgb-restoration-in-image-signal-processors)  
   标签：评分：8.0/10、query:real-ir
   evidence：围绕ISP系统化评测RAW与RGB盲图像恢复

### 速读区论文标签
1. [Efficient All-in-One Weather Restoration using Spectral Harmonization](/202609/03/2609.02839v1-efficient-all-in-one-weather-restoration-using-spectral-harmonization)  
   标签：评分：8.0/10、query:real-ir
   evidence：面向雨雾雪等天气退化的轻量全能图像恢复
2. [A Cone-Constrained Bilinear Decomposition for Total Scaled-Gradient Variation Models](/202609/03/2609.00036v1-a-cone-constrained-bilinear-decomposition-for-total-scaled-gradient-variation-models)  
   标签：评分：7.0/10、query:real-ir
   evidence：面向边缘保持图像恢复正则化的锥约束优化方法
3. [SelfLift: Accelerating Few-Step Diffusion via Self-Recovering Resolution Transition](/202609/03/2609.02036v1-selflift-accelerating-few-step-diffusion-via-self-recovering-resolution-transition)  
   标签：评分：7.0/10、query:real-ir
   evidence：通过渐进分辨率推理加速少步扩散，与扩散模型效率高度相关
4. [Using Channel Representations in Regularization Terms: A Case Study on Image Diffusion](/202609/03/2608.29227v1-using-channel-representations-in-regularization-terms-a-case-study-on-image-diffusion)  
   标签：评分：6.0/10、query:real-ir
   evidence：面向图像重建与去噪的非线性扩散滤波新方法
5. [Test-Time Scaling for Video Diffusion Models via Diagnosis-Guided Candidate Recycling](/202609/03/2608.29322v1-test-time-scaling-for-video-diffusion-models-via-diagnosis-guided-candidate-recycling)  
   标签：评分：6.0/10、query:real-ir
   evidence：视频扩散模型的测试时扩展与候选回收方法，属于扩散生成模型方向而非恢复方向
6. [Efficient and High-Quality Depth Estimation via Pixel-Space Diffusion with Linear Attention](/202609/03/2608.30129v1-efficient-and-high-quality-depth-estimation-via-pixel-space-diffusion-with-linear-attention)  
   标签：评分：6.0/10、query:real-ir
   evidence：线性注意力像素空间扩散用于高分辨率深度估计，方法可迁移但任务非图像恢复
7. [GenScale: A Benchmark for Relative Object Scale in Image Generation and Editing](/202609/03/2609.00525v1-genscale-a-benchmark-for-relative-object-scale-in-image-generation-and-editing)  
   标签：评分：6.0/10、query:real-ir
   evidence：面向图像生成与编辑相对物体规模的评测基准和修正代理，属于编辑/生成模型评测方向
8. [Linear Fusion MultiDiffusion for Fast Training-Free Spherical Panorama Generation](/202609/03/2609.01997v1-linear-fusion-multidiffusion-for-fast-training-free-spherical-panorama-generation)  
   标签：评分：6.0/10、query:real-ir
   evidence：基于扩散模型的全景图生成方法，免训练线性融合属于扩散模型方法范畴
9. [InstEditSeg: Instruction-Driven Image Editing for Polyp and Skin Lesion Segmentation](/202609/03/2609.02004v1-insteditseg-instruction-driven-image-editing-for-polyp-and-skin-lesion-segmentation)  
   标签：评分：6.0/10、query:real-ir
   evidence：将医学分割重构为指令驱动图像编辑问题，属于图像编辑模型的应用型方法


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
