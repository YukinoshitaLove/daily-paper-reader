<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-09-02
- 运行时间：2026-09-02 22:53:24 UTC
- 运行状态：成功
- 本次总论文数：17
- 精读区：6
- 速读区：11

### 今日简报（AI）
今日精读6篇、速读11篇，焦点集中在图像恢复与扩散模型应用。最值得关注：ReBridge-Flow 以流匹配重耦合后验桥实现图像恢复，以及免训练跨域修复方法均获9.0高分。建议普通读者优先复现这两项工作，并尝试将其思路迁移到视频修复任务。
- 详情：[/202609/02/README](/202609/02/README)

### 精读区论文标签
1. [ReBridge-Flow: Re-Coupling Posterior Bridges in Flow Matching for Image Restoration](/202609/02/2609.00811v1-rebridge-flow-re-coupling-posterior-bridges-in-flow-matching-for-image-restoration)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于流匹配生成先验的图像恢复方法，通过后验桥重建耦来保持端点耦合
2. [Training-Free Inpainting Across Domains with a Frozen Text-to-Image Diffusion Model](/202609/02/2609.00862v1-training-free-inpainting-across-domains-with-a-frozen-text-to-image-diffusion-model)  
   标签：评分：9.0/10、query:real-ir
   evidence：利用冻结文生图扩散模型进行跨域免训练图像修复，直接对应图像修复与扩散生成需求
3. [P-PatchDiff: Progressive Patch Diffusion Models for Low-light Image Enhancement](/202609/02/2609.01123v1-p-patchdiff-progressive-patch-diffusion-models-for-low-light-image-enhancement)  
   标签：评分：9.0/10、query:real-ir
   evidence：渐进分块扩散实现任意尺寸低光图像复原
4. [Diffusion Based Unpaired Data Learning for Inverse Problems](/202609/02/2609.01370v1-diffusion-based-unpaired-data-learning-for-inverse-problems)  
   标签：评分：9.0/10、query:real-ir
   evidence：面向逆问题的非配对扩散学习方法，涵盖图像复原、超分辨等任务
5. [DocIntent: Answerability-Guided Agentic Restoration for Real-World Document Visual Question Answering](/202609/02/2608.29037v1-docintent-answerability-guided-agentic-restoration-for-real-world-document-visual-question-answering)  
   标签：评分：8.0/10、query:real-ir
   evidence：面向文档问答的真实退化图像恢复
6. [Training-Free Hidden-State Refinement for Flow-Matching Image Generators](/202609/02/2608.29160v1-training-free-hidden-state-refinement-for-flow-matching-image-generators)  
   标签：评分：8.0/10、query:real-ir
   evidence：针对冻结流匹配/扩散去噪器的免训练推理期细化

### 速读区论文标签
1. [Elastic Token Compression for Pixel-Space Diffusion Transformers](/202609/02/2608.29281v1-elastic-token-compression-for-pixel-space-diffusion-transformers)  
   标签：评分：8.0/10、query:real-ir
   evidence：面向像素空间扩散Transformer的令牌压缩以降低计算冗余
2. [GenFirst: Generation Before Reconstruction for Stable End-to-End Latent Generative Modeling](/202609/02/2608.29335v1-genfirst-generation-before-reconstruction-for-stable-end-to-end-latent-generative-modeling)  
   标签：评分：8.0/10、query:real-ir
   evidence：先生成后重建的稳定端到端潜变量生成建模训练方法
3. [Advanced Pixel Diffusion Model with Guided Sparse Global Refinement](/202609/02/2609.00798v1-advanced-pixel-diffusion-model-with-guided-sparse-global-refinement)  
   标签：评分：8.0/10、query:real-ir
   evidence：改进像素空间扩散模型并提出引导稀疏全局精修，属扩散生成模型算法改进方向
4. [PredErase: Training-Free Object-and-Effect Removal with Predictive Latent Guidance](/202609/02/2609.00956v1-prederase-training-free-object-and-effect-removal-with-predictive-latent-guidance)  
   标签：评分：8.0/10、query:real-ir
   evidence：基于冻结扩散模型的无训练图像编辑，去除对象及其阴影等光影效果
5. [CameraEditor: Camera-Controlled Image Editing via Video-Prior Sequential Modeling](/202609/02/2609.01479v1-cameraeditor-camera-controlled-image-editing-via-video-prior-sequential-modeling)  
   标签：评分：8.0/10、query:real-ir
   evidence：基于视频扩散先验的相机参数控制图像编辑模型
6. [Denoising as Projection: Constrained Optimization with Gradient-Guided Diffusion](/202609/02/2608.29507v1-denoising-as-projection-constrained-optimization-with-gradient-guided-diffusion)  
   标签：评分：7.0/10、query:real-ir
   evidence：以去噪算子为投影的梯度引导扩散，保持数据流形约束
7. [ASSERT: Adaptive Stochastic Sampling for Robust Diffusion Models on Analog Compute-in-Memory Hardware](/202609/02/2609.00955v1-assert-adaptive-stochastic-sampling-for-robust-diffusion-models-on-analog-compute-in-memory-hardware)  
   标签：评分：7.0/10、query:real-ir
   evidence：面向模拟存算硬件的扩散模型噪声鲁棒采样方法，核心是扩散模型推理
8. [Learning the Target Priors Before Image Translation: A Decoupled Training Paradigm for Cross-Modal Image Translation in Remote Sensing](/202609/02/2608.28517v1-learning-the-target-priors-before-image-translation-a-decoupled-training-paradigm-for-cross-modal-image-translation-in-remote-sensing)  
   标签：评分：6.0/10、query:real-ir
   evidence：面向跨模态翻译的目标域生成先验学习，符合生成模型主题
9. [Coarse to Fine: Iterative Adversarial Neural Cellular Automata for Medical Image Synthesis](/202609/02/2608.28909v1-coarse-to-fine-iterative-adversarial-neural-cellular-automata-for-medical-image-synthesis)  
   标签：评分：6.0/10、query:real-ir
   evidence：医学图像合成使用的轻量NCA生成对抗网络，属生成模型范畴但与扩散修复无直接联系
10. [EpaCache: Error-Propagation-Aware Caching for Accelerating Diffusion-Based Visual Generation](/202609/02/2608.29264v1-epacache-error-propagation-aware-caching-for-accelerating-diffusion-based-visual-generation)  
   标签：评分：6.0/10、query:real-ir
   evidence：面向扩散图像/视频生成的无训练缓存加速方法
11. [Reward-guided Fine-Tuning of One-Step Generative Models via Wasserstein Gradient Flow](/202609/02/2608.29647v1-reward-guided-fine-tuning-of-one-step-generative-models-via-wasserstein-gradient-flow)  
   标签：评分：6.0/10、query:real-ir
   evidence：一步生成模型的奖励引导微调


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
