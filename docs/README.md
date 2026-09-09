<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-09-09
- 运行时间：2026-09-09 21:52:38 UTC
- 运行状态：成功
- 本次总论文数：15
- 精读区：7
- 速读区：8

### 今日简报（AI）
今日精读聚焦卫星影像盲去模糊超分与情感图像编辑两大高分突破，另速读覆盖扩散模型对齐等三篇新作。最值得关注的是满分论文AstraMoE-SR，它用轨迹引导扩散同时解决卫星抖动去模糊和超分辨率问题，堪称遥感图像“稳像神器”；AffectDelta则以9分打通了情绪标签到图像内容编辑的鸿沟。若想跟进前沿，建议优先精读这两篇，再泛读SwiftExplorer以了解免训练的扩散模型对齐技巧。
- 详情：[/202609/09/README](/202609/09/README)

### 精读区论文标签
1. [AstraMoE-SR: Trajectory-Guided Diffusion for Blind Satellite Jitter Deblurring and Super-Resolution](/202609/09/2609.07012v1-astramoe-sr-trajectory-guided-diffusion-for-blind-satellite-jitter-deblurring-and-super-resolution)  
   标签：评分：10.0/10、query:real-ir
   evidence：用轨迹引导扩散直接解决卫星抖动盲去模糊和超分辨率，完全属于图像恢复与超分任务
2. [AffectDelta: Beyond Emotion Labels for Image Editing](/202609/09/2609.02616v1-affectdelta-beyond-emotion-labels-for-image-editing)  
   标签：评分：9.0/10、query:real-ir
   evidence：面向情绪驱动的源感知图像编辑模型，与图像编辑模型需求直接匹配
3. [FreeTransformSR: Efficient Lightweight Image Super-Resolution via Free Low-Rank Learnable Transform](/202609/09/2609.05912v1-freetransformsr-efficient-lightweight-image-super-resolution-via-free-low-rank-learnable-transform)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于自由低秩变换的图像超分辨率算法
4. [Object-Aware Background-Controlled Editing via Weighted Velocity Guidance](/202609/09/2609.06288v1-object-aware-background-controlled-editing-via-weighted-velocity-guidance)  
   标签：评分：9.0/10、query:real-ir
   evidence：扩散与流模型速度引导中的训练无关对象级编辑
5. [OracleZoom: On-Policy Self-Distillation Inspired Reference-Constrained Recursive Image Super Resolution](/202609/09/2609.06490v1-oraclezoom-on-policy-self-distillation-inspired-reference-constrained-recursive-image-super-resolution)  
   标签：评分：9.0/10、query:real-ir
   evidence：直接研究图像超分辨率，提出递归参考约束训练框架。
6. [Multi-History-Step SDE Inversion for Image Editing with Superior Regional Awareness](/202609/09/2609.06602v1-multi-history-step-sde-inversion-for-image-editing-with-superior-regional-awareness)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于扩散SDE反演的无训练图像编辑
7. [Revisiting Spectral Representations in Generative Diffusion Models](/202609/09/2609.08253v1-revisiting-spectral-representations-in-generative-diffusion-models)  
   标签：评分：9.0/10、query:real-ir
   evidence：从谱表示角度分析生成扩散模型的理论与机制

### 速读区论文标签
1. [SwiftExplorer: Training-free Diffusion Model Alignment with Swift Diversity Exploration](/202609/09/2609.06651v1-swiftexplorer-training-free-diffusion-model-alignment-with-swift-diversity-exploration)  
   标签：评分：8.0/10、query:real-ir
   evidence：免训练扩散模型对齐与多样性引导采样
2. [Geodesic-informed Generative Diffusion Model For Topology-preserved Image Video Generation](/202609/09/2609.08153v1-geodesic-informed-generative-diffusion-model-for-topology-preserved-image-video-generation)  
   标签：评分：8.0/10、query:real-ir
   evidence：将测地线信息引入扩散生成过程以保持图像和视频几何拓扑，属于扩散生成模型方法改进
3. [Dotting the Eye: An Intent-Driven Image Retouching Agent for Visual Focus Enhancement](/202609/09/2609.01148v1-dotting-the-eye-an-intent-driven-image-retouching-agent-for-visual-focus-enhancement)  
   标签：评分：7.0/10、query:real-ir
   evidence：利用扩散模型作为润饰执行器进行视觉焦点增强，与扩散生成式图像增强/修复高度相关
4. [CAT-Flow: Curvature-Adaptive sTeps for Flow Matching](/202609/09/2609.01746v1-cat-flow-curvature-adaptive-steps-for-flow-matching)  
   标签：评分：7.0/10、query:real-ir
   evidence：为流匹配生成模型提供免训练的曲率自适应步长算法。
5. [RelightFormer: Feed-forward Generative Transformer for Multiview Object Relighting](/202609/09/2609.07414v1-relightformer-feed-forward-generative-transformer-for-multiview-object-relighting)  
   标签：评分：7.0/10、query:real-ir
   evidence：前馈生成式Transformer实现多视图物体重光照，属图像编辑与生成任务
6. [Poisson Image Denoising Using Minimax Concave and Reweighted $\ell_1$ Penalties: Nonblind and Blind Approaches](/202609/09/2609.07916v1-poisson-image-denoising-using-minimax-concave-and-reweighted-ell1-penalties-nonblind-and-blind-approaches)  
   标签：评分：7.0/10、query:real-ir
   evidence：应用极小极大凹与重加权ℓ1惩罚的泊松图像去噪与去模糊方法。
7. [PLSR: Progressive and Localized Super-Resolution of 3D Objects via Localized Latent Voxel Diffusion](/202609/09/2609.06436v1-plsr-progressive-and-localized-super-resolution-of-3d-objects-via-localized-latent-voxel-diffusion)  
   标签：评分：6.0/10、query:real-ir
   evidence：基于局部潜在体素扩散的3D物体渐进式超分辨率方法。
8. [Marigold V2: Revisiting Diffusion Transformers for Monocular Depth Estimation](/202609/09/2609.08084v1-marigold-v2-revisiting-diffusion-transformers-for-monocular-depth-estimation)  
   标签：评分：6.0/10、query:real-ir
   evidence：基于扩散Transformer并迁移生成/编辑模型到单目深度估计


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
