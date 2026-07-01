<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-07-01
- 运行时间：2026-07-01 22:06:13 UTC
- 运行状态：成功
- 本次总论文数：17
- 精读区：9
- 速读区：8

### 今日简报（AI）
今日精读两篇满分论文，探索超分辨率扩散模型与图像去反射的结构化生成，并速览流匹配、图像变形等前沿工作。  
最值得关注的是在扩散模型中加入结构先验（如Patch POD）实现超分与不确定性量化，以及通过潜在组合一致性移除反射的创新思路。  
建议读者从这两篇满分精读入手，体会如何为生成模型注入结构约束或语义一致性，再对比速读中流匹配的简化方法，拓宽建模路径。
- 详情：[/202607/01/README](/202607/01/README)

### 精读区论文标签
1. [Patch-PODiff-ViT: Structured Latent Diffusion with Patchwise POD for Super-Resolution and Uncertainty Quantification](/202607/01/2606.31290v1-patch-podiff-vit-structured-latent-diffusion-with-patchwise-pod-for-super-resolution-and-uncertainty-quantification)  
   标签：评分：10.0/10、query:real-ir
   evidence：结构化潜在扩散实现可解释不确定性的超分辨率
2. [PRISM: Latent Composition Consistency for Single-Image Reflection Removal](/202607/01/2606.31513v1-prism-latent-composition-consistency-for-single-image-reflection-removal)  
   标签：评分：10.0/10、query:real-ir
   evidence：利用预训练VAE潜在空间中的流匹配速度场进行单图反射去除，生成式模型用于图像复原
3. [Quality-Aware Modulation for Diffusion Transformers](/202607/01/2606.30934v1-quality-aware-modulation-for-diffusion-transformers)  
   标签：评分：9.0/10、query:real-ir
   evidence：提出质量表示模块学习质量感知调制，增强扩散变压器生成图像的保真度
4. [Editing Everything Everywhere All at Once](/202607/01/2606.31278v1-editing-everything-everywhere-all-at-once)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于多模态扩散Transformer的无训练多实例并发图像编辑
5. [Accelerated Likelihood Maximization for Diffusion-based Versatile Content Generation](/202607/01/2606.31323v1-accelerated-likelihood-maximization-for-diffusion-based-versatile-content-generation)  
   标签：评分：9.0/10、query:real-ir
   evidence：将似然最大化集成到反向过程的扩散模型无需训练采样策略
6. [Language-Assisted Super-Resolution from Real-World Low-Resolution Patches](/202607/01/2606.31363v1-language-assisted-super-resolution-from-real-world-low-resolution-patches)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于语言辅助的真实世界低分辨率块超分辨率重建
7. [Intrinsic decomposition and editing of 3D Gaussian splats](/202607/01/2606.31637v1-intrinsic-decomposition-and-editing-of-3d-gaussian-splats)  
   标签：评分：9.0/10、query:real-ir
   evidence：用三维高斯斑点进行本征分解以支持场景编辑
8. [AnyBokeh: Physics-Guided Any-to-Any Bokeh Editing with Optical Fingerprint Transfer](/202607/01/2606.31959v1-anybokeh-physics-guided-any-to-any-bokeh-editing-with-optical-fingerprint-transfer)  
   标签：评分：9.0/10、query:real-ir
   evidence：物理引导的任意到任意散景编辑，从单张图像出发
9. [GEAR: Guided End-to-End AutoRegression for Image Synthesis](/202607/01/2606.32039v1-gear-guided-end-to-end-autoregression-for-image-synthesis)  
   标签：评分：9.0/10、query:real-ir
   evidence：通过表示对齐联合端到端训练VQ分词器和自回归生成器进行图像合成

### 速读区论文标签
1. [MIMFlow: Integrating Masked Image Modeling with Normalizing Flows for End-to-End Image Generation](/202607/01/2606.26016v2-mimflow-integrating-masked-image-modeling-with-normalizing-flows-for-end-to-end-image-generation)  
   标签：评分：8.0/10、query:real-ir
   evidence：将掩码图像建模与归一化流结合用于图像生成
2. [Simplifying Flow Matching Transformations with Low-Rank Mixture Models](/202607/01/2606.29724v1-simplifying-flow-matching-transformations-with-low-rank-mixture-models)  
   标签：评分：8.0/10、query:real-ir
   evidence：使用MPPCA混合模型作为标准化流的潜在密度以简化流变换并加速收敛
3. [WarpI2I: Image Warping for Image-to-Image Translation](/202607/01/2606.31018v1-warpi2i-image-warping-for-image-to-image-translation)  
   标签：评分：8.0/10、query:real-ir
   evidence：显著性引导的变形-反变形框架提升潜在扩散模型在图像到图像转换中的细节保留
4. [AC3S: Adaptive Conditioning for 3D-Aware Synthetic Data Generation](/202607/01/2606.31204v1-ac3s-adaptive-conditioning-for-3d-aware-synthetic-data-generation)  
   标签：评分：7.0/10、query:real-ir
   evidence：3D感知的合成数据生成与自适应条件扩散模型
5. [Introduction to Stochastic Differential Equations for Generative Machine Learning: A Variational Perspective](/202607/01/2606.31576v1-introduction-to-stochastic-differential-equations-for-generative-machine-learning-a-variational-perspective)  
   标签：评分：7.0/10、query:real-ir
   evidence：从变分角度介绍生成机器学习中SDE的教程，涵盖扩散模型、分数匹配和流匹配
6. [Preserve the Hard, Regenerate the Rest: Uncertainty-Guided Synthetic Training Data Augmentation with Diffusion Models](/202607/01/2606.31603v1-preserve-the-hard-regenerate-the-rest-uncertainty-guided-synthetic-training-data-augmentation-with-diffusion-models)  
   标签：评分：7.0/10、query:real-ir
   evidence：不确定性引导的扩散数据增强用于语义分割
7. [Histogram-constrained Image Generation](/202607/01/2606.31683v1-histogram-constrained-image-generation)  
   标签：评分：7.0/10、query:real-ir
   evidence：通过直方图约束控制扩散模型进行图像生成
8. [PhotoQuilt: Training-Free Arbitrary-Resolution Photomosaics via Bootstrapped Tiled Denoising](/202607/01/2606.30968v1-photoquilt-training-free-arbitrary-resolution-photomosaics-via-bootstrapped-tiled-denoising)  
   标签：评分：6.0/10、query:real-ir
   evidence：使用扩散模型通过自举分块去噪生成照片马赛克


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
